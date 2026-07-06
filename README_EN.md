<p align="center">
  <img src="assets/banner.jpg" alt="Kino Design System">
</p>

<h1 align="center">Kino Design System</h1>

<p align="center">
  Weather-themed design system monorepo<br>
  <a href="README.md">中文</a> | English
</p>

---

## Overview

Kino is a monorepo of weather-themed design system variants. Each style is a self-contained design system with its own tokens, components, previews, and documentation.

The first release, **Twilight**, is a dark cinematic dashboard design system tailored for data-dense products like film/TV information databases.

## Styles

| Style | Version | Description | Palette |
|---|---|---|---|
| [Twilight](styles/twilight/) | v1.0.0 | Dark cinematic dashboard with warmth | Amber `#e8922a` + Teal `#14b8a6` on warm dark surface |

### Roadmap

| Style | Vision |
|---|---|
| Dawn | Bright, optimistic palette for marketing and landing pages |
| Frost | Cool, crisp palette for data-heavy analytical tools |
| Aurora | Vibrant, gradient-rich palette for creative and media applications |
| Thunder | Bold, high-contrast palette for admin and operations dashboards |

## UI Kit Preview

**Twilight — Dashboard**

<p align="center">
  <img src="assets/uikit-dashboard.jpg" alt="Twilight Dashboard UI Kit" width="640">
</p>

## Repository Structure

```
kino/
├── assets/                          # README image assets
├── styles/
│   └── twilight/                    # Each style is a complete design system
│       ├── tokens/
│       │   ├── colors_and_type.css  # CSS custom properties (SSOT)
│       │   └── css.json             # Structured token data
│       ├── components/
│       │   ├── index.json           # Component index
│       │   └── {slug}.json          # Per-component contracts
│       ├── preview/
│       │   └── component-{slug}.html # Component preview cards
│       ├── ui_kits/
│       │   └── dashboard/index.html # Interactive UI Kit
│       ├── README.md                # Style documentation (Chinese)
│       ├── README_EN.md             # Style documentation (English)
│       └── SKILL.md                 # AI-consumable skill card
└── shared/                          # (planned) Common assets
```

## Usage

### Drop-in CSS Variables

```html
<link rel="stylesheet" href="styles/twilight/tokens/colors_and_type.css">
```

All components consume design tokens via CSS variables like `var(--color-primary)`, `var(--radius-md)`, `var(--space-4)`.

### Token Data for Toolchains

```js
import tokens from './styles/twilight/tokens/css.json';
// Use to generate Tailwind config, CSS-in-JS themes, Figma variables, etc.
```

### Component Contracts

Each `components/{slug}.json` defines:
- Variant dimensions and representative variants
- Component anatomy, structure patterns, and usage hints
- AI confidence levels

## Design Philosophy

- **Minimal restraint** — Clean, medium information density, no visual clutter
- **Dark-first** — Dark canvas for cinematic feel, optimized for extended data browsing
- **Apple-inspired aesthetics** — Ultra-subtle shadows, generous whitespace, refined typography
- **Warm neutral tones** — Avoids cold greys; uses warm neutrals with amber as the dominant accent

## Contributing

1. Create a new style branch: `git checkout -b style/dawn`
2. Follow the existing directory structure under `styles/`
3. Ensure `tokens/colors_and_type.css` is the single source of truth
4. All color values must be 6-digit hex or rgba()

## License

MIT
