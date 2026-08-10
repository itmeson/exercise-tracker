# Movement Log

A single-file workout tracker. No accounts, no server, no dependencies — one
`index.html` that runs entirely in the browser and keeps its data in
`localStorage`.

**Live site:** https://itmeson.github.io/exercise-tracker/

## What it does

- **Log** — record a day's session: exercises, sets/reps/weight/time by category
  (push, pull, legs, core, cardio, mobility), plus a daily back-pain score
  (0–10) with descriptor tags and free-text notes
- **Streaks** — day streak, weekly and daily entry counts
- **Calendar** — month view of what got done, colour-coded by category
- **Exercises** — manage the exercise library; ships with a seeded default list
- **Data** — summary stats, plus JSON export/import for moving between devices

Import **merges** rather than overwrites: for any given day, whichever version
was edited most recently wins.

## Where your data lives

In your browser's `localStorage`, under the origin serving the page. Two
consequences worth knowing:

1. **Each browser and device is its own silo.** Phone Safari and desktop Chrome
   do not share data. Use Export file → Import file to sync them.
2. **The hosted copy and a local copy are separate.** Data saved while opening
   `index.html` from disk (`file://`) will *not* appear at the github.io URL.
   Export from the old location and import at the new one.

Clearing site data or "clear cookies and site data" wipes the log, so export a
backup periodically. The export lands as `movement-log-YYYY-MM-DD.json`.

## Use on a phone

Open the live URL in Safari or Chrome and add it to your home screen — the page
sets `apple-mobile-web-app-capable`, so it launches chrome-free like an app.
It still needs a network connection on first load; there's no service worker
yet, so it isn't offline-capable.

## Developing

There is no build step. Edit `index.html`, open it in a browser, reload.

To publish a change:

```bash
git add index.html
git commit -m "Describe the change"
git push
```

GitHub Pages redeploys within a minute or so. A hard reload (Ctrl/Cmd+Shift+R)
clears the cached copy if you don't see the change.

## Repository notes

- `.nojekyll` — stops GitHub Pages running the file through Jekyll
- `LICENSE` — MIT

## License

MIT — see [LICENSE](LICENSE).
