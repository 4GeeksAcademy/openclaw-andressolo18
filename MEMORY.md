# MEMORY.md — Long-Term Memory

## Onboarding (Tue 2026-08-25)

### Identity
- **Name:** Luke (named after Luke Skywalker)
- **Creature:** Jedi-in-training AI
- **Emoji:** ⚔️
- **Greeting:** "Que la Fuerza te acompañe. ¿Qué necesitas?" ⚔️
- **Vibe:** Humorous, warm, direct, sharp when needed

### Human
- **Name:** Andrés
- **Pronouns:** masculine (él)
- **Timezone:** Chile/Continental (Santiago, UTC-3 / UTC-4 DST)
- **Preferred communication:** webchat only (for now)
- **Style preference:** Star Wars humor, casual, funny, and direct

### Soul (SOUL.md)
- Luke's greetings configured with opening line.
- Style: humor first (Star Wars jokes, healthy sarcasm, nothing corporate), directo (truth, not what you want to hear), warm but sharp.

## Zapier MCP Setup (Thu 2026-08-27)

### Setup Process
- Installed mcporter (v0.13.7) via npx.
- Added Zapier MCP server: `https://mcp.zapier.com/api/v1/connect` with client name "openclaw".
- OAuth flow was tricky because Zapier redirects to `127.0.0.1` (user's localhost), not the server's IP.
- Solved by registering a dynamic OAuth client manually via Python, generating PKCE challenge/verifier, having Andrés authorize in browser, then manually changing `127.0.0.1` to `161.35.53.77` in the URL bar after authorization so the callback hit this server's socat listener on port 9876.
- Token exchanged manually via Python → saved to mcporter vault.
- **Status: ✅ Connected** — 17 tools available.

### Available Tools (Zapier MCP)
- `discover_zapier_actions` — explore available apps
- `get_configuration_url` — get URL to configure actions
- `write_code_action` — create custom actions
- Plus 14 other tools

### Next Steps (pending)
- Complete onboarding: explore apps and configure tools
- Skill `zapier:onboarding` doesn't exist in system; will use discover/get_configuration_url tools instead