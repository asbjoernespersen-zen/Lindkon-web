# LINDKON — Duplicates, Inconsistencies & Suspicious Content (PRELIMINARY)

> **Status: PRELIMINARY.** Based on search-index evidence only (live site blocked
> by session network policy). Each item must be re-verified on the live pages.
> Nothing here is a removal decision — everything is flagged for owner review.

## 1. Factual inconsistencies found in indexed site text

| # | Topic | Conflicting values | Where seen | Severity |
|---|---|---|---|---|
| 1 | Number of factories in the Czech network | "about **40** modern factories" vs "about **50** factories" vs "more than **50** factories" | About-text snippets (~40) vs Outsourcing snippet (~50) vs homepage snippet (>50) | High — core credibility claim; one number must be agreed |
| 2 | Phone number formatting | `96 732 900` vs `96 73 29 00` | Different snippets/pages | Low — same number, inconsistent formatting; standardise |
| 3 | Company address | `Industrivej 38, 9440 Aabybro` vs `Industrivej 17A, 9440 Aabybro` | External directories (kompass vs 118.dk); on-site address NOT yet verified | Medium — confirm the current address shown on /kontakt/ and in footer |
| 4 | Brand casing | `LINDKON` vs `lindkon` ("Om lindkon" page title) vs `Lindkon` | Page titles | Low — standardise casing site-wide |
| 5 | Size notation in product titles | `50×70 cm.` (multiplication sign, space) vs `50x35cm.` (letter x, no space) | /vare/ product titles (e.g. st05070 vs li500-1) | Low — catalogue consistency |
| 6 | Title separator style | `–` dashes in most titles vs `\|` pipes on Flag page vs `-` hyphen on legacy pages | SEO titles | Low |
| 7 | Contact person routing | Generic `info@lindkon.com` / 96 732 900 on most pages vs personal `ll@lindkon.com` / 40959006 on Sport | /sport/ vs rest of site | Medium — confirm intended routing for redesign |

## 2. Duplicate / overlapping content (topic level)

| # | Overlap | Pages involved | Note |
|---|---|---|---|
| 1 | Construction-site signage covered twice | `/skilte/` and `/projektskiltning/` | Both target byggeplads/erhverv signage; check for duplicated copy and cannibalising SEO |
| 2 | Steel-stand content in three places | `/stativer/` (landing), `/vare-kategori/staalstativer/` (WooCommerce archive), individual `/vare/…` pages | Landing vs category archive may duplicate purpose; check canonicals |
| 3 | Legacy vs current product pages | `/produkter/stativer.aspx`, `/produkter/bannerstativer.aspx`, `/produkter/klistermaerke---folie.aspx`, `/digital-print/erhvervsmaeglere.aspx` vs current `/stativer/`, `/bannere/`, `/folie/` | Old ASP.NET pages still indexed — duplicate topics on two platforms |

## 3. Obsolete / suspicious content

| # | Item | Why suspicious | Action |
|---|---|---|---|
| 1 | Legacy ASP.NET URLs still indexed (`*.aspx`, `/CustomerData/...`) | Old site remnants; suggests missing or incomplete 301 redirects after WordPress migration | Verify whether they 404/redirect/serve; map 301s in redesign |
| 2 | Product catalogue PDF dated **2018-08** | 8 years old at audit time; hosted on legacy file path | Owner review: replace or retire |
| 3 | ESG report is for **2023** | Two ESG cycles behind by 2026 — newer report may exist offline | Ask owner for 2024/2025 report |
| 4 | "Denmark's cheapest prices on signs" claim | Superlative marketing claim; legal/marketing risk if unsubstantiated | Owner review before reuse |
| 5 | `21 forskellige modeller` (steel stands) in page title | Only 11 product URLs indexed; count may be stale | Verify against live catalogue |
| 6 | Mixed http/https index entries (`http://lindkon.com/folie/`) | Possible missing https canonical/redirect signals | Verify in technical crawl |
| 7 | Sports concept phone `40959006` (unformatted) | Formatting + verify person/number still current | Owner review |
| 8 | Facebook page `LINDKONaps` referenced externally | Social links on site not yet verified; check freshness of linked profiles | Verify in full crawl |

## 4. Pages possibly needing consolidation (flag only — no removals)

- `/skilte/` + `/projektskiltning/` — same audience/topic family.
- `/stativer/` + `/vare-kategori/staalstativer/` — landing vs archive.
- Legacy `.aspx` pages — consolidate into current equivalents via redirects.

## 5. To re-check when live access is available

- Footer vs Contact page vs Google Business data (address, CVR 27761577, phone).
- Whether the same intro paragraph ("leading supplier of banners, stands, signs…")
  is repeated across many pages (it appears in nearly every index snippet —
  possible site-wide boilerplate/duplicated meta description).
- Consent banner text vs actual trackers (see TECHNICAL_AUDIT.md).
