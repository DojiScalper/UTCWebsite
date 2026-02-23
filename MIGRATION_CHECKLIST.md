# UTC Domain Move Checklist (GoDaddy -> Cloudflare + GitHub Pages)

Use this checklist when moving `ultimatetechnologyconsulting.com` and keeping research working.

## 1. Pre-Move Preparation
- [ ] Confirm both repos exist:
- [ ] Main site repo (this project)
- [ ] Research repo (separate project)
- [ ] Confirm each repo has correct `CNAME` file:
- [ ] Main repo `CNAME`: `ultimatetechnologyconsulting.com`
- [ ] Research repo `CNAME`: `research.ultimatetechnologyconsulting.com`
- [ ] Confirm both repos are deploying successfully from GitHub Pages.
- [ ] Keep old site live until DNS cutover is verified.

## 2. GitHub Pages Configuration
- [ ] Main repo: set custom domain to `ultimatetechnologyconsulting.com`.
- [ ] Research repo: set custom domain to `research.ultimatetechnologyconsulting.com`.
- [ ] Enable HTTPS in both Pages settings after DNS resolves.

## 3. Cloudflare DNS Records
- [ ] Add root (`@`) A records for GitHub Pages:
- [ ] `185.199.108.153`
- [ ] `185.199.109.153`
- [ ] `185.199.110.153`
- [ ] `185.199.111.153`
- [ ] Add `CNAME` for `www` -> `<github-username>.github.io`
- [ ] Add `CNAME` for `research` -> `<github-username>.github.io`
- [ ] Set all GitHub Pages records to DNS only (gray cloud) initially.

## 4. DNS Cutover Validation
- [ ] Main site loads at `https://ultimatetechnologyconsulting.com/`.
- [ ] Research site loads at `https://research.ultimatetechnologyconsulting.com/`.
- [ ] Legacy path bridge loads and redirects:
- [ ] `https://ultimatetechnologyconsulting.com/research`
- [ ] TLS certificates are active and browsers show secure lock for both hosts.

## 5. SEO and Crawl Safety
- [ ] Main sitemap accessible: `https://ultimatetechnologyconsulting.com/sitemap.xml`
- [ ] Research sitemap accessible: `https://research.ultimatetechnologyconsulting.com/sitemap.xml`
- [ ] `robots.txt` accessible on both hosts.
- [ ] Canonical tags point to intended final URLs.
- [ ] Keep `/research` bridge page live during migration period.
- [ ] Submit/refresh both properties and sitemaps in Google Search Console.

## 6. Post-Move Monitoring (First 2-4 Weeks)
- [ ] Monitor Search Console coverage and indexing for both properties.
- [ ] Check for crawl errors and fix broken links quickly.
- [ ] Verify analytics/traffic continuity.
- [ ] Keep old GoDaddy DNS zone inactive only after stable Cloudflare resolution.

## 7. Optional Hardening After Stabilization
- [ ] Test Cloudflare proxy mode for performance/security (if desired).
- [ ] Add caching/page rules only after confirming no routing issues.
- [ ] Optimize local images (WebP/compression) and re-check page speed.

