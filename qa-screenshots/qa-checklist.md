# QA Report: Dr. Jonh M. Astete Cornejo

**Date:** 2026-03-05
**URL:** https://jonh-astete.cofoundy.dev
**Status:** FAIL

## Data Validation
- [x] Name matches source (form: "Jonh M. Astete Cornejo", page: "Dr. Jonh M. Astete Cornejo")
- [x] Email matches source (jastetecornejo@gmail.com — Cloudflare-obfuscated but decodes correctly)
- [x] Title matches source ("Médico Ocupacional | Investigador | Docente")
- [x] No hallucinated data — all institutions, publications, credentials, and stats trace to config.ts
- [x] LinkedIn URL correct (linkedin.com/in/jonh-astete-cornejo-a4498539)
- [x] ORCID correct (0000-0001-6225-6720)
- [x] Google Scholar URL correct with user ID
- [x] DOI links present for 3 of 4 publications (4th has no DOI — intentional, matches config)

## Clean Deploy
- [x] No third-party watermarks (Astro logo, Vercel badge, etc.)
- [x] No placeholder text (no "Lorem ipsum", "Your name here", "[placeholder]", "Diego Quispe")
- [x] No template links ("View source", "Fork this", "View on GitHub")
- [x] No "undefined" or "null" visible in content
- [x] "Desarrollado por Cofoundy" in footer at 20% opacity — our own branding, acceptable
- [x] All navigation anchors (#expertise, #trayectoria, #publicaciones, #liderazgo, #contacto) correspond to real section IDs

## Sections Present
- [x] Hero (name, title, tagline, stats bar, CTA buttons, photo placeholder)
- [x] Expertise Grid (6 cards: Medicina Ocupacional, Toxicología, Neurociencias, Salud Psicosocial, Radiológico OIT, Docencia)
- [x] Trayectoria / Academic Positions (4 timeline items: UPCH, INS, U. Continental, UDEP/ESAN)
- [x] Publicaciones (4 publication cards with journal, year, DOI links)
- [x] Liderazgo (3 leadership cards + 6 services)
- [x] Footer/Contact (email, LinkedIn, ORCID, Scholar, institutional affiliations grid)

## Technical
- [x] CSS loads (/_astro/index.N9Pb9xsH.css — HTTP 200)
- [x] Favicon loads (/favicon.svg — HTTP 200)
- [!] Profile image MISSING (/profile.jpg — HTTP 404, /profile.png — HTTP 404)
- [x] Google Fonts loading (DM Serif Display + Source Sans 3)
- [x] Site returns HTTP 200
- [x] Cloudflare proxy active (email obfuscation working)
- [x] CNAME file present (jonh-astete.cofoundy.dev)
- [x] Open Graph meta tags present and correct

## Issues Found

### CRITICAL: Profile Photo Missing (HTTP 404)
- `/profile.jpg` returns 404
- `/profile.png` returns 404
- Local `public/` folder only contains `CNAME` and `favicon.svg`
- The hero section references `/profile.jpg` but the file was never added to `public/`
- **Fix:** Copy the client's professional photo to `public/profile.jpg` and redeploy

### No other issues found.

## Evidence
- Page HTML downloaded and analyzed (38,815 bytes)
- All HTTP status codes verified via curl
- Email decoded from Cloudflare obfuscation and verified
- No screenshots taken (no Chrome MCP available in this session)
