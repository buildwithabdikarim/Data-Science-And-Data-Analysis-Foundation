# PPT

This folder contains the executive presentation deliverable for the **Customer Purchase & Sales Performance Analysis** project: `Presentation.pptx`. It is the story-telling companion to the [DATASET](../DATASET/README.md) workbook and the [Overview report](../SCREENSHOTS/README.md) — condensing the same data-cleaning and analysis work into a 9-slide deck aimed at a non-technical, executive audience.

| | |
|---|---|
| **File** | `Presentation.pptx` |
| **Format** | Microsoft PowerPoint (`.pptx`) |
| **Size** | ~1.93 MB |
| **Slide count** | 9 |
| **Author / Presenter** | Abdikarim Ismail Ali — Software & AI Engineer |
| **Date** | August 2026 |

## Purpose

Where the [DATASET workbook](../DATASET/README.md) is the working analysis and the [Overview PDF](../SCREENSHOTS/README.md) is the formal written report, this deck is built to be **presented** — it distills the data-cleaning methodology, key findings, and recommendations from those two artifacts into a narrative arc: *"From Raw Data to Executive Insight."*

## Slide-by-slide breakdown

| # | Title | Content |
|---|---|---|
| 1 | **Title Slide** | "Excel Individual Project — From Raw Data to Executive Insight." One-line project summary: cleaning and analyzing 300 retail sales transactions to build a clean dataset and an executive sales dashboard. Presenter: Abdikarim Ismail Ali, Software & AI Engineer, August 2026. |
| 2 | **About the Presenter** | Bio and contact: Full Stack Software Engineer (Web, Mobile & Backend Systems), based in Mogadishu, Somalia. Contact: cabdikariim405@gmail.com · github.com/Abdikarim-dev. Core skills grid — **Frontend:** React, Next.js, TypeScript · **Backend:** Node.js, Django, Laravel · **Mobile:** Flutter, React Native · **Database:** PostgreSQL, MongoDB · **Tools:** Docker, Git, Figma. |
| 3 | **Project Workflow** | The four-stage methodology: **01 Inspect** (audit all 300 raw records for missing values, duplicates, inconsistencies) → **02 Clean** (standardize text, flag missing IDs, resolve invalid entries into `Cleaned_Data`) → **03 Analyze** (summarize with PivotTables by category, city, customer type, year, month) → **04 Visualize** (combine KPIs and PivotTables into the one-page executive Dashboard). |
| 4 | **Data Quality Audit** | The 300-record audit results as a visual scorecard: 15 Missing IDs · 16 Duplicate IDs (8 groups) · 15 Missing Dates · 18 Invalid Customer Type · 17 Invalid Category · 19 Invalid Quantity · 19 Invalid Unit Price · 18 Invalid City. Also notes inconsistent capitalization across `Customer_Type` and `City` (e.g. `New`/`new`/`NEW`, `Mogadishu`/`MOGADISHU`/`mogadishu`). Sourced from `Raw_Data`, `Data_Quality_Notes`, `Problems`. |
| 5 | **Data Cleaning** | How each issue was fixed: standardized text casing, blank `Transaction_ID`s reassigned as traceable placeholders (`MISSING-1`, `MISSING-2`, …), invalid `Quantity`/`Unit_Price` entries resolved, rows with missing `Purchase_Date` flagged, and a calculated `Revenue` column added (`Quantity × Unit_Price`). Includes a before/after example row. Result: **292 clean, analysis-ready records.** |
| 6 | **Key Results** | Dashboard KPIs at a glance: **$198,536.78** total sales revenue · **292** transactions · **1,293** units sold · **$679.92** average sale · **Electronics** top category · **Mogadishu** top city. |
| 7 | **Dashboard Visuals (1 of 2)** | Sales by City, Sales by Category, New vs. Returning Customers charts. |
| 8 | **Dashboard Visuals (2 of 2)** | Current Year vs. Prior Year vs. No-Date, and Sales by Month (2025–26). Peak: **June ($4,601)**. Lowest: **November ($804)**. |
| 9 | **Conclusions** | Key conclusions: Electronics drives ~65% of category sales value (more than every other category combined); Mogadishu leads all cities by a wide margin; returning customers contribute ~62% of sales value, ahead of new customers; June was the strongest month, November the weakest. Recommendations: add data-entry validation (dropdowns, required fields); standardize `Category`/`City` fields going forward; investigate the June peak and November dip for demand planning; study why Electronics and Mogadishu dominate to guide inventory and marketing focus. |

## Relationship to the other folders

- Every number and chart in this deck traces back to the `Dashboard` and `Pivot Tables` sheets in [`../DATASET/dataset.xlsx`](../DATASET/README.md).
- The data-quality figures on slide 4 mirror the audit table documented in the [DATASET README](../DATASET/README.md#2-data_quality_notes) and in the [Overview report](../SCREENSHOTS/README.md).
- Treat this deck as the **presentation layer**: use it when explaining the project verbally to an audience; use the workbook when you need to verify or re-derive a number.

## Requirements to use this file

- Microsoft PowerPoint (or a compatible viewer such as Google Slides/LibreOffice Impress) to open and present `Presentation.pptx`.
