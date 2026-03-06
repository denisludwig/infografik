# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A collection of standalone, self-contained HTML infographic files created by Denis Ludwig. Files cover journalism/data visualization work (primarily for MDR – Mitteldeutscher Rundfunk) and a personal consulting portfolio. All content is in German.

## Architecture

- **No build system.** Every file is a single `.html` with all CSS and JavaScript inlined.
- **No package manager, no dependencies to install.** External libraries are loaded via CDN inside each file.
- **Each file is fully independent** — no shared components, modules, or imports between files.
- Open any `.html` file directly in a browser to preview it.

## Common External Libraries (loaded via CDN)

- **Chart.js** (`cdn.jsdelivr.net` or `cdnjs.cloudflare.com`) — bar charts, line charts, data visualizations
- **Google Fonts** — DM Sans, DM Serif Display, Playfair Display, DM Mono

## File Inventory

| File | Description |
|---|---|
| `Denis-Ludwig-Consulting.html` | Personal portfolio / consulting landing page (dark, gold accent) |
| `MDR-*.html` | MDR journalism dashboards and data visualizations |
| `heizkosten-*.html` | Energy cost infographic / scrollytelling piece |
| `kausal.html` | LinkedIn carousel-style slide deck (500×500 px fixed format) |
| `mdr-coverage-map*.html` / `MDR-coverage-map*.html` | SVG-based interactive map of Saxony |
| `Konflikt-*.html` | Conflict / role-clarity dashboard |
| `kidiskussion.html` | Standalone infographic page |

## Design Patterns

- CSS custom properties (`--var`) defined in `:root` for theming; each file has its own color palette.
- Dark-theme files use backgrounds like `#0a0a0a` / `#0e0f13`; light-theme files use `#fafafa`.
- Noise texture overlays applied via inline SVG data URIs on `body::before`.
- JS is vanilla — no frameworks; interactivity via DOM manipulation and CSS class toggling (e.g. `body.ist` / `body.soll` for IST/SOLL toggle in dashboard files).
- Paginated/slide navigation is driven by JS switching active classes, not routing.
