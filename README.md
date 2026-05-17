# SEO Analytics Intelligence System

A multi-tool SEO analytics project evaluating content performance across Google Search Console, Google Analytics 4, Ahrefs, and Microsoft Clarity for a Nepal-based IT and cloud consulting firm.

The project is structured across four milestones, each analyzing a different data source, culminating in a cross-tool coherence analysis that tests whether all four tools tell a consistent story about content performance.

---

## Milestones

| Milestone | Focus | Status |
|-----------|-------|--------|
| [Milestone 1 — Visibility vs Value](./google-analysis/) | GSC × GA4 integrated analysis | ✅ Completed |
| Milestone 2 — Ahrefs Analysis | Keyword difficulty and competition | ✅ Completed |
| Milestone 3 — Microsoft Clarity | User behavior and heatmap analysis | Planned |
| Milestone 4 — Cross-tool Coherence | Unified scoring across all tools | Planned |

---

## Project structure

```text
SEO-Analysis/
│
├── google-analysis/        # Completed
│   ├── notebook-google/
│   │   └── google-seo-analysis.ipynb
│   └── output-google/
│       └── chart/
│           └── quadrant_plot.png
│   └──README.md
│  
├── ahrefs-analysis/         # In Progress
│   ├── notebook-ahrefs/
│   │   └── ahrefs-seo-analysis.ipynb
│   └── output-ahrefs/
│       └── chart/
│           └── kd_vs_volume.png
│           └── keyword_opportunity.png
│           └── position_vs_kd.png
│           └── ahrefs_vs_ga4.png
│           └── page_ranking_efficiency.png
│   └── README.md
│        
├── clarity-analysis/         # planned
├── coherence-analysis/       # planned
│
├── data/                     # excluded via .gitignore
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
| Matplotlib | Visualization |
| Jupyter Notebook | Analysis environment |
| Git & GitHub | Version control |

---

## Author

[github.com/sonaml-007](https://github.com/sonaml-007)
