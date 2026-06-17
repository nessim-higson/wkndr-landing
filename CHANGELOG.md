# Changelog — WKNDR landing

## Versioning scheme
Each iteration bumps the **minor** by one: `v1.1 → v1.2 → … → v1.20`.
When the minor reaches **20**, roll the **major** and reset: `v1.20 → v2.1 → v2.2 → …`
The current version lives in [`VERSION`](VERSION), is shown in the page footer, and is tagged in git (`v1.2`, etc.).

---

## v1.8 — 2026-06-17 — matching becomes the story; cards match the app
- **Added a prominent Match section** — WKNDR's social hook. Reproduces the app's signature
  "It's a match" slam (You + partner avatars, sparkle, the shared pick card "you both want to
  go here") next to "Swipe together. Match. Go." + a 3-step how-to. This was missing entirely.
- **Rebalanced the positioning** away from "we train an algorithm on your taste" and
  "weather is the whole thesis" → swipe + match lead; weather is one smart input (kept the
  weather-engine section, softened the claims). Hero sub + how-it-works + value props rewritten.
- **Cards now match the real app front exactly** — dropped the category eyebrow + venue I'd
  added; the front is just the frosted when-stamp, one signal pill, and the title (fixes the
  cramped small bento tiles too). Venue/source still live in the list rows.
- **Sources are now a scrolling ticker** (full-bleed marquee, edge-faded, pause on hover)
  instead of a static row.

## v1.7 — 2026-06-17 — swipe-first rebuild on the real app UI
- Rebuilt the site around WKNDR's **actual app UI** (tokens, Card, SwipeStack, ListView
  lifted from `~/Code/wkndr/app/src`): Clash Display + Helvetica, paper/ink/accent tokens,
  film-grain overlay, the real image-led card (frosted "when" ticket-stamp, one signal pill,
  category eyebrow, title over scrim).
- **Hero now leads with the swipe mechanic** (chosen direction C, editorial split): a fully
  **interactive, draggable swipe deck** reproducing the app physics in vanilla JS — tilt,
  red/green wash, glass ✓/✕ stamps, fling-to-commit, ✕/★ dock, non-destructive recycle.
- **A** — "What's on" bento gallery built from the same real cards.
- **D** — "Or read it as a list" ranked rows reproducing the app's ListView.
- Kept the weather-engine section, sources strip, how-it-works, values, FAQ, CTA, footer.
- Earlier hero explorations preserved: `alternatives.html` (A/B/C/D), `fresh.html` (E–H),
  `shuffle.html`.

## v1.6 — 2026-06-10
- Reverted the source strip back to plain **type wordmarks** (dropped the monogram chips).
- **Fixed mirror-reversed text mid-flip**: an `overflow:hidden` perspective parent (`.pcard`)
  was flattening the 3D context, so `backface-visibility` was ignored and the hidden face
  showed through backwards. Moved the clip/border/radius onto the faces; `.pcard` is now
  `overflow:visible`, so the flip hides its backface correctly.
- **More varied content**: expanded the real-pick pool from 10 → 19 (Amsterdam Open Air,
  909 Festival, Samora Pinderhughes, MCDE, Moeders, Haarlem, Sauna Deco, Amsterdam Sevens,
  Tony's), so the 12-deep bench keeps the flips genuinely fresh.

## v1.5 — 2026-06-10
- **Finessed the bento movement**: replaced the rudimentary single-element 90° content
  swap with a real **two-faced card flip** (front/back faces, 180° rotateY) — eased
  motion, a mid-flip depth lift + shadow, randomized 1.9–2.8s cadence, and no-repeat tile
  selection. State is baked on a timer so it stays robust if the tab is backgrounded.
- **Source strip → monogram "logo" chips**: styled wordmark chips (mark + name) instead of
  plain text. Deliberately NOT real third-party brand logos — copying those raises
  copyright + false-endorsement (trademark) risk for a marketing site. Naming sources is
  fair use; their actual logos would need per-source permission.

## v1.4 — 2026-06-10
- Replaced the cover-flow hero with a **live bento gallery** (the chosen "A" direction):
  an editorial grid of real weekend picks that introduces **movement** — every ~2.2s a
  random tile flips (3D rotateY) to a fresh pick from the pool, so the wall visibly
  re-ranks in real time. Pauses on hover; respects reduced-motion.
- Pulled **real app content** from `~/Code/wkndr` (FKA twigs, Red Light Jazz, Jungle by
  Night, Noordermarkt, Zaanse Schans…) with real images and source credits; BEST WHEN
  pills now derive from each pick's `weatherFit`.
- **Reduced the nav** to a compact pill that hugs its content (was full-width).
- Converted the lower phone demo from a second swipe deck to the **List view**, so the
  page shows the stack→list duality it describes instead of two decks.

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
