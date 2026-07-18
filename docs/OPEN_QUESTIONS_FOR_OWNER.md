# LINDKON — Open Questions for the Owner

> Questions the site owner must answer before (or early in) the redesign.
> Items marked ⚠ are also blockers for completing this audit.

## Audit blockers

1. ⚠ **Network access:** The audit environment cannot reach lindkon.com (egress
   policy denies it). Please allow `lindkon.com` + `www.lindkon.com` (and ideally
   `web.archive.org`) in the Claude Code environment's network settings so the
   full crawl, asset download, screenshots, and Lighthouse runs can be executed.
2. ⚠ **Logo master files:** Where is the authoritative LINDKON logo (vector
   SVG/EPS/AI, plus any approved variants — light/dark/monochrome)? The audit can
   only harvest what the website serves; a print-quality master is likely needed.

## Facts to confirm (inconsistencies found)

3. How many factories are in the Czech network today — **~40, ~50, or >50**?
   The site currently states different numbers in different places.
4. Which address is current: **Industrivej 38** or **Industrivej 17A**, 9440 Aabybro?
   (External directories disagree; the on-page address will be verified in the crawl.)
5. Preferred phone formatting: `96 73 29 00` or `96 732 900`? One standard should
   be used site-wide.
6. Is **Lars Lindvang (40 95 90 06 / ll@lindkon.com)** still the intended contact
   for LINDKON SPORT, and should personal contacts appear on the public site at all?
7. Is the claim **"Denmark's cheapest prices on signs"** one you can substantiate
   and want to keep? (Marketing-law risk if not.)
8. The steel-stand page advertises **21 models** — is that count current?

## Content decisions

9. The **2018 product catalogue PDF** (on a legacy URL) — retire, replace, or update?
10. The newest ESG report on the site is **2023** — do 2024/2025 reports exist and
    should they be published?
11. Does a **Code of Conduct** document exist (mentioned in the project brief but
    not found in the search index)? Provide it if it should be on the site.
12. Should `/skilte/` and `/projektskiltning/` remain separate pages, or is
    consolidation acceptable? (Flagged only — no removal decided.)
13. The old ASP.NET pages (`/produkter/*.aspx`, `/digital-print/*.aspx`) are still
    indexed by Google — confirm they should permanently redirect to current pages.
14. Are there pages that intentionally exist but are unlinked (campaign/landing
    pages) that the crawl should include?
15. Which content is **must-preserve verbatim** (legal texts, certifications,
    Gold-AAA credit rating claim, history) vs. free to rewrite?

## Structure & audience

16. Who are the priority audiences to serve first on the homepage: estate agents,
    construction companies, sports clubs, outsourcing clients — in which order?
17. Outsourcing addresses "Danish and foreign companies" — is an **English version**
    of (parts of) the site wanted in the redesign?
18. Is the WooCommerce layer (`/vare/…`) intended as a browsable catalogue only?
    (The redesign scope explicitly excludes building a webshop; confirm current
    purchase/inquiry flow so it is preserved, not extended.)
19. Which forms exist today and where do submissions go (email inbox/CRM)?

## Brand

20. Confirm the brand palette details for later phases: exact **dark navy** and
    **red** values (from logo/graphic profile), and any typography standards.
21. Are there professional photo assets (products, production hall, employees)
    beyond what the website currently shows, e.g. from the 2019 factory build?
