# Metabase Overview

Social Print Studio's analytics lives in a Metabase instance at `https://metabase.saved.work`. You access it via the `metabase*` tools — never via URLs or the UI.

## The Database

**Name:** Shopify Postgres on Minix
**Database ID:** `2` (this is the default for `metabaseRunSql` and `metabaseCreateCard`)

Despite the name, the database contains data from multiple sources:
- **Shopify orders** — `orders` table (full history, synced via Airbyte)
- **Google Sheets** — inventory snapshots for products
- **Facebook Ads** — campaign and ad performance

All data is kept fresh by Airbyte (at least daily, often more frequent).

## Tables

**Sales**
- `orders` — Main Shopify transaction table. 265k+ rows. Line items, customer, addresses, fulfillments stored as JSONB. See `shopify-data.md` for the full schema and query patterns.
- `products` — Shopify product catalog with options and variant definitions (also in `shopify-data.md`).

**Inventory** (synced from Google Sheets)
- `Brass_Stands` — brass stand inventory snapshots
- `Sheet1` — tinybook covers inventory (Print Pro supplier)
- `Tiny_Bookshelf` — bookshelf inventory
- `signature_stands` — calendar stand inventory (aggregated)
- `signature_stands_locations` — calendar stand inventory by fulfillment location

**Marketing** (synced from Facebook Ads)
- `campaigns`, `ad_sets`, `ads`, `ad_creatives` — campaign structure
- `ads_insights` — main performance metrics
- `ads_insights_action_type`, `ads_insights_age_and_gender`, `ads_insights_country`, `ads_insights_dma`, `ads_insights_platform_and_device`, `ads_insights_region` — breakdowns
- `custom_conversions`, `images`, `activities` — supporting data

## Saved Cards (Questions) — Prefer these over custom SQL

Use `metabaseSearchCards` to find more, `metabaseGetCard` to inspect, `metabaseRunCard` to execute. Card IDs and purposes below are current as of the last update to this doc.

### Inventory

| ID | Name | Returns | Params |
|---|---|---|---|
| 49 | Signature Stands Current Inventory — BY LOCATION | Calendar stands by color and location (BayPhoto vs Black River), with TOTAL row | none |
| 46 | Brass Stands — Current Inventory | Brass stand inventory by size (`stand_label`, `inventory_on_hand`) | none |
| 45 | Tiny Bookshelf — Current Inventory | Bookshelf inventory on hand | none |
| 41 | Tinybook Covers Current Inventory | Per-cover inventory with sales-since-snapshot and current running total | none |

### Sales

| ID | Name | Returns | Params |
|---|---|---|---|
| 51 | Yesterday's Total Revenue | Revenue + order count for yesterday (auto-updates) | none |
| 47 | Brass Stands Sales | Brass stand sales by size (Small vs Large) | `created_at` (date range) |
| 43 | Daily Calendar Stand Sales By Color | Calendar stand sales by color | `created_at` (date range) |
| 48 | Tiny Bookshelf Sales | Bookshelf sales: standalone vs. as part of sets, with percentages | `created_at` (date range) |
| 38 | How Many Tinybook Sets Have We Sold? | Total tinybook sets sold | `productId` (number), `created_at` (date) |
| 39 | Tinybook Cover Breakdown | Which cover designs sold and how many | `created_at` (date range) |
| 40 | Tinybook Cover Sales By Date Range | Like #39 but with a TOTAL row | `created_at` (date range) |

## When to use custom SQL

Use `metabaseRunSql` only when no saved card fits. Guidelines:
- Write aggregates, not raw row dumps — `COUNT`, `SUM`, `GROUP BY`, top-N.
- Default row limit is 25, hard cap 100. If you need more, you're probably writing the wrong query.
- For JSONB fields in `orders` (`line_items`, `customer`, `shipping_address`), see `shopify-data.md` for extraction patterns.
- Always filter by `created_at` when touching `orders` — it's a 265k-row table.

## Creating new cards

`metabaseCreateCard` saves a native-SQL question in the default database. Only use when the caller explicitly asks to save, create, or add a question. Confirm the name and description are reasonable before saving. The tool validates SELECT-only and returns the new card's ID + URL.

## Dashboards

One main dashboard exists: **"Social Print Studio"** (ID 2), with tabs for tinybook metrics and calendar-stand / brass-stand metrics. You don't interact with dashboards directly — just the underlying cards.
