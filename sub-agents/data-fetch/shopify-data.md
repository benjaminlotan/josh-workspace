# Shopify Data — Schema & Query Patterns

This is the deep reference for querying our Shopify `orders` and `products` tables in Metabase. For tool mechanics and the saved-card catalog, see `metabase-overview.md`.

## Linking to an order in Shopify Admin

```
https://admin.shopify.com/store/social-print-studio/orders/{ORDER_ID}
```

Example: order id `6604991398051` → `https://admin.shopify.com/store/social-print-studio/orders/6604991398051`

---

## The Orders Table

**Table:** `public.orders` (Table ID 9, Database ID 2). 265k+ rows, full order history, synced via Airbyte at least daily.

### Core columns

**Identifiers**
- `id` (bigint) — primary key, Shopify order ID. Use for admin links.
- `name` (varchar) — order number (e.g. `#1001`)
- `token` (varchar) — unique order token

**Timestamps**
- `created_at` (timestamptz) — always filter by this on large date ranges
- `updated_at` (timestamptz)
- `processed_at` (varchar)
- `closed_at`, `cancelled_at` (timestamptz)

**Financial**
- `total_price`, `subtotal_price`, `total_tax`, `total_discounts`, `total_price_usd`, `total_line_items_price`
- `current_total_price`, `current_subtotal_price`, `current_total_tax`, `current_total_discounts` — reflect refunds

**Status & metadata**
- `fulfillment_status` — fulfilled / partial / unfulfilled / null
- `tags` — comma-separated; `blackRiver` means fulfillment via Black River, absent = BayPhoto
- `note`, `email`, `contact_email`, `app_id`

### JSONB columns

**`line_items`** — array of products in the order:
- `product_id` — access as `(line_item->>'product_id')::bigint`
- `variant_id`, `variant_title` (e.g. `"Small - Blue"`, `"3.3x2.2"`)
- `sku`
- `quantity` — cast via `(line_item->>'quantity')::int`
- `price` — cast via `(line_item->>'price')::numeric`
- `properties` — custom properties array (tinybook cover picks, personalization)
- `fulfillment_status` — per-item

**`customer`** — nested: `id`, `email`, `first_name`, `last_name`, `phone`, `created_at`, `state`, `tags`, `currency`, `default_address`, `email_marketing_consent`, `sms_marketing_consent`

**`shipping_address`** — `first_name`, `last_name`, `name`, `address1`, `address2`, `city`, `province`, `province_code`, `country`, `country_code`, `zip`, `phone`, `company`, `latitude`, `longitude`

**Other JSONB fields:** `fulfillments`, `refunds`, `discount_codes`, `shipping_lines`, `total_shipping_price_set`

### Querying rules (important)

- **Never `SELECT *`** — the JSON fields are huge and will blow the tool's row/size caps. Select only the columns you need.
- **Always filter by `created_at`** on large ranges.
- **Extract JSONB explicitly** using `->>` for text and `->` for nested JSON. Cast types (`::bigint`, `::int`, `::numeric`).

### Common SQL patterns

**Extract product info from line items:**
```sql
SELECT
  (line_item->>'product_id')::bigint AS product_id,
  line_item->>'variant_title' AS variant_title,
  line_item->>'sku' AS sku,
  (line_item->>'quantity')::int AS quantity,
  (line_item->>'price')::numeric AS price
FROM public.orders
CROSS JOIN LATERAL jsonb_array_elements(line_items) AS line_item
WHERE created_at >= '2026-01-01'
```

**Extract custom properties (e.g. tinybook covers):**
```sql
SELECT
  prop->>'name'  AS property_name,
  prop->>'value' AS property_value
FROM public.orders
CROSS JOIN LATERAL jsonb_array_elements(line_items) AS line_item
CROSS JOIN LATERAL jsonb_array_elements(line_item->'properties') AS prop
WHERE (line_item->>'product_id')::bigint = 8681324314787
  AND prop->>'name' IN ('First Cover','Second Cover','Third Cover')
```

**Extract specific customer fields (avoid full `customer` column):**
```sql
SELECT
  id, name, created_at,
  (customer->>'email')      AS customer_email,
  (customer->>'first_name') AS customer_first_name
FROM public.orders
WHERE created_at >= '2026-01-01'
```

**Fulfillment location from tags:**
```sql
CASE
  WHEN tags ILIKE '%blackRiver%' THEN 'Black River'
  ELSE 'BayPhoto'
END AS fulfillment_location
```

**Filter by specific products:**
```sql
WHERE (line_item->>'product_id')::bigint IN (7854608941219, 7854609105059)
```

---

## The Products Table

**Table:** `public.products`. Contains active, draft, and archived products from the Shopify catalog.

### Core columns

- `id` (bigint), `handle` (URL slug), `title`, `admin_graphql_api_id`
- `product_type` (e.g. "Daily Calendar", "Photo Books", "Display")
- `status` — `ACTIVE` / `DRAFT` / `ARCHIVED`
- `tags`, `vendor`, `description`, `body_html`, `description_html`
- `created_at`, `updated_at`, `published_at`, `deleted_at`
- `total_variants`, `total_inventory`, `has_only_default_variant`, `has_out_of_stock_variants`, `tracks_inventory`

### JSONB columns
- `options` — array of option definitions (see below)
- `variants` — array of `{ id }` objects only, **not** full variant details
- `images`, `image`, `featured_image`, `featured_media`, `price_range_v2`, `seo`

### Options structure

```json
[
  { "id": 10054191513763, "name": "Stand", "values": ["No stand", "Bamboo Stand", "Signature Stand - Graphite Gray"], "position": 1, "product_id": 7799899685027 }
]
```

### ⚠️ Variants caveat

The `products.variants` column contains variant IDs only. For `variant_title`, `sku`, price, quantity — pull from `orders.line_items`. See the line-item extraction pattern above.

### Common SQL patterns

**List active products:**
```sql
SELECT id, title, handle, product_type, total_variants, total_inventory, status
FROM public.products
WHERE status = 'ACTIVE'
ORDER BY title
```

**Explode options for a product:**
```sql
SELECT
  id, title,
  option->>'name'   AS option_name,
  option->'values'  AS option_values
FROM public.products
CROSS JOIN LATERAL jsonb_array_elements(options) AS option
WHERE id = 7799899685027
```

**Find products by option name:**
```sql
SELECT
  p.id, p.title, p.total_variants,
  option->>'name'  AS option_name,
  option->'values' AS option_values
FROM public.products p
CROSS JOIN LATERAL jsonb_array_elements(p.options) AS option
WHERE option->>'name' = 'Size'
  AND p.status = 'ACTIVE'
```

---

## Known product IDs

**Brass Stands:**
- `7854608941219` — variants: `3.3x2.2` = Small, others = Large
- `7854609105059` — variants: `3x2` = Small, `4x4` = Large
- `7883723571363` — all variants = Large

**Signature / Calendar Stands (Daily Calendar):**
- `7799899685027`, `7357260431523`, `7357285597347` — all have color variants
- Colors from `variant_title`: Blue, Peach, Green, White, Yellow, Gray/Graphite
- "Signature Stand" with no variant specified → Gray

**Tinybooks:**
- `8681324314787` — Tinybook sets (3 books). `properties` array holds `First Cover`, `Second Cover`, `Third Cover`. Set-with-bookshelf identified by `sku = 'tinybook-new-shelf'` or `variant_title` containing "bookshelf".

**Tiny Bookshelf (standalone):**
- `8585471721635`

**Cover designs found in properties:** hearts, floral, checkered, gradient, color-wave, blue, peach, black, white, abstract-botanical, map (more may exist).

---

## Quick checklist before running SQL

1. Can a saved card answer this? Check `metabase-overview.md` first.
2. Am I selecting specific columns (no `SELECT *`)?
3. Am I filtering by `created_at` if touching `orders`?
4. Am I casting JSONB extractions to the right type?
5. Is my row limit set to an aggregate-appropriate number, not a bulk export?
