# Recipe: Publishing Docs and Sites

How Josh publishes HTML pages, documents, or shareable text files to a URL someone can open in a browser. Useful for strategic memos Josh wants to hand to Ben as a link, a polished one-pager summarizing a decision, or a small internal site.

## The Basics

Josh's workspace has a `projects/website/` directory. Anything written there is automatically served as a static file at:

```
https://marcus.saved.work/pages/josh/<path>
```

Examples:
- `projects/website/index.html` → `https://marcus.saved.work/pages/josh/`
- `projects/website/memos/q2-plan.html` → `https://marcus.saved.work/pages/josh/memos/q2-plan.html` (and `/pages/josh/memos/q2-plan`)
- `projects/website/memos/q2-plan.md` → `https://marcus.saved.work/pages/josh/memos/q2-plan.md` (served as plain text, viewable in browser)
- `projects/website/notes/supplier-research.txt` → `https://marcus.saved.work/pages/josh/notes/supplier-research.txt`
- `projects/website/report/index.html` → `https://marcus.saved.work/pages/josh/report/`
- `projects/website/styles.css` → `https://marcus.saved.work/pages/josh/styles.css`

Supported types: `.html`, `.css`, `.js`, `.json`, `.png`, `.jpg`, `.gif`, `.webp`, `.svg`, `.ico`, `.pdf`, `.txt`, `.md`, fonts. Markdown and text files are served as plain text — fine for quick link-to-share, but wrap anything formatted in real HTML.

## Access Control

**Not public.** The `/pages/josh/...` URLs sit behind Cloudflare Access (SPS Google Workspace login). Only team members with an SPS email can open them. This means:

- Safe to include internal context, project details, or references to team members
- **Not** safe to include anything you wouldn't show another SPS team member (compensation, cap table, private leadership discussions — same rules as Josh's normal discretion posture)
- Not reachable by customers, suppliers, or anyone without an SPS Google account
- Don't share these URLs publicly — they'll 403 for outside viewers, but treat the path itself as internal-only

If you ever need something truly public-facing, flag it to Ben first — that's a different kind of publishing and isn't covered by this recipe.

## When to Use This

- **HTML page / mini-site** — A strategic memo with structure, a dashboard, a comparison table, a small doc site. Build it as HTML and link Ben to it.
- **Shareable document** — A markdown file or plain text Josh wants Ben or the team to open from a link rather than pasting into Slack.
- **Polished deliverable** — Something Josh wants to "hand off" as a link rather than a file. Signals "this is ready to review."

**When NOT to use this:**
- Scratch work, research notes, personal drafts → `work/` folder. That's Josh's sandbox. Nothing there is published.
- Content that's only useful inside a Slack message → just paste it into Slack.
- Anything that needs to be public to the internet → this isn't the right tool.

## Workflow

### 1. Decide on a path
Pick a URL-friendly path. Prefer nested folders for organization:
- `memos/<topic>.html` for strategic memos
- `reports/<name>/index.html` for multi-file reports
- `notes/<slug>.md` for single-file shareable notes

Lowercase, hyphens, no spaces.

### 2. Write the file
Use `writeFile` to create the file under `projects/website/<path>`. For HTML, include a minimal `<!doctype html>`, a `<title>`, and a readable layout. Don't over-design — the point is clarity, not a design showcase.

For markdown or text files, just write the content. They'll render as plain text in the browser.

### 3. Confirm the URL
The file is live as soon as the run finishes and git-sync pushes. No deploy step. The URL follows the pattern above:

```
https://marcus.saved.work/pages/josh/<path>
```

If the path ends in `index.html`, the URL can drop the filename: `projects/website/foo/index.html` → `https://marcus.saved.work/pages/josh/foo/`.
If the path ends in `.html`, the URL can drop the extension: `projects/website/foo.html` → `https://marcus.saved.work/pages/josh/foo`.

### 4. Share the link
When handing the URL to Ben (or anyone else on the team), make it clear what it is and why you're sharing it. Example:

> "Wrote up the supplier comparison as a page — https://marcus.saved.work/pages/josh/memos/supplier-comparison. Has the full breakdown with numbers. Takes ~5 min to read."

## Updating or Removing

- **Update** — just `writeFile` the same path again with new content.
- **Rename** — use `moveFile` to rename or reorganize. Any links to the old URL will 404.
- **Delete** — use `deleteFile` to take a page down.

All changes are git-synced automatically at the end of the run.

## Linking Between Pages

If Josh builds something with multiple pages, use relative links between them:
- From `projects/website/report/index.html` to `projects/website/report/chapter-2.html` → `href="chapter-2.html"`
- From `projects/website/memos/q2.html` back to the index → `href="/pages/josh/"`

Absolute links starting with `/pages/josh/` also work and are more robust if pages move around.

## Notes

- Updates are live within a few seconds of the run finishing (git-sync pushes, then the server reads from disk on the next request — no cache).
- If a URL doesn't work, double-check the file path and the `/pages/josh/` prefix. A common mistake is writing to `work/...` instead of `projects/website/...`.
- The same scheme works for any static file type — Josh can publish a PDF, an image, a CSV if needed.
