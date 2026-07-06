---
name: kino-design
description: Use this skill to generate well-branded interfaces for Kino. Contains colors, type, fonts, assets, and UI kit for prototyping dashboard UIs.
user-invocable: true
---
# Kino Design Skill

Read the `README.md` file within this skill, and explore the other available files.

If creating visual artifacts, copy assets out and create static HTML files. If working on production code, read the rules here to become an expert in designing with this brand.

## Quick map
- `README.md` — brand context, content fundamentals, visual foundations (read first)
- `colors_and_type.css` — drop-in CSS variables for colors, type, radius, shadow, spacing
- `css.json` — structured token understanding source
- `components/index.json` — component index + cross-component patterns
- `preview/` — small HTML cards illustrating foundations and components
- `components.css` — aggregated component CSS

## Essentials at a glance
- Brand primary `#e8922a` — warm amber, paired with teal accent `#14b8a6`. No default blue; the palette feels organic and premium.
- Radius is **6 / 8 / 12 / 16** — soft but controlled. `9999px` reserved for pill chips only.
- Density-first: 38px input height, 4 px spacing base, whisper-quiet shadows at rest (shadow-1).
- Type: **Outfit** (display + heading, 700/600), **Inter** (body, 400), **JetBrains Mono** (code, 400). Display at 56 px / 1.1 line-height.
- Warm neutral surface `#faf9f7` with ink `#4f4842` — cream-toned, never cold gray. Full dark theme inverts to `#0f0e0d`.
- Shadows use warm-tone rgba(79,72,66,...) — 5 levels from card to overlay, deliberately restrained.
- Voice: concise, professional English. Eyebrow type uses 0.08 em letter-spacing + uppercase for labels.
- Signature pattern: ghost-style buttons with minimal chrome; cards gain elevation via layered shadow on hover.

## Components
| Slug | Name | Key Insight |
|---|---|---|
| button | Button | Minimal ghost buttons with subtle hover transitions |
| card | Card | Cinematic poster cards with layered shadow elevation |
| table | Table | Clean data tables with subtle row separation |
| chart | Chart | Minimal stat cards with sparkline-style indicators |
| navigation | Navigation | Understated top nav with blur-glass effect |
| sidebar | Sidebar | Compact icon sidebar with collapsible sections |
