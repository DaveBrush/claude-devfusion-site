# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is
A static website for Devfusion, a software consultancy based in Offenham, Worcestershire. Currently a single `index.html` with `df_logo.png`, but multi-page and multi-file structure is fine going forward.

## Tech choices
- Vanilla HTML, CSS, JS — no React, no bundler, no npm
- External JS libraries are permitted where they add clear value
- Fonts can be self-hosted or CDN — currently loaded via Google Fonts CDN (DM Serif Display, DM Sans, Inter)
- No prescribed deployment method — Netlify, GitHub Pages, or similar all work

## Current structure
- `index.html` — full site, single scroll page
- `df_logo.png` — high-res logo (use this, not `logo.png`)
- `logo.png` — lower-res version, can be removed

## Theme system
`index.html` has a two-theme toggle (Blue / Inter vs Orange / DM Serif). Theme is stored in `localStorage` under `df-theme`. Defaults to orange. The `[data-theme="orange"]` attribute is set on `<html>`. All theme differences are driven by CSS custom properties in `:root` and `[data-theme="orange"]` overrides.

## Design conventions
- Color palette: `--ink` (#0f1117), `--accent` (#1a3cff blue / #ff6600 orange), `--warm` (#e8440a)
- All CSS uses custom properties defined in `:root`
- Blue theme: DM Serif Display for headings, pill buttons (100px radius), dark hero
- Orange theme: Inter for headings, rounded-rect buttons (6px radius), light hero
- Section pattern: `section > .section-inner > content` (max-width `--max`)
- Responsive breakpoint: 768px — two-column layouts collapse, nav links hidden

## Content rules
- Company name: **Devfusion** (not Dev Fusion, not devFusion, not DevFusion)
- Address: The Code Hub, Haddonsacre, Station Road, Offenham. WR11 8JJ
- Email: enquiries@devfusion.net
- Phone: 07866 733164
- Tone: confident, direct, no fluff — speaks to business owners not tech teams
