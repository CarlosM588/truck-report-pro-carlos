# Truck Report Pro - Home-Screen Launcher

This tiny page exists for ONE reason: to put the **Truck Report Pro icon** on your
iPhone home screen.

## Why this page has to exist

The dashboard is a Google Apps Script web app. Google serves it inside a locked
frame (an iframe) that we don't control. When iOS "Add to Home Screen" looks for an
icon, it reads **Google's outer frame**, and Google gives us no way to put an icon
there. So the icon can't be set from the dashboard code itself.

This launcher is a normal web page **we** control. It holds the icon and instantly
forwards to the real dashboard. You add THIS page to your home screen, iOS reads the
icon from it, and tapping it opens the exact same app.

## What's in this folder

| File | Purpose |
|------|---------|
| `index.html` | The launcher. Holds the icon tags + auto-forward to the dashboard. |
| `apple-touch-icon.png` | 180x180 - the icon iOS puts on the home screen. |
| `icon-512.png` / `icon-192.png` | Larger icons (Android / browser tab / on-page logo). |
| `favicon-32.png` | Small browser-tab favicon. |
| `icon-1024.png` | Full-size master copy (App Store / future use). |

## Put it live on GitHub Pages (no command line needed)

1. Go to **github.com** → top-right **+** → **New repository**.
   - Name: `trp-launcher`  (any name works; keep it short)
   - Visibility: **Public**  (Pages is free on public repos)
   - Click **Create repository**.
2. On the new repo page, click **"uploading an existing file"**.
   - Drag in **every file in this folder** (`index.html` + all 5 `.png` files).
   - Click **Commit changes**.
3. Go to **Settings → Pages** (left sidebar).
   - Under "Source" pick **Deploy from a branch**.
   - Branch: **main**, folder: **/ (root)** → **Save**.
4. Wait about a minute. The page shows a green link like:
   `https://YOURNAME.github.io/trp-launcher/`
   That is your launcher URL.

## Add it to the iPhone home screen

1. On the iPhone, open **Safari** (must be Safari, not Chrome) and go to the
   `https://YOURNAME.github.io/trp-launcher/` URL.
2. It will flash the Truck Report Pro logo, then open your dashboard. Good.
3. Go **back** to the launcher URL (or just re-type it), then tap the **Share**
   button → **Add to Home Screen**.
4. The preview should now show the **new truck icon**. Tap **Add**.
5. Delete your old "TruckReport Pro" bookmark so only the new one remains.

## Reusing this for the Master template / one-click customers

The launcher is not tied to the Carlos sheet. To point it at a different deployment
(the Master template, or a one-click buyer's app):

1. Copy this whole folder.
2. Open `index.html` and change **only** the `TARGET_URL` line (near the top of the
   `<script>`) AND the fallback link at the bottom to that deployment's `/exec` URL.
3. Host it the same way (its own repo, or a subfolder in an existing repo).

The icon files stay the same for every customer.
