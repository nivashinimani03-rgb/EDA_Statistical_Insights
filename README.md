# Exploratory Data Analysis & Statistical Insights

**Internship Project 04 — Data Analytics & Business Intelligence**
Author: Nivashini Manivannan

Comprehensive EDA on a synthetic retail transactions dataset (12,000 rows, FY2024–FY2025),
using statistical distributions, correlation matrices, and multivariate visualizations to
uncover hidden business patterns — plus three formal hypothesis tests.

## 📊 Live Dashboard
Open [`dashboard/index.html`](dashboard/index.html) in any browser, or enable **GitHub Pages**
(Settings → Pages → Deploy from branch → `main` / root) to get a shareable link.

## 📁 Repository Structure
```
├── data/
│   └── business_transactions.csv         # Synthetic dataset (12,000 rows × 18 columns)
├── notebooks/
│   └── EDA_Statistical_Insights.ipynb    # Full EDA notebook — charts + markdown commentary
├── dashboard/
│   ├── index.html                        # Self-contained interactive dashboard (Chart.js)
│   └── index_template.html               # Template used to (re)generate index.html
├── reports/
│   ├── EDA_Statistical_Insights.xlsx     # Formula-driven Excel workbook
│   ├── summary_statistics.csv            # Descriptive stats export
│   └── findings.json                     # Structured findings consumed by the dashboard
├── charts/                               # 8 exported PNG figures used across deliverables
├── scripts/
│   ├── generate_data.py                  # Synthetic data generator
│   ├── eda_analysis.py                   # Stats, charts, hypothesis tests
│   ├── build_workbook.py                 # Builds the Excel deliverable
│   ├── build_notebook.py                 # Assembles the Jupyter notebook
│   ├── build_dashboard.py                # Injects findings into the dashboard template
│   └── run_full_eda.py                   # Single-command pipeline (runs all of the above)
└── requirements.txt
```

## ▶️ Reproduce Locally
```bash
pip install -r requirements.txt
python scripts/run_full_eda.py
```
This regenerates the dataset, all 8 charts, the Excel workbook, the notebook, and the
dashboard data from a single source of truth.

## 🔎 Implementation Steps Covered
- [x] Summary descriptive statistics (mean, median, standard deviation, quartiles)
- [x] Correlation heatmap, histogram distributions, box plots (anomaly/outlier detection)
- [x] 3 business hypothesis tests:
  1. **Customer retention vs. discount rate** — Welch's t-test
  2. **Revenue across regions** — one-way ANOVA
  3. **Discount rate vs. profit margin** — Pearson correlation
- [x] Top 5 critical findings summarized in markdown (see notebook, Section 6)

## 📈 Key Results (α = 0.05)
| Hypothesis | Test | p-value | Result |
|---|---|---|---|
| H1: Retention vs. Discount Rate | Welch's t-test | < 0.0001 | **Significant** |
| H2: Revenue Across Regions | One-way ANOVA | 0.5685 | Not significant |
| H3: Discount Rate vs. Profit Margin | Pearson r = -0.34 | < 0.0001 | **Significant** |

## 🛠️ Tech Stack
Python · pandas · NumPy · SciPy (stats) · Matplotlib · Seaborn · openpyxl · Chart.js

## Expected Proof
Jupyter Notebook containing detailed charts and markdown analysis commentary —
see [`notebooks/EDA_Statistical_Insights.ipynb`](notebooks/EDA_Statistical_Insights.ipynb).
