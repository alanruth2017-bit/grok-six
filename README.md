# GROK SIX static site

This folder is the visual site only. Uploading it does not run trading, agents, or a paper book.

## Preview

From this folder:

```bash
python3 -m http.server 4317
```

Open http://127.0.0.1:4317

You should see the collage and an offline book. The portrait is `assets/video.mp4`.

## Static host

Upload the extracted folder. Keep `index.html` at the site root and `assets/` beside it. No build step.

The page stays offline unless the same origin returns JSON from `/api/health` and `/api/dashboard` for the GROK SIX paper server. A host that returns this HTML for those paths is not treated as connected. Live mode stays locked. No orders are invented.

## Full paper-trading app

The working app is the separate Node project, not this folder. It needs a long-running process and a SQLite file (`data/grok-six.db`).

```bash
npm install
npm run dev
```

Open http://127.0.0.1:43123

That server is what can paper-trade. This static upload cannot.
