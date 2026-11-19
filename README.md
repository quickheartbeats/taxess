# DebtFree PWA

A private offline-first liabilities tracker built with HTML, CSS and JavaScript, with no backend and no external dependencies.

## Run locally

From this folder, run `python -m http.server 8000`, then visit `http://localhost:8000`.

## Install on Android

Host the files on a static HTTPS host (e.g. GitHub Pages, Cloudflare Pages, Netlify), open the URL in Chrome and select **Install app** or **Add to Home screen**. Static hosting is enough: no backend server is required. After the first visit, the service worker caches the app for offline use.

## Storage

Data is saved in browser localStorage, and is not synced. Export backups from Settings regularly. Clearing site data or using a different browser/device loses access unless a backup is imported.

## Calculations

Remaining payments are calendar occurrences of the configured payment day up to the end date, including today. Months without that day use the last day of the month. Progress is time-based from the date the liability was added and is not a measure of the original loan principal repaid. Payment recording reduces remaining balance, but does not alter the end date or the scheduled monthly amount. For loans with interest, the remaining balance should be the balance that the user wishes to track; the app does not calculate interest or fees.

## Files

- `index.html`: app layout and forms
- `style.css`: mobile-first styling
- `app.js`: storage, rendering and calculations
- `sw.js`: offline caching
- `manifest.webmanifest`: install metadata
- `icon.svg`: app icon
