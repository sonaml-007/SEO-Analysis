## Overview

This project is a cross-platform SEO analytics pipeline built using:

* Google Search Console (GSC)
* Google Analytics 4 (GA4)
* Python
* Pandas
* Jupyter Notebook

The objective of the project is to analyze the relationship between:

* Search visibility
* Organic traffic acquisition
* User engagement
* Content effectiveness

The analysis integrates page-level SEO metrics from GSC with behavioral engagement metrics from GA4 to identify:

* High-performing content clusters
* Visibility vs engagement mismatches
* Potential content optimization opportunities
* Search intent alignment

---

# Key Features

## Data Integration

Merged datasets from:

### Google Search Console

* Clicks
* Impressions
* CTR
* Average Position

### Google Analytics 4

* Sessions
* Active Users
* New Users
* Engagement Time
* Conversion Signals

---

# Engineered Metrics

Derived performance metrics include:

| Metric                 | Description                                     |
| ---------------------- | ----------------------------------------------- |
| click_to_session_ratio | Relationship between search clicks and sessions |
| visibility_score       | Composite visibility indicator                  |
| engagement_efficiency  | Engagement quality relative to traffic          |
| engagement_per_session | Average engagement depth                        |

---

# Content Classification System

Pages are segmented into categories such as:

* High traffic driver
* High-quality content
* Normal

This helps identify:

* Content attracting strong visibility
* Pages with high user satisfaction
* Underperforming pages requiring optimization

---

# Example Insights

## AWS Content Cluster

Observed:

* Huge no. of impressions
* Low CTR
* Lower engagement efficiency

Interpretation:
High visibility informational content with weaker intent satisfaction.

---

## Zoom Content Cluster

Observed:

* Strong engagement time
* Higher engagement efficiency
* Better CTR

Interpretation:
Problem-solving and high-intent content with stronger user satisfaction (especially on content about troubleshooting).

---

## PayPal in Nepal Content

Observed:

* Strong click volume
* High commercial intent
* Consistent engagement

Interpretation:
Potential monetization and conversion-oriented traffic source.

---

# Tech Stack

| Tool             | Purpose                 |
| ---------------- | ----------------------- |
| Python           | Data processing         |
| Pandas           | Data manipulation       |
| Jupyter Notebook | Exploratory analysis    |
| VS Code          | Development environment |
| Git & GitHub     | Version control         |

---

# Project Structure

```text
thinkmove-seo-analytics/
│
├── data/
│   ├── raw/
│   │   ├── gsc_pages.csv
│   │   ├── gsc_queries.csv
│   │   └── ga4_landing_page.csv
│
├── notebooks/
│   └── analysis.ipynb
│
├── outputs/
│   ├── charts/
│   └── tables/
│
├── .gitignore
├── LICENSE
├── requirements.txt
└── README.md
```

---

# Setup Instructions

## 1. Clone Repository

```bash
git clone https://github.com/sonaml-007/SEO-Analysis.git
```

## 2. Install Dependencies

```bash
pip install -r requirements.txt
```

## 3. Launch Jupyter Notebook

```bash
python -m notebook
```

---

# Recommended requirements.txt

```text
pandas
numpy
matplotlib
seaborn
jupyter
notebook
```

---

# Future Improvements

Planned extensions include:

* Ahrefs keyword integration
* SEMrush competitive analysis
* Content opportunity scoring
* SEO quadrant visualization model
* Executive dashboard layer
* Search intent clustering

---

# Author

Sonam Lama
