# Stoat Weekly Gaming News

Once a week, GitHub Actions builds a short gaming brief and posts it to a Stoat channel.

No RSS.app. No hosted bot. No paid Zapier. The script is in the workflow file where you can read it.

## What the Monday post covers
- **Watchlist + hot on Steam** — games you pin, plus current most-played
- **Official updates** — Steam news from those games (last 7 days)
- **Dropping this week / next week** — RAWG release calendar
- **Gamer convos** — community threads, labeled as chatter, not reporting

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

### 4. Customize games
Edit `.github/workflows/weekly_gaming_report.yml`. At the top of the script:

```python
WATCHLIST = [
    3932890,  # Escape from Tarkov
    1808500,  # ARC Raiders
]
BLACKLIST = {
    431960,   # Wallpaper Engine
}
