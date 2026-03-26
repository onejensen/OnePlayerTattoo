# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static website for **One Player Tattoo**, a tattoo studio in Llucmajor, Mallorca. Hosted on GitHub Pages at `oneplayertattoo.com` (see `CNAME`). Pure HTML + CSS — no build tools, no frameworks, no package manager.

## Development

No build step. Open any `.html` file in a browser to preview. To serve locally with live reload, use any static server (e.g., `npx serve .` or `python3 -m http.server`).

## Architecture

- **`index.html`** — Main landing page. Contains Schema.org structured data (`TattooParlor`), Open Graph meta, Google Analytics (`G-CPRQ0JD1N8`), Beam Analytics, and an IntersectionObserver for scroll animations.
- **`cuidados.html`** — Tattoo aftercare page with client-side i18n (ES/EN/FR/IT/DE). Translations are inline in a `translations` JS object; elements use `data-i18n` attributes. The `setLanguage()` function swaps content via `innerHTML`.
- **`privacidad.html`** — Privacy policy page.
- **`availables.html`** — Displays Instagram story highlights via SociableKit embed widget.
- **`styles.css`** — Single shared stylesheet for all pages. Uses custom font `imperfecta_regularregular` (local `.woff`/`.woff2` files) plus Google Fonts (`Bebas Neue`, `Inter`). Dark theme with red (`#ee2623` / `#8b0000`) accent color.
- **`sitemap.xml`** / **`robots.txt`** — SEO files. Update `sitemap.xml` when adding/removing pages.

## Key Conventions

- Primary language is Spanish; bilingual content where noted.
- All pages share the same `styles.css` — no per-page stylesheets.
- CSS animations use `fade-in`, `fade-in-delay`, `fade-in-delay-2` classes for load animations, and `fade-in-scroll` + IntersectionObserver for scroll-triggered reveals.
- The `.paper` CSS class creates a light "document" card used by the aftercare page — distinct from the dark site theme.
- Instagram feed on the homepage uses a horizontal scroll carousel with `ig-*` classes.
- Buttons use `.btn` (standard) and `.btn-cta` (prominent call-to-action) classes.

## Deployment

Push to `main` branch — GitHub Pages deploys automatically from the root directory.
