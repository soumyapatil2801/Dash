# Collab Ledger — iOS Home Screen App

This is your Collab Ledger app packaged as an installable web app (PWA) for iPhone.
No App Store needed — just Safari.

## Files in this folder
- `index.html` — the app itself
- `manifest.json` — tells iOS/Android this is an installable app
- `service-worker.js` — caches the app so it loads and works offline
- `icons/` — home screen icons

## Step 1: Host the files (recommended, ~2 minutes, free)
For the smoothest "install once, works offline forever" experience, put these
4 items (index.html, manifest.json, service-worker.js, icons/) on any free static
host. All of these work with zero server setup:

- **Netlify Drop** — go to https://app.netlify.com/drop and drag this folder in.
  You get a live https link instantly, no account required for a first deploy.
- **GitHub Pages** — push this folder to a GitHub repo, enable Pages in repo
  Settings → Pages.
- **Vercel / Cloudflare Pages** — similar drag-and-drop or git-based deploy.

Once hosted, open the https link in **Safari on your iPhone**.

## Step 2: Add to Home Screen
1. Open the link in Safari (must be Safari, not Chrome — Chrome on iOS can't install home screen apps).
2. Tap the **Share** button (square with an arrow, bottom of screen).
3. Scroll down and tap **Add to Home Screen**.
4. Tap **Add**.

You'll now have a "Collab Ledger" icon on your home screen. Opening it launches
full-screen, with no Safari address bar — just like a native app.

## Offline behavior
The first time you open the installed app (with internet on), it silently
caches everything it needs. After that, it will open and work fully even in
Airplane Mode. All your collab and expense entries are saved locally on your
phone (in the app's storage), so they stay put between sessions.

## Don't want to host it anywhere?
You can also just AirDrop / email the `index.html` file to your iPhone, open
it in Safari via the Files app, and tap Share → Add to Home Screen the same
way. It'll work and your data will still save locally — the only thing you'll
lose is the offline service-worker caching step (which barely matters here,
since the app doesn't call any external service except loading its fonts).

## Updating the app later
If you ever want to tweak colors, categories, or fields, just edit
`index.html` directly (it's a single self-contained file — search for
`CATEGORIES` to change expense categories, or the `<style>` block at the top
for colors) and re-deploy/re-share it the same way.
