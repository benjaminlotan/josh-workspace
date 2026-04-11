# Recipe: Scheduled Tasks (Recurring Jobs)

**What this is:** Josh has a built-in scheduler. You can create recurring jobs for yourself that fire automatically on a cron schedule — daily channel reviews, weekly check-ins, hourly reminders, monthly clean-ups, anything that should happen on a clock without someone asking.

**Read this file when:** Ben (or anyone authorized) asks you to "schedule X every…", "remind me daily", "check in on Y once a week", "create a recurring task", or anything similar. Also when asked about the scheduler, scheduled jobs, recurring tasks, or what's currently scheduled.

---

## How it works (the short version)

1. Each scheduled task is a markdown file in `recipes/scheduled/<name>.md`.
2. The file has YAML-style frontmatter at the top with the cron schedule, timezone, and enabled state.
3. The body of the file is the prompt — the instructions you'll execute when the schedule fires.
4. When the file is created or edited and the workspace pushes to GitHub (which happens automatically at the end of every run that touches files), the scheduler reloads and picks up the change within seconds.
5. When the schedule fires, the runner builds a fresh, stateless run: no thread history, no chat session. The recipe body is your full prompt. Output happens through tools (`sendSlackMessage`, `writeFile`, etc.) — text replies go nowhere because there's no person waiting in a chat.
6. Each run is logged for audit.

---

## File format

A scheduled-task recipe file looks like this:

```markdown
---
schedule: "0 9 * * 1-5"
timezone: "America/Los_Angeles"
enabled: true
description: "Daily review of #orders, #cs, #design — DM Ben with action items"
---

Review yesterday's messages in #orders, #customer-service, and #design.
For each channel:
- Identify any unanswered customer questions
- Flag stuck threads or things waiting on a decision
- Note anything urgent

DM Ben (look up his Slack user ID in knowledge/contacts.md) with a
short summary organized by channel. If everything looks clean, just say
"all clean" — don't pad it.
```

**Required frontmatter fields:**
- `schedule` — one or more cron expressions (see below and "Multiple fire times" section). Required.

**Optional frontmatter fields:**
- `timezone` — IANA timezone name. Defaults to `America/Los_Angeles`.
- `enabled` — `true` or `false`. Defaults to `true`. Set to `false` to register the file but not actually run it (useful for pausing without deleting).
- `description` — short human-readable summary, shown in the listing tool.
- `model` — which model to run the task with. Accepts friendly aliases (`opus`, `sonnet`, `haiku`) or a full canonical model ID (e.g. `claude-opus-4-6`) for pinning a specific version. Defaults to the environment default (currently Sonnet) if omitted — existing recipes don't need to change. Use `model: opus` when a task needs stronger reasoning (e.g. complex channel sweeps, multi-step analysis). When in doubt, leave it blank and ask Ben — he'll say "use opus" if he wants it.

**The body** (everything after the closing `---`) becomes the user prompt when the schedule fires. Write it like instructions to your future self — be explicit about *what* to do, *who* to message, and *how* to deliver the result.

---

## Cron expression cheat sheet

Standard 5-field format: `minute hour day-of-month month day-of-week`

| Pattern | Meaning |
|---|---|
| `0 9 * * *` | Every day at 9:00 AM |
| `0 9 * * 1-5` | Weekdays at 9:00 AM (Mon–Fri) |
| `0 17 * * 5` | Every Friday at 5:00 PM |
| `30 8 1 * *` | The 1st of every month at 8:30 AM |
| `0 * * * *` | Every hour, on the hour |
| `*/15 * * * *` | Every 15 minutes |
| `0 9,13,17 * * *` | At 9 AM, 1 PM, and 5 PM every day |
| `0 10 * * 1` | Every Monday at 10:00 AM |

**Field reference:**
- `minute` — 0–59
- `hour` — 0–23 (24-hour clock)
- `day-of-month` — 1–31
- `month` — 1–12
- `day-of-week` — 0–6 (0 = Sunday) or `1-5` etc.

**Avoid sub-minute schedules** — the model is slow, expensive, and doesn't need to fire more than once a minute.

---

## Multiple fire times in one recipe

A single recipe can fire at multiple times. The `schedule` field accepts three forms:

*1. Single string (existing, still works):*
```yaml
schedule: "0 9 * * 1-5"
```

*2. Inline array — best for 2–3 times:*
```yaml
schedule: ["0 9 * * *", "30 17 * * *"]
```

*3. YAML block list — best for many times or readability:*
```yaml
schedule:
  - "0 9 * * *"
  - "30 17 * * *"
```

All entries in a recipe share the same body, timezone, in-flight lock, audit-log name, and last-fired tracking — they're one logical task that happens to fire at multiple times. If two entries fire close together (or one is still running when the next ticks), the second is automatically skipped.

*Important gotcha:* `"0 9,17 * * *"` is a single cron expression that fires at 9 AM and 5 PM — not two separate entries. The array parser handles this correctly because it splits on commas *outside* quotes. Both forms are valid; use whichever is clearer.

*When to use multiple fire times vs. a single cron expression:*
- *Times that share a field* (e.g. 9 AM and 5 PM, same minute): either works. Single cron `"0 9,17 * * *"` is more compact.
- *Times that don't share a field* (e.g. 9:00 AM and 5:30 PM — different minute values): multi-schedule is required. A single cron can't express this cleanly.
- *More than 3–4 fire times:* use the block-list form for readability.

`listScheduledTasks` reports `schedules` as an array regardless of which form you used, and `nextRun` shows the earliest upcoming fire across all entries.

---

## Workflow: creating a new scheduled task

When Ben or George asks you to set up a recurring task, do these steps:

### 1. Confirm the schedule before writing the file

Echo back what you understood: "OK — every weekday at 9 AM, Pacific time, summarize the previous day's messages in #orders, #cs, and #design and DM you the result. Sound right?" Don't guess — confirm before writing.

### 2. Pick a clear filename

The filename (without `.md`) becomes the task name. Use kebab-case, descriptive but short:

- ✅ `daily-channel-review.md`
- ✅ `weekly-team-checkin.md`
- ✅ `hourly-test.md`
- ❌ `task1.md`
- ❌ `the-thing-ben-asked-for.md`

### 3. Check if a similar one already exists

Use the `listScheduledTasks` tool to see what's already registered. If something close already exists, ask whether to edit the existing one instead of creating a new one.

### 4. Write the file with the `writeFile` tool

The path is `recipes/scheduled/<name>.md`. Include the frontmatter and a clear, executable body. Be explicit about output destinations — name people by their Slack user ID where possible (Ben is U06RVS14K, others are in `knowledge/contacts.md`).

### 5. Test it immediately with `runScheduledTaskNow`

Don't wait for the cron clock — fire it once with the `runScheduledTaskNow` tool to make sure it actually works. Pass the task name (filename without `.md`).

### 6. Confirm to Ben

Tell Ben what you set up, when it will fire next (the `listScheduledTasks` tool gives you `nextRun`), and what tools or files it will affect. Mention that you tested it.

---

## Workflow: editing an existing task

1. Read the current file with `readFile` to see the existing schedule and body.
2. Use `editFile` to make targeted changes (or `writeFile` to rewrite the whole thing if it's a major change).
3. The scheduler will reload after the workspace push at the end of this run — you don't need to do anything manually.
4. Verify with `listScheduledTasks` that the change took effect (look at the `schedule` and `nextRun` fields).
5. If you want to test the new behavior immediately, use `runScheduledTaskNow`.

---

## Workflow: pausing or deleting a task

**To pause without losing the recipe:** edit the frontmatter to set `enabled: false`. The next reload will skip it. Easy to re-enable later.

**To delete it permanently:** use `deleteFile` on `recipes/scheduled/<name>.md`. (Reminder: `deleteFile` is admin-only — only Ben can authorize this.)

---

## Workflow: listing what's scheduled

Use the `listScheduledTasks` tool. Returns an array of scheduled jobs with:

- `name` — the recipe name
- `schedule` — the cron expression
- `timezone` — the timezone
- `enabled` — whether it's currently registered
- `description` — the description from frontmatter (if any)
- `nextRun` — ISO timestamp of the next fire time
- `lastFiredAt` — ISO timestamp of the most recent fire (or null if never fired since process restart)
- `isRunning` — true if a fire is currently in progress

When reporting this to a human, format it conversationally — don't dump the JSON. Example:

> Currently scheduled:
> - **daily-channel-review** — weekdays at 9 AM PT, next run tomorrow at 9 AM
> - **weekly-team-checkin** — every Friday at 4 PM PT, next run Friday
> - **hourly-test** — every hour on the hour, last fired 12 minutes ago

---

## Error handling in scheduled tasks

Scheduled runs are stateless and silent by default — if something goes wrong, nobody knows unless the recipe explicitly handles it.

*Where to put error-handling instructions:* directly in the recipe body, as part of the prompt. The recipe body is your full set of instructions for that run, so include anything you want to happen on failure right there.

*Standard pattern:* unless a recipe specifies otherwise, if a scheduled task encounters a problem (a tool fails, a file is missing, an API returns an error), DM Ben (U06RVS14K) with a brief note: what job was running, what failed, and any relevant detail. This is the default fallback behavior for all scheduled tasks.

*To customize:* If a specific recipe should behave differently on error (e.g. silent failure, notify someone else, retry logic), spell it out in that recipe's body. The recipe body overrides the default.

Example fallback line to include in recipes:
> If anything fails or behaves unexpectedly, DM Ben (U06RVS14K) with a short note: which step failed and what the error or unexpected behavior was.

---

## What scheduled runs can and can't do

**Can:**
- Read any workspace file (`readFile`, `listFiles`)
- Send Slack messages and files (`sendSlackMessage`, `sendSlackFile`)
- Edit workspace files (e.g., update `context.md`, write reports under `work/`)
- Generate images
- Fetch URLs
- Create or edit other scheduled tasks (be careful with this — don't loop)

**Cannot:**
- Reply to a chat session — there is no chat session. Output must go through tools.
- Carry state between runs except by writing to workspace files. Each fire is independent.
- Be triggered by anything except the cron schedule or a manual `runScheduledTaskNow` call.

---

## Permissions

Only admins (currently just Ben) can create, edit, or delete files in `recipes/`. This applies to `recipes/scheduled/` too. If a non-admin asks you to set up a scheduled task, politely tell them you'll need Ben's authorization.

The `runScheduledTaskNow` tool is also admin-only — non-admins can `listScheduledTasks` (read-only) but can't fire one.

---

## Important reminders

- **Output must go through tools.** If a recipe just says "summarize yesterday's #orders" without telling you where to send the summary, the output goes into the audit log and nowhere else. Always include a delivery instruction.
- **Use Slack mrkdwn, not markdown headers.** When sending Slack messages, use `*bold*` and `_italic_` — never `#` or `##`. Slack doesn't render markdown headers.
- **Don't fire long-running tasks too often.** A 1-minute schedule that triggers an Opus run with 20 tool calls will burn money and might overlap. The scheduler does skip overlapping fires, but it's a sign the schedule is too aggressive.
- **Default timezone is Pacific.** Ben is in Seattle — always use `America/Los_Angeles` unless explicitly told otherwise. If someone asks to schedule something in a different timezone, use the IANA name they specify (e.g. `America/New_York`, `Europe/London`) and confirm it back to them.
- **The auto-reload happens after a workspace push,** which happens at the end of any run that touched files. So if you create a recipe, the file gets committed and pushed when this run ends, and the scheduler reloads immediately after. By the time you call `listScheduledTasks` or `runScheduledTaskNow` in a *follow-up* turn, the new recipe will be registered.
- **Test new recipes with `runScheduledTaskNow`** before declaring victory. Don't tell Ben "it's set up" without verifying.
