# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Static landing page for [jaknapodcasty.cz](https://jaknapodcasty.cz) — a podcast consulting and production service run by Pavla and Vojta. No build step, no framework, no package manager.

## Stack

- Plain HTML (`index.html`) + CSS (`style.css`) + vanilla JS (`main.js`)
- Hosted on GitHub Pages; auto-deploys on push to `main` via `.github/workflows/deploy.yml`
- Newsletter embed powered by [Forendors](https://www.forendors.cz) (inline script in footer)
- CSS cache-busted manually via query string: `style.css?v=N` — bump `N` after CSS changes

## Key placeholders / TODOs

- **Google Analytics**: `G-XXXXXXXXXX` in `index.html` `<head>` must be replaced with the real Measurement ID
- **Consultation CTA links**: currently point to a Google Doc (`docs.google.com/document/…`); marked with `TODO: nahradit URL za odkaz na poptávkový formulář`

## Structure

- `index.html` — entire single-page site; sections: nav, hero, podcast, služby (pricing), konzultace, reference, o nás, footer
- `konzultace/index.html` — redirect shim (`<meta http-equiv="refresh">`) that forwards `/konzultace` to `/#konzultace`
- `assets/` — images only (PNG/JPG); no SVG assets — all icons are inline SVGs in HTML
- `style.css` — all styles; uses CSS custom properties (`--clr-*`, `--r-*`, etc.) defined in `:root`
- `main.js` — nav scroll effect, mobile burger menu toggle, IntersectionObserver scroll-reveal

## Deployment

Push to `main` triggers GitHub Actions → GitHub Pages deploy. No preview environments. To test locally, open `index.html` directly in a browser or use any static file server (e.g. `python3 -m http.server`).
