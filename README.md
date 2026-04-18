# Workday Scraper

Extract structured data from [myworkdayjobs.com](https://myworkdayjobs.com) — job listings from any Workday-powered careers site. Extract titles, descriptions, salary, location, remote type, and more from myworkdayjobs.com company pages.

**[Workday Scraper - Corporate Career Sites on Apify →](https://apify.com/blackfalcondata/workday-scraper?fpr=1h3gvi)**

---

## Key features





**Search with filters** — Search by keyword and location.

**Detail enrichment** — Fetch full job descriptions, salary data, contact information for each listing.

**Incremental mode** — Only get new or changed listings since your last run. Content hash per listing — no duplicates, no re-processing.

**Change classification** — Track cross-run repost detection across runs. Build audit trails of how listings evolve over time.

**Compact output** — Emit core fields only (AI-agent / MCP-friendly). Keeps response size small for LLM workflows.

**Description truncation** — Cap description length per listing to control output size and cost.

**Result cap** — Stop after N listings (up to 5.000). Set to 0 for the full catalog.

**Export anywhere** — Download as JSON, CSV, or Excel. Stream via Apify API, webhooks, or integrations with Make, Zapier, Airbyte, Keboola.

**Structured data** — Every listing returns the same schema with consistent field naming. All fields always present — `null` when unavailable, never omitted.

---

## Use cases





**Data pipeline automation**
Integrate with your ETL pipeline to collect structured listings from myworkdayjobs.com on a schedule. Export to CSV, JSON, or directly to your database. Use compact mode to control output size.

**Market research**
Monitor listings, track trends, and analyze market dynamics with structured, deduplicated data from myworkdayjobs.com.

**Change monitoring**
Run daily or hourly in incremental mode to capture only new, updated, or expired listings. Perfect for price-tracking, churn analysis, and alerting pipelines.

**Lead generation**
Extract employer contact details alongside listings to build outreach lists for recruiters, staffing agencies, or B2B sales teams.

**AI / LLM training data**
Structured JSON per listing is ready for RAG pipelines, embeddings, and agent workflows. Compact mode trims tokens for LLM context windows.

---

## Quick start

```json
{
  "query": "software engineer",
  "maxResults": 50,
  "includeDetails": true
}
```

---

## Input parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `companyUrl` | string | — | Workday careers page URL (e.g. https://workday.wd5.myworkdayjobs.com/en-US/Workday). |
| `query` | string | — | Job search keywords. Leave empty for all jobs. |
| `remoteType` | string | — | Filter by work arrangement (e.g. Remote, Onsite, Flex, Hybrid). Matched against the company's available options. |
| `timeType` | string | — | Filter by time type (e.g. Full Time, Part Time). |
| `jobCategory` | string | — | Filter by job family/category (e.g. Engineering, Marketing). Matched against the company's categories. |
| `maxResults` | integer | `50` | Maximum total results (0 = unlimited). |
| `includeDetails` | boolean | `true` | Fetch full job details (description, company, salary, etc.). |
| `descriptionMaxLength` | integer | `0` | Truncate description to N chars. 0 = no truncation. |
| `compact` | boolean | `false` | Core fields only (for AI-agent/MCP workflows). |
| `incrementalMode` | boolean | `false` | Only output new/changed jobs compared to the previous run. |
| `stateKey` | string | — | Stable identifier for tracking universe. Defaults to tenant name. |

---

## FAQ

<!-- WRITE: 4-6 Q&A pairs relevant to this product -->

**Is it legal to scrape myworkdayjobs.com?**
Web scraping of publicly available data is generally legal. This actor only accesses publicly visible information. Always check the target site's terms of service for your specific use case.

**How does incremental mode work?**
Each listing gets a content hash. On subsequent runs, only new or changed listings are emitted — saving time, compute, and storage.

---

## Known limitations

<!-- WRITE: 4-6 honest limitations -->

- <!-- WRITE: limitation 1 -->
- <!-- WRITE: limitation 2 -->


## Output fields

Every listing returns the same 20-field schema. Missing values are `null` — never omitted.

- `jobId`
- `title`
- `company`
- `location`
- `country`
- `countryCode`
- `description`
- `employmentType`
- `remoteType`
- `jobReqId`
- `postedDate`
- `applicationDeadline`
- `applyUrl`
- `contactEmail`
- `contactPhone`
- `portalUrl`
- `salaryText`
- `scrapedAt`
- `source`
- `changeType`


## Sample output

One object per listing. Here is a real example from a production run:

```json
{
  "jobId": "921ca094cc84d530247c6ef4b267c338ceda4c76aa93f42f0680470be28f6829",
  "title": "Software Engineer/Data Engineering",
  "company": "Workday, Inc.",
  "location": "New Zealand, Auckland",
  "country": "New Zealand",
  "countryCode": "NZ",
  "description": "Your work days are brighter here.\n\nWe’re obsessed with making hard work pay off, for our people, our customers, and the world around us. As a Fortune 500 company and a leading AI p…",
  "employmentType": "Full Time",
  "remoteType": "Flex",
  "jobReqId": "JR-0103130",
  "postedDate": "2026-03-22",
  "applicationDeadline": null
}
```

*Truncated — full records contain 20 fields. See Output fields for the complete schema.*


**[Try Workday Scraper - Corporate Career Sites now — $5 free credit, no credit card →](https://apify.com/blackfalcondata/workday-scraper?fpr=1h3gvi)**


## Pricing

Pay only for what you extract. No subscription required — Apify's free $5 credit covers thousands of results.

| Event | Price (USD) |
| --- | --- |
| Actor Start | $0.005 |
| Result | $0.002 |

See the [actor on Apify](https://apify.com/blackfalcondata/workday-scraper?fpr=1h3gvi) for current pricing.

---

## Related products by Black Falcon Data





- [StepStone Scraper](https://apify.com/blackfalcondata/stepstone-scraper?fpr=1h3gvi) — Job listings from 18 European portals
- [Indeed Job Scraper](https://apify.com/blackfalcondata/indeed-job-scraper?fpr=1h3gvi) — Indeed job listings with salary data
- [Glassdoor Job Scraper](https://apify.com/blackfalcondata/glassdoor-job-scraper?fpr=1h3gvi) — Glassdoor listings with company ratings
- [Arbeitsagentur Scraper](https://apify.com/blackfalcondata/arbeitsagentur-scraper?fpr=1h3gvi) — Germany's official job portal (1M+ listings)
- [SEEK Scraper](https://apify.com/blackfalcondata/seek-scraper?fpr=1h3gvi) — Australia & NZ's largest job board
- [Naukri Scraper](https://apify.com/blackfalcondata/naukri-scraper?fpr=1h3gvi) — India's largest job portal


## Getting started with Apify

New to Apify? [Create a free account with $5 credit](https://console.apify.com/sign-up?fpr=1h3gvi) — no credit card required.

1. [Sign up free](https://console.apify.com/sign-up?fpr=1h3gvi) — $5 credit included
2. Open the actor and paste your input
3. Click Start — results download as JSON, CSV, or Excel

Need more volume? [See pricing](https://apify.com/pricing?fpr=1h3gvi).

---


## About Black Falcon Data

Black Falcon Data builds production-grade web scrapers for job boards and marketplace data. Browse our full actor catalog at [www.blackfalcondata.com](https://www.blackfalcondata.com).

---
---

*Last updated: 2026 03*
