# Rv19 Fergeavganger

A mobile-first Progressive Web App (PWA) for checking real-time ferry departures on the Rv19 route (Horten ↔ Moss) operated by Torghatten.

## Features

- Next 5 departures in real-time from Entur JourneyPlanner API
- Color-coded countdown (green → yellow → red as departure nears)
- Direction toggle: Horten→Moss / Moss→Horten
- Auto-detects nearest port using device GPS
- Service messages and deviations fetched from Torghatten
- Arrival time at destination shown on each card
- Auto-refreshes every 60 seconds
- Installable as a home screen app on iPhone (Safari → Share → Add to Home Screen)

## Install on iPhone

1. Open the deployed URL in **Safari**
2. Tap the **Share** button
3. Tap **Add to Home Screen**

The app will appear as a standalone icon and open without browser chrome.

## Local development

No build step required — it's a single HTML file.

```bash
npx serve .
```

Then open [http://localhost:3000](http://localhost:3000).

## Deployment

The app is deployed via GitHub Pages from the `main` branch automatically on every push.

The live URL will be:
```
https://<your-username>.github.io/<repo-name>/
```

## Data sources

| Source | What |
|--------|------|
| [Entur JourneyPlanner v3](https://api.entur.io/journey-planner/v3/graphql) | Real-time departure times |
| [Torghatten deviations page](https://www.torghatten.no/en/our-routes/deviations) | Service messages and deviations |

Stop IDs:
- Horten ferjekai: `NSR:StopPlace:18699`
- Moss ferjekai: `NSR:StopPlace:58092`

## Files

```
ferry-pwa/
├── index.html      # App shell + all logic
├── manifest.json   # PWA manifest
├── sw.js           # Service worker (offline shell caching)
├── background.png  # Background illustration
└── README.md
```
