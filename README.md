# Iron Log — deploy in ~10 minutes

Iron Log is a standalone PWA: 5 static files, no build step, no backend.
It needs HTTPS hosting (required for the Home Screen install + offline mode).

## Files
- index.html          — the entire app (UI, database layer, training engine, coach)
- manifest.webmanifest — makes it installable as an app
- sw.js               — offline caching (opens instantly at the gym, even with bad signal)
- icon-512.png, icon-192.png, icon-180.png — app icons

## Option A — GitHub Pages (recommended, free, permanent URL)
1. Go to github.com → New repository → name it `ironlog` → Public → Create.
2. Click "uploading an existing file" and drag in all 6 files → Commit.
3. Repo → Settings → Pages → Source: "Deploy from a branch" → Branch: main, folder: / (root) → Save.
4. Wait ~1 minute. Your app is live at:
   https://YOUR-USERNAME.github.io/ironlog/
5. Updating later: just upload a new index.html over the old one.

## Option B — Netlify Drop (fastest: drag and drop)
1. Go to app.netlify.com/drop (free account).
2. Drag the whole ironlog folder onto the page.
3. It gives you a URL like https://something.netlify.app — done.

## Install on your iPhone
1. Open the URL in **Safari** (must be Safari, not Chrome).
2. Share button → **Add to Home Screen** → Add.
3. Tap the barbell icon: Iron Log opens full screen, no browser chrome, works offline.

## Turn on the AI coach (one-time, on your phone)
1. console.anthropic.com → API Keys → Create Key → copy it.
2. In Iron Log → Coach tab → paste the key → Save.
The key is stored ONLY in your phone's browser storage — it is never in the
hosted files, so the public URL exposes nothing. Each coach chat costs well
under a cent. Everything except the Coach tab works with no key at all.

## Your data
All workout history lives in your phone's local storage under the app's URL.
- Back up: History tab → Export backup (saves a JSON file).
- Restore / move phones: History tab → Import backup.
- Don't clear Safari website data for this site without exporting first.
