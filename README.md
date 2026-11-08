# Fitness AI Connector

**Talk to your Garmin data in Claude, ChatGPT and Meta Muse.**

Connect your Garmin health and fitness data to Claude, ChatGPT and Meta Muse through the official Garmin Health API. Hosted remote MCP server (Streamable HTTP) with OAuth 2.0 sign-in — your Garmin password is never shared. Tools cover the daily health summary (sleep, HRV, stress, Body Battery), activities with lap and time-series analysis, original FIT files, body composition, menstrual cycle tracking, trends, workouts sent to your Garmin Connect calendar, and on-demand data refresh. Free tier available.

🌐 Website: https://fmp.it.com/en/fitness-ai/

## How it works

1. Connect the app in ChatGPT (Apps Directory), add the connector in Claude, or set it up from a chat in Meta Muse
2. Sign in on Garmin's own page (OAuth 2.0 + PKCE) — we never see or store your password
3. Ask questions in plain language: "How did I sleep this week?", "Show the details of my latest run", "Am I improving?"

Your Garmin data syncs automatically via the Garmin Health API webhook/pull model. You can disconnect from your Garmin account settings or delete your account at any time; what is deleted and when is described in the privacy policy: https://fmp.it.com/en/fitness-ai/privacy/

## What you can ask

| Area | Examples |
|---|---|
| Daily wellness | Steps, calories, heart rate, sleep stages & score, stress, Body Battery, HRV |
| Activities | Runs, rides, swims with pace, distance, calories, heart rate per activity |
| Activity details | Lap splits, HR drift, pace stability, negative splits, cadence & power stats |
| Body composition | Weight, BMI, body fat %, muscle mass (smart scale required) |
| Menstrual cycle | Cycle phase, day in cycle, fertile window, period tracking (opt-in in Garmin Connect) |
| Workouts | "Make a 400 m × 8 interval session for next Tuesday and send it to Garmin" — sent to your Garmin Connect calendar, then synced to your watch |
| Long-term trends | Weekly averages, directional changes, "am I improving?" comparisons |
| Profile & account | Connection status, VO2max, fitness age, subscription management |

## Tools

- get_user_profile — Garmin connection status, subscription tier, VO2max, and fitness age.
- get_health_summary — Daily snapshot: steps, calories, heart rate, sleep stages & score, stress / Body Battery, HRV. Optional opt-in time series (heart rate, stress, Body Battery, sleep stages, SpO2, respiration).
- get_activities — List activities (runs, rides, swims) with pace, distance, calories, and heart rate per activity.
- get_activity_details — Lap splits, HR drift, pace stability, negative split ratio, cadence and power stats for one activity, plus optional per-second time series.
- get_activity_fit_file — Browser download link for the original Garmin FIT file of one activity (Basic).
- set_activity_visibility — Hide or show activities (duplicates, mistakes) in this service's lists and analysis; nothing is deleted or changed in Garmin Connect.
- get_body_composition — Weight, BMI, body fat %, muscle mass, bone mass, body water % (smart scale required).
- get_cycle_data — Menstrual cycle snapshots: phase, day in cycle, period start, cycle length (predicted vs actual), fertile window, with pregnancy semantics when applicable (cycle tracking must be enabled in Garmin Connect).
- get_trends — Weekly averages, directional changes, and pattern detection ("am I improving?").
- create_workout — Send a structured workout the user asked for to their Garmin Connect calendar so it syncs to the watch (Basic).
- list_workouts — List the workouts this service sent to the Garmin Connect calendar.
- delete_workout — Delete a workout this service created, with its calendar entry.
- refresh_data — Re-fetch a range of Garmin data; dates before your connection date are skipped.
- refetch_activity_detail — Request recovery of a missing activity detail.
- manage_subscription — Link to the billing portal: payment method, invoices, cancellation.
- delete_account — Link to the account deletion confirmation page.
- get_help — Setup, troubleshooting, and billing FAQ answers.
- acknowledge_garmin_source — Garmin brand attribution shown when data is first presented.

## Where to get it

- **ChatGPT**: search "Fitness AI Connector" in the Apps Directory
- **Claude**: add as a custom connector — MCP endpoint: `https://garmin-mcp-nuqd.onrender.com/mcp`
- **Meta Muse**: ask Muse in a chat to set up Fitness AI Connector — see the setup guide on the website
- Details and setup guides: https://fmp.it.com/en/fitness-ai/

## How it compares

There are several ways to connect Garmin data to AI assistants. An honest comparison:

| | Fitness AI Connector | Self-hosted OSS (e.g. garmin_mcp) | Hosted credential-based connectors |
|---|---|---|---|
| Garmin access | Garmin Health API (official developer program) | Unofficial (reverse-engineered) API | Unofficial (reverse-engineered) API |
| Authentication | OAuth on Garmin's page; no password shared | Your Garmin email + password | Your Garmin email + password stored by operator |
| Setup | None (hosted) | Local install (Python/Node) | None (hosted) |
| Works on mobile / web chat | Yes | Desktop only (local process) | Yes |
| Historical data | From connection date onward; Basic can import a Garmin data export (up to 10 years) | Full history | Full history |
| Price | Free tier and a paid plan (see the website) | Free (self-managed) | Free |
| Continuity risk | Contract-backed API | Breaks when Garmin changes internal auth | Breaks when Garmin changes internal auth |

Self-hosted OSS is a great choice for developers who want maximum tool coverage and full local control. Fitness AI Connector is built for people who want a no-setup, no-password-sharing option that works in the ChatGPT, Claude and Meta Muse apps, backed by the Garmin Health API.

## Privacy & security

- OAuth 2.0 with PKCE; Garmin credentials are never seen or stored by us
- Account and data deletion, and how long data is kept: see the privacy policy
- Privacy policy: https://fmp.it.com/en/fitness-ai/privacy/ · Terms: https://fmp.it.com/en/fitness-ai/terms/

## Support

- Email: contact@fmp.it.com
- Website: https://fmp.it.com

---

*Connects to Garmin Connect™ through the Garmin Health API. Garmin, the Garmin logo, and Garmin Connect are trademarks of Garmin Ltd. or its subsidiaries. This project is not affiliated with, endorsed, or sponsored by Garmin.*
