# Kino Design System

A monorepo of weather-themed design system variants. Each style is a self-contained design system with its own tokens, components, previews, and documentation.

## Styles

| Style | Version | Description | Palette |
|-------|---------|-------------|---------|
| [Twilight](styles/twilight/) | v1.0.0 | Dark-mode dashboard with cinematic warmth | Amber `#e8922a` + Teal `#14b8a6` on warm dark surface |

### Roadmap

- **Dawn** — Bright, optimistic palette for marketing/landing pages
- **Frost** — Cool, crisp palette for data-heavy analytical tools
- **Aurora** — Vibrant, gradient-rich palette for creative/media applications
- **Thunder** — Bold, high-contrast palette for admin/operations dashboards

## Repository Structure

```
kino/
├── styles/
│   └── twilight/              # Each style is a complete design system
│       ├── tokens/
│       │   ├── colors_and_type.css   # CSS custom properties (SSOT)
│       │   └── css.json              # Structured token data
│       ├── components/
│       │   ├── index.json            # Component index
│       │   └── {slug}.json           # Per-component contracts
│       ├── preview/
│       │   └── component-{slug}.html # Component preview cards
│       ├── ui_kits/
│       │   └── dashboard/index.html  # Interactive UI Kit
│       ├── README.md                 # Style-specific documentation
│       └── SKILL.md                  # AI-consumable skill card
└── shared/                           # (planned) Common assets
```

## Usage

### Drop-in CSS Variables

```html
<link rel="stylesheet" href="styles/twilight/tokens/colors_and_type.css">
```

### Token Data for Toolchains

```js
import tokens from './styles/twilight/tokens/css.json';
// Generate Tailwind config, CSS-in-JS theme, Figma variables, etc.
```

### Component Contracts

Each component in `components/{slug}.json` defines:
- Variant dimensions and representative variants
- Anatomy, structure patterns, and usage hints
- AI-generated confidence levels

## Contributing

1. Create a new style branch: `git checkout -b style/dawn`
2. Follow the existing directory structure under `styles/`
3. Ensure `tokens/colors_and_type.css` is the single source of truth
4. All color values must be 6-digit hex or rgba()

## License

MIT
