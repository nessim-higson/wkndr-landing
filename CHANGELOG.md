# Changelog — WKNDR landing

## Versioning scheme
Each iteration bumps the **minor** by one: `v1.1 → v1.2 → … → v1.20`.
When the minor reaches **20**, roll the **major** and reset: `v1.20 → v2.1 → v2.2 → …`
The current version lives in [`VERSION`](VERSION), is shown in the page footer, and is tagged in git (`v1.2`, etc.).

---

## v1.3 — 2026-06-09
- Replaced the hero's auto-scrolling marquee with a **3D cover flow**: a finite, centered,
  viewport-independent carousel (the marquee's looping seam showed on wide screens because
  the duplicated track didn't fill the width). Center card upright + large; neighbors recede
  in perspective. Auto-advances, pauses on hover, click cards/dots/arrows to navigate.
- Tuned the hero's vertical rhythm so the active card sits in view; cards reordered so no
  two same-weather tiles sit adjacent; narrower cards on mobile so neighbors peek on both
  sides. Works on desktop + mobile.

## v1.2 — 2026-06-09
- Removed the gallery edge-fade overlay entirely. The left/right paper→transparent
  gradients were reading as a translucent "scrim" sitting over the pick-cards; the
  marquee now runs full-saturation to the screen edge.
- Added a version badge to the footer.

## v1.1 — 2026-06-09 — initial build
- Maneken-style landing page for WKNDR (single self-contained `index.html`).
- Floating pill nav, weather-cycling hero (ambient field + chip + CTA rotate through
  the five weather modes), three auto-scrolling rows of weather-tinted pick-cards.
- Sections: how-it-works, dark "Five skies" weather-mode panel, swipe-deck phone
  mockup, 9-category grid, value props, FAQ, CTA band, footer.
- Published to GitHub Pages.
- Fixes folded into this baseline: hero ambient field switched off `multiply`/dark
  palette colour (which muddied the cream into a grey scrim) to `screen` + light
  colours; gallery edge-fade narrowed (later removed in v1.2).
