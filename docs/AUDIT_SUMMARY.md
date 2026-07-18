# LINDKON Redesign — Audit Summary (Executive)

**Date:** 2026-07-18 · **Status: PRELIMINARY — full audit blocked by network policy**

## TL;DR

The audit environment has **no network route to lindkon.com** (session egress
policy returns 403 for every request, from both the container and the harness
fetcher; archive.org is also blocked). The full evidence-based audit — page
crawl, asset downloads, screenshots at 1440/768/390 px, Lighthouse, accessibility
checks — **cannot be executed until `lindkon.com` and `www.lindkon.com` are added
to the environment's allowed network egress hosts.**

What *was* possible: a systematic sweep of the search-engine index, which yielded
a reliable page list, platform identification, two downloadable-document URLs,
and several genuine content inconsistencies. All deliverable documents have been
created and honestly labelled; blocked sections contain ready-to-execute plans.

## What we know (high confidence)

- **Site:** Danish-language corporate/product site for LINDKON aps (Aabybro):
  large-format print & signage products (signs, banners, steel stands, pavement
  signs, foil, flags, project signage) + outsourcing of technical steel goods via
  a Czech factory network + LINDKON SPORT club-signage concept.
- **Platform:** WordPress + WooCommerce (Danish `/vare/` product permalinks);
  predecessor ASP.NET site whose URLs are still in Google's index.
- **Inventory found:** 13 main pages, 1 product-category archive, 11 product
  detail pages, 4 legacy .aspx pages, 2 PDFs (ESG Rapport 2023; 2018 product
  catalogue on a legacy path).

## Ten most important findings

1. **Audit blocker:** lindkon.com unreachable from this environment — resolve first.
2. **Incomplete legacy migration:** old ASP.NET URLs (and a 2018 catalogue PDF on
   a legacy file path) still indexed — redirect strategy needed in redesign.
3. **Core-claim inconsistency:** Czech factory network stated as ~40, ~50, and
   >50 in different on-site texts.
4. **SEO hygiene:** apparent site-wide boilerplate meta description (same snippet
   for pages and PDFs); mixed http/https + www/apex variants indexed;
   inconsistent title separators and brand casing ("Om lindkon").
5. **Stale collateral:** newest catalogue is 2018; newest ESG report is 2023.
6. **Catalogue gap:** steel-stand page claims 21 models, only 11 SKUs indexed;
   other product families show no SKU pages at all.
7. **Inconsistent contact routing/formatting:** info@ + 96 732 900 vs personal
   ll@ + 40959006 (Sport); two phone formats; address discrepancy in external
   directories (Industrivej 38 vs 17A) to verify on-site.
8. **Legal/marketing risk:** "Denmark's cheapest prices on signs" superlative
   needs substantiation or removal (owner decision).
9. **No privacy/cookie/terms pages in the index** — verify existence (GDPR).
10. **Danish only**, though Outsourcing targets foreign companies — language
    strategy question for the owner.

## Deliverables created

- docs/CURRENT_SITE_AUDIT.md (master, preliminary)
- docs/CURRENT_SITEMAP.md (index-derived)
- docs/CONTENT_INVENTORY.csv (28 URLs, per-page fields where known)
- docs/ASSET_INVENTORY.csv (2 known PDFs; logo/media pending)
- docs/DUPLICATES_AND_INCONSISTENCIES.md (7 inconsistencies, 3 overlap groups, 8 suspicious items)
- docs/TECHNICAL_AUDIT.md (platform confirmed; re-run checklist)
- docs/RESPONSIVE_VISUAL_AUDIT.md (blocked; full capture matrix prepared)
- docs/OPEN_QUESTIONS_FOR_OWNER.md (21 questions)
- docs/AUDIT_SUMMARY.md (this file)
- audit/assets/, audit/screenshots/, audit/crawl/ (structured, empty pending access)

## Crawl limitations

- 100% of live-site requests blocked (egress policy), incl. robots.txt/sitemap.
- archive.org fallback also blocked.
- Search index only: no H1s, body copy, images, forms, internal links, headers,
  scripts, or performance data; unindexed pages invisible.

## Assets not downloaded

All of them — including, critically, the **LINDKON logo** (must be taken from the
live site, never recreated), all photography, and both identified PDFs.

## Before redesign begins

Answer docs/OPEN_QUESTIONS_FOR_OWNER.md — above all: unblock network access,
provide/confirm logo masters, settle the factory-count figure, confirm the
address, and decide on the superlative price claim. Then re-run the full audit.
No wireframes, design concepts, or production code have been created.
