# Retail Profitability Analysis

An end-to-end analysis of the Superstore retail dataset, exploring profitability drivers across products, regions, discounts, and seasonality. The project combines SQL for data querying, Python for data enrichment and visualization, and Tableau for interactive dashboarding.

## Project Structure

```
retail-analysis/
├── data/
│   ├── Sample - Superstore.csv          ← Kaggle download
│   └── superstore_enriched.csv          ← Python output
├── sql/
│   ├── superstore.sqbpro                ← All SQL queries
│   └── superstore.db                    ← SQLite database
├── python/
│   └── analysis.py                      ← Python script
├── visuals/
│   ├── chart_01_subcategory_profit.png
│   ├── chart_02_correlation.png
│   ├── chart_03_discount_impact.png
│   ├── chart_04_seasonal.png
│   ├── chart_05_regional.png
│   ├── chart_06_products.png
│   └── chart_07_inventory_risk_matrix.png
└── tableau/
    └── RetailDashboard.twbx
```

## Overview

Retailers don't just need to know *what* sold — they need to know what's actually profitable to sell. This project digs into the Superstore dataset to answer questions like:

- Which product sub-categories have the healthiest (and weakest) profit margins?
- How does discounting affect profitability?
- Are there seasonal patterns in sales and profit?
- Which regions are over- or under-performing?
- How does inventory/order volume relate to profit?

## Data

- **Source:** [Sample Superstore dataset](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final) (Kaggle)
- **Raw file:** `data/Sample - Superstore.csv`
- **Enriched file:** `data/superstore_enriched.csv` — output of `python/analysis.py`, with derived fields (e.g. profit margin, order processing time, seasonal flags) used downstream in SQL and Tableau

## Tools & Workflow

1. **SQL (`sql/superstore.sqbpro`, `sql/superstore.db`)**
   Queries used to explore profitability by category, region, and discount tier, run against the SQLite database in [DB Browser for SQLite](https://sqlitebrowser.org/).

2. **Python (`python/analysis.py`)**
   Cleans the raw CSV, engineers additional features, and generates the static charts in `visuals/`.

3. **Tableau (`tableau/RetailDashboard.twbx`)**
   Interactive dashboard built from the enriched dataset for exploring profitability and sales trends visually.

## Key Visuals

| Visual | Insight |
|---|---|
| `chart_01_subcategory_profit.png` | Profit margin by product sub-category |
| `chart_02_correlation.png` | Correlation between key metrics (e.g. sales, profit, discount, quantity) |
| `chart_03_discount_impact.png` | Effect of discount levels on profitability |
| `chart_04_seasonal.png` | Sales/profit seasonality across months |
| `chart_05_regional.png` | Profit margin breakdown by region |
| `chart_06_products.png` | Top/bottom performing products |
| `chart_07_inventory_risk_matrix.png` | Products flagged by inventory/order risk vs. profitability |

## Getting Started

### Prerequisites

- Python 3.x with `pandas`, `matplotlib`/`seaborn` (or your chosen plotting library)
- [DB Browser for SQLite](https://sqlitebrowser.org/) to open `.sqbpro` files
- [Tableau Public](https://public.tableau.com/) or Tableau Desktop to open `.twbx` files

### Run the Python analysis

```bash
cd python
python analysis.py
```

This regenerates `data/superstore_enriched.csv` and the charts in `visuals/`.

### Explore the SQL queries

Open `sql/superstore.sqbpro` in DB Browser for SQLite to inspect and run the queries against the dataset.

### View the dashboard

Open `tableau/RetailDashboard.twbx` in Tableau to explore the interactive version.

## Findings

Key takeaways from the analysis (see `sql/` queries and `visuals/` charts for full detail):

- Profitability varies significantly by sub-category — some categories drive strong margins while others are sold at a loss.
- Heavy discounting is associated with declining profit margins beyond certain thresholds.
- Sales and profit show seasonal patterns across the year.
- Regional performance is uneven, with some regions consistently outperforming others on margin.
- The inventory risk matrix highlights products that are high-volume but low-profit (or vice versa), useful for stocking decisions.

## License

This project uses publicly available sample data from Kaggle for educational/portfolio purposes.
