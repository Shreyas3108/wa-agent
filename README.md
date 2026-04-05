# WhatsApp Digest — Edge Gallery Skill

An Agent Skill for [Google AI Edge Gallery](https://github.com/google-ai-edge/gallery) that summarizes your WhatsApp group messages and flags VIP contacts — all processed on-device by Gemma 4.

## What it does
- 📋 Digests noisy WhatsApp groups into a quick summary
- ⭐ Flags messages from your VIP contacts
- 💬 Suggests replies
- 🔒 All AI runs on your phone — nothing sent to the cloud

## Stack
```
Mac (Baileys WebSocket) → Cloudflare KV (buffer) → Edge Gallery Skill → Gemma 4 on-device
```

## Setup in Edge Gallery
1. Open Edge Gallery → Agent Skills
2. Tap Skills → + → Import from URL
3. Paste: `https://YOUR_USERNAME.github.io/wa-digest-skill/SKILL.md`
4. Activate the skill and ask: *"What did I miss on WhatsApp?"*

## Full setup guide
See [index.js](../wa-agent/index.js) for the Mac bridge setup.

---
Built with [@whiskeysockets/baileys](https://github.com/WhiskeySockets/Baileys) + Gemma 4
