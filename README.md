# Dr. Lal PathLabs — Healthcare Diagnostics Performance Dashboard

An interactive **Power BI dashboard** analysing the financial, operational and regional performance of **Dr. Lal PathLabs Ltd.** across FY2023–24 and FY2024–25.

The project transforms information from the company's annual reports into a three-page dashboard designed to make key performance indicators, year-on-year changes and regional revenue contribution easier to explore.

---

## Dashboard Preview

The dashboard contains three report pages:

### 1. Executive Overview

A high-level view of the company's performance, with headline financial KPIs and an at-a-glance summary.

![Executive Overview](screenshots/01-executive-overview.png)

### 2. Financial Performance Analysis

A comparison of revenue, EBITDA, PAT and profitability margins across FY2023–24 and FY2024–25.

![Financial Performance Analysis](screenshots/02-financial-performance.png)

### 3. Operational & Regional Performance

A view of regional revenue share and operational metrics, including patient volume, revenue per patient, sample volume and tests per patient.

![Operational and Regional Performance](screenshots/03-operational-regional-performance.png)

> Save the three report-page images in a folder named `screenshots` using the exact filenames shown above. See [Adding the dashboard screenshots](#adding-the-dashboard-screenshots) for instructions.

---

## Project Objectives

- Summarise the company's reported financial performance for FY2023–24 and FY2024–25.
- Compare revenue growth and profitability indicators between the two financial years.
- Show how FY2024–25 regional revenue is distributed across the regions represented in the source data.
- Compare selected operational metrics year over year.
- Present the results in an accessible, executive-style Power BI report.

## Dashboard Pages and Features

### Page 1 — Executive Overview

Provides a concise snapshot of the company's performance using headline financial indicators and summary visuals. It is intended to help viewers understand the overall performance before exploring the detailed analysis on the following pages.

### Page 2 — Financial Performance Analysis

Includes the following indicators and comparisons:

| KPI | FY2024–25 dashboard value |
|---|---:|
| Revenue | ₹2,461.40 Cr |
| Revenue growth | 10.54% |
| EBITDA | ₹695.60 Cr |
| EBITDA margin | 28.28% |
| PAT | ₹492.25 Cr |
| PAT margin | 20.00% |

The page includes:
- Revenue trend across the two financial years.
- EBITDA and PAT margin trends.
- EBITDA versus PAT comparison.
- KPI cards for FY2024–25.
- Key financial observations.

### Page 3 — Operational & Regional Performance

Includes:
- **Regions covered:** 7 named regions in the dashboard.
- **Operational metrics tracked:** 4.
- **Top regional share:** Delhi NCR, at 31.08% in FY2024–25.
- A clustered bar chart comparing regional revenue share for FY2023–24 and FY2024–25.
- A donut chart showing FY2024–25 regional contribution.
- A year-on-year operational comparison table.
- Data-backed operational and regional insights.

The seven regions displayed are Delhi NCR, UP & UK, West, East India, Rest of North India, South and Others.

### Operational Metrics

| Metric | FY2023–24 | FY2024–25 | Unit |
|---|---:|---:|---|
| Revenue per Patient | 806.00 | 855.00 | INR |
| Sample Volume | 78.20 | 85.60 | Million |
| Patient Volume | 27.60 | 28.80 | Million |
| Tests Per Patient | 2.83 | 2.97 | Ratio (No.) |

Values and labels in the report should be interpreted in the context of the underlying annual-report disclosures and the prepared source dataset.

---

## Tools and Technologies

- **Microsoft Power BI Desktop** — report development and visualisation.
- **DAX (Data Analysis Expressions)** — measures and KPI calculations.
- **Power Query** — data import, cleaning and transformation.
- **Excel / CSV** — structured source-data preparation.

## Data Sources

The analysis is based on information reported in the following annual reports:

1. [Dr. Lal PathLabs Annual Report FY2024–25](https://media.lalpathlabs.com/2025-05/Annual-Report-2024-25.pdf)
2. [Dr. Lal PathLabs Annual Report FY2023–24](https://media.lalpathlabs.com/2024-06/Annual-Report-2023-24.pdf)

The annual reports are the underlying references. Consult the relevant consolidated financial statements and regional disclosures when checking individual figures.

## Methodology

1. Reviewed the FY2023–24 and FY2024–25 annual reports.
2. Identified the financial, regional and operational information relevant to the dashboard.
3. Prepared structured tabular data for use in Power BI.
4. Imported and prepared the data using Power Query.
5. Created DAX measures for the required financial KPIs and comparisons.
6. Built visuals to compare financial performance, regional revenue share and operational metrics.
7. Organised the visuals into three report pages and added concise observations.

## Key Calculations

The following formulas describe the calculation logic. The actual measure names in the Power BI model may differ.

**Revenue growth**

```text
((FY2025 Revenue - FY2024 Revenue) / FY2024 Revenue) * 100
```

**EBITDA margin**

```text
(FY2025 EBITDA / FY2025 Revenue) * 100
```

**PAT margin**

```text
(FY2025 PAT / FY2025 Revenue) * 100
```

**Regional revenue share**

```text
(Revenue attributed to a region / Total regional revenue) * 100
```

Regional contribution is presented as a percentage share, based on the regional information prepared from the annual-report disclosures.

---

## Repository Structure

Use a structure like the following, and keep only files that are actually included in your repository:

```text
Healthcare-Diagnostics-Financial-Dashboard/
│
├── data/
│   ├── financial_summary.csv
│   ├── region_wise_revenue.csv
│   └── operational_metrics.csv
│
├── screenshots/
│   ├── 01-executive-overview.png
│   ├── 02-financial-performance.png
│   └── 03-operational-regional-performance.png
│
├── Healthcare_Diagnostics_Dashboard.pbix
└── README.md
```

If your project uses an Excel workbook instead of CSV files, include the actual workbook name. If you are sharing a Power BI Project (`.pbip`) rather than a `.pbix`, include the `.pbip` file and its associated project folders instead of using the example `.pbix` entry above. Do not rename or omit files that the report needs to open.

## Adding the Dashboard Screenshots

Take one screenshot for **each report page** so that someone visiting the GitHub repository can preview the full dashboard without opening Power BI.

1. Open the report in **Power BI Desktop**.
2. Select the **Executive Overview** page tab.
3. Hide the Filters, Visualizations and Data panes if they are open.
4. Set the report view to **Fit to page** (or adjust zoom so the complete page is visible).
5. Capture the report canvas using Windows Snipping Tool (`Win + Shift + S`).
6. Save the image as `01-executive-overview.png`.
7. Repeat for the **Financial Performance Analysis** page and save it as `02-financial-performance.png`.
8. Repeat for the **Operational & Regional Performance** page and save it as `03-operational-regional-performance.png`.
9. Place all three images inside the repository's `screenshots/` folder.
10. Keep the filenames and folder path identical to the Markdown image references in this README.

**Screenshot tips**
- Capture the whole report canvas, not the Power BI ribbon or editing panes.
- Use the same zoom level and window size for all three pages where possible.
- Make sure no visual is selected and no resize handles or menus are visible.
- Check that titles, chart labels, KPI values and source notes are readable.
- Use PNG format to keep text and chart labels sharp.

GitHub displays the images directly in the README when the relative paths are correct and the image files have been committed to the repository.

## How to View the Dashboard

1. Clone or download this repository.
2. Install [Microsoft Power BI Desktop](https://www.microsoft.com/power-platform/products/power-bi/desktop).
3. Open the included `.pbix` file, or open the `.pbip` project if that is the format included in the repository.
4. If Power BI reports a missing data source, update the source path in Power Query to point to the data files included in the repository.
5. Select **Refresh** and confirm that the queries load successfully.
6. Navigate through the three report pages and interact with the available visuals and filters.

> The Power BI report file provides the interactive experience. The PNG files in `screenshots/` are static previews only.

## Scope and Limitations

- The dashboard focuses on FY2023–24 and FY2024–25; it is not a live financial-data feed.
- Regional visuals show percentage contribution, not absolute regional revenue in ₹ crore.
- The analysis is limited to the financial, regional and operational measures included in the prepared dataset.
- The dashboard presents descriptive analysis of historical information. Forecasting, DCF valuation, competitor benchmarking and market-entry analysis are outside the current scope.
- Figures should be checked against the original annual reports before being reused for formal financial analysis.

## Disclaimer

This is an independent academic and portfolio project created for learning and demonstration purposes. It is not affiliated with, endorsed by or prepared on behalf of Dr. Lal PathLabs Ltd. Company information is based on publicly available annual reports and should be verified against the original source documents.

## Author

**Sumit Kosta**  
B.Tech, Electrical Engineering — National Institute of Technology Rourkela

- GitHub: [@sumitkosta001](https://github.com/sumitkosta001)
