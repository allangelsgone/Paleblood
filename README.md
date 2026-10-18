# Paleblood — Bloodborne ending tracker

A checklist app for the three endings of Bloodborne. Pick an ending and tick off each step in play order. For Childhood's Beginning it tracks the One Third of Umbilical Cord you've found (3 of 4 needed). Tap a step for details and wiki links. Progress is saved in the browser.

Steps are based on the [Bloodborne Wiki Endings page](https://bloodborne.wiki.fextralife.com/Endings).

## Files
- `index.html` – the app
- `support.js` – runtime (must sit next to index.html; generated, don't edit)
- `vendor/` – React 18.3.1, served locally so the app doesn't depend on a CDN (see `vendor/README.md`)
- `manifest.json` – web app manifest
- `apple-touch-icon.png`, `icon-512.png`, `icon-1024.png`, `favicon.png` – icons

## GitHub Pages
1. Upload all files, including the `vendor/` folder, to the repo root.
2. Settings → Pages → Deploy from branch → `main` / root.
3. Open `https://<user>.github.io/<repo>/` in Safari → Share → Add to Home Screen.

## Notes
- The footer on the start screen shows the app version. If your phone still shows an older number after an update, close the app and open it again; browsers cache the files for a few minutes.
- `index.html` points the runtime at the local React copies through the `window.__resources` script in its `<head>`. If you re-export `index.html` from the design tool, keep that script, otherwise the app falls back to loading React from unpkg.com.
- Progress is stored in the browser's `localStorage` under `paleblood-endings-v1`.
