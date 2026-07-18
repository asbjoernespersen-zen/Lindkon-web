# LINDKON — Technical Reconnaissance (PRELIMINARY)

> **Status: PRELIMINARY / MOSTLY BLOCKED.** The session's network egress policy
> denies all requests to lindkon.com (and archive.org), so no headers, HTML, CSS,
> JS, or Lighthouse data could be collected. Findings below are limited to what
> URL structures and index data prove or strongly imply. Every item marked
> *(inferred)* needs confirmation from a live crawl.

## 1. Platform / CMS

| Aspect | Finding | Evidence | Confidence |
|---|---|---|---|
| CMS | **WordPress** | `wp-content/uploads/2024/07/…` upload path | High |
| E-commerce layer | **WooCommerce** (Danish permalink bases) | `/vare/{sku}/` product URLs and `/vare-kategori/…/` category archives — WooCommerce's translated `product`/`product-category` bases | High |
| Theme / page builder | UNKNOWN — determine from HTML (`wp-content/themes/…`), likely a builder (Elementor/Divi/WPBakery) *(inferred)* | — | — |
| Predecessor platform | **ASP.NET site** (pre-migration) | `.aspx` URLs + `/CustomerData/Files/Folders/…` file paths still indexed | High |
| Migration hygiene | Incomplete redirect strategy suspected: legacy URLs and `http://` variants still indexed | Index entries for `.aspx` pages and `http://lindkon.com/folie/` | Medium |

## 2. Hosting & delivery

- Host/CDN, server headers, HTTP version, compression, TLS details: **BLOCKED** —
  collect via `curl -I`, `dig`, and header inspection when access is granted.
- Both `lindkon.com` and `www.lindkon.com` resolve publicly; canonical host in the
  index is the apex `lindkon.com` — confirm the www→apex redirect chain.

## 3. Frontend, assets, performance

- CSS/JS architecture, jQuery/plugin payloads, image formats (JPEG vs WebP/AVIF),
  lazy-loading, font loading: **BLOCKED**.
- WordPress+WooCommerce with a page builder typically implies many render-blocking
  assets — Lighthouse (desktop+mobile) runs are planned for: home, /skilte/,
  /stativer/, one /vare/ product page, /kontakt/. **BLOCKED** in this session.

## 4. SEO observations possible from the index

| Observation | Detail | Severity |
|---|---|---|
| Site-wide boilerplate meta description suspected | The same snippet ("leading supplier of banners, stands, signs and large stickers…") is returned for the homepage, product pages, and even both PDFs — suggests many pages lack unique meta descriptions | High |
| Legacy `.aspx` URLs still indexed | At least 4 legacy pages + 1 legacy PDF path | Medium |
| Mixed protocol/host variants indexed | `http://lindkon.com/folie/`, `http://www.lindkon.com/...` alongside `https://lindkon.com/...` | Medium |
| Title tag conventions inconsistent | `–` vs `|` vs `-` separators; casing "Om lindkon" | Low |
| Danish-only content | No hreflang/language variants observed in index; fine if intended, but Outsourcing targets "Danish and foreign companies" — consider EN page in redesign (owner decision) | Info |
| robots.txt / XML sitemap | **BLOCKED** — could not be fetched | — |

## 5. Analytics, tracking, consent

- **BLOCKED.** To collect when access granted: GA4/Gtag/Matomo scripts, Meta pixel,
  cookie-consent platform (CookieBot/Complianz/CookieYes etc.), and whether consent
  is obtained *before* trackers fire (GDPR — Danish practice per Datatilsynet).
- No privacy-policy or cookie-policy page appears in the index at all — flag:
  either not indexed (noindex) or missing; must be verified.

## 6. Forms

- **BLOCKED.** Expect at minimum a contact form on /kontakt/ (plugin —
  CF7/Gravity/WPForms — TBD), plus possible quote-request CTAs on product pages.
  Verify spam protection, success handling, and where submissions go.

## 7. Accessibility

- **BLOCKED.** Planned checks: colour contrast (esp. any red accent on navy),
  alt texts, heading order, keyboard navigation, focus states, form labels,
  Danish `lang` attribute, touch-target sizes on mobile.

## 8. Checklist for the unblocked re-run

1. `robots.txt`, `wp-sitemap.xml`/`sitemap_index.xml`, full BFS crawl of internal links.
2. Response headers (server, cache, CDN, HSTS), redirect chains (http/https, www/apex, legacy .aspx).
3. `wp-content` fingerprinting: theme, builder, plugin slugs, WP/WooCommerce versions in asset query strings.
4. Full asset harvest from `/wp-content/uploads/` referenced by pages (logo first).
5. Lighthouse desktop+mobile on 5 representative pages; Core Web Vitals.
6. axe-core accessibility pass on the same pages.
7. Tracking/consent inventory from rendered DOM (Playwright).
