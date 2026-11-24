# Connecting and using Search Console & Bing Webmaster

These are the official, legitimate sources of ranking data and the proper way to
submit sitemaps and request indexing. **Always use these instead of scraping
Google results** (scraping for rank-checking is against Google's rules).

## Google Search Console (GSC)

The free dashboard every site should have. It shows which queries you appear for,
impressions, clicks, average position, indexing status, Core Web Vitals, manual
actions, and more. It has an official **Search Console API** for programmatic
access — view/add/remove properties and sitemaps, query Search-results data, and
run URL inspection. API access requires the appropriate permission (owner, full,
or read) on the property, so the **user must own/verify the site** first.

### Getting the user set up (walk them through it)

1. Go to **search.google.com/search-console** and add the site as a property
   (Domain property is best; needs a DNS TXT record to verify. URL-prefix is
   simpler; can verify via an HTML file, meta tag, or Google Analytics).
2. Verify ownership (you can generate the HTML verification file or meta tag for
   them; they place it, then click Verify).
3. **Submit the sitemap** under Sitemaps → enter `sitemap.xml`.
4. Use **URL Inspection** to request indexing of important new/changed pages.

### Using the data (the honest rank tracker)

Pull the **Performance** report (or the API's Search Analytics) for: top queries,
pages, average position, and click-through rate. The best content targets are
queries where the site ranks on page 2 (positions 11–20) with decent impressions
— small improvements there often jump to page 1. This replaces any need to scrape
Google.

If the host AI has a connector/browser the user has authenticated, read this data
through it; otherwise have the user paste a Performance export. Never query Google
Search with automated scraping to fake this.

## Bing Webmaster Tools

Don't skip Bing — it matters more than its market share suggests because
**ChatGPT's web results lean on Bing's index**, so Bing visibility feeds a major
AI assistant. Bing Webmaster Tools is free and has its own **Bing Webmaster API**
to submit URLs and sitemaps and read your site's data.

### Setup

1. Go to **bing.com/webmasters**, add the site (you can **import** directly from
   Google Search Console to save time), and verify.
2. Submit the sitemap.
3. Use **URL submission** to push important URLs (Bing is generous with direct
   URL submission via IndexNow).

## IndexNow (bonus, legitimate)

IndexNow lets you instantly notify Bing (and other participating engines) when
URLs are added/updated/deleted, instead of waiting for a crawl. It's a simple,
approved protocol — worth enabling for fast indexing of changes.

## What to report back to the user

After connecting, summarize: how many pages are indexed, any coverage/manual-action
issues, Core Web Vitals status, and the top 10–20 query opportunities (page-2
rankings to push to page 1). That summary drives the content and fix priorities
in the main workflow.
