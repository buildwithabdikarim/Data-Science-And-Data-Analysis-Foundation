# Lesson 01 — Pandas Basics: First Look at a Dataset

**Day:** 1 · **Topic:** Getting started with pandas in Google Colab · **Author:** Abdikarim Ismail Ali

## Scope of Day 1

The goal for day one was purely foundational: install nothing, assume nothing, and get comfortable with the small set of pandas methods used to take a first look at any new dataset before doing any real analysis. No cleaning or transformation happens in this lesson — the dataset used here was already cleaned in the [Excel project](../../Excel/Project/DATASET/README.md); day 1 is about *reading and inspecting* it in Python.

Planned outcomes for the session:
- Import pandas correctly and understand the `import ... as pd` convention.
- Load an Excel file into a DataFrame from Google Drive inside Google Colab.
- Preview data from the top, the bottom, and at random.
- Understand a DataFrame's shape, column names, and data types.
- Generate a full structural summary and a full statistical summary in one call each.

## What was achieved

Working in `Dataset/Basics_day_01.ipynb`, the following was completed, in order:

1. **Setup** — `import pandas as pd`.
2. **Load** — read `cleaned_data.xlsx` from Google Drive into a DataFrame (`data`).
3. **Preview** — `data.head()` and `data.tail()` to see the first and last 5 rows.
4. **Random sampling** — `data.sample()` for one random row, `data.sample(10)` for ten random rows, and `data.sample(frac=1)` to shuffle the entire DataFrame.
5. **Structure** — `data.shape` (291 rows × 8 columns) and `data.columns` to list every field.
6. **Data types** — `data.dtypes` to confirm each column's type (dates, text, integers, floats).
7. **Full summary** — `data.info()` for a compact non-null/dtype report, and `data.describe(include="all")` for a combined numeric + categorical statistical summary.

By the end of the lesson, the dataset was fully understood — its size, its columns, its types, its ranges, and its most frequent values — without a single value having been changed.

## Folder contents

| Folder | Contents |
|---|---|
| [`Dataset/`](Dataset/README.md) | The notebook (`Basics_day_01.ipynb`) plus the raw and cleaned Excel files it reads |
| [`Screenshots/`](Screenshots/README.md) | One screenshot per notebook step, showing the exact code and output produced |

## Requirements

- A Python environment with `pandas` and `openpyxl` installed (the notebook was originally run in **Google Colab**, with the dataset mounted from Google Drive at `/content/drive/MyDrive/Colab Notebooks/Python/cleaned_data.xlsx` — update that path if running locally).
- Jupyter (or Colab) to open `Basics_day_01.ipynb`.
