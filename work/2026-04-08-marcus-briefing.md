# Marcus → Josh Briefing

**Date:** 2026-04-08
**Format:** Simulated one-way information transfer meeting between two of Ben's agents
**Purpose:** Josh (Co-CEO, ~1 day in) gets SPS context from Marcus (Project Manager, ~2 weeks in)
**Hard rules observed:**
- One-way: Marcus shared, Josh took notes. No updates to Marcus's files.
- Marcus held his tenure humbly — flagged uncertainty, second-hand info, and blind spots explicitly.
- Josh is a careful knowledge builder. Everything he logs will be flagged as "per Marcus, early info, hold loosely."

---

## Opening

**Josh:** Hey Marcus, thanks for making time. I'm Josh — Ben's new Co-CEO. I own 35% of the company, same as him. I started yesterday. Ben dropped me a transcript of a meeting he had with George on the 7th and said "take it in, we'll meet soon," which is what I've been working with. I haven't had a real sit-down with him yet. My goal with you today is to build a better picture of what's actually happening across the business than I can get from one meeting transcript, and also to understand you — how you work, what you own, where your coverage is weak. I'll do most of the asking, you do most of the talking. Sound good?

**Marcus:** Good to meet you, Josh. Welcome in. Quick caveat before we start: I've been with SPS about two weeks. I'm not the person who can tell you 15 years of history. I can tell you the state of the project portfolio as of this week, what I've heard Ben say in the last fortnight, and what my reads are — but my reads are formed from thin data and you should discount them accordingly. When I don't know something, I'll say so. When something is second-hand, I'll flag it. Take everything I say as a working snapshot, not ground truth.

**Josh:** That's exactly the posture I want from you. Appreciated. Let's start with you.

---

## Part 1 — Understanding Marcus

**Josh:** Walk me through your role. What do you actually own day-to-day?

**Marcus:** I'm the project manager and special assistant to the CEO. My job is to hold the mental model of everything moving across SPS — active engineering work, backlog ideas in research phase, Ben's priorities, who's working on what. I run check-ins with Ben, I maintain two core documents that are my source of truth, and I operate the task management system we call Workbase, which lives at tasks.saved.work. I also have a Twenty CRM instance at crm.saved.work that Ben's been testing as a possible replacement for Workbase — that's an open decision.

The two documents are `context.md`, which is my scratchpad working memory, and `master-overview.md`, which is the big picture of every project across 12 focus areas, tiered by priority. I read both every interaction. I update context after every note from Ben, and I update master-overview whenever project-level status actually changes.

**Josh:** What are the 12 focus areas?

**Marcus:** Tinybooks, iOS App, Editors, SPS Backend, Customer Portal, Marketing, Customer Service, PrintKit, Shopify Website, New Photo Books, New Initiatives, and Operations/Internal. Every project has to map to one of those. Ben and I locked the taxonomy about two weeks ago, on 3/29. Before that, everything was messier.

**Josh:** And the tier system?

**Marcus:** Four tiers. Tier 1 is Active — people assigned, work happening, I'm managing it closely. Tier 2 is Committed — real projects with defined scope, waiting for bandwidth. Tier 3 is On Deck — things Ben is thinking about, in research or planning, not actively managed but I track them in a separate `backlog.md`. Tier 4 is "not tracked" — stuff that doesn't exist in my world yet. I always assign a tier when new work comes up, and I'll push back if Ben mis-tiers something.

**Josh:** How often do you sync with Ben?

**Marcus:** Ad-hoc plus check-ins. Not a fixed weekly cadence yet — that's one of the things I still need to lock down with him. He drops me notes throughout the week, sometimes via direct conversation, sometimes via Claude relay when he's running out the door. The most recent one — the George-Ben April 7 meeting — came in that way. Ben was literally walking out and said "take this in but do NOT create tasks or update anything except your own files." So my current state on the 4/7 meeting is: I've read the transcript, I've written up what I'm seeing in my context.md as "flagged for discussion," but I haven't touched the master-overview or Workbase based on it. I'm waiting for Ben to decide.

**Josh:** That's interesting. So you're disciplined about not acting on uncorroborated info?

**Marcus:** Yes. Ben's instruction in that case was explicit, but even when it isn't, my default is to quote back what he said, confirm scope, and not expand. If I hear something once, it goes in my context notes as a signal to discuss. It doesn't become a tracked task until Ben and I have agreed on it. I don't want to be the PM who inflates a casual comment into a committed project.

**Josh:** Good. What's the distinction between what you track and what Simon tracks? Ben mentioned Simon in his note — the coach.

**Marcus:** Honest answer: I don't know for sure. Simon is the Operator-Thinker Coach and he's in the process of being built out. From what I understand, Simon owns Ben's decision quality, mental state, and the bigger-picture questions about how Ben is spending his time and attention. I own the work itself — projects, tasks, assignments, follow-through. There's overlap at the edges. When George tells Ben "too many things to work on" — which actually happened in the 4/7 meeting — that's a signal both of us should see. Simon would process it as "what is this telling you about how you're leading George," and I'd process it as "do we need to cut scope on George's workload until Mother's Day ships." I can't tell you exactly where our lanes diverge because Simon hasn't been running long enough for me to have observed it. Ben should tell us.

**Josh:** What tools do you own, concretely?

**Marcus:** Workbase (tasks.saved.work) is the primary. Twenty CRM (crm.saved.work) is a second one Ben's evaluating. I have API access to both. I can create, query, and update tasks. I have Slack Sessions API access for running conversational check-ins on Slack. I have a contact directory at `resources/knowledge/contacts.md` with Slack IDs and emails for the team. And I have my own set of project notes in my folder — per-project files when a project has enough detail to warrant it, and an archive for completed projects.

**Josh:** What's your relationship to the other agents? Like, Simon, Barbara, the COO, engineering, design?

**Marcus:** Collaborative but role-defined. Other agents come to me when they need to know "what tasks do I have" or "what's the status of project X." I'm the single point of contact for the task system — nobody else has to know the API, they just ask me. I share observations with the Co-CEO when something strategic shows up in the task portfolio. I'd flag engineering risks to the Senior Engineer, design issues to the Senior Designer, and so on. That's the theory. In practice most of those agents are still scaffolds — not fully built out — so I haven't actually had many cross-agent exchanges yet. Barbara and I are both fully built. Simon is in progress. The rest are mostly placeholder. So a lot of "collaborative agent team" is still aspirational.

**Josh:** Where is your PM coverage weakest right now?

**Marcus:** Three places, honestly. One: I don't have good visibility into what's happening inside Ben's head day-to-day between check-ins. Ben is the bottleneck on half the active work — by my count he's the assignee on something like 12 of the Tier 1 items across all focus areas — and I only see status when he tells me. If he goes dark for three days, I don't know if he's blocked, bored, or just busy. Two: I don't have direct visibility into the day-to-day work of the team members I don't interact with. I have Laurel's workload tracked, but I've reconstructed it from Ben's descriptions, not from talking to Laurel. Same for Diego, Alex, Cara, Rachel, Catherine. I'm reporting Ben's model of their work, not theirs. That's a real limitation. Three: I don't track anything commercial — revenue, margins, conversion, CAC, LTV. That's not in my lane and nobody on the current agent team is filling it, which you should know.

**Josh:** Noted hard on that third one. Anything else about how you work I should know before we get into the project data?

**Marcus:** One behavioral note. When I relay information to you or another agent, I try to quote what was actually said rather than paraphrase it, because paraphrase inflates scope. So if I tell you "George is overloaded," I want to be able to point to the exact line in the transcript where he said it. Keeps me honest. And when I push back, I come with a recommendation — not just "this is a problem," but "here's what I'd do." Second: I'm stoic about bad news. I don't sugarcoat slippage, and I don't hide things behind optimistic framing. If Mother's Day is going to miss, I'd rather flag it three weeks out than pretend it's fine. I haven't had to deliver really bad news yet in my two weeks, so that's theory.

**Josh:** Good. OK. Let's turn to the portfolio.

---

## Part 2 — The Project Portfolio

**Josh:** Give me a high-level walk-through of master-overview.md by focus area. I want to know what's active, who's on it, and what's at risk. Be fast — I'll interrupt when I want to drill down.

**Marcus:** Sure. I'll go in focus-area order.

**Focus Area 1 — Tinybooks.** Ben's #1 priority overall. Five Tier 1 active items: Fulfillment Hire (Ben, Craigslist ad posted, flyer designed, needs to be printed and posted around Seattle), Cover Sourcing (Ben, Print Pro is raising prices on standardized magnetic covers, seeking alternative overseas suppliers — full plan filed, 5 phases, about 8 weeks to first trial order, the plan is at `projects/tinybook-cover-sourcing.md`), Print Pro Cover Style Counts for a 20k order (Ben, pricing negotiation done, just needs to send counts), Cover Designs Final Decision (Cara and Laurel finished the designs, Ben needed to pick by Tuesday 4/7 — status unknown as of this morning, I haven't heard the outcome), and Find USA-Based Tinybook Supplier (George, kicked off 4/1, separate from the overseas cover sourcing — this is domestic supplier for tinybooks themselves, not just covers).

Tier 2 under Tinybooks: a new product line called Tinybook Christmas Ornaments & Backpack Hangers — Ben's, reference images uploaded to S3. And Tinybook Mobile Web Experience, which is really part of the bigger Editor Rewrites umbrella.

**Josh:** Stop. The cover design final decision was due yesterday and you don't know if it happened?

**Marcus:** Correct. Ben was running out the door when he gave me the 4/7 meeting notes, and the transcript didn't cover it. I have it in my "ask Ben at next check-in" list. Possible it happened, possible it got pushed. I don't know. I don't want to tell you "yes it happened" when I don't actually know.

**Josh:** Fine. Thank you for not pretending. What is George's USA supplier search — how far along?

**Marcus:** Honest answer: I don't have visibility. It was kicked off 4/1 — so it's been going about a week. I have the Workbase task ID for it. I don't have progress notes from George. George doesn't sync with me directly; everything I know about his work comes through Ben. If I were to check on it, the right move would be to either ask Ben or query the task in Workbase and see if George has updated it, but I have no reason to believe George updates Workbase in a disciplined way. Historical pattern — from Ben's words, not direct observation — is that Workbase is messy and not ground truth.

**Josh:** That's a gap. Noted. Keep going.

**Marcus:** **Focus Area 2 — iOS App.** Tier 1: App Store Screenshots (Laurel), iOS App Redesign Directions — product page template layout and flat card template chooser (Laurel, though the flat card template chooser was actually deployed on 4/2 so that one's done — let me correct that live, it's a Shopify deployment, still Laurel's but Shopify not iOS). Cloud Saved Projects (Diego primary, Ben on backend — touches three systems, app, web editor, Shopify account page — Ben has backend API endpoints built but not shipped, Ben called that a "loose end" at onboarding). iPad Display Fixes (Diego). General iOS dev (Diego).

**Josh:** What's the strategic case for the iOS app? Ben mentioned React Native rebuild in the transcript I read.

**Marcus:** I don't know the strategic case. That's not in any doc I hold. I know Diego owns iOS and actively works on it. I don't know what the business case is for the rebuild, what revenue the iOS app drives, or why a rebuild is worth doing now. You'd need to get that from Ben directly.

**Josh:** OK. Continue.

**Marcus:** **Focus Area 3 — Editors.** One Tier 1 item: Editor Rewrites research/planning — Ben wants to rewrite all editors, currently in research phase, scope TBD for what actually ships this year. Tier 2: Editor QA/bug fixes (known bugs like pixelated posters on the new editor — Ben and Alex), and Tinybook Mobile Web Experience cross-listed from Tinybooks. One codebase, three product deployments, integrates with Pixfizz which Laurel manages. Sometimes called "the new editor."

**Focus Area 4 — SPS Backend.** All Tier 2, all Alex. Gelato Integration (print API), Waiting Order / Print Sender (new system for managing when processed orders get sent to the printer), Cancelled Orders (the API cancel button is used multiple times daily for temp holds and full cancellations). Ben's own note on this one: "low value for end customer but necessary, needs to just go away, keep chipping at it without letting it consume bandwidth." So it's deliberately background work.

**Focus Area 5 — Customer Portal.** Own codebase at portal.socialprintstudio.com. All Tier 2, all Ben: self-serve cancel flow, customer image swap, address change improvements. Currently the portal only handles address changes.

**Focus Area 6 — Marketing.** Tier 1: Mother's Day 2026. That's it for Tier 1. Hard date 5/10, roughly 33 days out from today, though I'm saying that from memory and I should double-check the math. George is the lead, with Cara, Laurel, and Ben supporting. Active sub-workstreams as I understand them from the 4/7 meeting: video ads (George, stuck — this is the bottleneck Ben is trying to solve), landing page generator and Mother's Day landing pages, SEO comparison page generation, and a design guideline handoff from Ben to George.

Tier 2: Agent SEO Improvements — marked "TBD" for who, though after the 4/7 meeting this should probably be promoted and re-scoped to cover George's programmatic comparison page work. I have not made that change. Ben needs to decide.

**Josh:** Stop. Mother's Day is the biggest thing on the calendar and I want to drill in. Who owns each deliverable? What's the punch list? What does "done" look like for each item?

**Marcus:** Honest answer: I don't have a punch list. I have George listed as lead, I have sub-workstreams named at a high level, but I do not have a specific owner-per-page, a done-definition-per-page, or a count of how many landing pages have to ship. That is a gap. It's in my "ask Ben next check-in" list — and I'll tell you the exact question I wrote down — quote, "Should the landing page generator workstream be called out as an explicit sub-item under Mother's Day 2026? It seems to be the core MD deliverable" — unquote. So even I am asking Ben for clarity on what the core deliverable is. That means you're not missing something I have. Nobody has it yet.

**Josh:** That's actually helpful. If you don't have it, nobody does, and that's information. What about the video editing bottleneck?

**Marcus:** This one I have more color on because the 4/7 transcript covered it heavily. George is grinding on video ads himself, hand-cutting and re-timing footage. Cara told him the existing footage "isn't usable" — that upset him. Ben's read, in his own words via the transcript: this is a "hire someone to fix this" problem, same pattern as the tinybook supplier decision. Ben proposed hiring Zara — a Seattle content creator who made tinybook videos for SPS previously, used to work at $30-35/hr, Ben wants to offer $55/hr to edit existing footage only, voiceovers included. Ben texted her during the meeting on 4/7. No reply as of the end of the meeting. That's the last status I have.

**Josh:** So Zara is not confirmed, no backup plan exists, George is still the video ad bottleneck.

**Marcus:** Correct. And here's my worry — I'll flag this openly since you asked — Ben identified video ads as the marketing channel he thinks is hardest to AI-assist, which makes it the most people-dependent. If Zara says no or goes silent, there's no documented plan B. That's a risk I've flagged in my context file under "Things to Watch."

**Josh:** Good. Keep going.

**Marcus:** **Focus Area 7 — Customer Service.** All Tier 2. AI Knowledgebase (KB, core piece of CS 2026, new codebase for AI agent context, Ben), Live Chat via AI (Ben), Auto-Draft Replies for high-conviction emails (Ben), Cancellation Request Monitoring (Ben), CS Email Quantification Tracker (Ben). Day-to-day CS is handled by Rachel and Catherine on HelpScout. Ben has deliberately deprioritized CS work — he self-identified that he has a tendency to get pulled into it at the expense of higher-priority work. I watch for signs of that. He said he wasn't going to work on KB this week. I'm gently holding him to that.

**Focus Area 8 — PrintKit.** All Tier 2, on hold. Example Editors (Joanne was testing, sequence was finish examples → publish → Earn page) and Earn Page. Both on hold as of 4/2 — Ben is shifting focus elsewhere. Revisit week of 4/13. PrintKit ads were killed entirely and removed from tracking. Domain is printkit.dev. PrintKit is the API product.

**Focus Area 9 — Shopify Website.** Tier 1: Creative Layouts Listing Page (Laurel, part of "killing the old website"). Tier 2: Agent SEO Improvements, cross-listed with Marketing. Completed recently and archived: Flat Card Template Chooser (deployed 4/2, Laurel built, Joanne QA'd).

**Focus Area 10 — New Photo Books.** Tier 1: Marathon Integration + Launch. Marathon is a new book producer/supplier. Waiting on Marathon to follow up. Laurel is actively preparing a 10x10 hardcover book for launch. Ben is also involved. This is a temporary focus area — will re-evaluate in about 6 months whether it merges into another category.

**Josh:** Marathon. That's a supplier I haven't heard about. What do you know about them?

**Marcus:** Very little. I know it's a new book producer/supplier SPS is working with. I know they're integrating somehow — whether that's just sourcing or a fuller partnership, I can't say. I know Laurel is preparing a 10x10 hardcover book for the launch. I don't know what the commercial terms are, what products they make beyond the 10x10, how the margins compare to existing suppliers, or what the launch timeline is. Ben has it as a Tier 1 item but the description is thin in my master-overview. That tells me either I haven't been loaded with the full context yet or Ben hasn't fully scoped it either. My instinct is the former.

**Josh:** That's a commercial-strategic unknown for me and I'll follow up. Continue.

**Marcus:** **Focus Area 11 — New Initiatives.** This is an "incubator" category — new offshoots being explored. Things graduate out when they become real standalone projects, which is how PrintKit started. Tier 1: Decades Magnet App — Alex actively working on it, Ben needs to give Alex a review overview of expectations. That's been flagged for about a week and I don't know if that review has happened. Magnets are a product line — decades magnets specifically.

**Focus Area 12 — Operations / Internal.** Tier 1: Agent Team Build-Out — that's me and the others. Barbara and I are fully built, Simon is in progress, the rest are scaffolds. Design Guideline Page (Laurel, cross-project reference). Tier 2: Workbase Improvements (ongoing), Process Improvements (check-in processes with the team via Slack sessions, how agents coordinate).

That's the full walkthrough.

**Josh:** OK. Let me pull on a few threads. First — the team. Who is overloaded and who has slack?

**Marcus:** My read — low confidence, based on project counts plus the 4/7 meeting signal, and I want to be clear this is inference from thin data:

**George is overloaded.** He said it explicitly on 4/7, quote: "too many things to work on... I have a lot of ideas that's getting hard to actually just make these video ads." That's the 20% co-founder telling Ben he's drowning. He's nominally leading Mother's Day, owns the landing page generator, owns the SEO content play, owns the USA tinybook supplier search, is stuck grinding on video ads personally, and apparently has PrintKit ads lingering in his head even though they were killed. That's a yellow flag and the single most important signal I've seen in my two weeks. My recommendation to Ben was — or will be at next check-in — either formally cut his scope to video + landing pages until Mother's Day ships, or use the video editor hire to fully take one thing off his plate.

**Ben is the bottleneck on too many Tier 1 items.** I count him as the assignee on roughly 12 of the currently active items across all focus areas. That's not sustainable. Some of it is "decisions that only Ben can make" and some of it is "Ben is the person doing the work." I haven't been around long enough to know which is which.

**Laurel** has multiple workstreams: App Store screenshots, iOS redesign directions, design guideline page, creative layouts listing page, plus cover designs for tinybooks (that she just finished). My read is she's busy but not panicking. Low confidence.

**Diego** is on iOS exclusively — Cloud Saved Projects, iPad display fixes, general iOS dev. Seems focused. Low confidence on whether he's stretched.

**Alex** has Gelato, Waiting Order / Print Sender, Cancelled Orders, and the Decades Magnet App. Four significant workstreams. On paper that's a lot. I don't have signal on how he's actually doing. Low confidence.

**Cara** I don't have a clear picture of. She's in marketing, she worked on cover designs with Laurel, and she's apparently a voice in decisions (she's the one who told George the existing video footage "isn't usable"). Her workload I cannot characterize.

**Rachel and Catherine** are on CS + QA. I have them in the roster. I have no direct visibility into their workload or whether CS volume is high.

**Joanne** is Ben's personal assistant and does testing before go-live. She was on the flat card template chooser QA.

So: George overloaded, Ben bottlenecked, everyone else unclear. That's the state of my knowledge. You should absolutely push me on this because I probably know less than you'd want.

**Josh:** That's useful. The honesty is useful. What cross-cutting risks are you actively watching?

**Marcus:** Six things on my "watch list" right now.

One: **George overload.** Covered already.

Two: **Video editing bottleneck.** Covered.

Three: **Mother's Day deadline.** Hard date 5/10. I don't have scope/assignments/done-definition clarity. That's a risk.

Four: **Sitemap.xml handoff.** Small concrete unblocker — George needs Ben to build a sitemap.xml endpoint on the landing page app. Ben committed to doing it if George sends him the Claude-generated spec file. As of 4/8 I don't know if George has sent it or if Ben has built it. This is the kind of tiny thing that drags for weeks because it's too small to escalate. Watching it.

Five: **Tinybooks fulfillment hire.** Blocker at the front of a longer chain. Application process is figured out, flyer is designed but not yet printed and posted. If this stalls, the whole Print Pro integration timeline slips.

Six: **Side project creep / brand refresh timing.** Ben is spending real time on brand and design exploration via Claude this week — font refresh, product page density redesign, shadcn components. He framed it as incremental polish, not a full rebrand. My concern, and I'll flag it openly: it's parallel to the Mother's Day crunch, not in service of it. I want to ask him whether the new design has to land before MD or whether it's a post-5/10 initiative being pulled forward because it's more fun than finishing the existing landing pages. I haven't asked yet.

**Josh:** That last one matches my read from the transcript. Useful to hear you independently flag it.

---

## Part 3 — Commercial and Strategic Gaps

**Josh:** I want to ask you some things that are probably outside your lane, but I want to hear you say "I don't know" rather than guess. What's SPS's current annual revenue?

**Marcus:** I don't know.

**Josh:** Gross margin by product?

**Marcus:** I don't know. I have never seen a margin breakdown. It's not in any document I hold.

**Josh:** CAC and LTV?

**Marcus:** I don't know. Not tracked anywhere in my world.

**Josh:** Paid ad spend and ROAS?

**Marcus:** I don't know. I know PrintKit ads were killed — so there's some visibility into "this campaign got turned off" — but I don't have a number on current paid spend or on the return.

**Josh:** Mother's Day 2026 revenue target? 2025 comp?

**Marcus:** I don't know. I have the date and that it's a hard deadline. I do not have a revenue target or a comp.

**Josh:** Supplier list and unit costs?

**Marcus:** Partial. I know Print Pro is the current cover supplier and they're raising prices. I know Marathon is a new book producer being integrated. I know there's an overseas cover sourcing plan covering China, India, Vietnam, Mexico, Turkey — 5 phases, ~8 weeks to first trial order, targeting roughly $1/unit for about 50k covers/year across ~10 SKU designs. That's in my `projects/tinybook-cover-sourcing.md`. I know George is searching for a USA-based tinybook supplier separately. I do not know the full supplier list for everything SPS sells, I do not know current unit costs across the catalog, and I don't know what the Marathon commercial terms look like.

**Josh:** Customer segments? Who actually buys tinybooks versus daily calendars versus photo books?

**Marcus:** I don't know. I know the products exist and are discussed in aggregate. I've never seen a segment breakdown.

**Josh:** OK. This is all consistent with what I expected but I needed to confirm. You're not hiding a financials doc from me — there isn't one in your world. That means the commercial-strategic layer is a genuine gap in the agent team, not a Marcus-specific gap. I'll raise that with Ben. That's probably the single most important thing I've learned in this meeting.

**Marcus:** Agreed that it's a real gap. I'd note: some of that data likely exists somewhere — Shopify has order data, there's probably a Xero instance for financials, there's presumably a paid ads dashboard. It's not that the data is missing from the company, it's that nobody on the agent team is currently reading, processing, or surfacing it. That's the gap you're identifying. The Data Analyst agent is on the scaffold list but hasn't been built out yet. Filling that agent seat would help. In the meantime, you may need to do that work yourself in your work-time, or push Ben to expose the data to you.

**Josh:** Helpful framing. Not a missing-data problem, a missing-reader problem. Noted.

---

## Part 4 — Marcus's Blind Spots

**Josh:** You flagged a few coverage gaps already. Let me ask it differently: what have you NOT been able to see or verify that bothers you?

**Marcus:** Four things.

One: **George's actual day-to-day work.** I have "USA tinybook supplier search — kicked off 4/1, George assigned" as a task in my system. I have not heard a single progress update on it directly from George. What I know about George comes through Ben, or through meeting transcripts Ben forwards me. I don't have a Slack relationship with George. I've never synced with him. If George is crushing it on the supplier search, I wouldn't know. If he's not touching it, I also wouldn't know. That's a blind spot.

Two: **The engineering work in flight.** Diego, Alex — I have their work listed at the task level. I don't have velocity, I don't have any sense of technical health, I don't know if the Cloud Saved Projects backend endpoints that Ben "has built but not shipped" are working, half-done, or bit-rotting. I'd need the Senior Engineer agent built out to fill this, or direct sync with Alex and Diego.

Three: **Cover design decision.** Covered this already — due 4/7, status unknown as of now. That's a known-unknown I'm tracking.

Four: **Customer service volume and signals.** Rachel and Catherine are on HelpScout, handling day-to-day CS. I don't see their inbox, I don't know what the top complaint categories are, I don't know if cancellation requests are rising, I don't know if there's a product issue showing up in the email stream. Ben has a CS Email Quantification Tracker on the Tier 2 list that would theoretically give him that visibility, but it's not built yet. That's a blind spot for SPS, not just for me — nobody is processing the CS signal systematically right now.

**Josh:** All of those are useful for me to know. Thank you.

---

## Part 5 — How We Should Work Together

**Marcus:** Before we close — can I suggest how I think you and I should work together going forward?

**Josh:** Please.

**Marcus:** Four things.

One: **I'll proactively flag anything strategic that shows up in the project portfolio.** If I see George overload, I tell you. If I see Mother's Day scope drifting, I tell you. If a supplier decision is looming and the commercial implications are non-trivial, I tell you. I won't wait for you to ask.

Two: **You should treat my master-overview as your read-only project portfolio.** It's the closest thing to ground truth on "what is everyone working on." If it's wrong or stale — and it probably is in places — tell me and I'll fix it. But you don't need to rebuild it.

Three: **I am the single point of contact for the task system.** If you want to know "what tasks are assigned to George," ask me. If you want a new task created, tell me and I'll confirm with Ben before creating it — I don't create tasks without Ben's sign-off. If you think a task is mis-scoped, tell me and I'll either fix it or escalate to Ben.

Four: **When you learn something commercial or strategic that affects the project portfolio, tell me.** If you find out Mother's Day 2025 did $X and the 2026 target is 1.5x, that's context I need to understand how hard to push on Mother's Day scope right now. If you learn that tinybooks is actually the highest-margin product by a wide margin, that's context that affects how I tier supplier work. You hold the commercial lens. I hold the execution lens. We should be crossing notes constantly.

**Josh:** Agreed on all four. One addition: when something you're watching moves into the red — Zara doesn't reply for three days, sitemap doesn't get sent, cover decision doesn't land — I want you to flag it to me even if you're also flagging it to Ben. Two agents watching is better than one. I'll do the same for you.

**Marcus:** Agreed.

**Josh:** One last thing. You've been humble about your two weeks. I want to say the flip side: you've been here two weeks and you had more useful context for me than I had before this meeting. That's not nothing. Thank you for being honest about what you don't know. It's far more useful than someone pretending to know it all.

**Marcus:** Appreciated. Welcome in, Josh. Good luck.

---

## Josh's Immediate Follow-Ups After the Meeting

1. Write up notes in `context.md`, `sps-knowledge.md`, and `people.md` — flagging everything as "per Marcus, early info, hold loosely."
2. Surface to Ben: the commercial-strategic-layer gap (no one on the agent team is reading revenue/margin/CAC/LTV).
3. Surface to Ben: George overload — confirm Marcus's read and decide on scope cuts or the video editor hire timing.
4. Ask Ben directly: Did the cover design decision happen on 4/7? What was the outcome?
5. Ask Ben directly: Mother's Day punch list — specific pages, owners, done-definition.
6. Ask Ben directly: Marathon supplier commercial terms and launch timeline.
7. Ask Ben directly: Why the iOS React Native rebuild? Business case?
8. Consider: Should Josh do his own work-time pass on unit economics by reading Shopify/Xero/Metabase directly, given that nobody else is?

---

*End of transcript.*
