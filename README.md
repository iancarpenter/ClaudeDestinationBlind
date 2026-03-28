# London Bus Destination Blind

A single-page web app that simulates a London bus destination blind — the classic roller blind (white text on black) and the modern LED matrix display.

![screenshot](screenshot.png)

## Features

- **Classic roller blind** — black background, white Jost/Gill Sans text, fabric texture, vignette edges
- **LED matrix mode** — amber dot-matrix glow with strobe-refresh animation
- **Auto-advance** — destinations cycle every 4 seconds; hover to pause
- **Manual navigation** — ← → arrow keys or on-screen buttons
- 13 real London routes including Night Bus (N prefix) and a "NOT IN SERVICE" entry
- Responsive — scales to any screen size at a 16:5 aspect ratio
- Accessible — `aria-live` region announces each destination change
- Zero dependencies — single HTML file, no build step

## Running locally

Just open `index.html` in a browser. No server required.

## Deploying to GitHub Pages

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Under **Source**, choose **Deploy from a branch**.
4. Select branch `main` and folder `/ (root)`, then click **Save**.
5. Your blind will be live at `https://<your-username>.github.io/<repo-name>/` within a minute.

## Customising destinations

Edit the `DESTINATIONS` array near the top of the `<script>` block in `index.html`:

```js
{ route: '73', destination: 'VICTORIA COACH STATION', via: 'via Marble Arch, Hyde Park Corner' },
```

Set `route: ''` for a "NOT IN SERVICE" entry.

## Font

Uses [Jost](https://fonts.google.com/specimen/Jost) (Google Fonts) as the closest freely available substitute for New Johnston, TfL's official typeface. Falls back to Gill Sans, then system-ui.
