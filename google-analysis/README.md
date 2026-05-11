# Google Search Analytics Intelligence System

Cross-platform SEO and engagement analysis integrating Google Search Console and Google Analytics 4 to evaluate content performance across visibility, traffic, and engagement dimensions.

> Data files are excluded from this repository (see `data/`). The notebook documents all column names, data formats, and transformation steps needed to reproduce the analysis with your own exports.

---

## Overview

This project builds a page-level analytics pipeline that merges two datasets most teams analyze in isolation — search visibility data from GSC and behavioral data from GA4. The core question: Does a page that ranks well actually satisfy the users who find it?

The analysis covers **74 matched pages** from a well-reputed SAAS and IT Company in the Kathmandu Valley, over five months (Jan–May 2026), and surfaces specific content optimization opportunities grounded in integrated metrics rather than single-source reporting.

---

## Key features

### Data integration
Merges page-level exports from two sources with different URL formats (GSC exports full URLs; GA4 exports relative paths). A normalization pipeline handles domain stripping, lowercasing, and trailing slash removal before joining on the `Page` key.

**Google Search Console** — clicks · impressions · CTR · average position

**Google Analytics 4** — sessions · active users · new users · avg. engagement time · conversion signals

### Engineered metrics

| Metric | Formula | What it reveals |
|--------|---------|----------------|
| `visibility_score` | `impressions × CTR` | Effective reach weighted by click likelihood |
| `click_to_session_ratio` | `ga_sessions / gsc_clicks` | Whether sessions come from organic search or other channels |
| `engagement_efficiency` | `ga_engagement_time / ga_sessions` | Content quality signal — time invested per visit |
| `engagement_per_session` | `ga_engagement_time` (per row) | Absolute engagement depth per page |

### Content classification

A rule-based classifier segments pages into four categories:

| Category | Criteria | What it means |
|----------|----------|---------------|
| High visibility / low engagement | impressions > 20,000 AND sessions < 100 | Ranks well, fails to satisfy intent |
| High quality content | avg. engagement time > 30s | Users investing meaningful time |
| High traffic driver | GSC clicks > 100 | Proven organic demand |
| Normal | All other pages | Baseline performers |

---

## Key findings

### The visibility–engagement gap

The highest-impression page on the site — `/blogs/aws-in-2026-latest-services-updates` at **80,547 impressions** — recorded only 17.7s average engagement time and an `engagement_efficiency` score of **0.03**. The `/zoom` product page, with 95% fewer impressions (4,076), recorded **74s average engagement time** and an `engagement_efficiency` of **1.14** — nearly 40× higher.

This pattern holds across the dataset: impression volume and engagement quality are weakly correlated, which has direct implications for where content investment should be directed.

### AWS content cluster

- 80,547 impressions · 29 GSC clicks · 592 GA4 sessions · 17.7s avg. engagement
- `click_to_session_ratio` of 20× indicates most sessions arrive from non-organic channels
- Low CTR (0.04%) despite top-10 average position suggests a title/meta mismatch with search intent

### Zoom content cluster

- `/zoom`: 74s avg. engagement · `engagement_efficiency` 1.14 · 107 GSC clicks from 4,076 impressions
- `/blogs/zoom-not-working-troubleshoot-guide`: 36.8s avg. engagement across 140 sessions
- Troubleshooting and product pages consistently outperform informational AWS content on engagement metrics — strong evidence of intent alignment

### PayPal in Nepal

- 349 GSC clicks · avg. position 4.46 · 257 sessions · 215 new users
- Near-threshold engagement time (29.6s) is consistent with high-intent informational queries where users find a direct answer quickly — not a signal of shallow engagement
- Highest organic click volume of any page; strong candidate for conversion path optimization

---

## Phase 2 — Query intent analysis

2,611 queries across 6 top pages were classified into five intent categories: Informational, Commercial, Troubleshooting, Transactional, and Local.

### Intent distribution by page

| Page | Dominant intent | Engagement efficiency |
|------|----------------|----------------------|
| /zoom | Commercial | 1.14 |
| /blogs/zoom-not-working-troubleshoot-guide | Informational | 0.26 |
| /blogs/paypal-in-nepal | Informational + Local | 0.12 |
| /blogs/simple-comparison-of-zoom-vs-discord | Commercial | 0.04 |
| /blogs/aws-in-2026-latest-services-updates | Informational | 0.03 |
| /blogs/amazon-bedrock-aws-ai-platform-guide | Informational | 0.03 |

### Key insight — same intent, different outcomes

Both `/zoom` and `/blogs/simple-comparison-of-zoom-vs-discord` are dominated by Commercial intent queries, yet their engagement efficiency scores differ by 27×. This demonstrates that intent classification alone doesn't predict performance — content structure and specificity determine whether intent is actually satisfied.

`/blogs/paypal-in-nepal` stands out for its strong Local intent signal (143 queries containing geographic qualifiers), explaining its high click volume and new user rate despite modest engagement time.

### Content performance quadrant

Plotting impressions against engagement efficiency reveals four distinct performance zones. Bubble size represents session volume.

![Content Performance Quadrant](output/charts/quadrant_plot.png)

---

## Project structure

```text
seo-analytics-intelligence-system/
│
├── data/                           # excluded via .gitignore
│   ├── gsc_pages.csv
│   ├── gsc_queries.csv
│   ├── ga4_landing_page.csv
│   ├── aws_bedrock_queries.csv
│   ├── aws_updates_queries.csv
│   ├── paypal_in_nepal_queries.csv
│   ├── zoom_queries.csv
│   ├── zoom_troubleshoot_queries.csv
│   └── zoom_discord_queries.csv
│   └── README.md                   # data schema and export instructions
│
├── notebooks/
│   └── analysis.ipynb              # full pipeline: cleaning → merging → KPIs → classification
│
├── output/
│   └── charts/
│
├── .gitignore
├── LICENSE
├── README.md 
└── requirements.txt
```

---

## Setup

```bash
git clone https://github.com/sonaml-007/SEO-Analysis.git
cd SEO-Analysis
pip install -r requirements.txt
python -m notebook
```

To reproduce the analysis, export your own GSC (Pages report) and GA4 (Landing pages report) CSVs and place them in `data/raw/`. Column names and expected formats are documented in `data/README.md`.

---

## Tech stack

| Tool | Purpose |
|------|---------|
| Python | Data processing |
| Pandas | Data cleaning, merging, feature engineering |
| Jupyter Notebook | Exploratory analysis and documentation |
| VS Code | Development environment |
| Git & GitHub | Version control |

---

## Future improvements

- Opportunity scoring — combine visibility, engagement efficiency, CTR, and position into a single prioritization score per page
- Ahrefs / SEMrush keyword integration for external competition data
- NLP-based intent classification to replace rule-based keyword matching
- Automated GSC + GA4 merge pipeline for monthly reporting
- Executive dashboard layer

---

## Author

**Sonam Lama** 
