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
- `aber-app-whats-new.html` — standalone client landing page (Aberystwyth Comedy Festival app "what's new") — see Client project pages below
- `aber-app-whats-new/images/` — self-hosted screenshots for the above page
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

## Client project pages
Standalone one-off pages built for a specific client/app (e.g. `aber-app-whats-new.html`) live at the repo root alongside the main site but are a different pattern:
- Full HTML boilerplate required (`<!DOCTYPE>`, `<html lang="en">`, `<head>` with charset + viewport meta + favicon link) — these aren't fragments
- Header and fonts match the main site for a seamless feel: the shared `nav.site-nav` (logo → `index.html`, same nav links, `.nav-cta`, `.nav-burger` mobile toggle) and self-hosted Inter (`fonts/inter-latin.woff2` / `fonts/inter-latin-ext.woff2`), even though the page isn't linked from anywhere — see `aber-app-whats-new.html` for the reference implementation. Below the shared nav, the page's own content/section structure and accent color (client-specific, not Devfusion orange) stay as designed for that client
- `nav.site-nav` is scoped with hardcoded hex values (`#ff6600`, `#0f1117`, etc.) rather than the page's own CSS custom properties, so it renders identically to `index.html`/`tools.html` regardless of what palette the page itself uses
- Not part of site nav — not reachable from `index.html` or `tools.html` unless explicitly asked for; the shared header on the page itself is one-way (lets visitors navigate back into the site, doesn't create an inbound link)
- Footer credits Devfusion with a link to `https://devfusion.net`, matching the site's contact email/phone
- Self-host any images as real files in a sibling folder (e.g. `aber-app-whats-new/images/`) — never inline large assets as base64 data URIs in the HTML, it bloats the page and blocks caching

## Contact form
`index.html` uses Netlify Forms (`data-netlify="true"`, `netlify-honeypot="bot-field"`, hidden `form-name` input). Fields: name, email, phone (optional), budget (select), message.

## Content rules
- Company name: **Devfusion** (not Dev Fusion, not devFusion, not DevFusion)
- Address: The Code Hub, Haddonsacre, Station Road, Offenham. WR11 8JJ
- Email: enquiries@devfusion.net
- Phone: 07866 733164
- Tone: confident, direct, no fluff — speaks to business owners not tech teams
