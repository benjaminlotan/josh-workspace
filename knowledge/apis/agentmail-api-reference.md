# AgentMail API Reference

**Service:** [AgentMail](https://agentmail.to) — Email inbox API for AI agents
**Console:** https://console.agentmail.to
**Docs:** https://docs.agentmail.to
**Account Email:** claude@socialprintstudio.com
**Console Login:** No password — uses email verification codes sent to claude@socialprintstudio.com. Sign in at console.agentmail.to, enter the email, then check Gmail for the code.

---

## Authentication

All requests require a Bearer token in the `Authorization` header:

```
Authorization: Bearer AGENTMAIL_API_KEY
```

**API Key:** `am_us_8eacb10316c0a5bd8d696ed05fb4346ab38dc175e9d7955e5bf7c74601fbe539`

Store the key in the environment or reference it from this file. The key starts with `am_`.

---

## Base URL

```
https://api.agentmail.to/v0
```

---

## Inboxes

### Create Inbox

```bash
curl -s -X POST \
  -H "Authorization: Bearer $AGENTMAIL_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"username": "barbara", "domain": "agentmail.to", "display_name": "Barbara"}' \
  https://api.agentmail.to/v0/inboxes
```

**Request body:**
| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `username` | string | No | Local part of the email (e.g., `barbara`). Auto-generated if omitted. |
| `domain` | string | No | Domain for the inbox. Default: `agentmail.to`. |
| `display_name` | string | No | Friendly name shown in emails. |

**Response:** Returns inbox object with `inbox_id` and `email_address`.

### List Inboxes

```bash
curl -s -H "Authorization: Bearer $AGENTMAIL_API_KEY" \
  https://api.agentmail.to/v0/inboxes
```

### Get Inbox

```bash
curl -s -H "Authorization: Bearer $AGENTMAIL_API_KEY" \
  https://api.agentmail.to/v0/inboxes/{inbox_id}
```

### Delete Inbox

```bash
curl -s -X DELETE \
  -H "Authorization: Bearer $AGENTMAIL_API_KEY" \
  https://api.agentmail.to/v0/inboxes/{inbox_id}
```

---

## Messages

### Send Message

```bash
curl -s -X POST \
  -H "Authorization: Bearer $AGENTMAIL_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "to": ["recipient@example.com"],
    "subject": "Hello",
    "text": "Plain text body"
  }' \
  https://api.agentmail.to/v0/inboxes/{inbox_id}/messages/send
```

**Request body:**
| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `to` | string[] | Yes | Recipient email addresses. |
| `subject` | string | Yes | Email subject line. |
| `text` | string | No | Plain text body. |
| `html` | string | No | HTML body. |
| `cc` | string[] | No | CC recipients. |
| `bcc` | string[] | No | BCC recipients. |

### List Messages

```bash
curl -s -H "Authorization: Bearer $AGENTMAIL_API_KEY" \
  "https://api.agentmail.to/v0/inboxes/{inbox_id}/messages?limit=10"
```

### Get Message

```bash
curl -s -H "Authorization: Bearer $AGENTMAIL_API_KEY" \
  https://api.agentmail.to/v0/inboxes/{inbox_id}/messages/{message_id}
```

### Reply to Message

```bash
curl -s -X POST \
  -H "Authorization: Bearer $AGENTMAIL_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"text": "Reply body here"}' \
  https://api.agentmail.to/v0/inboxes/{inbox_id}/messages/{message_id}/reply
```

### Reply All

```bash
curl -s -X POST \
  -H "Authorization: Bearer $AGENTMAIL_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"text": "Reply all body here"}' \
  https://api.agentmail.to/v0/inboxes/{inbox_id}/messages/{message_id}/reply-all
```

### Forward Message

```bash
curl -s -X POST \
  -H "Authorization: Bearer $AGENTMAIL_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"to": ["forward-to@example.com"], "text": "FYI see below"}' \
  https://api.agentmail.to/v0/inboxes/{inbox_id}/messages/{message_id}/forward
```

---

## Threads

### List Threads

```bash
curl -s -H "Authorization: Bearer $AGENTMAIL_API_KEY" \
  "https://api.agentmail.to/v0/inboxes/{inbox_id}/threads?limit=10"
```

### Get Thread

```bash
curl -s -H "Authorization: Bearer $AGENTMAIL_API_KEY" \
  https://api.agentmail.to/v0/inboxes/{inbox_id}/threads/{thread_id}
```

---

## Agent Inboxes

| Agent | Email | Inbox ID |
|-------|-------|----------|
| Josh (Therapist) | `sps-josh@agentmail.to` | `sps-josh@agentmail.to` |
| Simon (Coach) | `sps-simon@agentmail.to` | `sps-simon@agentmail.to` |
| Marcus (Project Manager) | `sps-marcus@agentmail.to` | `sps-marcus@agentmail.to` |

---

## Notes

- Default domain is `@agentmail.to`. Custom domains require paid plan with DNS setup (SPF, DKIM, DMARC).
- The API supports webhooks for real-time email notifications.
- Messages support attachments.
- Rate limits and pricing details at https://agentmail.to.
