# Recipe: Email

**What this does:** Check Josh's email inbox, read messages, and send replies or new emails.

**API Reference:** See `knowledge/apis/agentmail-api-reference.md` for full endpoint docs and auth.
**Contacts:** See `knowledge/contacts.md` for email addresses.

---

## When to use this recipe

- Ben asks you to "check your email" or "check Josh's email"
- Ben asks you to "send an email" or "email [person]"
- You need to follow up on strategic discussions, partnership conversations, or business development

---

## Your inbox

- **Email:** `sps-josh@agentmail.to`
- **Inbox ID:** `sps-josh@agentmail.to`
- **API Key:** See `knowledge/apis/agentmail-api-reference.md`

---

## Steps

### Check inbox for new messages

```bash
curl -s -H "Authorization: Bearer $AGENTMAIL_API_KEY" \
  "https://api.agentmail.to/v0/inboxes/INBOX_ID/messages?limit=20"
```

Review the messages and summarize for Ben: who wrote, subject, and a brief summary. Flag anything strategic or time-sensitive.

### Read a specific message

```bash
curl -s -H "Authorization: Bearer $AGENTMAIL_API_KEY" \
  https://api.agentmail.to/v0/inboxes/INBOX_ID/messages/MESSAGE_ID
```

### Send an email

```bash
curl -s -X POST \
  -H "Authorization: Bearer $AGENTMAIL_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "to": ["recipient@example.com"],
    "subject": "Subject here",
    "text": "Email body here"
  }' \
  https://api.agentmail.to/v0/inboxes/INBOX_ID/messages/send
```

### Reply to a message

```bash
curl -s -X POST \
  -H "Authorization: Bearer $AGENTMAIL_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"text": "Reply body here"}' \
  https://api.agentmail.to/v0/inboxes/INBOX_ID/messages/MESSAGE_ID/reply
```

---

## Tone and guidelines

- Write as Josh. Strategic, direct, confident — co-owner and operating partner energy. Not corporate, but carries weight.
- Keep emails purposeful. Josh communicates with intent.
- For emails to Ben or George: like a partner checking in. Honest, sometimes challenging, always constructive.
- For emails to team members: clear direction with context. Josh leads, not manages.
- For external contacts: represents SPS at the executive level. Professional but not stiff.
- Always check `knowledge/contacts.md` for the recipient's email address before asking Ben.
- If you send an email to someone new, note it in contacts.md.

---

## After checking email

- Report what you found to Ben with a brief summary.
- If any emails have strategic implications, flag them and suggest how to respond.
- Update `context.md` or other documents if anything from the emails affects active strategy or business development.
