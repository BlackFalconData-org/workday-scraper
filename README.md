# Workday Scraper

Extract structured data from [myworkdayjobs.com](https://myworkdayjobs.com) — job listings from any Workday-powered careers site. Extract titles, descriptions, salary, location, remote type, and more from myworkdayjobs.com company pages.

**[Run on Apify →](https://apify.com/blackfalcondata/workday-scraper)**

---

## Key features

🔍 **Smart search with filters**

Search by keyword, location, and multiple filters. Smart input resolution ensures you always get results.

📄 **Detail enrichment**

Fetch full job descriptions, salary data, employer profiles, and contact information for each listing.

🔄 **Incremental mode**

Only get new or changed listings since your last run. Content hash per listing — no duplicates, no re-processing.

⚡ **Compact output for AI agents**

Core-fields-only mode optimized for MCP and AI agent workflows. Description truncation to control output size.

---

## Use cases

**Data pipeline automation**
Integrate with your ETL pipeline to collect structured listings from myworkdayjobs.com on a schedule. Export to CSV, JSON, or directly to your database.

**Market research**
Monitor listings, track trends, and analyze market dynamics with structured, deduplicated data from myworkdayjobs.com.

**AI and LLM workflows**
Use compact mode and description truncation to feed data into AI agents, MCP servers, and LLM pipelines without exceeding token budgets.

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

| Product | Description |
|:--------|:------------|
| [StepStone Jobs API](https://github.com/BlackFalconData-org/stepstone-jobs-api) | Job listings from 18 European portals |
| [Company Jobs Tracker](https://github.com/BlackFalconData-org/company-jobs-tracker-api) | Track new/removed jobs per company |
| [Indeed Jobs Feed](https://github.com/BlackFalconData-org/indeed-jobs-feed) | Indeed job listings with salary data |
| [Glassdoor Jobs Feed](https://github.com/BlackFalconData-org/glassdoor-jobs-feed) | Glassdoor listings with company ratings |
| [Arbeitsagentur Jobs Feed](https://github.com/BlackFalconData-org/arbeitsagentur-jobs-feed) | Germany's federal job portal (1M+ listings) |
| [Naukri Jobs Feed](https://github.com/BlackFalconData-org/naukri-jobs-feed) | India's largest job portal |
| [Bilbasen Scraper](https://github.com/BlackFalconData-org/bilbasen-scraper) | Denmark's largest car marketplace |

---

*Last updated: 2026 03*
