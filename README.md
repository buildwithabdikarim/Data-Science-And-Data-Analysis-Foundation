# Data Science & Data Analysis Foundation

A portfolio repository of foundational data science and data analysis projects. It currently holds one complete, end-to-end **Excel** project: **Customer Purchase & Sales Performance Analysis** — cleaning 300 raw retail sales records and turning them into an interactive executive dashboard, backed by a written report and a presentation deck.

**Author:** Abdikarim Ismail Ali — Software & AI Engineer, Mogadishu, Somalia
**Contact:** cabdikariim405@gmail.com · [github.com/Abdikarim-dev](https://github.com/Abdikarim-dev)

## Project overview: Customer Purchase & Sales Performance Analysis

A retail sales dataset of 300 transactions was inspected, audited for data-quality issues, cleaned into 292 analysis-ready records, summarized with PivotTables, and visualized in a single slicer-driven Excel dashboard. The work followed a four-stage workflow:

**Inspect** → **Clean** → **Analyze** → **Visualize**

### Headline results

| Metric | Value |
|---|---|
| Total Sales Revenue | $198,536.78 |
| Transactions | 292 |
| Units Sold | 1,293 |
| Average Sale | $679.92 |
| Returning-customer Revenue | $110,692 (≈62% of sales) |
| New-customer Revenue | $87,845 |
| Top Category | Electronics (≈65% of category value) |
| Top City | Mogadishu |
| Peak Month | June ($4,601) |
| Lowest Month | November ($804) |

### Data quality, at a glance

Of the 300 raw records, 12 distinct categories of data-quality issues were found and logged before any cleaning began — duplicate and missing `Transaction_ID`s, missing `Purchase_Date`s, invalid `Customer_Type`/`Product_Category`/`Quantity`/`City`/`Unit_Price` values, and inconsistent text casing throughout. Every fix is traceable: missing IDs became `MISSING-#` placeholders rather than being deleted, and duplicate groups were resolved by keeping the most complete record. Full details are in the [DATASET README](Excel/Project/DATASET/README.md).

## Repository structure

```
Data-Science-And-Data-Analysis-Foundation/
├── README.md                          ← you are here
└── Excel/
    └── Project/
        ├── DATASET/
        │   ├── README.md               ← detailed workbook documentation
        │   └── dataset.xlsx            ← the analysis: raw data, cleaning, pivots, dashboard
        ├── PPT/
        │   ├── README.md               ← detailed slide-by-slide documentation
        │   └── Presentation.pptx       ← 9-slide executive presentation
        └── SCREENSHOTS/
            ├── README.md                       ← detailed documentation
            ├── Overview.pdf                    ← 5-page written project report
            ├── KPIS.png                        ← dashboard KPI cards
            ├── PIVOT TABLE.png                 ← all 5 PivotTables
            ├── SALES BY MONTHS.png             ← dashboard chart
            ├── SALES BY CITY.png               ← dashboard chart
            ├── CURRENT YEAR VS PRIOR YEAR.png  ← dashboard chart
            └── NEW VS RETURNING.png            ← dashboard chart
```

## The three deliverable folders

Each folder covers the *same* project from a different angle, and each has its own detailed README.

| Folder | What it holds | Use it when you want to... |
|---|---|---|
| **[DATASET](Excel/Project/DATASET/README.md)** | `dataset.xlsx` — the source-of-truth workbook: 7 sheets covering raw data, the data-quality audit, the cleaning workspace, the cleaned table, PivotTables, and the interactive dashboard. | Verify a number, re-run the analysis, or interact with the live slicers/PivotTables/charts yourself. |
| **[PPT](Excel/Project/PPT/README.md)** | `Presentation.pptx` — a 9-slide executive deck narrating the project from raw data to insight, including presenter bio and skills. | Present the findings to an audience, or get the story in slide form without touching the raw data. |
| **[SCREENSHOTS](Excel/Project/SCREENSHOTS/README.md)** | `Overview.pdf` (5-page formal written report) plus 6 standalone PNGs of the dashboard's KPI cards, PivotTables, and charts, captured straight from Excel. | Get a self-contained, citable write-up and a visual proof of every KPI/chart/pivot without opening Excel or PowerPoint. |

Read them in whichever order suits your need: the **PPT** for a quick narrated summary, the **SCREENSHOTS** folder for the full written report plus standalone visuals, and the **DATASET** workbook to inspect or interact with the underlying analysis.

## Tools & techniques demonstrated

- Manual data-quality auditing and issue logging (duplicates, missing values, invalid values, inconsistent casing)
- Non-destructive, traceable data cleaning (placeholder IDs, flagged rows, standardized categories)
- Excel Tables, calculated columns, and lookup/whitespace-detection formulas
- PivotTables across multiple dimensions (category, customer type, city, year, month)
- An interactive, slicer-driven single-page Excel dashboard
- Translating an analysis into both a written report (PDF) and an executive presentation (PPTX)

## Requirements

- **Microsoft Excel** (desktop) to open and interact with `dataset.xlsx` — slicers and PivotTables require full Excel, not a lightweight viewer.
- **Microsoft PowerPoint** (or a compatible viewer) for `Presentation.pptx`.
- Any PDF viewer for `Overview.pdf`.
