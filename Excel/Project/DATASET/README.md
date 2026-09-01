# DATASET

This folder contains the single source-of-truth workbook for the **Customer Purchase & Sales Performance Analysis** project: `dataset.xlsx`. Every other deliverable in this repository (the [PPT](../PPT/README.md) and the [Overview report](../SCREENSHOTS/README.md)) is derived from the data and pivot tables built inside this file.

| | |
|---|---|
| **File** | `dataset.xlsx` |
| **Format** | Excel Workbook (`.xlsx`), no macros |
| **Size** | ~141 KB |
| **Sheets** | 7 (`Raw_Data`, `Data_Quality_Notes`, `Problems`, `Detail1`, `Cleaned_Data`, `Pivot Tables`, `Dashboard`) |
| **Source records** | 300 raw retail transactions |
| **Clean records** | 292 analysis-ready transactions |
| **Author** | Abdikarim Ismail Ali |

## Purpose

The workbook documents the full analytics lifecycle for a retail sales dataset, end to end, inside Excel:

1. **Inspect** the raw export for data-quality problems.
2. **Log** every problem found before touching a single cell.
3. **Clean** the data using traceable, auditable fixes (no silent overwrites).
4. **Summarize** the clean data with PivotTables.
5. **Visualize** the summaries in a single interactive, slicer-driven dashboard.

## Sheet-by-sheet breakdown

### 1. `Raw_Data`
The original, untouched export — **300 rows × 8 columns**. Nothing in this sheet is ever edited; it exists purely as the audit baseline.

| Column | Description |
|---|---|
| `Transaction_ID` | Unique transaction identifier (format `TRX#####`); 15 rows blank |
| `Purchase_Date` | Date of sale; 15 rows blank |
| *(unlabeled helper column)* | Formula `=OR(LEFT(H,1)=" ", RIGHT(H,1)=" ")` — flags rows where `City` has leading/trailing whitespace |
| `Customer_Type` | `New` or `Returning`; inconsistent casing and 1 literal `NULL` string |
| `Product_Category` | e.g. `Electronics`, `Groceries`, `Clothing`, `Home & Living`, `Stationery`, `Other`; includes an invalid `"-"` entry |
| `Quantity` | Units purchased; includes non-numeric `"Unknown"` entries |
| `Unit_Price` | Price per unit (USD); includes blanks, `N/A`, and a negative value |
| `City` | Somali cities: Mogadishu, Hargeisa, Bosaso, Garowe, Kismayo, Baidoa, and an `Other`/`Unknown` bucket |

### 2. `Data_Quality_Notes`
The audit log — every issue found in `Raw_Data`, recorded **before** any cleaning took place, numbered 1–12 for traceability back to the report and presentation.

| # | Data Quality Issue | Count |
|---|---|---|
| 1 | Duplicate `Transaction_ID` rows (8 groups, 16 rows, 2 with conflicting fields) | 16 |
| 2 | Missing `Transaction_ID` values | 15 |
| 3 | Missing `Purchase_Date` values | 15 |
| 4 | Missing `Customer_Type` values | 17 |
| 5 | Null `Customer_Type` value | 1 |
| 6 | Missing `Product_Category` values | 16 |
| 7 | Invalid `"-"` `Product_Category` value | 1 |
| 8 | Missing `Quantity` values | 16 |
| 9 | Non-numeric `"Unknown"` `Quantity` values | 3 |
| 10 | Missing `City` values (incl. 1 literal `"Unknown"`) | 17 |
| 11 | Missing `Unit_Price` values | 16 |
| 12 | Invalid `Unit_Price` (blank, `N/A`, negative) | 3 |

> **Known quirk:** cell `P2` on this sheet retains a paragraph of descriptive boilerplate from the original workbook template (it references a "Student" dataset with `GPA`/`Attendance`/`Department` fields). That text does **not** describe this project — it's inherited template copy that was never deleted. The authoritative log for this project is the numbered table above (rows 14–37 in the sheet), which is what feeds the [Overview report](../SCREENSHOTS/README.md) and [presentation](../PPT/README.md).

### 3. `Problems`
A working/staging sheet used to isolate the two hardest issues before fixing them:
- **Missing ID'S** — the 15 rows with a blank `Transaction_ID`, alongside their `Purchase_Date`, so each could be assigned a traceable placeholder.
- **Duplicate ID'S** — the 16 rows across 8 duplicate `Transaction_ID` groups, alongside `Unit_Price` and `City`, so the most complete record in each group could be identified and kept.

### 4. `Detail1` *(hidden sheet)*
An Excel-generated drill-through sheet — the underlying row-level detail behind a "Sum of Unit_Price" PivotTable value. Kept for transparency/auditability rather than manually removed.

### 5. `Cleaned_Data`
The analysis-ready output — **292 rows × 8 columns**, structured as an Excel Table (`Table1`) so it feeds the PivotTables dynamically.

| Column | Notes |
|---|---|
| `Transaction_ID` | Blanks replaced with traceable placeholders, e.g. `MISSING-231` (row-based concatenation) |
| `Purchase_Date` | Rows with unrecoverable missing dates were excluded from this table |
| `Customer_Type` | Standardized to `New` / `Returning` |
| `Product_Category` | Standardized category labels |
| `Quantity` | Invalid/`Unknown` entries corrected or removed |
| `Unit_Price` | Invalid entries corrected or removed |
| `Revenue` | **Calculated column**, `=Quantity × Unit_Price` (formula: `Table1[[#This Row],[Quantity]]*Table1[[#This Row],[Unit_Price]]`) |
| `City` | Standardized city names |

### 6. `Pivot Tables`
Four summary PivotTables built from `Cleaned_Data`/`Detail1` (values are **Sum of Unit_Price**, USD):

**By Category**
| Category | Sum of Unit_Price |
|---|---|
| Electronics | 16,457.43 |
| Home & Living | 3,361.23 |
| Clothing | 2,742.41 |
| Other | 1,048.69 |
| Groceries | 1,412.37 |
| Stationery | 250.89 |
| **Grand Total** | **25,273.02** |

**By Customer Type**
| Type | Sum of Unit_Price |
|---|---|
| Returning | 15,724.98 |
| New | 9,548.04 |
| **Grand Total** | **25,273.02** |

**By City**
| City | Sum of Unit_Price |
|---|---|
| Mogadishu | 9,405.35 |
| Other | 3,157.38 |
| Bosaso | 3,620.11 |
| Hargeisa | 3,657.37 |
| Kismayo | 2,160.22 |
| Baidoa | 2,259.81 |
| Garowe | 1,012.78 |
| **Grand Total** | **25,273.02** |

**By Year / By Month**
| Year | Sum | | Month | Sum |
|---|---|---|---|---|
| 2025 | 17,428.18 | | Jun (peak) | 4,601.28 |
| 2026 | 6,005.01 | | Nov (lowest) | 804.01 |
| 2099 *(data-entry error, flagged for source correction)* | 1,839.83 | | — | — |

### 7. `Dashboard`
The single-page executive dashboard, built on top of the PivotTables above, with 4 slicers (**Years**, **City**, **Product_Category**, **Months**) and the following visuals/KPI cards:

- **KPI cards:** Total Sales Revenue ($198,536.78) · Transactions (292) · Units Sold (1,293) · Returning Sales ($110,692) · Top Category (Electronics) · Top City (Mogadishu) · New Sales Revenue ($87,845) · Average Sale ($679.92)
- **Chart — Sales by Month (2025–26):** clustered column chart, one color per month
- **Chart — Current Year vs. Prior Year vs. No-Date:** column chart comparing 2025 / 2026 / 2099
- **Chart — Sales by City:** column chart across all 7 city buckets
- (Additional category and new-vs-returning breakdown charts referenced in the [presentation](../PPT/README.md))

## Requirements to use this file

- **Microsoft Excel (desktop)** is required to interact with the slicers and PivotTables — they will not render interactively in most lightweight spreadsheet viewers or Excel Online in read-only mode.
- No macros, add-ins, or external data connections are used; everything is native Excel (Tables, PivotTables, Slicers, formulas).

## How to explore

1. Open `dataset.xlsx` in Excel.
2. Start at `Raw_Data` to see the untouched source, then `Data_Quality_Notes` and `Problems` to see the audit.
3. Compare against `Cleaned_Data` to see the fixes applied (look at the `Transaction_ID` and `Revenue` columns).
4. Go to `Pivot Tables` to see the aggregations, then `Dashboard` to interact with the slicers and filter the KPIs/charts live.
