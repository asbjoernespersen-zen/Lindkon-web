# LINDKON — Current Site Audit (Master Document)

> **Status: PRELIMINARY — AUDIT BLOCKED BY NETWORK POLICY.**
> Date: 2026-07-18. Source of evidence: search-engine index only (titles, URLs,
> snippets). The session's egress policy denies all connections to lindkon.com
> (and to archive.org as fallback), so pages, assets, screenshots, headers, and
> Lighthouse data could not be collected. See README.md for the unblock steps.
> Everything below is honestly labelled by confidence; nothing has been altered
> on the live site.

## 1. What the site is (verified via index)

- **Company:** LINDKON aps, Industrivej, 9440 Aabybro (NW of Aalborg), Denmark.
  CVR 27761577. Founded 28 May 2004; owner Lars K. Lindvang (100% via LKL Holding
  Invest ApS); Czech production network started 1 Jan 1998; own 1,100 m² factory
  since late 2019; Gold-AAA credit rated. (Company facts partly from public
  registries; on-site wording to be verified.)
- **Business:** Manufacturer/supplier of physical large-format print and signage
  products — banners, signs, steel stands, pavement signs, foil/stickers, flags,
  project signage — plus an outsourcing service for technical steel goods via
  ~40–50 Czech factories (number inconsistent on site), and a sports-club
  signage concept (LINDKON SPORT).
- **Language:** Danish only (as indexed).
- **Tagline:** "Kvalitetsbevidst og frem for alt ordentlige!" (homepage title).

## 2. Phase status

| Phase | Status | Notes |
|---|---|---|
| 1 — Crawl & inventory | **Partial** | 14 main pages + 11 product pages + 1 category archive + 5 legacy URLs identified from index; per-page fields (H1s, images, forms, links) NOT collectable |
| 2 — Asset collection | **Blocked** | 0 assets downloaded; 2 PDFs identified by URL; logo not yet retrievable |
| 3 — Visual documentation | **Blocked** | 0 screenshots; capture plan prepared in RESPONSIVE_VISUAL_AUDIT.md |
| 4 — Technical reconnaissance | **Partial** | WordPress + WooCommerce confirmed from URL structure; ASP.NET predecessor confirmed; everything else blocked |
| 5 — Content & structure audit | **Partial** | Preliminary sitemap, hierarchy, duplicates and inconsistencies from index evidence |

## 3. Site structure (summary — full detail in CURRENT_SITEMAP.md)

- **Home** → 7 product/solution pages (Skilte, Bannere, Stativer, Gadesælgere,
  Folie, Flag, Projektskiltning) → WooCommerce catalogue (`/vare-kategori/`,
  `/vare/{sku}`) for at least steel stands.
- **Company pages:** Outsourcing, Sport, Going Green, Om LINDKON, Kontakt.
- **Legacy layer:** at least 4 ASP.NET pages + 1 legacy PDF path still indexed.

## 4. Content hierarchy (preliminary)

```
Products (physical, core)
├── Skilte (signs) ── overlaps → Projektskiltning
├── Bannere (PVC / MESH, rail systems)
├── Stålstativer ── /vare-kategori/staalstativer/ ── 11+ /vare/ SKUs (site claims 21)
├── Gadesælgere / A-bukke
├── Folie (oneway, 3-layer, floor/window stickers)
└── Flag (beachflag: shark fin & drop; kioskflag)

Services / segments
├── Outsourcing (steel goods, Czech network) — B2B service
└── LINDKON SPORT (club signage concept)

Company
├── Om LINDKON (history, quality, credit rating)
├── Going Green (environment; ESG Rapport 2023 PDF)
└── Kontakt
```

## 5. Key findings so far (evidence-based)

1. **The audit itself is blocked** — no network route to lindkon.com from this
   environment; this is the single most important issue to resolve.
2. **Platform:** current site is WordPress + WooCommerce (Danish `vare` permalinks);
   the previous site was ASP.NET and its URLs are still in Google's index —
   migration redirects appear incomplete.
3. **Factual inconsistency on a core claim:** the Czech factory network is stated
   as ~40, ~50, and >50 in different indexed texts.
4. **SEO hygiene problems:** one boilerplate description appears to serve many
   pages (identical snippet returned for pages *and* PDFs); mixed http/https and
   www/apex variants indexed; inconsistent title conventions.
5. **Stale collateral:** newest indexed catalogue PDF is from 2018 (on a legacy
   URL); newest ESG report is 2023.
6. **Catalogue depth is thin in the index:** 11 of a claimed 21 steel-stand models
   indexed; other product families (banners, flags, foil) show no `/vare/` SKUs
   at all — either not in WooCommerce or not indexed.
7. **Contact routing is inconsistent:** generic info@/96 732 900 everywhere except
   Sport (personal ll@/40 95 90 06); phone formats vary.
8. **No privacy/cookie/terms pages appear in the index** — they may exist with
   noindex, or be missing; must be verified (GDPR relevance).
9. **No English content** despite outsourcing targeting foreign companies.
10. **Product focus is real and must be preserved:** the site sells concrete
    physical products with model numbers, sizes, and stock/delivery statements
    ("in stock, delivery 1–2 business days") — the redesign must keep this
    concreteness (per project scope).

## 6. Content that must be preserved (initial list — owner to confirm)

- The actual LINDKON logo (asset not yet retrievable — mandatory, never recreate).
- Product data: SKUs (ST04834, ST04060, ST05070, ST06030, ST06040D, ST07050D,
  ST10060D, ST08834, LI500-1, …), sizes, materials (hot-galvanised steel, Ø10/22/32 mm),
  stock/delivery statements.
- Company history facts (1998 network, 2004 founding, 2019 factory) — after the
  factory-count figure is corrected.
- Gold-AAA credit-rating claim (verify currency), CVR, address, contact details.
- ESG Rapport 2023 (and successors), any Code of Conduct.
- Tagline "Kvalitetsbevidst og frem for alt ordentlige!" (owner to confirm).

## 7. Content requiring owner review before reuse

- "Denmark's cheapest prices" superlative.
- Factory-count figure (pick one).
- 2018 product catalogue.
- Personal contact details on public pages.
- All legacy .aspx content (retire + redirect).

## 8. Next steps

1. Owner/admin allows lindkon.com in the environment's network egress settings.
2. Re-run: full BFS crawl → complete CONTENT_INVENTORY.csv; harvest all assets
   into `audit/assets/` → complete ASSET_INVENTORY.csv; Playwright screenshots at
   1440/768/390 into `audit/screenshots/`; Lighthouse + axe on representative
   pages → complete TECHNICAL_AUDIT.md and RESPONSIVE_VISUAL_AUDIT.md.
3. Owner answers OPEN_QUESTIONS_FOR_OWNER.md.
4. Only after audit review/approval: begin structure and design work (out of scope
   for this phase).
