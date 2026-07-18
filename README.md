# LINDKON Website Redesign — Audit Project

This repository contains the evidence-based audit of the existing public website
**https://www.lindkon.com** (LINDKON aps, Aabybro, Denmark), performed as the first
phase of a complete redesign project.

**Scope guard:** This project is strictly a redesign audit of the current corporate
website. No webshop, customer portal, QR platform, AI assistant, or online designer
is in scope. LINDKON is a manufacturer/supplier of physical products (large-format
print, signs, banners, steel stands, foil, flags) and the site must present and sell
those products. No changes are made to the live website or its source.

## ⚠️ Current status: AUDIT BLOCKED — network egress denied

The remote session that produced this initial commit **cannot reach lindkon.com**:

- The container's egress proxy denies `CONNECT` to `lindkon.com:443` and
  `www.lindkon.com:443` (HTTP 403 — organisation/session network policy).
- The harness-side `WebFetch` tool also receives HTTP 403 for every lindkon.com URL.
- `archive.org` / `web.archive.org` are likewise not on the network allowlist,
  so archived copies could not be used as a fallback.

**Consequently only search-engine index data could be used.** Everything in `docs/`
is marked **PRELIMINARY** and derived from indexed titles, snippets, and URLs —
not from the live pages. No assets could be downloaded, no screenshots captured,
no Lighthouse runs performed.

### How to unblock

In the Claude Code environment's **network egress settings**, allow at least:

- `lindkon.com`
- `www.lindkon.com`
- (optional, useful fallback) `web.archive.org`, `archive.org`

Then re-run the audit task; the structure below is ready to receive the full data.

## Repository layout

| Path | Purpose |
|---|---|
| `docs/CURRENT_SITE_AUDIT.md` | Master audit document (preliminary) |
| `docs/CURRENT_SITEMAP.md` | Sitemap reconstructed from the search index |
| `docs/CONTENT_INVENTORY.csv` | Page-by-page inventory (preliminary) |
| `docs/ASSET_INVENTORY.csv` | Asset catalogue (only index-known assets so far) |
| `docs/DUPLICATES_AND_INCONSISTENCIES.md` | Duplicates, contradictions, legacy remnants |
| `docs/TECHNICAL_AUDIT.md` | Technical reconnaissance (what is inferable so far) |
| `docs/RESPONSIVE_VISUAL_AUDIT.md` | Visual/responsive audit (blocked — plan only) |
| `docs/OPEN_QUESTIONS_FOR_OWNER.md` | Questions for the site owner |
| `docs/AUDIT_SUMMARY.md` | Executive summary incl. limitations |
| `audit/assets/` | Downloaded public assets (empty — blocked) |
| `audit/screenshots/` | Full-page screenshots per page/viewport (empty — blocked) |
| `audit/crawl/` | Raw crawl data (empty — blocked; contains index-derived URL list) |

## Brand facts (given, for the later redesign — not applied yet)

- Primary brand colour: dark navy blue; white as key background; red as controlled accent.
- The actual LINDKON logo must be preserved (never recreated or approximated).
- Product-focused site; excellent desktop/tablet/mobile behaviour required.
- Motion/parallax only in support of products; result must not feel like a generic template.
