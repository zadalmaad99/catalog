---
name: catalog-design
description: Catalog app design system (colors, type, RTL/Arabic, mobile-first rules). Use for any UI, theme, styling or layout change in index.html or the Android WebView assets.
---

# Catalog design system

App is a single `index.html` (Tailwind + inline CSS, Inter font) wrapped in an Android WebView. Mobile-first, phone width ~360–412px.

## Tokens (reuse; do not invent new hues)
- Brand: `#e85d3a` (light `#ff7a5a`, dark `#c44828`)
- Page surface: `#fdf6f0` · Cards: `#ffffff`
- Dark/navy: `#1a1a2e` (text primary + dark panels), `#2d2d4e` (dark raised)
- Muted text: `#6b7280` / `#9ca3af`
- Accents: cyan `#00bcd4`, yellow `#ffd600`, purple `#a855f7`
- Success `#16a34a`/`#22c55e` · Danger `#ef4444`

## Rules
1. Brand orange is for the primary action and key highlights only; one primary button per screen.
2. Cards: white, radius 16–20px, soft layered shadow (e.g. `0 4px 16px rgba(26,26,46,.08)`), 12–16px padding.
3. Spacing on a 4px scale; touch targets >= 44px.
4. Type: Inter; clear hierarchy (title 18–20 bold, body 14, caption 12 muted). Arabic text must keep RTL direction and comfortable line-height (1.6).
5. Motion: 150–250ms ease-out on press/open; scale .97 on tap; no heavy animation on lists.
6. Icons: use the project's PNG/SVG set in `Icons/` (e.g. delete.png for delete); never mix icon styles.
7. Contrast: text >= 4.5:1; do not put brand orange text on `#fdf6f0` at small sizes.
8. After editing `index.html`, run `node sync_android_assets.js` so the Android assets match.

## Workflow
Edit -> preview in the built-in browser at mobile size (375x812) -> screenshot and check spacing, RTL, overflow -> fix -> sync assets.
