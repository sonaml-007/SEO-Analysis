# SEO Analytics Intelligence System

A multi-tool SEO analytics project evaluating content performance across Google Search Console, Google Analytics 4, Ahrefs, and Microsoft Clarity for a Nepal-based IT, SAAS, and cloud consulting firm.

The project is structured across four milestones, each analyzing a different data source, culminating in a cross-tool coherence analysis that tests whether all four tools tell a consistent story about content performance.

---

## Milestones

| Milestone | Focus | Status |
|-----------|-------|--------|
| [Milestone 1 — Visibility vs Value](./google-analysis/) | GSC × GA4 integrated analysis | ✅ Complete |
| [Milestone 2 — Ahrefs Analysis](./ahrefs-analysis/) | Keyword difficulty and competition | ✅ Complete |
| [Milestone 3 — Microsoft Clarity](./clarity-analysis/) | User behavior and heatmap analysis | ✅ Complete |
| [Milestone 4 — Cross-tool Coherence](./coherence-analysis/) | Unified scoring across all tools | ✅ Complete |

---

## Headline finding

I tested four independent analytical approaches: search visibility, behavioral engagement, competitive keyword positioning, and on-site user behavior. These converge on the same conclusion: the AWS content cluster (`aws-in-2026-latest-services-updates`, `amazon-bedrock-aws-ai-platform-guide`) is the site's single largest optimization opportunity. High search visibility is not being converted into user satisfaction, and this is confirmed independently across all four tools.

See [Milestone 4](./coherence-analysis/) for the full cross-tool synthesis.

---

## Project structure

```text
SEO-Analysis/
│
├── google-analysis/
│   ├── notebook-google/
│   │   └── google-seo-analysis.ipynb
│   ├── output-google/
│   │   └── chart/
│   │       ├── quadrant_plot.png
│   │       └── opportunity_score.png
│   └── README.md
│
├── ahrefs-analysis/
│   ├── notebook-ahrefs/
│   │   └── ahrefs-seo-analysis.ipynb
│   ├── output-ahrefs/
│   │   └── chart/
│   │       ├── kd_vs_volume.png
│   │       ├── keyword_opportunity.png
│   │       ├── position_vs_kd.png
│   │       ├── ahrefs_vs_ga4.png
│   │       └── page_ranking_efficiency.png
│   └── README.md
│
├── clarity-analysis/
│   ├── notebook-clarity/
│   │   └── clarity-seo-analysis.ipynb
│   ├── output-clarity/
│   │   └── chart/
│   │       ├── traffic_sources.png
│   │       ├── behavioral_signals.png
│   │       ├── clarity_vs_ga4.png
│   │       ├── core_web_vitals.png
│   │       └── session_quality.png
│   └── README.md
│
├── coherence-analysis/
│   ├── notebook-coherence/
│   │   └── coherence-analysis.ipynb
│   ├── output-coherence/
│   │   └── chart/
│   │       ├── coherence_map.png
│   │       └── unified_opportunity.png
│   └── README.md
│
├── data/
│   └── README.md
│
├── .gitignore
├── requirements.txt
└── README.md
```

---

## Data privacy

All raw data files are excluded from this repository. The `data/README.md` documents the schema and export instructions needed to reproduce the analysis with your own GSC, GA4, Ahrefs, and Clarity exports.

---

## Tech stack

| Tool | Purpose |
|------|---------|
| Python | Data processing |
| Pandas | Data cleaning and feature engineering |
| NumPy | Statistical calculations |
| Matplotlib | Visualization |
| Jupyter Notebook | Analysis environment |
| Git & GitHub | Version control |

---

## Author

**Sonam Lama**
[github.com/sonaml-007](https://github.com/sonaml-007)
