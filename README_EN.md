<p align="center">
  <img src="assets/banner.jpg" alt="Kino Design System">
</p>

<h1 align="center">Kino — Web Design Framework</h1>

<p align="center">
  Weather-themed design framework<br>
  <a href="README.md">中文</a> | English
</p>

---

## Overview

Kino is a weather-themed design framework with a three-layer architecture:

- **Theme layer** `styles/` — CSS-driven visual styles; switch themes by switching CSS files
- **Component layer** `components/` — Pure presentational UI units, each in its own folder (HTML+CSS+JSON)
- **Page layer** `pages/` — Complete pages with separated data and templates

## Current Theme

| Style | Version | Palette |
|---|---|---|
| [Twilight](styles/twilight/README_EN.md) | v1.0.0 | Amber `#e8922a` + Teal `#14b8a6`, warm dark base |

## Directory

```
kino/
├── assets/                       Images
├── styles/                       Theme layer
│   └── twilight/tokens.css       CSS variables (single source of truth)
├── components/                   Component layer (self-contained)
│   ├── button/button.html        Preview + CSS + contract
│   ├── card/
│   ├── table/
│   ├── chart/
│   ├── navigation/
│   ├── sidebar/
│   └── index.json                Component index
├── pages/                        Page layer
│   └── dashboard/
│       ├── index.html            Page template
│       └── data/                 Data files (JSON)
├── contracts/                    Rules & metadata
│   ├── AI_RULES.md               AI architecture rules
│   └── styles-index.json         Theme registry
└── README.md
```

## Core Constraints

1. **Components contain no data or logic** — they only render
2. **Add features by creating folders** — never modify existing files
3. **All style values via CSS variables** — switch themes by switching CSS

## License

MIT
