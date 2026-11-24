# The recurring loop (every ~3 days)

SEO is never finished — rankings move, competitors publish, facts go stale, and
Google updates. MugenSEO is designed to run as a recurring check-in so the site
keeps improving. The user asked for roughly every 3 days; any cadence works.

## How to set it up

Use whatever scheduling the host AI supports (a scheduled task / recurring job).
Create a task that re-invokes the MugenSEO workflow with the user's site and
chosen mode. If the host **can't** schedule, say so plainly and offer to run the
loop whenever the user comes back — don't pretend it's automated when it isn't.

**Each scheduled run must still respect the approval gate.** It may *prepare*
everything, but it must not apply changes to a live site without the user's
go-ahead — a scheduled run often has no one watching, so default to proposing and
waiting. The exception is read-only work (auditing, researching, drafting a
report), which is always safe to do unattended.

## What each run does (lightweight version of the full workflow)

1. **Re-audit the essentials** — re-check the technical checklist for regressions
   (new broken links, a page that slipped to `noindex`, Core Web Vitals changes,
   crawl errors in Search Console).
2. **Check Search Console / Bing trends** — what gained or lost impressions,
   clicks, or position since last time? Which queries are newly on page 2
   (opportunities)? Any manual actions or coverage issues (urgent)?
3. **Research freshness** — web-search the user's niche for new developments,
   news, questions, or competitor content worth responding to. Identify pages
   whose facts/stats are now out of date.
4. **Produce a short delta report** — "since last run: X improved, Y dropped,
   here are the 3 highest-impact things to do now," using the report template.
   Keep it short; this is a check-in, not a full re-audit essay.
5. **Wait for approval, then apply** the approved items (fixes, refreshed content,
   a new cluster post, re-submitted sitemap/URLs).

## Guardrails specific to the loop

- Never let the loop drift into black-hat territory to "show progress." No
  automated links, no scraping, no mass content. Slow, legitimate gains only.
- Don't republish/"freshen" a page by only changing the date — that's a
  manipulation Google can detect. Only update the date when the content genuinely
  changed.
- Track what was changed each run so improvements are attributable and reversible.
- If Search Console shows a drop after a change, investigate and be ready to roll
  back; correlation over several runs is more trustworthy than one data point.

## Reporting cadence

Keep a running log (a doc/artifact if the host supports it) so the user can see
the trajectory over weeks: what was changed, and how impressions/positions moved.
That long view — not any single run — is how you prove the program is working.
