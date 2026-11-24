# Generating and validating sitemap.xml and robots.txt

These two files control how search engines crawl and index the site. Getting
them wrong (e.g. blocking the whole site) is one of the most common and most
damaging SEO mistakes, so generate carefully and validate.

## robots.txt

Lives at the domain root: `https://example.com/robots.txt`. It tells crawlers
what they may crawl and points to the sitemap. It does **not** stop indexing —
use a `noindex` meta tag for that.

Sensible default (allow everything, point to sitemap):

```
User-agent: *
Allow: /

Sitemap: https://example.com/sitemap.xml
```

Rules of thumb:
- **Never `Disallow: /`** on a site you want ranked — it blocks the whole site.
- Only disallow genuinely private/duplicate areas (e.g. `/cart`, `/admin`,
  internal search results). Don't disallow CSS/JS the page needs to render.
- Blocking a page in robots.txt does **not** remove it from the index and can
  even leave a URL-only listing; to keep a page out of search, allow crawling but
  add `noindex`.
- Always reference the sitemap with its absolute URL.
- About AI crawlers: you *can* allow or disallow bots like `GPTBot`, `ClaudeBot`,
  `PerplexityBot`, `Google-Extended`. Explain the trade-off to the user —
  blocking them can reduce AI-answer visibility; it's their call. (This is also
  where a tarpit like Mugen complements SEO: SEO invites the crawlers you want,
  the tarpit traps the hostile ones.)

A ready template is in `templates/robots.txt`.

## sitemap.xml

An XML list of the canonical URLs you want indexed, at
`https://example.com/sitemap.xml`. Helps search engines discover pages and know
when they changed.

Minimal valid structure:

```
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://example.com/</loc>
    <lastmod>2026-01-15</lastmod>
  </url>
  <url>
    <loc>https://example.com/blog/my-post</loc>
    <lastmod>2026-01-20</lastmod>
  </url>
</urlset>
```

Rules of thumb:
- **Canonical URLs only** — one per page, matching the canonical tag, HTTPS,
  no `noindex` pages, no redirects, no 404s.
- Keep `<lastmod>` accurate (engines use it; a fake "everything changed today"
  erodes trust).
- `<changefreq>` and `<priority>` are largely ignored — fine to omit.
- Max 50,000 URLs / 50 MB per file; beyond that, split and use a sitemap index.
- For big or frequently-changing sites, generate it from the live list of pages
  rather than hand-maintaining it.

A ready template is in `templates/sitemap.xml`.

## After generating

1. Validate: the XML must be well-formed; robots.txt must not block what you want
   indexed. (Google Search Console has a robots.txt tester and a sitemap report.)
2. Place both at the domain root.
3. **Submit the sitemap** in Search Console and Bing Webmaster (see
   `search-console-bing.md`), and request indexing of important new/changed URLs.
