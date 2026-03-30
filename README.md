# Workday Scraper

Extract structured data from [myworkdayjobs.com](https://myworkdayjobs.com) — job listings from any Workday-powered careers site. Extract titles, descriptions, salary, location, remote type, and more from myworkdayjobs.com company pages.

**[Workday Scraper on Apify →](https://apify.com/blackfalcondata/workday-scraper)**

---

## Key features



**Search with filters** — Search by keyword and location.

**Detail enrichment** — Fetch full job descriptions, salary data, contact information for each listing.

**Incremental mode** — Only get new or changed listings since your last run. Content hash per listing — no duplicates, no re-processing.

---

## Use cases



**Data pipeline automation**
Integrate with your ETL pipeline to collect structured listings from myworkdayjobs.com on a schedule. Export to CSV, JSON, or directly to your database. Use compact mode to control output size.

**Market research**
Monitor listings, track trends, and analyze market dynamics with structured, deduplicated data from myworkdayjobs.com.

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

---

## Related products by Black Falcon Data



- [StepStone Scraper](https://github.com/BlackFalconData-org/stepstone-scraper) — Job listings from 18 European portals
- [Indeed Job Scraper](https://github.com/BlackFalconData-org/indeed-job-scraper) — Indeed job listings with salary data
- [Glassdoor Job Scraper](https://github.com/BlackFalconData-org/glassdoor-job-scraper) — Glassdoor listings with company ratings

---

*Last updated: 2026 03*
