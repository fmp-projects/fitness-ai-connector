# Fitness AI Connector

**Talk to your Garmin data in Claude and ChatGPT.**

Fitness AI Connector links your Garmin health and fitness data to AI assistants. It is a hosted MCP (Model Context Protocol) server built on the Garmin Health API with OAuth sign-in — **your Garmin password is never shared**, and access can be revoked anytime from your Garmin account. No local setup required; works on web and mobile.

🌐 Website: https://fmp.it.com/en/fitness-ai/

## How it works

1. Connect the app in ChatGPT (Apps Directory) or add the connector in Claude
2. Sign in on Garmin's own page (OAuth 2.0 + PKCE) — we never see or store your password
3. Ask questions in plain language: "How did I sleep this week?", "Show the details of my latest run", "Am I improving?"

Your Garmin data syncs automatically via the Garmin Health API webhook/pull model. You can disconnect from your Garmin account settings or delete all data at any time.

## What you can ask

| Area | Examples |
|---|---|
| Daily wellness | Steps, calories, heart rate, sleep stages & score, stress, Body Battery, HRV |
| Activities | Runs, rides, swims with pace, distance, calories, heart rate per activity |
| Activity details | Pace zones, HR zone distribution, lap splits, HR drift, training effect |
| Body composition | Weight, BMI, body fat %, muscle mass (smart scale required) |
| Long-term trends | Weekly averages, directional changes, "am I improving?" comparisons |
| Profile & account | Connection status, VO2max, fitness age, subscription management |

## Where to get it

- **ChatGPT**: search "Fitness AI Connector" in the Apps Directory (works with Free ChatGPT accounts via our Custom GPT as well)
- **Claude**: add as a custom connector — MCP endpoint: `https://garmin-mcp-nuqd.onrender.com/mcp`
- Details and setup guides: https://fmp.it.com/en/fitness-ai/

## How it compares

There are several ways to connect Garmin data to AI assistants. An honest comparison:

| | Fitness AI Connector | Self-hosted OSS (e.g. garmin_mcp) | Hosted credential-based connectors |
|---|---|---|---|
| Garmin access | Garmin Health API (official developer program) | Unofficial (reverse-engineered) API | Unofficial (reverse-engineered) API |
| Authentication | OAuth on Garmin's page; no password shared | Your Garmin email + password | Your Garmin email + password stored by operator |
| Setup | None (hosted) | Local install (Python/Node) | None (hosted) |
| Works on mobile / web chat | Yes | Desktop only (local process) | Yes |
| Historical data | From connection date onward (Garmin API policy) | Full history | Full history |
| Tool count | 10 focused tools | Up to 110+ tools | Varies |
| Price | Free tier; Basic $3/month | Free (self-managed) | Free |
| Continuity risk | Contract-backed API | Breaks when Garmin changes internal auth | Breaks when Garmin changes internal auth |

Self-hosted OSS is a great choice for developers who want maximum tool coverage and full local control. Fitness AI Connector is built for people who want a no-setup, no-password-sharing option that works in the ChatGPT and Claude apps, backed by the Garmin Health API.

## Privacy & security

- OAuth 2.0 with PKCE; Garmin credentials are never seen or stored by us
- Data deletion on request with a 30-day recovery window; automated purge afterwards
- Privacy policy: https://fmp.it.com/en/fitness-ai/privacy/ · Terms: https://fmp.it.com/en/fitness-ai/terms/

## Support

- Email: contact@fmp.it.com
- Website: https://fmp.it.com

---

*Connects to Garmin Connect™ through the Garmin Health API. Garmin, the Garmin logo, and Garmin Connect are trademarks of Garmin Ltd. or its subsidiaries. This project is not affiliated with, endorsed, or sponsored by Garmin.*
