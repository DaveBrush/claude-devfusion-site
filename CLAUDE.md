# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is
A static website for Devfusion, a software consultancy based in Offenham, Worcestershire. Multi-page, multi-file structure. No build tools.

## Tech choices
- Vanilla HTML, CSS, JS — no React, no bundler, no npm
- External JS libraries are permitted where they add clear value
- Fonts are self-hosted (Inter variable font in `fonts/`)
- No prescribed deployment method — Netlify, GitHub Pages, or similar all work

## Current file structure
- `index.html` — main marketing site, single scroll page
- `tools.html` — developer tools directory page
- `df_logo.png` — logo (always use this)
- `favicon.png` — site favicon (300×300 PNG)
- `fonts/inter-latin.woff2` — Inter variable font, Latin subset (weights 300–600)
- `fonts/inter-latin-ext.woff2` — Inter variable font, Latin-extended subset

## Design conventions
- Single orange theme — no theme toggle
- Color palette: `--ink` (#0f1117), `--ink-mid` (#3a3d47), `--ink-muted` (#7a7f8e), `--accent` (#ff6600), `--accent-hover` (#e55a00), `--accent-light` (#fff3eb)
- Surfaces: `--surface` (#fff), `--surface-2` (#f8f8f7), `--surface-dark` (#0f1117)
- Font: Inter variable via `@font-face`, `font-weight: 300 600` range
- Buttons: 6px radius (`--radius`), orange fill (primary) or outlined (secondary)
- Section pattern: `section > .inner > content` (max-width `--max` = 1120px)
- Scroll animations: `.fade-up` + `.is-visible` via IntersectionObserver; staggered with `.delay-1` through `.delay-5`
- Responsive breakpoints: 900px (services/why grid reflow), 768px (single column, mobile nav), 480px (further reflow)
- Mobile nav: hamburger button (`.nav-burger`) toggles `.menu-open` on `<nav>`, revealing `.nav-end` as an absolute dropdown

## Navigation
Both pages share the same nav structure:
- Logo → links to `index.html`
- Links wrapped in `.nav-end` div alongside `.nav-cta`
- `.nav-burger` button for mobile toggle
- Active page marked with `aria-current="page"` on the relevant link

## Contact form
`index.html` uses Netlify Forms (`data-netlify="true"`, `netlify-honeypot="bot-field"`, hidden `form-name` input). Fields: name, email, phone (optional), budget (select), message.

## Content rules
- Company name: **Devfusion** (not Dev Fusion, not devFusion, not DevFusion)
- Address: The Code Hub, Haddonsacre, Station Road, Offenham. WR11 8JJ
- Email: enquiries@devfusion.net
- Phone: 07866 733164
- Tone: confident, direct, no fluff — speaks to business owners not tech teams
