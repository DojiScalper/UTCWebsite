# UTC Website Project Agent Guide

This file defines how agents should build and maintain the UTC web presence.

## Project Scope
- Business landing site only, minimal and professional.
- No online sales.
- No residential-style service positioning.
- Keep implementation lightweight and maintainable.

## Site Architecture
- Use two separate GitHub Pages sites:
- Main site: `ultimatetechnologyconsulting.com`
- Research site (real subdomain): `research.ultimatetechnologyconsulting.com`

Reason:
- DNS and current setup already use a real research subdomain.
- Keeps research content isolated and easy to manage.
- Supports independent updates and SEO control per site.

## Repositories
- `UTCWebsite` (this repo): main marketing/landing site.
- `UTCResearch` (separate repo): research publications/projects site.

If both are ever colocated temporarily, maintain separate build/deploy targets and separate `CNAME` values.

## Technology Decisions
- Stack: plain `HTML + CSS + minimal vanilla JS`.
- No framework by default.
- No backend required.
- Host via GitHub Pages.

Allowed additions:
- Small, non-build-step libraries only when clearly justified.
- Avoid introducing Node build tooling unless specifically requested.

## Main Site Requirements
- Core page: `index.html`.
- Navigation should include link to research subdomain.
- Include contact details relevant to business clients.
- Keep design modern, simple, and fast.

Suggested structure:
- `/index.html`
- `/assets/css/styles.css`
- `/assets/js/main.js` (only if needed)
- `/assets/img/...`
- `/robots.txt`
- `/sitemap.xml`
- `/CNAME`

## Research Site Requirements
- Home page for research index and links to papers/projects.
- Can expand to detail pages later.
- Must include link back to main domain.

Suggested structure (in `UTCResearch` repo):
- `/index.html`
- `/papers/...` (optional now, likely later)
- `/assets/...`
- `/robots.txt`
- `/sitemap.xml`
- `/CNAME`

## SEO and Crawlability (Required)
Apply to both main and research sites:
- Unique `<title>` and `<meta name="description">` per page.
- Canonical URL tag on each page.
- Valid `robots.txt` allowing crawl.
- `sitemap.xml` listing canonical URLs.
- Clean semantic headings (`h1`, `h2`, etc.).
- Descriptive link text (avoid generic "click here").
- Mobile responsive layout and fast load times.

Recommended:
- Add Search Console verification for both properties.
- Submit each sitemap in Search Console.

## Content and Tone
- Tone: technical, credible, concise.
- Audience: business and institutional clients.
- Avoid consumer retail language.
- Avoid overdesigned or flashy UI.

## Accessibility and Quality
- Use semantic HTML landmarks (`header`, `main`, `nav`, `footer`).
- Ensure sufficient color contrast.
- Keyboard-focus visible states for links/buttons.
- Add `alt` text for all meaningful images.
- Keep pages valid and easy to scan.

## Deployment Rules
- Each repo deploys independently through GitHub Pages.
- Each repo must contain correct `CNAME`:
- Main repo `CNAME`: `ultimatetechnologyconsulting.com`
- Research repo `CNAME`: `research.ultimatetechnologyconsulting.com`

DNS notes (high level):
- Main domain and subdomain records must point to GitHub Pages targets.
- Do not change DNS strategy without explicit approval.

## Change Management
- Prefer small, reviewable commits.
- Keep HTML/CSS readable; avoid unnecessary abstraction.
- Do not add heavy dependencies for simple layout/content updates.
- Preserve URL stability when possible.

## Initial Build Order
1. Build main site `index.html` with clean nav and business-focused content.
2. Add SEO baseline files (`robots.txt`, `sitemap.xml`, metadata, canonical).
3. Build research site repo skeleton with same SEO baseline.
4. Link both sites bidirectionally.
5. Validate responsiveness and crawlability.

