# Data

All data files are excluded from this repository via `.gitignore` to protect client privacy.

To reproduce the analysis, export your own data from Google Search Console and Google Analytics 4 and place the CSV files in this folder.

---

## File list used

| File | Source | Description |
|------|--------|-------------|
| `gsc_pages.csv` | Google Search Console | Page-level search performance data |
| `gsc_queries.csv` | Google Search Console | Query-level search performance data |
| `ga4_landing_page.csv` | Google Analytics 4 | Landing page behavioral data |
| `aws_bedrock_queries.csv` | Google Search Console | Queries for the Amazon Bedrock page |
| `aws_updates_queries.csv` | Google Search Console | Queries for the AWS updates page |
| `paypal_in_nepal_queries.csv` | Google Search Console | Queries for the PayPal in Nepal page |
| `zoom_queries.csv` | Google Search Console | Queries for the Zoom product page |
| `zoom_troubleshoot_queries.csv` | Google Search Console | Queries for the Zoom troubleshoot guide |
| `zoom_discord_queries.csv` | Google Search Console | Queries for the Zoom vs Discord page |

---

## Schemas

### gsc_pages.csv
Exported from GSC → Search Results → Pages tab.

| Column | Type | Description |
|--------|------|-------------|
| `Top pages` | string | Full URL of the page |
| `Clicks` | integer | Number of clicks from search results |
| `Impressions` | integer | Number of times page appeared in search |
| `CTR` | string | Click-through rate (e.g. `1.23%`) |
| `Position` | float | Average search position |

---

### gsc_queries.csv
Exported from GSC → Search Results → Queries tab.

| Column | Type | Description |
|--------|------|-------------|
| `Top queries` | string | Search query text |
| `Clicks` | integer | Number of clicks for that query |
| `Impressions` | integer | Number of impressions for that query |
| `CTR` | string | Click-through rate (e.g. `1.23%`) |
| `Position` | float | Average search position for that query |

---

### ga4_landing_page.csv
Exported from GA4 → Reports → Engagement → Landing page.

> Note: GA4 exports include metadata rows at the top. The notebook handles this automatically by detecting the header row.

| Column | Type | Description |
|--------|------|-------------|
| `Landing page` | string | Relative URL path (e.g. `/blogs/paypal-in-nepal`) |
| `Sessions` | integer | Total sessions starting on that page |
| `Active users` | integer | Users who had an engaged session |
| `New users` | integer | First-time users |
| `Average engagement time per session` | float | Avg. seconds spent per session |
| `Key events` | integer | Conversion events (if configured) |
| `Total revenue` | integer | Revenue attributed (if configured) |
| `Session key event rate` | float | Share of sessions with a key event |

---

### Page-level query files
Exported from GSC → Search Results → Pages tab → select a page → Queries tab.

Same schema as `gsc_queries.csv`. Each file corresponds to one specific page.

---

## Export instructions

### Google Search Console
1. Go to [search.google.com/search-console](https://search.google.com/search-console)
2. Select your property
3. Go to **Search Results** in the left sidebar
4. Set your date range
5. Click the **Pages** tab → Export → Download CSV → save as `gsc_pages.csv`
6. Click the **Queries** tab → Export → Download CSV → save as `gsc_queries.csv`
7. For page-level query files: click a page → switch to Queries tab → Export

### Google Analytics 4
1. Go to [analytics.google.com](https://analytics.google.com)
2. Select your property
3. Go to **Reports → Engagement → Landing page**
4. Set your date range
5. Click the Export icon → Download CSV → save as `ga4_landing_page.csv`