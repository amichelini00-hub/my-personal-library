# My Personal Library

A personal book library, wishlist, and barcode-scanner app that syncs with a Google Sheet. Works in any browser — phone, tablet, or desktop.

## One-time setup

1. **Deploy the Google Apps Script** (if you haven't already): open your Apps Script project at [script.google.com](https://script.google.com), paste in `GoogleAppsScript.gs`, set `SPREADSHEET_ID` at the top to your actual Google Sheet's ID, then **Deploy → New deployment → Web app**, with access set to "Anyone". Copy the `/exec` URL it gives you.
2. **Open the site** (see deployment below) and go to **Settings**, then paste your `/exec` URL into the sync field and save. It's stored only in your browser (`localStorage`), never in this repo.

## Deploying this site with GitHub Pages

This is a static site (`index.html` + `app.js`), so GitHub Pages can host it for free:

1. Create a new **public** GitHub repository (Pages on the free plan requires public).
2. Upload all the files in this folder to the repo (drag-and-drop on the GitHub website works fine, no command line needed).
3. In the repo, go to **Settings → Pages**, set Source to the `main` branch and `/ (root)`, and save.
4. GitHub gives you a URL like `https://yourusername.github.io/your-repo-name/` — that's your library, on any device.

## Notes

- `seed.js` is only used to bootstrap a brand-new browser/device before it's ever synced — once you set your webhook URL, your live Google Sheet is always the source of truth.
- Because this repo is public, don't commit real Google Apps Script `/exec` URLs or spreadsheet IDs into any file — they're left blank/placeholder in this repo on purpose.
