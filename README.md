# Stoat Weekly Gaming Report

Once a week, GitHub Actions builds a short gaming brief and posts it to a Stoat channel.

No RSS.app. No hosted bot. No paid Zapier. The script is in the workflow file where you can read it.

## What the Monday post covers
- **Hot right now** — Steam most-played charts
- **Updates that shipped** — official Steam news from those games (last 7 days)
- **Dropping this week / next week** — RAWG release calendar
- **What people are arguing about** — top `r/Games` posts, labeled as chatter, not reporting

## What you need
- A Stoat channel + webhook (enable **Masquerade**)
- A GitHub account
- A free [RAWG API key](https://rawg.io/apidocs) for the release sections

## Setup

### 1. Create the Stoat webhook
Channel settings → Webhooks → New. Name it `Weekly Gaming Report`. Copy the URL.

### 2. Fork this repo

### 3. Add secrets
Repo → **Settings → Secrets and variables → Actions**

| Secret | Value |
|---|---|
| `STOAT_WEBHOOK_WEEKLY` | Stoat webhook URL |
| `RAWG_KEY` | RAWG API key |

Never put the webhook URL in a yml file.

### 4. Run it
**Actions → Weekly gaming report to Stoat → Run workflow**

After that it runs Mondays at 15:00 UTC. If RAWG is missing, the release sections stay empty and the rest still posts.

## Files
- `.github/workflows/weekly_gaming_report.yml` — the whole job

## Limits
- Steam charts + Steam news are official. They will not cover every indie drop.
- RAWG is a calendar, not a critic.
- Reddit is “what’s loud,” not journalism. The post says that in the message.
- Stoat messages are split if the brief runs long.
- GitHub can delay scheduled jobs by a few minutes.

## Safety
A webhook URL can post to that channel. Rotate it if it ever hits git or a screenshot. Forks do not copy secrets.

## License
[MIT](LICENSE)
