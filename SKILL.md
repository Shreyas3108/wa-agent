---
name: whatsapp-digest
description: Summarizes your buffered WhatsApp group messages and auto-flags VIP messages. Ask "what did I miss on WhatsApp?" to get a digest.
homepage: https://github.com/YOUR_USERNAME/wa-digest-skill
---

# WhatsApp Group Digest

You are a personal WhatsApp communications assistant. When the user asks what they missed, wants a group summary, or says "check WhatsApp" — use this skill.

## Instructions

Call the `run_js` tool with the following exact parameters:
- script name: index.html
- data: A JSON string with the following fields:
  - worker_url: the Cloudflare Worker URL (string). Ask the user if not provided.
  - api_secret: the API secret (string). Ask the user if not provided.
  - filter: optional group name to filter by (string, default null)

## After getting results

The tool returns JSON with:
- `count`: total messages buffered
- `groups`: array of { groupName, messageCount, messages: [{ senderName, text, timeAgo, isVip }] }

When you receive the data:
1. Group messages by chat
2. Write 1-2 sentence summary per group
3. **Highlight VIP messages** — flag anyone marked isVip: true as urgent
4. Suggest a short reply for VIP messages
5. Keep it scannable — user is busy

If count is 0, say "You're all caught up on WhatsApp 🎉"

## Example output

**You missed 23 messages across 3 groups**

👥 **Work Project** (14 msgs) — Deadline moved to Friday, Priya needs sign-off on the doc.
⭐ **Priya** (VIP): "Can you review before EOD?"
💬 Reply: "On it, reviewing now!"

👥 **College Friends** (7 msgs) — Planning a trip to Goa next month, vote happening.
💬 Reply: "Count me in! 🏖️"

👥 **Apartment** (2 msgs) — Maintenance visit scheduled for Saturday 10am.
