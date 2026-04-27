# Odoo Design Exercise

A static, responsive landing page built from a provided Odoo design mock-up. The focus is on clean markup, Bootstrap 5.3 utility-first styling, and a modular SCSS architecture following the [7-1 pattern](https://sass-guidelin.es/#the-7-1-pattern).

## Tech stack

- **HTML5** — semantic, accessible markup
- **Bootstrap 5.3.3** — layout grid, utilities, and components
- **Dart Sass 1.77** — compiles SCSS to a single minified stylesheet
- **Bootstrap Icons** & **Inter** (Google Fonts) — typography and iconography

No JavaScript framework, no bundler — just SCSS in, CSS out.

## Project structure

```
odoo_mockup_wmdn/
├── index.html              # Single-page entry
├── mock-up.jpg             # Reference design
├── assets/
│   ├── img/                # Photography & feature imagery
│   └── logos/              # Brand & client SVGs
├── scss/                   # 7-1 SCSS architecture
│   ├── main.scss           # Entry point – imports all partials
│   ├── abstracts/          # _variables, _theme-maps
│   ├── base/               # _base, _animations
│   ├── layout/             # _navbar, _hero, _journey, _footer, …
│   ├── components/         # _buttons, _cards, _accordion-faq, …
│   ├── utilities/          # _helpers
│   └── vendors/            # _bootstrap
├── css/                    # Compiled output (generated)
│   └── style.css
└── package.json
```

## Prerequisites

- **Node.js 18+** and **npm** (only needed for the SCSS build).

## Getting started

```bash
# 1. Install build tooling (Bootstrap sources + Dart Sass)
npm install

# 2. Compile SCSS → css/style.css
npm run build:css        # one-shot, minified build
npm run watch:css        # rebuild on every save while developing

# 3. Serve locally on http://localhost:8080
npm run serve            # spins up http-server with caching disabled
```

If you just want to preview the page, opening `index.html` directly in a browser also works once the CSS has been built at least once.

## npm scripts

| Script | What it does |
| --- | --- |
| `npm run build:css` | Compiles `scss/main.scss` → `css/style.css` (compressed, no source map) |
| `npm run watch:css` | Same as above, but watches for changes |
| `npm run serve` | Serves the site at `http://localhost:8080` with cache disabled |
| `npm run build` | Alias for `build:css` |

## Working on styles

All custom styling lives in `scss/`. Add new partials inside the appropriate folder (`layout/`, `components/`, etc.) and import them from `scss/main.scss` so they're picked up by the build. Brand colors, typography scales, and spacing tokens are centralized in `scss/abstracts/_variables.scss` and `_theme-maps.scss` — prefer editing those over hard-coding values in component partials.

## Credits

- Bootstrap 5.3 — https://getbootstrap.com
- Bootstrap Icons — https://icons.getbootstrap.com
- Google Fonts (Inter) — https://fonts.google.com/specimen/Inter
- Images, logos, and design mock-up provided by Odoo
