# Master Project Overview

*Marcus's central reference for all projects and work happening at SPS. Organized by focus area. Contains Tier 1 (Active) and Tier 2 (Committed) items. For Tier 3 (On Deck), see `backlog.md`. For team member profiles and roles, see `team.md`.*

**Last updated:** 2026-04-10 (evening)

---

## 1. Tinybooks

**Priority:** #1 overall

### Tier 1 — Active
- **Fulfillment Hire** — Strong progress. 40+ applicants. Ben has scheduled interviews and follow-ups with a handful of candidates. Flyer posting no longer needed (sufficient applicants already). Target: wrap up hiring by end of next week (Apr 18). **Who:** Ben
- **Cover Sourcing** — Print Pro raising prices on standardized magnetic covers. Seeking alternative overseas suppliers. ~50k covers/year across ~10 SKU designs, target ~$1/unit. 5-phase sourcing plan, ~8 week timeline. Full plan: `projects/tinybook-cover-sourcing.md`. **Who:** Ben
- **Get Print Pro Cover Style Counts for 20k Order** — Pricing negotiations complete. Now need to send Print Pro the cover style counts for the 20k cover order. **Who:** Ben
- **Cover Designs** — All stakeholder feedback gathered (Cara). Decision made: Laurel doing another round of design — tweaking existing designs + one new design. Laurel's next round expected week of 4/14 or 4/21. *Tentative launch: May 18.* Designs to Print Pro by ~Apr 28 (3-week turnaround from submission to samples at Bay Photo). Ben's preference is ASAP; Cara's priority is quality over speed — date can slip if designs need more time. ⚠️ Apr 28 deadline is tight given Mother's Day bandwidth — flag to Ben + Laurel. **Who:** Cara, Laurel
- **Find USA-Based Tinybook Supplier** — Research and identify potential tinybook suppliers in the USA. Separate from the overseas cover sourcing effort. This is about finding a domestic supplier for tinybooks themselves. Kicked off 2026-04-01. Update 2026-04-08: Call with Alexanders complete — they're interested in Tinybook + Daily Calendar business (500k envelopes/day peak capacity). Next: send Chase (Alexanders) sales volume data, target pricing, and sample Tinybook orders so they can price it out. Open invitation to visit their Utah facility — potential George/Ben offsite. Full notes: `projects/tinybooks/usa-supplier-search.md`. **Who:** George

### Tier 2 — Committed
- **Tinybook Christmas Ornaments & Backpack Hangers** — New tinybook product line. Reference images at `projects/tinybooks/backpack-hanger/`. **Who:** Ben
- **Tinybook Mobile Web Experience** — New mobile-optimized web experience for tinybooks. Part of the broader Editor Rewrites initiative (see Editors). **Who:** Ben

---

## 2. iOS App

### Tier 1 — Active
- **App Store Screenshots** — Laurel making fresh screenshots. **Who:** Laurel
- **iOS App Redesign Directions** — Laurel working on redesign explorations: product page template layout and flat card template chooser. **Who:** Laurel
- **Cloud Saved Projects** — Adding more products to use cloud save instead of local. Currently only Daily Calendar uses it. Touches three systems: app, web editor, Shopify (account page). Ben has backend API endpoints built but not shipped — loose end. Diego: Remote Saving for Classic Prints in active QA as of 2026-04-10 (v18.3.5 on TestFlight). Joanne testing — cloud sync to second device not immediately visible; Diego clarified UX flow (manual "Save to Cloud" step required from device tab). Brass Stands + Mini Prints not yet supported for cloud save. Web rendering coming soon. **Who:** Diego (primary), Ben (backend)
- **"Your Text Here" Bug Fix — Hardcover + Softcover Books** — ✅ COMPLETE. iOS 18.3.4 released to App Store 2026-04-08. Placeholder text bug fixed for both hardcover and softcover photo books. **Who:** Diego. See `projects/ios/app-log.md` for full build history.
- **iPad Display Fixes** — iPad-specific UI issues found late week of 3/24. Diego fixing. **Who:** Diego
- **General iOS Development** — Diego actively working. **Who:** Diego
- **Ben + Diego Xcode Screenshare** — Schedule a meeting for Diego to screenshare Xcode with Ben so Ben gets set up better on the iOS codebase. **Who:** Ben + Diego

**QA:** Joanne, Rachel, Catherine

**Build log:** `projects/ios/app-log.md` — update this file whenever a new build ships.

---

## 3. Editors

### Tier 1 — Active
- **Editor Rewrites — Research/Planning** — Ben wants to rewrite all editors. Currently in research/planning phase. Scope TBD for what actually ships this year. Active as research, but the actual build scope may end up as Tier 2 or 3 depending on what's decided. **Who:** Ben

### Tier 2 — Committed
- **Editor QA / Bug Fixes** — Known bugs (e.g., pixelated posters on new editor). Needs dedicated time. **Who:** Ben, Alex
- **Tinybook Mobile Web Experience** — (Cross-listed with Tinybooks. Primary home is Tinybooks.)
- **Wedding Mobile Experience** — Pixfizz editor doesn't work on mobile; 80–92% of wedding PDP traffic is mobile. Three options: block mobile traffic, educate/push to desktop, or build mobile experience. *Decision needed first* (Ben + George) before any build work starts. Cross-listed with Marketing (Wedding Conversion Problem). **Who:** Ben (lead)

**Note:** One codebase, 3 product deployments. Integrates with Pixfizz (Laurel manages). Sometimes called "the new editor."

---

## 4. SPS Backend

### Tier 2 — Committed
- **Gelato Integration** — Print API integration. **Who:** Alex
- **Waiting Order / Print Sender** — New system for managing when processed orders get sent to the printer. Alex targeting production deployment 2026-04-09. Will send team writeup on how it works once live. **Who:** Alex
- **Cancelled Orders** — Improving the cancel/hold workflow. API cancel button used multiple times daily for temp holds and full cancellations. See `projects/sps-backend/cancelled-orders.md`. **Who:** Alex

**Note:** Low value for end customer but necessary. Needs to "just go away" — keep chipping at it without letting it consume bandwidth from higher-priority work.

---

## 5. Customer Portal

### Tier 2 — Committed
- **Cancel Order Flow (Self-Serve)** — Let customers cancel their own orders via portal.socialprintstudio.com. **Who:** Ben
- **Customer Image Swap (Self-Serve)** — Let customers swap images themselves. **Who:** Ben
- **Address Change Improvements** — Current functionality exists but needs improvement. **Who:** Ben

**Domain:** portal.socialprintstudio.com
**Note:** Own codebase. Currently only handles address change requests.

---

## 6. Marketing

### Tier 1 — Active
- **Mother's Day 2026** — Hard deadline May 10. Sale launches Apr 14 (Early MD Sale). One ad round complete. Multiple new ads in production (Cara + George: creator video edits, scripts, hooks, captions). Email plan: 3 emails for Early MD Sale (next week), 5 emails for main MD Sale (week after) + new sale ads. MD order-by dates now live on shipping pages. Peak CS dates expected Apr 28–29. *Laurel OOO note: half days Apr 14–15, off Apr 16 — plan sale deployment accordingly.* War room: https://design.saved.work/projects/mothers-day/war-room/index.html **Who:** George (lead), Cara (ads, emails), Laurel
- **Wedding Conversion Problem** — Three converging forces hurting Wedding Album + Wedding Guest Book conversion: (1) audience quality spiral (Meta widening audience, lower intent), (2) mobile wall (80-92% mobile traffic, Pixfizz doesn't work on mobile), (3) price increase ($129→$149 Mar 2025, effective price ~$125 is in the danger zone). Three workstreams: (a) improve funnel flow (Cara), (b) revisit pricing by May 1 (George/Cara/Ben), (c) decide mobile approach — block, educate, or build (Ben lead). Bright spot: 35.8% of wedding popup signups eventually buy with 4-day median delay — lean into multi-session/email-capture strategy. Full notes: `projects/wedding-conversion.md` **Who:** Cara (funnel), George + Ben (pricing + mobile strategy)
- **Klaviyo Flows** — New and expanded email flows. Estimated $100k+/yr incremental revenue once live. Priority flows: (1) Guest Book → Wedding Album upsell, (2) Saved Project Reminder for photo books + wedding albums (Tinybooks + Calendars already exist), (3) WinBack flow for lapsed customers. **Who:** George (lead)

### Tier 2 — Committed
- **Agent SEO Improvements** — Improving SEO and AI agent browsability. **Who:** TBD
- **Find Video Editing Help for George** — George needs video editing support for ad creative. **Who:** Ben, George
- **Landing Page API Endpoint — Shopify Proxy App** — Build a landing page API endpoint in the SPS Shopify proxy app. **Who:** Ben

**Who:** George (lead), Cara, Laurel. Ben supports/oversees.
**Sub-initiatives:** Briefs App and Script Editor (Script Studio) — both now part of the Marketing focus area. Previously tracked as standalone projects.

---

## 7. Customer Service

### Tier 2 — Committed
- **AI Knowledgebase (KB)** — Core piece of CS 2026. KB is a new codebase for AI agent context, being tested against real HelpScout emails. **Who:** Ben
- **Live Chat** — Turn on live chat for customers via AI. **Who:** Ben
- **Auto-Draft Replies** — Auto-draft replies for high-conviction emails. **Who:** Ben
- **Cancellation Request Monitoring** — Monitor all incoming emails for cancellation requests. **Who:** Ben
- **CS Email Quantification Tracker** — Real-time review and quantification of CS emails. Track issues coming up, especially technical/product issues. **Who:** Ben

**Day-to-day CS:** Rachel, Catherine (on HelpScout)
**Note:** Ben deliberately deprioritized CS work — watching his own tendency to get pulled into it at the expense of higher-priority work. KB is the foundation; other items depend on it.

---

## 8. PrintKit

### Tier 2 — Committed
- **Example Editors** — Joanne completed QA for PrintKit selectors. Sequence: finish examples → publish on site → Earn page. On hold as of 2026-04-02 — will revisit in 1-2 weeks. **Who:** Ben, Joanne (testing)
- **Earn Page** — Sequenced after examples are published. On hold. **Who:** Ben

**Domain:** printkit.dev

---

## 9. Shopify Website

### Tier 1 — Active
- **Creative Layouts Listing Page** — Laurel designing a creative layouts listing page as part of "killing the old website." **Who:** Laurel
- **Auth Email List Re-engagement** — ~70k users from auth flow never integrated into the main list. First email sent to a 5K test segment. Analyzing results — plan to send to the larger group + two more emails total. Then add all to main list. **Who:** Cara, Laurel

### Tier 2 — Committed
- **Agent SEO Improvements** — Improving site for AI agent browsability. (Cross-listed with Marketing.) **Who:** TBD
- **Shopify Proxy App — Custom Sitemap** — Add a `/a/pages/sitemap.xml` route to the proxy app listing all pages. **Who:** Ben
- **Shopify Proxy App — Confirm Meta Pixel** — Verify Meta pixel is loading correctly on proxy app pages. **Who:** Ben

### Completed
- **Flat Card Template Chooser** — Deployed 2026-04-02.

**Who:** Laurel (primary), George (marketing content)
**Note:** Also used as a CMS. General Shopify tasks and data management happen here.

---

## 10. New Photo Books

### Tier 1 — Active
- **Marathon Integration + Launch** — New book producer/supplier. 2 orders submitted for printing next week (in Marathon's court). Follow-up meeting set for next Wednesday. Moving forward *without foil for now* — scope is hardcover and layflat only. Laurel actively preparing 10x10 hardcover book for launch. **Who:** Ben, Laurel

**Note:** Temporary focus area. Re-evaluate ~6 months after launch whether it should merge into another category.

---

## 11. New Initiatives

*New offshoots being explored. Projects graduate out when they become real standalone projects (e.g., PrintKit started here).*

### Tier 1 — Active
- **Decades Magnet App** — Alex deployed new version 2026-04-09 (multiple photos per option). Joanne testing complete. Key finding: photo output quality not good enough (AI not generating likeness). Now in Ben's court — review needed to determine if/how output can be improved. Ben also doing a design pass. Staging: https://decades-staging-4ffaa6fbe6f0.herokuapp.com/. **Who:** Ben (design pass + model decision), Alex (dev)

*See `backlog.md` for Tier 3 ideas in this space.*

---

## 12. Operations / Internal

### Tier 1 — Active
- **Agent Team Build-Out** — Establishing patterns, building agents. Marcus is being onboarded as a team-facing colleague. **Who:** Ben
- **Design Guideline Page** — Laurel building a design guideline page for use across projects. **Who:** Laurel
- **Order Brass Stands — Joseph Harpole** — ✅ COMPLETE (2026-04-08). Joanne completed the analysis. Small: order 139, Large: order 1,673 (15% buffer over 2025 actuals). Ben to place order.

### Tier 2 — Committed
- **Process Improvements** — Establishing check-in processes with team, improving coordination and visibility. **Who:** Ben, Marcus

---

## Cross-Project Notes

- **Tinybooks spans multiple focus areas:** Supplier (Print Pro), fulfillment ops, marketing (growth), editors (web experience), design (covers). Primary home is the Tinybooks focus area.
- **Cloud Saved Projects crosses three systems:** iOS app, web editor, Shopify. Backend API endpoints exist but aren't shipped.
- **Editor Rewrites is an umbrella:** Touches Editors focus area primarily, but Tinybook mobile web experience is part of it. Research phase — scope TBD.
- **Briefs App + Script Editor** are marketing tools now. Live apps, maintained under Marketing. No longer standalone projects.
- **Agent SEO** cross-listed between Marketing and Shopify Website. Implementation happens on Shopify; initiative is marketing-driven.
