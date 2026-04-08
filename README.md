# London Bus Destination Blind

> A faithful browser simulation of the iconic London bus destination blind, zero dependencies.

![screenshot](screenshots/readme.png)

---

## :bulb: About

This is a single-file web app that recreates the destination blind found on London buses — the black-and-white mechanical roller blind  Navigate real London destinations with keyboard, mouse wheel, touch swipe, or click-drag. No frameworks, no build step, just open `index.html`.

---

## :sparkles: Features

- **Classic roller blind** — cream text on black, vignette shadow, authentic proportions
- **London destinations** — including a "NOT IN SERVICE" entry
- **Multi-input navigation** — ← → arrow keys, on-screen buttons, mouse wheel, touch swipe, click-drag
- **Accessible** — `aria-live` region announces each destination change for screen readers
- **Responsive** — scales to any viewport at a fixed aspect ratio using `clamp()` fluid type
- **Zero dependencies** — single HTML file, no npm, no build toolchain

---

## :computer: Running locally

No server needed — just open the file in any modern browser

---

## :wrench: Customising destinations

Edit the `DESTINATIONS` array near the top of the `<script>` block in `index.html`:

```js
{ route: '19', destination: 'Finsbury Park', via: '' },
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

</details>

<details>
<summary>Accessibility</summary>

An `aria-live="polite"` region outside the visual blind reads each new destination aloud to screen reader users without interrupting their flow.

</details>
