# Devfusion Website — Project Context

## What this is
A static HTML website for Devfusion, a software consultancy based in Offenham, 
Worcestershire. Single-file HTML (`devfusion-website.html`) using vanilla 
HTML/CSS/JS — no build tools, no framework, no dependencies except Google Fonts.

## Tech choices (keep these)
- Pure HTML, CSS, JS — no React, no bundler, no npm
- Google Fonts: DM Serif Display + DM Sans (loaded via CDN link in <head>)
- No external JS libraries
- Deployable by dragging a single file to Netlify/GitHub Pages

## Design conventions
- Color palette: --ink (#0f1117), --accent (#1a3cff), --warm (#e8440a)
- All CSS uses custom properties defined in :root
- Typography: DM Serif Display for headings/display, DM Sans for body
- Sections follow pattern: section > .section-inner > content
- Buttons use 100px border-radius pill style

## Content rules
- Company name: Devfusion (not Dev Fusion, not devFusion, not DevFusion)
- Address: The Code Hub, Haddonsacre, Station Road, Offenham. WR11 8JJ
- Email: enquiries@devfusion.net
- Phone: 07866 733164
- Tone: confident, direct, no fluff — speaks to business owners not tech teams
