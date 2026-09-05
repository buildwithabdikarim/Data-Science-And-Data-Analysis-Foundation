# Dataset

Data used in [Lesson 01](../README.md), carried over from the [Excel project](../../../Excel/Project/DATASET/README.md).

| File | Rows | Columns | Description |
|---|---|---|---|
| `excel_raw_data.xlsx` | 300 | 7 | The uncleaned retail sales export |
| `cleaned_data.xlsx` | 291 | 8 | The cleaned dataset (adds a `Revenue` column) — this is the file the notebook actually loads |
| `Basics_day_01.ipynb` | — | — | The day 1 notebook that reads `cleaned_data.xlsx` and explores it with pandas |

For the full column-by-column breakdown, data-quality history, and cleaning methodology behind these two files, see the [Excel DATASET README](../../../Excel/Project/DATASET/README.md) — that level of detail is intentionally kept out of this README. For a walkthrough of what each pandas method actually produced when run against `cleaned_data.xlsx`, see the [Screenshots README](../Screenshots/README.md).
