# 🚂 Amtrak Tracker

A live Amtrak train tracker that shows your train's position on a map, upcoming station stops with arrival times and delay info, and a breadcrumb echo trail of where it's been.

---

## Using the App

1. Enter a train number in the header (e.g. `3`, `5`, `49`) and press **Track** or hit Enter.
2. Pick a refresh rate — **5m**, **10m**, or **15m** — to control how often the position updates.
3. The map shows the train's current location with a directional arrow, plus faded echo markers from previous polling positions.
4. The right panel lists upcoming stations with scheduled and actual arrival/departure times and delay badges.
5. Switch themes with the buttons in the top-right: **Dark**, **Retro** (orange), **Phosphor** (green), or **DOS**.

Popular train numbers to try:

| # | Route |
|---|-------|
| 3 | Southwest Chief (Chicago → LA) |
| 5 | California Zephyr (Chicago → SF) |
| 49 | Lake Shore Limited (Chicago → NYC) |
| 91 | Silver Star (NYC → Miami) |

---

## Tech Stack

A single self-contained HTML file — no build step, no bundler, no dependencies to install.

- **React 18** — loaded via CDN UMD build; UI state and component rendering
- **Babel Standalone** — in-browser JSX transpilation via `<script type="text/babel">`
- **Leaflet 1.9** — interactive map with CartoDB Dark Matter tiles
- **Vanilla fetch** — direct browser calls to the Amtraker REST API; no backend needed

---

## API

Train data is provided by **Amtraker v3**, an unofficial open-source wrapper around Amtrak's internal train-tracking feed.

- API: `https://api-v3.amtraker.com/v3/`
- Source: [github.com/piemadd/amtrak](https://github.com/piemadd/amtrak) by [@piemadd](https://github.com/piemadd)

---

## Deploying to Vercel

The app is a single static file and deploys in seconds.

**Option 1 — CLI**
```bash
npm i -g vercel
vercel
```

**Option 2 — GitHub**
1. Push to a GitHub repo with the file named `index.html`
2. Import the repo at [vercel.com/new](https://vercel.com/new)
3. No build settings needed — Vercel detects it as a static site automatically

Every `git push` to `main` triggers a redeploy.

## Development

Vibe-coded by Claude Sonnet 4.6