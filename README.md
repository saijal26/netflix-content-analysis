# Netflix Data Analysis | Python, Pandas, Excel, Tableau

An end-to-end data analysis project exploring Netflix's global content library of 8,800+ titles — from raw data cleaning in Python, to pivot-table analysis in Excel, to an interactive dashboard in Tableau.

🔗 **[View the live interactive dashboard on Tableau Public](https://public.tableau.com/app/profile/saijal.tomar/viz/Netflix_Content_Analysis_17896495659790/NetflixContentAnalysis?publish=yes)**

![Dashboard Screenshot](netflix-content-analysis/screenshots/Screenshot%201.png)

## Project Overview

This project analyzes Netflix's title catalog to understand:
- The balance between movies and TV shows
- How Netflix's content library has grown over time
- Which countries and genres are most represented
- Data quality issues in the source dataset (e.g. missing country/director/cast metadata)

## Key Insights

- **Movies dominate the catalog** — 6,131 movies vs. 2,676 TV shows (~70/30 split)
- **Explosive content growth post-2015** — title additions were flat for decades, then grew sharply from 2015–2019, reflecting Netflix's shift from a licensing platform to an original-content powerhouse
- **US-centric but globalizing** — the United States leads by a wide margin, but India, the UK, and Japan all appear in the top countries, showing investment in international content
- **Genre concentration** — International Movies, Dramas, and Comedies are the most common content categories
- **Data quality note** — a portion of titles had missing country data, labeled `Unknown` during cleaning (rather than dropped, to preserve rows for other analyses) and excluded specifically from the country-ranking chart in the dashboard

## Process

### 1. Data Cleaning & EDA (Python / Pandas)
- Loaded the raw dataset (8,807 rows) and inspected structure, nulls, and duplicates
- Filled missing `director`, `cast`, `country`, `rating`, and `duration` values with `"Unknown"` rather than dropping rows, to preserve usable data in other fields
- Parsed `date_added` into proper datetime format
- Stripped whitespace across all text columns
- Exported a cleaned CSV/Excel file for use downstream
- Ran exploratory analysis: content type distribution, release year trends, top countries, top genres, content ratings, and movie duration statistics (using Pandas + Matplotlib)

### 2. Pivot Analysis & Mini-Dashboard (Excel)
- Built PivotTables on the cleaned dataset to summarize:
  - Movies vs. TV Shows counts
  - Titles by Release Year
  - Titles by Rating
  - Movies vs. TV Shows broken down by Release Year
- Created native Excel charts from each PivotTable
- Assembled a summary **Dashboard** sheet with headline KPIs (Total Titles, Movies, TV Shows, Movie %) and Top Countries / Top Genres tables

### 3. Interactive Dashboard Design (Tableau)
- Built individual worksheets for each metric (KPI, type breakdown, release year trend, top genres, top countries)
- Assembled all worksheets into a single interactive dashboard
- Added cross-filtering dashboard actions so charts respond to user clicks
- Added a written "Key Insights" summary panel translating the visuals into takeaways

## Files in This Repo

| File | Description |
|---|---|
| `netflix-content-analysis/notebooks/Netflix_Data_Analysis.ipynb` | Data cleaning and exploratory analysis in Python/Pandas |
| `netflix-content-analysis/data/netflix_titles.csv` | Original raw dataset |
| `netflix-content-analysis/data/netflix_cleaned.csv` | Cleaned dataset (output of the notebook) |
| `netflix-content-analysis/excel/netflix_cleaned.xlsx` | Excel workbook with PivotTables, charts, and a summary Dashboard sheet |
| `netflix-content-analysis/tableau/Netflix_Content_Analysis.twbx` | Full Tableau packaged workbook (dashboard + data) |
| `netflix-content-analysis/screenshots/` | Preview images of the Tableau dashboard and Excel dashboard |

## Tools & Libraries

- **Python:** pandas, numpy, matplotlib
- **Excel:** PivotTables, PivotCharts, summary dashboard
- **Tableau Public** (dashboard design + interactivity)

## How to Run

**Notebook:**
1. Open `notebooks/Netflix_Data_Analysis.ipynb` in Jupyter
2. Ensure `pandas`, `numpy`, and `matplotlib` are installed (`pip install pandas numpy matplotlib`)
3. Run all cells — this reproduces the cleaning steps and exploratory charts

**Excel:**
1. Open `excel/netflix_cleaned.xlsx`
2. See the `Dashboard` sheet for the summary view, or individual tabs (`Movies vs TV Shows`, `Release Year`, `Ratings`, `Top Countries`, `Top Genres`) for each PivotTable/chart

**Tableau Dashboard:**
1. Download `tableau/Netflix_Content_Analysis.twbx`
2. Open it with [Tableau Public](https://public.tableau.com/) or Tableau Desktop
3. No additional setup needed — the data is packaged inside the file

## Dataset Source

[Netflix Movies and TV Shows dataset (Kaggle)](https://www.kaggle.com/datasets/shivamb/netflix-shows) 

---
