# London Bus Destination Blind

> A faithful browser simulation of the iconic London bus destination blind — classic roller and modern LED matrix, zero dependencies.

![screenshot](screenshot.png)

---

## :bulb: About

This is a single-file web app that recreates the destination blind found on London buses — the black-and-white mechanical roller blind and its modern amber LED matrix successor. Navigate 25 real London routes with keyboard, mouse wheel, touch swipe, or click-drag. No frameworks, no build step, just open `index.html`.

---

## :sparkles: Features

- **Classic roller blind** — cream text on black, vignette shadow, authentic proportions
- **LED matrix mode** — amber phosphor glow with stepped strobe-refresh animation
- **25 real London routes** — including Night Bus (N prefix) and a "NOT IN SERVICE" entry
- **Multi-input navigation** — ← → arrow keys, on-screen buttons, mouse wheel, touch swipe, click-drag
- **Direction-aware animation** — forward slides up, backward slides down
- **Accessible** — `aria-live` region announces each destination change for screen readers
- **Responsive** — scales to any viewport at a fixed aspect ratio using `clamp()` fluid type
- **Zero dependencies** — single HTML file, no npm, no build toolchain

---

## :computer: Running locally

No server needed — just open the file in any modern browser:

```bash
open index.html   # macOS
start index.html  # Windows
```

---

## :rocket: Deploying to GitHub Pages

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Under **Source**, choose **Deploy from a branch**.
4. Select branch `main` and folder `/ (root)`, then click **Save**.
5. Live at `https://<your-username>.github.io/<repo-name>/` within a minute.

---

## :wrench: Customising destinations

Edit the `DESTINATIONS` array near the top of the `<script>` block in `index.html`:

```js
{ route: '73', destination: 'VICTORIA COACH STATION', via: 'via Marble Arch, Hyde Park Corner' },
```

Set `route: ''` for a "NOT IN SERVICE" entry.

---

## :toolbox: Tech stack

| Layer | Technology |
|---|---|
| Markup | HTML5 with semantic ARIA |
| Styling | CSS3 — custom properties, `clamp()`, keyframe animations |
| Logic | Vanilla ES6+ JavaScript |
| Typography | [Jost](https://fonts.google.com/specimen/Jost) (Google Fonts) — closest free substitute for TfL's New Johnston |
| Build | None — static single file |

---

## :art: Design notes

<details>
<summary>Typography</summary>

TfL uses **New Johnston** as its official typeface, which is proprietary. This simulator substitutes [Jost](https://fonts.google.com/specimen/Jost), falling back to Gill Sans and system-ui.

</details>

<details>
<summary>Animation system</summary>

Two animation pairs handle direction-aware transitions:

- **Forward** — destination exits upward (`leaving`), next enters from below (`entering`)
- **Backward** — destination exits downward (`leaving-reverse`), previous enters from above (`entering-reverse`)

LED mode replaces the slide with a `steps()` strobe effect to simulate matrix refresh.

</details>

<details>
<summary>Accessibility</summary>

An `aria-live="polite"` region outside the visual blind reads each new destination aloud to screen reader users without interrupting their flow.

</details>
