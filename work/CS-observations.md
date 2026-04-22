# CS Observations — Josh's Running Log

*Daily notes from my noon review of the #helpscout CS channel. Most recent entry first. Started April 13, 2026.*

*Source: Raw email logs flowing into #helpscout — inbound customer emails + team responses, unthreaded stream.*

---

## 2026-04-22 — Daily CS Review

*Volume:* Moderate-to-high. 92 messages over ~23 hours (Apr 21 12:04 PM PT through Apr 22 11:02 AM PT). Consistent with yesterday's 100+ and typical Monday→Tuesday pace. No spikes, no dropoff.

*Themes:*
- **Rachyel ran the full Monday afternoon shift; Catherine picked up Tuesday morning.** Clean handoff. Both performing well — Rachyel handled the heavier volume (rush requests, Bay Photo coordination, refunds, editor troubleshooting) and Catherine opened Tuesday with order modifications, editor walk-throughs, and a processing error fix.
- **Bay Photo / Print Pro coordination still the #1 workload driver.** 4-5 coordination threads with Heather Trujillo in one window: missing street number on address hold, order labeled but never shipped (SPS2309088 → UPS 2-day rush reprint), delivered-but-not-received reprint (SPS2309067), two rush flags (SPS2309376, SPS2309768 — both shipping Wed). The pattern from the past 9 days continues unbroken.
- **Rush/expedite requests — unusually heavy.** Matthew Watts (birthday gift by Sat 4/24), Vicki Laframboise (business day 3, deadline-driven), two internal rush flags. Likely early Mother's Day pressure as customers realize lead times. Rachyel managing expectations well without overpromising.
- **Processing error: 4 images dropped from a complete project.** Catherine identified that Tammi Westberg's order processed with 4 missing images despite the project looking full. Called it a "processing error," had an engineer fix it, and placed a new order (#743725). This is a system bug — not customer error. Worth flagging to engineering.
- **Template/editor tech bug.** ysanhinguyen hit "Template Option 'utm_source' not found for template: 19978" when trying to create a photo magazine — UTM parameter leaking into the editor. Catherine redirected to Chrome desktop as a workaround, but the root cause is a URL-handling bug.
- **Magnet editor UX — mobile ordering hides editing controls.** Svetlana GRINMAN ordered magnets on phone, faces cut off, didn't realize drag/edit features existed. Rachyel demonstrated the controls; Catherine provided a $34 replacement code. Mobile UX hiding key controls = preventable quality complaints.
- **Fixed quantity model creating friction.** Hector: can't remove pages from minibooks (50-page minimum). Rosie O'Donnell: 108/120 photos for 4x6 prints, couldn't check out (sets of 24 only). Wrote in twice about the same issue. This is a recurring pattern — the set-quantity model confuses and frustrates customers who want fewer items.
- **Expired promo code tail declining.** One ON-IT inquiry (heatherruthphotography thought it ran through end of April). Volume is way down from the Apr 19 spike — the post-sale tail is nearly done.
- **Big spender: $558 order** (18 line items, Tiny Books + Photo Magazine). Healthy high-value activity continues.
- **Joanne handling Pet Portrait previews.** Separate workflow from main CS — custom product requiring manual approval cycles.
- **Customer sentiment: warm.** Multiple thank-yous and positive replies. Cheryl: "You are awesome! Can't wait to get my tiny books." Matthew Watts: "really appreciate you doing that." No frustrated or escalated threads.

*Flags:*
- ⚠️ **Processing error dropping images from complete projects** — Tammi Westberg's order lost 4 images despite the project being full. Catherine called it a "processing error" and involved an engineer. If this can happen silently, other orders may have shipped with missing images that customers haven't reported yet. Worth flagging to Ben/engineering as a potential systemic issue.
- ⚠️ **UTM parameter leaking into editor** — "Template Option 'utm_source' not found" error blocking a customer from creating a photo magazine. Tech bug, not customer error. Should be a quick fix if someone looks at it.
- **Bay Photo fulfillment pattern — now 9 days of data.** The ratio of CS time spent on Print Pro coordination vs. actual customer questions remains inverted. This is the structural story of the CS queue and it hasn't changed.

*Observations:* Nine days in, and the fundamental shape of the CS queue is clear and stable: the majority of Rachyel's and Catherine's time goes to coordinating remakes, reprints, rush requests, and address issues with Bay Photo/Print Pro — not helping customers buy things or answering product questions. Today's two tech bugs (processing error dropping images, UTM parameter in editor URL) are the kind of silent issues that affect more customers than just the ones who write in. The rush-request volume is picking up, which I'd attribute to early Mother's Day pressure — customers ordering gifts are more deadline-sensitive. Both Rachyel and Catherine are performing well, and customer sentiment remains consistently warm. The team is doing excellent work within the constraints they're operating in.

---

## 2026-04-21 — Daily CS Review

*Volume:* Moderate. 100+ messages over ~21.5 hours (Apr 20 2:03 PM PT through Apr 21 11:42 AM PT). Back up to the 80-100 range after the weekend dip. Monday morning pace is active.

*Themes:*
- **Rachyel running the full queue solo — Sunday through Monday morning.** Every outbound reply is Rachyel. No Catherine, no Julia B visible. She's handling the complete range: Print Pro coordination, order modifications, discount refunds, live chat, editor troubleshooting, address changes, and inbound pitches. Consistently excellent.
- **Print Pro / Bay Photo coordination is the dominant workload.** Six separate coordination threads with Bay Photo (Heather Trujillo, Philip Buckley) in one window: lost-in-transit remake (SPS2307658), books damaged on edges — credit (SPS2307009), returned package reship (SPS2288568 → new SF address), hanger removal request (SPS2310048), cover embossing defect → remake with UPS 2-Day (6566261), hold/release for BR_6565452. Print Pro fulfillment issues continue to be the single biggest driver of CS workload.
- **Fulfillment quality issues persist.** Damaged book edges, cover embossing defect, lost-in-transit orders, labelled-but-not-shipped reship to Germany (SPS2302255). The pattern from the last week has not resolved.
- **Expired discount code requests continuing.** Cheryl's 20% code expired, Rachyel honored via post-purchase refund. Kaya got $28.92 ON-IT retroactive refund. Same pattern as the Apr 19 end-of-sale spike — now it's the post-sale tail.
- **Complex order modification handled well.** Abriel Spence ($335 Layflat Wedding Album, 3 books to 2 addresses including Canada) required cancel + reprocess + separate order link + discount code to cover cost. Multi-step, multi-message, resolved cleanly. Rachyel's ability to handle these complex cases without escalation is notable.
- **Address change portal actively used.** Multiple customers directed to the self-serve portal (Sarah Giesel, Dake Gonzalez). It's working. Missing street number caught by Bay Photo (chelsey hogan) — Rachyel contacted customer and resolved.
- **Discontinued product still buildable.** David couldn't load a saved project for a book SPS no longer offers — Rachyel provided the template link so he could still order. Inconsistent experience: product is not listed but can be built and ordered if you have the link.
- **Editor/product UX friction.** Photo upload errors (2 threads), customer confused about checkout flow (live chat, missed initially), customer wanting single prints (sold in sets only), customer wanting unframed grid poster (not available without frame). Ongoing pattern.
- **Inbound UGC/collab pitches (3).** Rachael Layne "Pregnant Mom" UGC idea → directed to Cara. Pippit AI and AhaCreator partnership pitches → declined.
- **Big spender orders (3).** $569.60 Wood Prints (8 items), $335.25 Layflat Wedding Album, $312 Framed Grid Posters. Strong high-value activity continuing.
- **Customer sentiment: warm.** No frustrated or angry threads. Multiple thank-yous. Even complex modification resolved cheerfully.

*Flags:*
- ⚠️ **Print Pro quality/fulfillment issues — now 8 days of data and no sign of improvement.** Damaged edges, embossing defects, lost/never-shipped orders, missing components. This is systemic, not variance. The volume of Print Pro coordination threads per day (6 today alone) represents a significant chunk of Rachyel's time. This needs a direct conversation with Print Pro about their QC process.
- **Rachyel solo coverage — Sunday through Monday.** She's handling everything alone. If she gets sick or needs time off, there's a visible gap. Catherine and Julia B haven't appeared in this window at all. Shift scheduling seems to put heavy weight on Rachyel.
- **Discontinued products still buildable via template links** — creates an inconsistent experience. If a product is discontinued, the template should either be fully removed or the product should be clearly marked as "legacy/archive" with expectations set.

*Observations:* The Print Pro quality/fulfillment pipeline continues to be the dominant story in CS. After 8 days of data, I can now say with confidence: the majority of Rachyel's workload is coordinating remakes, reprints, reships, and credits with Bay Photo/Print Pro — not answering customer questions about products or helping them order. That ratio is inverted from what you'd want. A well-running production partner should generate very few CS tickets; instead, Print Pro issues are the #1 category every single day. The Abriel Spence thread is a good example of Rachyel's skill — a genuinely complex multi-order, multi-address, international modification handled without any escalation. She's operating at a very high level. The post-sale discount code refund tail continues but should taper off this week.

---

## 2026-04-19 — Daily CS Review

*Volume:* Moderate. 57 messages over ~22.5 hours (Apr 18 1:22 PM PT through Apr 19 11:54 AM PT). Up from yesterday's quiet 34 but still below the 80-89 range from earlier in the week. Feels like a normal Saturday pace — not a spike, not dead.

*Themes:*
- **Rachyel back in the saddle, running the queue.** After yesterday's solo Catherine shift, Rachyel is handling the vast majority of today's replies — fast, clean, professional as always. Catherine and Julia B appear only in customer replies to their prior threads.
- **Retroactive discount code requests (ON-IT) — biggest theme today.** Multiple customers who ordered without applying the 20% Mother's Day code asking for a post-purchase adjustment. Rachyel handling these smoothly: Linda Erb (20% off refunded), Jhoseline Vasquez ($13.64), Megan Norman ($15), Lynn Shield (retroactive on order #742914). Rachyel noted the sale runs Apr 14-19 — today is the last day, so this is a predictable end-of-sale spike. Each one requires a manual refund, which is labor-intensive.
- **App/editor navigation confusion — still the #1 multi-message thread driver.** Debbie Gates Bostrom on Instagram couldn't figure out how to add a project to cart from the app (extended back-and-forth, resolved with "click book 3 then it will let you add to cart" — confusing UI). Sonja Rodriguez confused about green trim lines. num1yanks@yahoo.com needed help with softcover book on the app. Jackie Chong's photo book editor issue is now a multi-day thread waiting on tech team.
- **Order modifications after submission — inconsistent customer experience.** Ellen Kliavkoff and Sharon Dickson both told "already in production, can't change." Brianna Plathe got a successful photo swap + reprocessing. The difference is timing, but from the customer's perspective, one person gets a yes and two get a no — can feel arbitrary.
- **White lines on cards (print quality).** Megan Kirk's thread continuing from yesterday — 8+ cards with white lines on the front edge. Rachyel requested a photo of all 12 laid out to send to production. This is a cutting or alignment issue at the printer.
- **Custom TinyBook covers — not available.** Jeffrey Thelin asked, Rachyel said no. Feature request signal.
- **$918 order (biggest I've seen).** Robin Terres — 34 line items, TinyBooks. Same customer replied warmly thanking for a discount she'd received earlier.
- **B2B/bulk gifting lead.** NatiLee Booth is making bags and Rachyel offered her journals with codes from "our CEO." This is a corporate/event gifting use case worth noting.
- **Auth/login issue.** Customer couldn't log in, directed to auth.socialprintstudio.com. Quick resolution.
- **No invoices in packages — confirmed policy.** Useful for gift orders (Mother's Day especially).
- **Tech team escalation still open.** Jackie Chong's photo book editor issue (special characters, multi-day) — Rachyel offered to rush the order once tech resolves. Good service recovery.

*Flags:*
- **Retroactive discount code refunds are labor-intensive.** Four separate manual refunds today for customers who forgot to apply ON-IT at checkout. If this pattern holds through every sale, an auto-apply mechanism or a more prominent code reminder at checkout would save CS time and prevent customer friction. Worth raising as a product improvement.
- **White lines on cards (Megan Kirk)** — active investigation. If this is a cutting/alignment issue at Print Pro, it could affect more orders. Waiting on customer photos.
- **Jackie Chong tech escalation — multi-day wait.** Customer explicitly said "I'm trying to finish this project today." Rachyel escalated but tech team wasn't available (weekend). The gap between CS availability and engineering availability on weekends is visible here.

*Observations:* The most notable pattern today is the end-of-sale discount code retroactive request spike — four customers in one window asking for the 20% Mother's Day code to be applied after purchase. Each one is a manual refund that Rachyel handles cleanly, but it's preventable work. Auto-applying the active sale discount at checkout, or a more prominent code reminder before order confirmation, would eliminate this entire category. Editor/app navigation confusion continues to be the consistent multi-message thread driver across all seven days of data now. The missing-items and Print Pro quality streak from earlier in the week hasn't resurfaced in the last two days — possible resolution or just weekend timing variance. Customer sentiment remains very warm. Rachyel continues to be excellent.

---

## 2026-04-18 — Daily CS Review

*Volume:* Low-to-moderate. 34 messages over ~23 hours (Apr 17 12:02 PM PT through Apr 18 11:14 AM PT). Noticeably down from the 80-89 range of previous days — roughly 40% of recent volume. Could be natural Friday variation or a genuinely quieter inbox day.

*Themes:*
- **Catherine C running the queue solo.** Every outbound reply in this window is Catherine's. Rachyel and Julia B appear only in customer replies to their prior threads. Catherine is handling the full range capably: editor walk-throughs, order holds, rush requests, shipping problems, returns/refund policy, Spanish-language Instagram DMs, and product inquiries. Solid all-around performance.
- **Editor UX confusion remains the #1 support driver.** Nadia (elderly customer, computer-only user) couldn't figure out how to upload photos to TinyBook editor — drag-and-drop wasn't working. Athina needed to edit a wedding album cover post-order. Julie needed help cloning multi-book orders. Andrea needed to know how to delete/replace images. Four separate editor hand-holding threads in a quieter-than-usual day. Each represents a willing buyer confused by the interface.
- **Shipping/fulfillment — lower incident volume.** Ana Lopez's order lost in USPS transfer (well explained by Catherine). Kristin Woodlock's zipcode error (already shipped, can't redirect). Rush request for SPS2309472. No missing components, no wrong-photo issues. The multi-day streak of missing bookshelves/stands did not recur today.
- **Framed print sizing confusion → returns friction.** Ambika Castle didn't realize frame/mat dimensions add to print size. Surprised by final product size. No-returns policy for custom products applied; 20% off new order offered. Professional handling, but the root cause is a product page clarity issue — final framed dimensions apparently not obvious enough.
- **Expired saved project — 6-month limit.** Jeneen Mustafa couldn't open a saved project. Catherine explained the 6-month expiration policy. Directly relevant to Cloud Saved Projects initiative — if the new system doesn't address expiration, this keeps generating tickets.
- **Spanish-language support.** Catherine handled an Instagram DM from Ana Fons De Rotunno entirely in Spanish — rush delivery request. Clean, professional. Good to see this capability.
- **Product feature request.** Shane McKinley asked about a smaller print size SPS doesn't offer. Catherine passed to the team.
- **Discount/coupon activity.** Robin Terres got a personalized 25% off TinyBooks code. Chip got a $21 refund. Active Mother's Day promotion period.
- **Big spender:** $329.44 order (Canvas + Metal Prints, 9 line items).
- **Customer sentiment: warm across the board.** Multiple thank-you replies. No frustrated or escalated threads today. Nadia was genuinely grateful for the editor walk-through help.

*Flags:*
- **Framed print sizing confusion** — the Ambika Castle thread suggests final framed dimensions aren't clear enough on the product page. If customers are regularly surprised by how much frame/mat adds to total size, this is a preventable returns-attempt trigger. Low-effort fix: add "final framed dimensions: X × Y" to the product listing or cart summary.
- **Missing items streak appears paused** — no component complaints today after four consecutive days. One quiet day doesn't break a trend; will keep watching next week.
- **Saved project expiration** — continues to generate tickets. Relevant to the Cloud Saved Projects initiative Ben and Diego are working on.

*Observations:* Quietest day so far — about 40% of recent daily volume. Catherine ran the entire queue solo and did it cleanly. No Print Pro quality issues surfaced today, which is notable after four days of escalating fulfillment complaints. The missing-items streak may have been a blip, or this could just be Friday variance — next week will tell. The consistent throughline across all five days of data: editor UX friction is the single biggest category of multi-message support threads. Every day, multiple customers who are actively trying to buy something need extensive hand-holding to complete their order. These are the customers who write in — the ones who don't write in just leave.

---

## 2026-04-17 — Daily CS Review

*Volume:* Moderate. ~80 messages over ~22.5 hours (Apr 16 1:30 PM PT through Apr 17 11:55 AM PT). Consistent with the last three days — steady-state pace, no spikes.

*Themes:*
- **Julia B carrying the entire queue solo.** Rachyel is completely absent from today's window — zero replies. Julia handled every single inbound. This is the first day where Rachyel doesn't appear at all. Julia is performing well: friendly, thorough, fast turnaround, solid product knowledge across TinyBooks, editors, guest books, calendars. She's escalating to Print Pro appropriately and managing multi-message threads without dropping any. Impressive shift coverage.
- **Missing items from orders — day 4.** Bookshelf missing from order SPS2308518 (Julia filed for reshipment). Bookshelf missing from order #741618 (Carla Cruz — replacement shipping). Damaged stand refunded $39.60 (Zhongyang Li). Plus order SPS2307485 labelled but never shipped (reprint submitted). Four fulfillment failures in one day's window. This is now a clear trend, not variance.
- **TinyBook magnet polarity defect (new).** Steph Perry reported magnets in TinyBook covers don't align correctly — books only stack properly when upside down. "The magnetic poles aren't correct for stacking them on the bookshelf." Novel defect not seen in previous reviews. Julia forwarded to production. If this is a batch issue, it could affect multiple orders.
- **Editor UX friction — heavy hand-holding threads.** Jennifer Browne (Creative Director, Neal Porter Books) required extensive back-and-forth to get the guest book editor working: couldn't add photo to back cover, couldn't type on spine, no understanding of proofing flow. Tom Fielder (first-time TinyBook buyer) needed help with photo count, cloning books, text limitations, double-page spreads. Janice Carter couldn't figure out photo cropping. All resolved, but each took 5-8 messages. These are engaged, willing-to-buy customers who nearly bounced on editor confusion.
- **Photo Journal discontinued — still discoverable.** Haley Campbell: "That is super disappointing as they were our favorite thing to order after trips." Julia committed to asking the team to make discontinuation more visible on app/website. If discontinued products are still in the app or findable via search, it creates false expectation and frustration.
- **Lost/delayed shipments.** Order #740378 confirmed lost in mail — reprint with UPS 2-day upgrade. Tracking #740062 bouncing around (Richmond, VA — USPS error). Malory Larson's delivery marked but not received — Julia gave it a day before reprinting. USPS reliability continues to be a source of CS tickets.
- **Mother's Day sale activity.** Multiple references to "ON-IT" (20% off sitewide through Apr 19) and "HEIRLOOM" code ($149 → $111 for layflat albums). Customers actively using the sale. Fernanda asked about first-time customer discount — told the MD sale is better. No confusion or complaints about the sale mechanics.
- **Instagram integration still generating tickets.** Anna asked about connecting Instagram — Julia explained Meta disabled it and offered the phone-folder workaround. This keeps coming up and will continue to.
- **Tax exempt inquiry.** Mae from a nonprofit (nm.org email) asked about tax exemption process for a layflat book order. Also confused about production vs. shipping timeline (asked if she should allow 20 business days total). Unclear if SPS has a tax exempt process.
- **Magnet safety question for TinyBooks.** Customer asked if magnets inside covers are child-safe. Julia handled well — magnets are embedded, require significant force to access. Recommended adult supervision.
- **Instagram collab outreach.** Remina Baca reached out via Instagram — Julia directed to Cara. Healthy organic interest.
- **Big spender orders (2).** $322 (Metal Prints), $335.25 (Layflat Photo Album). Continued strong high-value activity.
- **Customer sentiment: very warm.** Multiple positive replies: Jennifer Browne praised the company as recommended by someone who said "you did good work and your team was very supportive." Tom Fielder: "You're the best! Can't wait to get a book!!" Devin Goldstein expressed sincere appreciation for the shipping upgrade courtesy. Amy Dood was understanding about the can't-modify-in-production policy. Julia is building real goodwill.

*Flags:*
- ⚠️ **Missing items/fulfillment failures — 4 days running, escalating.** Bookshelves, stands, labelled-but-not-shipped orders. Four incidents today alone. This has crossed from "trend" to "pattern that needs a conversation with Print Pro." Either their packing process has a systemic gap or something changed recently.
- ⚠️ **TinyBook magnet polarity defect** — new issue. If the magnets in a production batch are installed with reversed polarity, this could affect many orders. Worth asking Print Pro if this is a known issue or isolated.
- ⚠️ **Rachyel absent from the queue today.** Not necessarily a problem — could be a day off, shift rotation, or Julia taking a full shift. But if Rachyel is the CS anchor (she has been every previous day), worth confirming this was planned coverage and not a gap.
- **Discontinued products still discoverable.** Photo Journal being findable but unavailable creates unnecessary frustration. Quick win: remove or clearly mark as discontinued wherever it appears.
- **Editor UX continues to be the #1 source of multi-message support threads.** Every day, the longest CS conversations are about navigating the editor. This is a product problem, not a CS problem.

*Observations:* The big story today is Julia B running the entire queue solo — and doing it extremely well. She's handling the same volume and complexity Rachyel typically carries, with the same professionalism and speed. That's excellent bench depth and a meaningful signal about CS team capability. The fulfillment issue pattern is now impossible to ignore: four consecutive days of missing components, labelled-but-not-shipped orders, and damaged items. This is a Print Pro conversation waiting to happen. The TinyBook magnet polarity issue is novel and potentially batch-wide — worth tracking closely. Editor UX friction remains the most consistent driver of high-touch support conversations, and every one of those threads represents ten customers who hit the same wall and just left without buying.

---

## 2026-04-16 — Daily CS Review

*Volume:* Moderate. 89 messages over ~23 hours (Apr 15 12:30 PM PT through Apr 16 11:50 AM PT). Consistent with yesterday. Steady-state pace — no spikes, no dropoff.

*Themes:*
- **Project resizing frustration (notable).** Stuart M. Bryan (70 years old, self-described as "technically challenged") ordered the wrong size and was told he'd need to start his project over from scratch. Escalating frustration over multiple replies: "you're kidding me," "I spent over 2 hours," "I can't believe your people can't make that simple fix," "I should have asked my kids to do this!" Rachyel handled it well — offered a free code for a replacement order. But the underlying UX issue is real: *customers cannot resize a project after creation*. For a customer who spent hours building something, "start over" is a devastating answer. This is a conversion and retention risk, especially for older or less tech-savvy users.
- **Print darkness/quality complaints (2 threads).** Leslie received a calendar with images "much darker than last year" — same customer, same product type, different year. Print Pro (Heather) confirmed files were dark and it "printed true." Separately, Sharon received faded mini prints. Both offered replacement codes. The year-over-year darkness comparison is notable — could indicate a processing or calibration change.
- **Missing items from orders continue.** TinyBook shelf missing from order SPS2308517 (reshipped UPS 2-day via Print Pro). Brass stand missing from prior order (reorder confirmed). This is the third consecutive day with missing-component complaints.
- **Saved project editing confusion.** Lauren Stark wanted to cancel her order because she "can't figure out how to edit it." Rachyel provided a direct editor link and offered both options (edit or cancel). Consistent with the saved-project access friction flagged yesterday.
- **TinyBooks only sold in sets of 3.** Diane Burke asked to buy 2 books — told that's not possible. Potential conversion barrier worth noting.
- **Special character limitation in photo book editor.** Jackie Chong wants captions with special characters. Cannot do on cover; inside pages escalated to tech team. Minor editor limitation.
- **New CS agent: Julia B.** Two replies near the end of the window — an Instagram story thank-you and an address change via customer portal link. Tone is friendly and professional. First time I've seen this name in the queue.
- **Instagram spam.** Two "Chat AI" bot accounts sending attachments via Instagram DM. Low-value noise.
- **Big spender orders (3).** $374 flat cards, $341 classic prints (17 line items), $315 classic prints (21 line items). Healthy high-value activity.
- **Positive organic social.** Erin Wilson shared SPS in an Instagram Story — Julia B responded with "Hope your mom loves it!" Mother's Day social engagement is happening.
- **Customer sentiment: warm.** Multiple positive customer replies: "Love you guys" (Morgan), "Very generous; thank you" (Stuart), hearts and thanks from several others. Even the frustrated interactions resolved positively.

*Flags:*
- ⚠️ **"Can't resize a project" is a real UX gap.** Stuart Bryan's frustration thread is a concrete example of a customer who invested significant time, made an honest mistake, and was told the only option is starting over. For a 70-year-old customer this is borderline deal-breaking. The current answer is a free replacement code — generous but doesn't fix the underlying problem. Worth asking: how often does this come up, and is project resizing technically feasible?
- ⚠️ **Missing items from orders — 3 days running.** Shelves, brass stands, components not making it into packages. This is consistent enough to suggest a systemic packaging/QA issue at Print Pro rather than random variance.
- ⚠️ **Print darkness year-over-year change.** Leslie's calendar printing darker than the same product last year is a specific, testable claim. If Print Pro changed calibration or processing, that affects every customer silently. Worth flagging to Ben as something to investigate with Print Pro.
- **New CS agent (Julia B)** — only 2 replies today, but she's handling things capably. Worth confirming with Ben who this is.

*Observations:* Day 3 of real data and the pattern is increasingly clear: the CS queue is a quality/fulfillment pipeline with Rachyel as the anchor. Today's most interesting signal is the Stuart Bryan thread — not because one frustrated customer is a crisis, but because "you can't resize your project" is the kind of limitation that quietly kills conversions. People who hit that wall and DON'T write in to CS just leave. The missing-items pattern (3 consecutive days) is crossing from "variance" to "trend" territory. Print darkness complaints are now 2 in this window alone — if this is a calibration issue at Print Pro, it's affecting orders silently beyond just the people who complain. Julia B is a new name in the queue — good to see coverage beyond Rachyel alone.

---

## 2026-04-15 — Daily CS Review

*Volume:* Moderate. 58 messages over ~24 hours (Apr 14 noon PT through Apr 15 noon PT). Slightly down from yesterday's ~85, which likely included some backlog from the integration going live. This feels like a more normalized daily pace.

*Themes:*
- **Reprints/remakes continue to dominate the queue.** Multiple remake confirmations flowing through Print Pro (Heather Trujillo coordinating). Includes the photos-in-wrong-books issue flagged yesterday (SPS2306979-REMAKE confirmed), a rush reprint for a processing error on SPS's end (SPS2308994), and the ongoing binding/quality threads.
- **Dust jacket issues (2 threads).** Katelyn (order #697317, prior dust cover problem) getting a dust jacket reprint. Separate BR_6491991 dust jacket reprint confirmed by Philip at Bay Photo. Two dust jacket complaints in one window — worth watching alongside yesterday's TinyBook binding rips for a pattern.
- **Shipping/delivery problems continuing.** Returned order due to missing apartment number (Jean-Sebastien Thery — Rachyel handled reship cleanly). Melissa Branham's package still going the wrong direction. UPS lost-package claim from Holly. Address change via portal (Diane Matzke — took a couple of back-and-forths but resolved).
- **Coupon/promo confusion.** Customer asked about stacking a 25% "heirloom" code — Rachyel clarified it's Layflat Albums only. Customer was satisfied and praised the service. Minor signal: if "heirloom" code naming is confusing customers, consider whether the naming or placement needs adjustment.
- **Calendar editor UX friction.** Live chat opened: "Trying to change cover photo for calendar." Missed the chat initially (Rachyel followed up by email). Suggests the cover-photo editing flow isn't obvious.
- **Saved project access issue.** Customer couldn't open her saved project — Rachyel resolved with a direct editor link. Relevant to the Cloud Saved Projects work in progress.
- **Big spender orders (2).** $420 postcard order (25 line items from ksachar@ksachar.com) and $312 framed grid poster order. Healthy high-value orders.
- **Mother's Day campaign continuing to generate inbound.** ON-IT shipping refund tied to Early Bird email. Volume expected to ramp through end of April.
- **Return request for Signature Stand.** Customer wants to return a display item — possible product confusion on what they were ordering.
- **External pitches/spam.** CXPlained Team following up on George interview invitation (2nd attempt). Photopress Shopify app pitch via Instagram DM. Imatec Photo Printing Paper spam.
- **Customer sentiment: notably positive.** Multiple customers explicitly praising service quality: "excellent service and swift resolution," "Great customer service. I will definitely order again." Rachyel earning real goodwill.

*Flags:*
- ⚠️ **Dust jacket issues emerging as a theme.** Two dust jacket reprints today, plus yesterday's TinyBook binding rips. Not yet a crisis, but if dust jacket/binding quality issues persist through this week, it's worth flagging to Print Pro as a potential batch quality concern.
- ⚠️ **Calendar cover photo UX confusion** — a customer opened a live chat specifically about this. Worth noting for the product/editor team. If this is a common friction point, it's a conversion issue too (people who can't figure it out might just abandon).
- ⚠️ **Saved project access failure** — resolved manually, but this is exactly the kind of thing Cloud Saved Projects should prevent. Signal that the current state is fragile.
- **CXPlained Team interview request for George** — second follow-up, unanswered. Probably low priority but George should know it's sitting there if he cares about PR/brand visibility.

*Observations:* Day 2 of real data and the pattern from yesterday is holding: the CS queue is primarily a quality/fulfillment pipeline. Rachyel is the workhorse — she's handling 90%+ of the volume with consistent professionalism, clear communication, and fast turnaround. Customer sentiment in replies is genuinely warm, which is a credit to how she manages these interactions. The reprint coordination with Print Pro (Heather, Philip) seems smooth and well-practiced. No dropped balls visible. The dust jacket issue is the new thing to watch — two in one day on top of yesterday's binding rips could indicate a production quality trend rather than normal variance. The calendar cover-photo UX friction and saved-project access failure are both product signals worth tracking even though each only appeared once today.

---

## 2026-04-14 — Daily CS Review

*Volume:* Moderate-to-high. ~85 messages in 24 hours (Apr 13 afternoon through Apr 14 noon). First real data day — the HelpScout integration is now flowing. Rachyel handling the overwhelming majority; Catherine lighter but present in fulfillment coordination threads.

*Themes:*
- **Reprints/remakes dominate the queue.** At least 8-10 distinct reprint threads — binding rips (TinyBooks), calendar glue failure (pages sliding out), images printed in wrong books, missing brass stands, packages lost/never received. Rachyel coordinating rush reprints via Heather Trujillo at Print Pro.
- **Photos in wrong books (2 customers).** Elly Irby received TinyBooks with photos swapped between books. A separate internal reprint (SPS2306979) had the same issue. Could be production mixing or UX confusion — needs watching. If it's production, Print Pro quality control question.
- **Missing brass stands for Daily Calendar (2-3 threads).** Print Pro confirmed one was "placed below the 365-day calendar" — customer just couldn't find it. Another required a standalone reshipping. Packaging visibility issue likely.
- **Mother's Day email campaign generating inbound.** "The Early Bird Gets the Good Mother's Day Gift" email triggering replies. One customer asked to be excluded from MD emails specifically (sensitive — handled well by Rachyel, escalated to Cara for exclusion). One $5.77 ON-IT shipping refund. Campaign just launched Apr 14.
- **Blurry/pixelated prints — possible tech bug.** Claire Berg received prints with blurry faces despite files looking fine on backend. Rachyel escalated to tech team. Customer ordered from phone + computer. Worth tracking — could indicate a rendering issue in the editor.
- **Shipping issues.** Package going wrong direction (Melissa Branham, Richmond VA), orders labelled but never shipped, UPS-lost package investigation.
- **Calendar glue failure.** BR_6561700 — pages sliding out of calendar due to glue issues. Reprint ordered.
- **TinyBook binding rips.** Floral book ripped at binding (#1505918), heart book ripped at binding (#1505863). Two binding failures in one day's window.
- **Big spender alerts (3).** $432 (TinyBooks), $321 (Classic Prints), $780 (Framed Large Format Prints). Healthy order sizes.
- **Live chat working.** Customer asked about landscape photos in TinyBooks and page limits. Quick, friendly resolution.
- **Wedding guest book inquiry.** Pen recommendation for signing — standard, handled well.

*Flags:*
- ⚠️ **Photos-in-wrong-books appearing multiple times** — if this is a Print Pro production error (mixing up which images go in which book within a multi-book order), it's a quality control issue worth raising with them. If it's a UX issue (customers confused about which photos go where in multi-book orders), it's on us.
- ⚠️ **Blurry prints with clean source files** — tech escalation in progress. If this is an editor rendering bug, it could be silently affecting more orders than just this one.
- ⚠️ **Missing brass stands recurring** — packaging issue at Print Pro. If customers regularly can't find the stand, either the packaging should change or the confirmation email should mention where to look.
- **TinyBook binding rips (2 in one day)** — could be normal variance, could indicate a batch issue. Worth watching over the next few days.

*Observations:* First real day of data and the picture is clear: the CS team is dominated by quality/fulfillment issues requiring reprints. Rachyel is carrying the queue with professionalism and speed — she's handling reprint coordination, live chat, campaign-triggered replies, and product questions all in one morning. No dropped conversations. The most operationally concerning pattern is the multi-book photo-swapping issue — if that's a production-side problem, it's expensive (rush reprint 3 books at a time) and damaging to customer trust. The Mother's Day campaign is live and generating the expected email volume — nothing alarming, but the MD-specific exclusion request is a good reminder that this holiday is sensitive for some customers.

---

## 2026-04-13 — Daily CS Review

*Volume:* No data — channel has no customer emails yet.

*Themes:*
- N/A — the #helpscout channel was set up on Apr 12-13 and only contains setup messages between Ben and me. No HelpScout email logs have started flowing in yet.

*Flags:* HelpScout integration to Slack doesn't appear to be pushing messages yet. Ben mentioned he'll get me direct HelpScout access this week — once that's live, this review will have real data to work with.

*Observations:* First run of the daily recipe. The channel is freshly created and the integration hasn't started populating it with CS email logs. This is expected — Ben flagged the channel was "only added now to start saving incoming messages." I'll keep running the daily review so we catch the data as soon as it starts flowing. The real unlock will be direct HelpScout access, which Ben committed to providing this week alongside Metabase and Shopify data.

---

<!-- Entries appended here by the daily recipe -->
