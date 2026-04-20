# Robbo — Productivity Tracker

A tiny offline-first PWA for tracking ~10 daily habits. Tick tasks, watch your daily score, and see past days color-coded on a calendar.

## Features

- 10 default daily tasks (fully editable in Settings)
- Live percentage score with color ring (red → yellow → green)
- Monthly calendar view; each day cell colored by completion %
- Tap any past day to see what got ticked
- Export / Import your full history as JSON
- Works offline — install to your home screen
- All data stored locally on your device (`localStorage`)

## How to use it on your phone

The simplest path is to host the files somewhere your phone can reach (any static host: GitHub Pages, Netlify, Cloudflare Pages, etc.) over HTTPS, then:

1. Open the URL in Safari (iOS) or Chrome (Android)
2. iOS: tap **Share → Add to Home Screen**
   Android: tap **⋮ menu → Install app / Add to Home Screen**
3. Launch from the home-screen icon — runs full-screen, no browser chrome

### Local testing

Open a terminal in this folder and run any static server, then visit it on your phone over the same Wi-Fi:

```sh
python3 -m http.server 8080
```

Then on your phone visit `http://<your-computer-ip>:8080`.
(Note: service worker / install prompt requires HTTPS or `localhost` — for full PWA behavior, host on HTTPS.)

## Data

Stored in `localStorage` under the key `robbo.v1`. Persists across reboots and app launches. Cleared only if you:

- Use the **Erase All Data** button
- Manually clear browser data for the site
- Uninstall the home-screen app **and** clear browser cache

Use the **Export Data** button regularly if you care about your history.

## Files

- `index.html` — the entire app (HTML/CSS/JS)
- `manifest.json` — PWA metadata
- `sw.js` — service worker for offline use
- `icon.svg` — app icon
