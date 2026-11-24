# Technical SEO audit checklist

Work through this in Phase 2. For each item, record: pass/fail, severity
(critical / high / medium / low), the specific page(s), and the fix. Critical
items are ones that can stop a page ranking at all.

## Crawlability & indexing (critical first)

- [ ] **robots.txt** exists, is reachable at `/robots.txt`, and does **not**
      accidentally block important pages or the sitemap. (See `sitemap-robots.md`.)
- [ ] No unintended **`noindex`** meta tags or `X-Robots-Tag` headers on pages
      that should rank. A stray noindex is a common, invisible ranking killer.
- [ ] **XML sitemap** exists, lists canonical URLs only, is referenced in
      robots.txt and submitted in Search Console/Bing.
- [ ] **Canonical tags** are correct — each page points to its own canonical, and
      duplicates point to the primary version.
- [ ] No **orphan pages** (pages with no internal links to them).
- [ ] Important pages are within a few clicks of the homepage (flat architecture).

## HTTPS & security

- [ ] Whole site served over **HTTPS**; no mixed content; HTTP redirects to HTTPS.
- [ ] Valid, non-expired TLS certificate.

## Mobile & rendering

- [ ] **Mobile-first parity**: the mobile version has the same content and
      structured data as desktop (Google indexes mobile).
- [ ] Responsive, readable without zoom, tap targets not cramped.
- [ ] Content is present in the rendered HTML (critical content shouldn't depend
      on a click or heavy JS the crawler may not run).

## Core Web Vitals / page experience

Measure with **PageSpeed Insights** (free). Targets:

- [ ] **LCP** (Largest Contentful Paint) — good ≤ 2.5s. Fixes: optimize/compress
      the hero image, use modern formats (WebP/AVIF), preload the LCP asset,
      improve server response time.
- [ ] **INP** (Interaction to Next Paint) — good ≤ 200ms. Fixes: reduce and
      defer JavaScript, break up long tasks.
- [ ] **CLS** (Cumulative Layout Shift) — good ≤ 0.1. Fixes: set width/height on
      images and embeds, reserve space for ads/banners, avoid late-injected content.
- [ ] Test the **template**, not just one page — if the blog template is slow,
      every post is slow.

## On-page elements (per page)

- [ ] **Title tag**: unique, descriptive, includes the primary intent/keyword
      naturally, ~50–60 chars, most important words first.
- [ ] **Meta description**: unique, compelling, ~140–160 chars (it affects
      click-through even though it's not a direct ranking factor).
- [ ] **One H1** that matches the page's purpose; logical H2/H3 structure.
- [ ] **Image alt text** that describes the image (accessibility + image search).
- [ ] **Descriptive, stable URLs** (words not IDs; avoid changing them).
- [ ] **Internal links** with descriptive anchor text to related pages (builds
      topical authority and spreads link equity).

## Structured data

- [ ] Relevant **JSON-LD schema** present and valid (Article, FAQPage, HowTo,
      Product, Breadcrumb, Organization as fits). See `geo-ai-overviews.md` and
      `templates/`.
- [ ] Schema **matches visible content** (never mark up what isn't on the page).
- [ ] Validate with Google's Rich Results Test / Schema.org validator.

## Errors & housekeeping

- [ ] Fix **broken links** (internal and outbound) and **404s**; set up sensible
      301 redirects for moved pages (avoid redirect chains).
- [ ] Remove or consolidate **duplicate/thin content**.
- [ ] Check Search Console's **Indexing** and **Core Web Vitals** and **Manual
      Actions** reports for anything flagged.

## Output

Feed every failed item into the Phase 4 report, sorted by severity then by
effort, so the user fixes the highest-impact, lowest-effort things first.
