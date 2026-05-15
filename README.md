# Chart Rewind

Browse every Billboard Hot 100 chart from 1958 to today. Jump to any era, walk week by week, and save any week's Top 50 directly to Spotify.

## Features

- **Every chart since 1958** — 3,000+ weeks of data
- **Album art** loaded automatically for every song
- **Era theming** — the UI shifts color palette by decade (neon for the 80s, teal for the 90s, etc.)
- **Cinematic hero** — the #1 song gets a full-width blurred backdrop with its cover art
- **Prev / Next navigation** — walk week by week, or use ← → arrow keys
- **Decade quick-jump** — 60s through 20s buttons
- **Date picker** — jump to any specific date
- **URL routing** — every week is shareable (e.g. `#1987-09-05`)
- **Spotify Top 50 Playlist** — create a playlist from any week in one click

## Spotify Setup (one-time)

To use the "＋ Top 50 Playlist" button you need a free Spotify Developer app.

### 1. Create a Spotify Developer app

1. Go to [developer.spotify.com/dashboard](https://developer.spotify.com/dashboard)
2. Log in and click **Create app**
3. Give it any name (e.g. "Chart Rewind"), tick **Web API**, accept terms
4. In **Settings → Redirect URIs**, add your app URL:
   - GitHub Pages: `https://macmenes.github.io/chart-rewind/`
   - Local: `http://localhost:8000/`
5. Copy your **Client ID** (32-character hex string)

### 2. Connect in the app

1. Open the app and click **＋ Top 50 Playlist** on any chart
2. Paste your Client ID when prompted
3. Authorize with Spotify — you're redirected back automatically
4. The playlist is created in your Spotify account

The Client ID and access token are stored in your browser's `localStorage`. You won't be asked again unless the token expires.

## Running locally

Since Spotify OAuth requires HTTP/HTTPS (not `file://`), serve the app with any static server:

```bash
cd chart-rewind
python3 -m http.server 8000
# then open http://localhost:8000
```

Or with Node:
```bash
npx serve .
```

## Data source

Chart data from [mhollingshead/billboard-hot-100](https://github.com/mhollingshead/billboard-hot-100) — a complete archive of every Billboard Hot 100 chart served directly from GitHub's CDN.

Album art from the iTunes Search API (no key required).
