# HR Attrition Analytics

Excel-based analysis of employee attrition drivers, built with PivotTables, formula-driven segmentation, and an interactive dashboard — the second project in a three-part data analyst portfolio (SQL → Excel → Pandas), all sharing Tableau as a common visualization layer.

## Dataset

**IBM HR Analytics Employee Attrition & Performance** (Kaggle) — a synthetic dataset of 1,470 employees across 35 original attributes (32 after removing constant columns), covering demographics, compensation, job satisfaction, overtime, and tenure, with `Attrition` (Yes/No) as the outcome.

## Methodology

1. **Data validation (Power Query)** — full-dataset profiling confirmed 1,470 rows with zero errors and 100% column validity. Verified `EmployeeNumber` had no duplicates (Distinct = Unique = 1,470). Removed three constant columns (`EmployeeCount`, `StandardHours`, `Over18`) that carried no analytical value.
2. **Driver analysis** — built PivotTables and COUNTIFS-based tables breaking attrition rate down by:
   - OverTime status
   - Department
   - Job Role
   - Monthly Income (binned into ranges of 2,000)
   - Years at Company (binned into ranges of 5)
3. **Dashboard** — five charts summarizing each driver, built with explicit data-series mapping (not auto-detected ranges) for accuracy.

## Key Findings

- **OverTime is the strongest single driver of attrition** — 31% attrition among employees working overtime vs. 10% among those who don't (a 3x gap, n=416 vs. n=1,054).
- **Attrition is heavily front-loaded by tenure** — 24% in years 0-4, dropping to 11-12% by years 5-14, and continuing to decline before small-sample noise takes over past year 25.
- **Job role reveals far more risk concentration than department alone** — Department shows only a 7-point spread (14%-21%), while Job Role shows a 37-point spread (Sales Representative 40% vs. Research Director 2.5%), meaning department-level reporting alone would understate the real risk.
- **Income has a real but non-linear relationship with attrition** — a sharp drop after the lowest income band, then a flatter (and statistically thinner) tail at higher incomes.

## Limitations

Income bands above 15,000 and tenure bands beyond 25 years have small sample sizes (n<15) — those attrition rates are indicative, not statistically reliable, and are flagged as such directly on the dashboard.

## Tools

Excel (Power Query, PivotTables, formulas), Tableau Public (published dashboard)

## Files

- `HR_Attrition_Analysis.xlsx` — full workbook (Raw Data, Analysis, Dashboard tabs)


## Live Dashboard

[View interactive dashboard on Tableau Public](https://public.tableau.com/app/profile/pratyush.singh3294/viz/HRAttritionAnalysis_17901492637640/HRAttritionDashboard)
