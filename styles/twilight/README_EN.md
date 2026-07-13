# Twilight

> [中文](README.md)

A design system built for a data-dense dashboard product with a warm, earthy visual identity. The palette centers on amber and teal, grounded by neutral tones that avoid the cold greys typical of enterprise analytics tools.

## What this design system covers

- **Foundations** -- amber/teal dual-accent palette, 9-stop scales per role, 4-stop radius, 5-level shadow, 8-step spacing, and a two-family type system (Outfit + Inter)
- **Components** -- 6 documented components: Button, Card, Table, Chart, Navigation, Sidebar
- **Previews** -- self-contained HTML preview cards for each component

## CONTENT FUNDAMENTALS

### Voice & tone

The system's visual language is warm but restrained. The earthy amber primary (`#e8922a`) signals approachability and energy without veering into playful territory, while the teal accent (`#14b8a6`) provides a cool counterpoint reserved for secondary actions and status indicators. Neutral tones (`#faf9f7` through `#4f4842`) carry a subtle warm undertone, deliberately avoiding the clinical feel of pure grey palettes. The typography pairing of Outfit (geometric, friendly) for headings and Inter (optimized for readability) for body text reinforces this balance: distinctive at a glance, comfortable over long sessions.

### When generating copy

- Use concise, professional language -- functional over decorative.
- Button labels are action-oriented single verbs or short verb phrases (e.g. "搜索", "提交", "查看详情").
- Status and trend indicators use percentage changes with directional arrows, not qualitative labels.
- Section labels in navigation follow noun-first conventions; no emoji in product UI.

## VISUAL FOUNDATIONS

### Color

The brand primary is **`#e8922a`**, a mid-amber that sits at the 500-stop of a 9-step scale running from the near-white `#fef9f0` (50) through to the deep brown `#773f17` (900). This warm tone is the system's dominant accent: it drives CTA buttons, active sidebar items, focus rings, and chart-1 color. The 600-stop `#d47a1c` serves as the hover/pressed state, darkening just enough to register interaction without shifting hue.

The secondary accent is **`#14b8a6`**, a teal at the 500-stop of its own 9-step scale. It appears in avatar gradients, secondary chart colors, and accent-foreground contexts. Its 600-stop `#0d9488` marks the interactive hover tier. The two accents are deliberately complementary -- warm action + cool information -- and never compete for the same visual role.

Semantic colors follow industry conventions but are tuned to the palette's warmth. Success draws from green (`#16a34a` at 600), warning from amber-yellow (`#d97706` at 600), error from red (`#dc2626` at 600), and info from blue (`#2563eb` at 600). Each has a full 9-stop scale plus a matching 50-stop tint for container backgrounds (`--error-container`, `--color-primary-container`, etc.).

Neutrals form a 9-stop scale from `#faf9f7` (50) to `#4f4842` (900) with a noticeable warm bias -- compare 50-stop `#faf9f7` against a pure `#fafafa`. The working surface tokens cluster in the lighter end: background `#faf9f7`, card `#ffffff`, muted `#e8e5df`, border `#d5d0c8`. In dark mode, the background inverts to `#0f0e0d` with card at `#1a1918`, and the primary shifts up to `#f2ae52` for legibility against dark surfaces.

Chart colors cycle through the five semantic families: amber, teal, blue, green, yellow -- enough to distinguish data series without clashing.

### Typography

The display and heading face is **Outfit**, a geometric sans-serif with a slightly rounded terminal treatment that echoes the palette's warmth. It carries weights 400-700 and handles all heading tiers from display (56px/700) down to h4 (20px/600). The display size runs at 56px with a tight 1.1 line-height and `-0.02em` letter-spacing, making it suitable for large numbers and hero metrics. Heading sizes descend: h1 at 40px/700/1.2, h2 at 32px/600/1.25, h3 at 24px/600/1.3, h4 at 20px/600/1.4.

Body text uses **Inter** at 16px/400/1.6 -- the standard workhorse for readability at paragraph length. A lead variant bumps to 18px/400/1.7 for introductory paragraphs. The eyebrow style sits at the opposite extreme: 11px/600/1.4 with `0.08em` letter-spacing and uppercase transform, serving as a label type for section headers and metadata tags.

Code and numeric data use **JetBrains Mono** at 14px/400/1.6. The `.test-price` class switches back to Outfit at 24px/700 with `font-variant-numeric: tabular-nums` to keep pricing and dashboard figures aligned.

All three families are loaded via Google Fonts. If Outfit is unavailable, fall back to `sans-serif` (the browser's default geometric sans will be a reasonable match). If Inter is unavailable, the `sans-serif` fallback applies similarly. For CJK contexts, the system font stack should resolve to PingFang SC / Noto Sans SC / Microsoft YaHei automatically, though this has not been explicitly tested.

### Spacing

The spacing scale is an 8-step, 4px-base progression: `--space-1` (4px), `--space-2` (8px), `--space-3` (12px), `--space-4` (16px), `--space-5` (24px), `--space-6` (32px), `--space-7` (48px), `--space-8` (64px). Most component internals live in the 8-24px range: button padding uses space-2/space-4 (sm) through space-3/space-6 (lg), card body padding is space-4, and the topbar uses space-8 for horizontal padding. Input height is fixed at 38px.

### Radius

The system uses four radius tokens plus a `--radius-full: 9999px` for pill shapes. Small (6px) applies to compact controls like small buttons and sidebar items. Medium (8px) is the default for standard buttons, stat cards, info cards, and table wrappers. Large (12px) handles poster cards and the sidebar container itself. Extra-large (16px) is available but not actively applied in the current component set. The pill radius appears on tags and avatar circles.

### Shadow / Elevation

Five shadow layers provide a clear elevation hierarchy. Level 1 (`--shadow-1`) is a barely-perceptible double-layer shadow for resting cards; level 2 (`--shadow-2`) adds depth for hover states on cards and stat rails. Level 3 (`--shadow-3`) introduces float elevation for popovers and dropdowns. Level 4 (`--shadow-4`) is the modal shadow, and level 5 (`--shadow-5`) is reserved for overlays and dramatic emphasis. All shadows use the foreground color `rgba(79,72,66,...)` as their base, which keeps them warm-toned rather than neutral black. In dark mode the shadow color switches to pure black with higher opacity values.

### Borders, backgrounds, animation

Borders are thin and utilitarian: the default border token is `#d5d0c8` (neutral-300), with variant borders at `#e8e5df` (neutral-200) for subtler dividers. The topbar uses a translucent rgba border (`rgba(255,255,255,0.08)`) over its blur-glass backdrop. Transition timing is consistently `0.15s` for color and filter changes, giving interactions a responsive but non-distracting feel. The `:active` state on buttons uses `brightness(0.92)` rather than a color shift, and hover states on cards use `brightness(0.97)` -- both subtle enough to avoid visual noise in dense dashboards.

## Component Patterns

| Component | Preview | Contract | CSS Source | Key Facts | Key Insight |
|---|---|---|---|---|---|
| Button | `preview/component-button.html` | `components/button.json` | `components.css` "Button" | 3 variants (solid/ghost/outline), 3 sizes (sm 32px / md 40px / lg 48px), disabled state | Hover uses brightness filter, not color swap -- keeps amber tone stable |
| Card | `preview/component-card.html` | `components/card.json` | `components.css` "Card" | 3 variants (poster/stat/info), poster has 2:3 image area | Cinematic shadow layering; stat cards use Outfit for large numbers |
| Table | `preview/component-table.html` | `components/table.json` | `components.css` "Table" | 2 densities (default 48px / compact 36px row height) | Row hover via brightness filter, consistent with card pattern |
| Chart | `preview/component-chart.html` | `components/chart.json` | `components.css` "Chart" | 2 variants (stat-card / sparkline-card) | Sparkline is a placeholder 40px block; stat-value uses h2 scale |
| Navigation | `preview/component-navigation.html` | `components/navigation.json` | `components.css` "Navigation" | 2 variants (topbar / breadcrumb), blur-glass topbar | Dark-mode glass effect with saturated backdrop blur |
| Sidebar | `preview/component-sidebar.html` | `components/sidebar.json` | `components.css` "Sidebar" | 2 variants (nav-sidebar / filter-sidebar), 240/260px width | Active item uses primary-container bg, not a left-border indicator |

## Index

- `tokens.css` -- all CSS custom properties for color, type, radius, shadow, spacing (light + dark)
- `tokens.json` -- structured JSON token representation
- `../../components/` -- component layer, each component in its own folder (HTML + CSS + JSON)
- `../../pages/` -- page layer, data separated from templates
- `../../contracts/` -- rules and metadata

## Caveats / known substitutions

1. **BrandFile was empty** -- no personality, language, uiCopySamples, or kitType were available from the upstream brand analysis phase. All brand narrative in this document is inferred from the CSS token structure (color relationships, font choices, naming conventions). Treat voice/tone guidance as directional, not authoritative.

2. **Outfit and Inter rely on Google Fonts CDN** -- these are not bundled locally. Offline use will fall back to `sans-serif`. The display-to-heading-to-body hierarchy will still function, but the geometric warmth of Outfit and the legibility optimization of Inter will be lost. For production, consider self-hosting or substituting with a local font that matches Outfit's rounded terminals (e.g. Nunito as a closer match than the system default sans-serif).

3. **Chart component is confidence `low`** -- the sparkline implementation is a placeholder (`<span class="sparkline">` with a 40px height block, no actual SVG rendering). Any real chart integration will need a separate charting library. The stat-card variant is functional as a layout pattern.

4. **Dark mode shadows are untested in this document** -- the token values for dark shadows exist in the CSS and use higher-opacity black, but no dark-mode preview HTML was generated. Verify contrast and elevation perception in dark contexts before shipping.

5. **No icon assets are bundled** -- component previews reference inline SVG symbols, but no standalone icon SVGs exist in an `assets/icons/` directory. If icons are needed for production, they must be sourced separately.
