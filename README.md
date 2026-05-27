# LND Homes — Portfolio Page Prototype

A self-contained HTML prototype of a `/portfolio` page for [LND Homes](https://www.lndhomes.com), a residential builder in Winston-Salem, NC. Built to close the credibility gap identified in a digital audit of the current site, where every "home" image is stock photography from other cities.

**Live preview:** _add GitHub Pages URL after deploy_

---

## Why this exists

The current LND Homes website asserts quality, experience, and a high client rating — but shows zero photos of actual LND homes. The hero images are labeled "Rochester, New York," "Naperville, IL," "Phoenix, Arizona." For a builder claiming 100+ homes delivered in the Winston-Salem area, that's a credibility cliff for any buyer doing due diligence.

This prototype demonstrates what the real `/portfolio` page should look like: five actual LND properties pulled from public Zillow listings, presented in an editorial layout that matches LND's verbal positioning ("Where life calls home," "Built to Serve").

---

## What's included

A single `index.html` file. No build step, no framework, no JavaScript. Two Google Fonts loaded via `<link>`. Opens in any browser; deploys to any static host.

The five properties featured:

| # | Address | Neighborhood | ZIP |
|---|---|---|---|
| 01 | 3724 Signet Dr | Boone Hill | 27101 |
| 02 | 4728 Spitfire Ln | Lauren Acres / Clemmons schools | 27103 |
| 03 | 3710 Wabash Blvd | Old Town Heights | 27106 |
| 04 | 1643 Ralee Dr | South Winston-Salem | 27127 |
| 05 | 1667 Ralee Dr | South Winston-Salem | 27127 |

---

## What's real vs. placeholder

| Element | Status |
|---|---|
| Addresses, neighborhoods, ZIPs | Real |
| 3724 Signet Dr full specs | Confirmed via Triad MLS (4 BR / 3 BA / 1,512 sqft / MLS 1218644) |
| 1643 Ralee Dr full specs | Confirmed via Triad MLS (4 BR / 2.5 BA / 1,440 sqft / 0.27 acres) |
| Other three properties' specs | Em-dashes (`—`) — to be filled from David's records |
| Photos | Placeholder slots (1 hero + 3 secondary per home, 20 total) |
| Prices, sale dates, listing agents (beyond Signet Dr) | Intentionally omitted to avoid fabrication |

---

## Deploy to GitHub Pages

1. Rename `lnd-portfolio-prototype.html` to `index.html` so GitHub serves it at the repo root.
2. Push to a public GitHub repo.
3. **Settings → Pages → Source:** `Deploy from a branch` → Branch: `main` → Folder: `/ (root)` → Save.
4. Wait ~30 seconds for the first build. The URL will be `https://<username>.github.io/<repo-name>`.

To use a custom domain like `portfolio.lndhomes.com`:

1. Add a file named `CNAME` (no extension) at the repo root containing only the domain.
2. In LND's DNS (currently Cloudflare), add a `CNAME` record pointing the subdomain to `<username>.github.io`.
3. Back in repo Settings → Pages, paste the custom domain and tick "Enforce HTTPS" once the cert provisions.

---

## Customizing

**To swap in real photos:** find each `.media-primary` and `.media-secondary > div` block. Replace the inline SVG placeholder + labels with an `<img src="..." alt="...">`. The CSS already handles aspect ratios — 4:3 for the hero, 1:1 for the thumbnails — so any image will fit cleanly.

**To fill in missing specs:** each property block has four `.fact-value` elements. Em-dashes (`—`) mark fields awaiting input.

**To reorder, add, or remove properties:** properties are five `<section class="feature">` blocks. The alternating left/right layout is controlled by the `.reverse` class on every other section.

**To re-theme:** all colors and fonts are CSS variables in `:root` at the top of the `<style>` block.

---

## Design notes

- **Typography:** Fraunces (display serif) and Manrope (body sans), both from Google Fonts.
- **Palette:** warm cream `#f6f3ee` base, moss green `#2f4a3a` accent, terracotta `#b8634b` for editorial accents, deep ink `#1d1d1b` for text.
- **Layout:** asymmetric editorial grid; alternating left/right at desktop, single column under 900px.
- **No tracking, no analytics, no cookies.** Static HTML only.

---

## Status

- **v0.1** — Initial scaffold with five properties, placeholder photos, partial specs.
- **Next:** real photos from David's listing photographers; specs filled for properties 02, 03, 05; listing agent attribution on each property where applicable.

---

## Context

This prototype was built as part of a broader digital audit of lndhomes.com. The audit identified several issues: stock photography across all "home" images, inconsistent stat claims across pages (100+ vs 500+ vs 950+ homes built), broken footer links (`/portfolio`, `/testimonials`, `/blog` all 404), missing phone number, non-functional social links, and weak local SEO. The portfolio page is the single highest-leverage fix — it converts "claimed quality" into "shown quality."

Property data sourced from public Zillow and Triad MLS listings.
