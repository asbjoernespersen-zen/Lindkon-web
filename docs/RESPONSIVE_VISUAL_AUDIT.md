# LINDKON — Responsive & Visual Audit (BLOCKED — PLAN ONLY)

> **Status: BLOCKED.** No screenshots could be captured: the session's network
> egress policy denies all requests to lindkon.com, so Playwright/Chromium cannot
> load the site. This document records the exact capture plan so the audit can be
> executed immediately once access is granted. **No visual findings are claimed.**

## Capture matrix (to execute)

Viewports: **1440 px (desktop), 768 px (tablet), 390 px (mobile)** — full-page
screenshots, stored as `audit/screenshots/<page-slug>/<width>.png`.

| Page | URL | 1440 | 768 | 390 |
|---|---|---|---|---|
| Homepage | https://lindkon.com/ | ☐ | ☐ | ☐ |
| Product overview / catalogue | (identify: nav "Produkter" target or /vare-kategori/…) | ☐ | ☐ | ☐ |
| Skilte | https://lindkon.com/skilte/ | ☐ | ☐ | ☐ |
| Bannere | https://lindkon.com/bannere/ | ☐ | ☐ | ☐ |
| Stativer | https://lindkon.com/stativer/ | ☐ | ☐ | ☐ |
| Gadesælgere / A-bukke | https://lindkon.com/gadesaelgere/ | ☐ | ☐ | ☐ |
| Folie | https://lindkon.com/folie/ | ☐ | ☐ | ☐ |
| Flag / Beachflag | https://lindkon.com/flag/ | ☐ | ☐ | ☐ |
| Projektskiltning | https://lindkon.com/projektskiltning/ | ☐ | ☐ | ☐ |
| Outsourcing | https://lindkon.com/outsourcing/ | ☐ | ☐ | ☐ |
| Sport | https://lindkon.com/sport/ | ☐ | ☐ | ☐ |
| Going Green | https://lindkon.com/going-green/ | ☐ | ☐ | ☐ |
| Om LINDKON | https://lindkon.com/om-lindkon/ | ☐ | ☐ | ☐ |
| Kontakt | https://lindkon.com/kontakt/ | ☐ | ☐ | ☐ |
| One representative product detail | https://lindkon.com/vare/st10060d/ | ☐ | ☐ | ☐ |

Also capture: cookie banner state (before/after consent), mobile menu open state,
and any hover/dropdown navigation on desktop.

## Issue checklist to evaluate per page (from the project brief)

- Broken layouts at any of the three widths
- Unnecessary repetition of sections/copy
- Weak visual hierarchy (headline vs body vs CTA)
- Inconsistent spacing rhythm
- Typography inconsistencies (families, sizes, weights, casing)
- Images with poor cropping or insufficient resolution (esp. product photos)
- Navigation problems (depth, labels, discoverability of product pages)
- Mobile usability (touch targets, text size, horizontal scroll, menu)
- Sections that appear duplicated across pages
- Missing or unclear calls to action (phone/email/quote)

## Hypotheses to verify (from index evidence only — NOT findings yet)

- Near-identical boilerplate intro copy may repeat across many pages
  (the same supplier sentence dominates every index snippet).
- Product pages may rely on generic contact CTAs ("call/email") rather than
  structured quote CTAs — check CTA clarity.
- Legacy content style may differ visibly between builder pages and WooCommerce
  templates (two visual systems on one site).
