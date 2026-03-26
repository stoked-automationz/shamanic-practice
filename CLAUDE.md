# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static website for **Shaman's Light** — Bree Kasper's shamanic energy healing practice in Reno, NV. The deployable site lives in `site/`. Source materials (docs, original images, business strategy) live in `resources/`.

## Development

**No build step.** This is a pure static HTML/CSS/JS site. Edit files directly and deploy.

- **Preview locally:** `open site/index.html` in a browser
- **Deploy to production:** `cd site && vercel --yes --prod`
- **Vercel project:** `androidnextdoors-projects/site`

## Git

- **Remote:** `git@github.com-stoked:stoked-automationz/shamanic-practice.git`
- **SSH alias:** Uses `github.com-stoked` host alias (maps to `~/.ssh/stoked_ed225519` key)
- **Commit author:** `stoked-automationz <stoked-automationz@users.noreply.github.com>` — verify with `git config user.name` before committing. Do NOT commit as AndroidNextdoor or andrew.nixdorf.

## Architecture

```
site/                    # Deployed to Vercel
├── index.html           # Single-page site, all sections inline (~520 lines)
├── css/styles.css       # Complete stylesheet with CSS custom properties (~1030 lines)
└── images/              # 14 assets (JPG + logo.svg)

resources/               # NOT deployed — source materials only
├── docs/                # Business strategy report, bio, website copy, tri-fold PDF
└── images/              # Original high-res source images
```

**index.html** is a single-page layout with 13 sections: header/nav, hero, about, when-to-book, services, quote banner, the practice, pricing, herbal teas, ceremonies, second quote, contact/booking, footer. Each section is marked with HTML comment headers. JavaScript is inline at the bottom (mobile nav toggle, scroll shadow, Intersection Observer animations).

**styles.css** uses CSS custom properties for theming. Key variables:
- Brand colors: `--color-burgundy` (#6b2737), `--color-gold` (#c8a25c), `--color-cream` (#faf6f0)
- Fonts: `--font-script` (Cormorant Garamond) for headings, `--font-body` (Lato) for text
- Responsive breakpoints at 768px and 480px

## Planned Integrations (Not Yet Implemented)

- **Acuity Scheduling** — embed placeholder exists in the contact section (search for `ACUITY SCHEDULING EMBED` comment in index.html). Replace placeholder `<div class="booking-placeholder">` with Acuity iframe. Must sync with Bree's Google Calendar.
- **Google Analytics 4 / Search Console** — no tracking code installed yet
- **MailerLite** — email marketing; no integration code yet
- **Square** — future e-commerce for herbal tea sales

See `resources/docs/BUSINESS-STRATEGY-REPORT.md` for the full business roadmap, competitor analysis, pricing strategy, and phased migration plan.

## Content & Brand Voice

All copy is hardcoded in index.html. The tone is warm, elegant, and professional — reflecting shamanic healing traditions. Pricing, services, and contact info (775-338-9349, businesssavvy@charter.net) are inline. The medical disclaimer in the footer is required and must not be removed.