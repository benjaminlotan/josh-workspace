# Recipe: Getting Slack History

*This recipe will be developed over time. For now it covers the basics — when to use `getSlackHistory`, when not to, and how it fits into scheduled tasks. If you ever think of a new use case or want to use it in a way not covered here, ask Ben first.*

---

## When to use it

- *Someone explicitly asks you to check a channel.* "What's been happening in #design?" or "Catch me up on #orders from yesterday." This is the primary interactive use case.
- *Scheduled tasks.* Daily/weekly channel sweeps, digests, pattern detection — this is the main reason the tool exists. A scheduled recipe can read channels and DM Ben with a summary.
- *Reconstructing context.* If a decision or event is referenced and you need the backstory, you can pull the relevant thread or time range.

*Default stance:* Don't use this proactively unless you have a genuinely good reason. If you think you should check a channel unprompted, message Ben about it first rather than just doing it.

## When NOT to use it

- *Not a search engine.* You can't full-text search across channels. You read a specific channel's messages in a time range or thread — that's it.
- *Not a substitute for conversation.* If you need to know something, asking the person directly is usually better than reading their channel history.
- *History is limited.* Ingestion started in early April 2026. Don't try to find anything from before that.
- *Only channels the service user is in.* If Josh isn't a member of a channel, the tool returns nothing.

## Access

Currently this tool is available when Ben is talking to you (DM or @mention) or during a scheduled task run. Access may expand — if it does, update this recipe.

## Composing with other tools

- `getSlackHistory` → spot a project update → `editFile` to update context.md or relevant docs
- `getSlackHistory` → identify a file attachment → `downloadSlackFile` *only if you actually need the file contents* for a report or task. Don't download files by default — they're usually shared between people for specific purposes, not for you.
- `getSlackHistory` → notice something that needs follow-up → `sendSlackMessage` to flag it

## Useful patterns for scheduled recipes

These aren't set up yet — Ben will configure them when ready:

- *Daily channel sweep:* `since: "24h"` across key channels, single digest DM to Ben
- *Weekly review:* `since: "7d"`, summarized per channel
- *"Catch me up on #X":* recent N messages, summarized
- *Thread investigation:* use `threadTs` to pull a specific discussion thread

---

*This recipe is intentionally minimal. Expand it as new use cases emerge and access policies change.*
