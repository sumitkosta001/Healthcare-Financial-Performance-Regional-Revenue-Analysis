# Dr. Lal PathLabs -- Financial Performance & Regional Revenue Analysis

An interactive **Power BI dashboard** analysing the FY2023--24 and
FY2024--25 financial performance of **Dr. Lal PathLabs Ltd.**, with a
focus on revenue growth, profitability and regional revenue
contribution.

## Project Overview

This project converts financial information published in the company's
annual reports into an executive-style dashboard. It is designed to help
a reader quickly understand the company's year-on-year financial
performance and how revenue is distributed across regions.

**Tools and technologies** - Microsoft Power BI Desktop - DAX (Data
Analysis Expressions) - Power Query / Power BI data preparation - Excel
or structured tabular data (for source-data preparation)

## Dashboard Preview

![Dr. Lal PathLabs Financial Performance
Dashboard](screenshots/dashboard.png)

> Add your exported dashboard screenshot to a folder named `screenshots`
> and save it as `dashboard.png`. If you use a different filename or
> folder, update the image path above.

## Dashboard Features

### 1. Financial KPI Cards

The executive overview displays six key indicators:

  KPI                      Dashboard value
  ---------------------- -----------------
  FY2025 Revenue               ₹2,461.4 Cr
  FY2024 Revenue               ₹2,226.6 Cr
  Revenue Growth                    10.54%
  FY2025 EBITDA                  ₹695.6 Cr
  FY2025 EBITDA Margin              28.26%
  FY2025 PAT                     ₹492.3 Cr

All monetary values are presented in **₹ crore (Cr)**. Revenue growth
and EBITDA margin are presented as percentages.

### 2. Regional Revenue Share -- FY2024 vs FY2025

A clustered bar chart compares the percentage contribution of each
region in FY2024 and FY2025. It covers: - Delhi NCR - UP & UK - West -
East India - Rest of North India - South - Others

This view makes it easier to compare the regional mix across the two
financial years.

### 3. FY2025 Revenue Contribution by Region

A separate bar chart displays FY2025 revenue share by region. It
highlights the relative contribution of each region, with Delhi NCR
representing the largest share in the dashboard.

### 4. Key Business Insights

The dashboard presents the following observations: - FY2025 revenue
increased by approximately **10.54%** compared with FY2024. - FY2025
EBITDA was **₹695.6 Cr**, with an EBITDA margin of **28.26%**. - FY2025
PAT was approximately **₹492.3 Cr**. - Delhi NCR contributed the largest
share of regional revenue. - Regional revenue contribution remained
broadly stable between FY2024 and FY2025.

## Data Sources

The dashboard is based on the consolidated financial information and
regional revenue-share information reported in the following company
annual reports:

1.  [Dr. Lal PathLabs Annual Report
    FY2024--25](https://media.lalpathlabs.com/2025-05/Annual-Report-2024-25.pdf)
2.  [Dr. Lal PathLabs Annual Report
    FY2023--24](https://media.lalpathlabs.com/2024-06/Annual-Report-2023-24.pdf)

The annual reports are the source documents. Refer to the relevant
financial statements and regional disclosures when validating individual
figures.

## Repository Structure

A suggested repository structure is:

``` text
Healthcare-Diagnostics-Financial-Dashboard/
│
├── data/
│   ├── financial_summary.csv
│   ├── region_wise_revenue.csv
│   └── operational_metrics.csv
│
├── screenshots/
│   └── dashboard.png
│
├── Healthcare_Diagnostics_Dashboard.pbix
├── README.md
└── LICENSE
```

Keep only the files and folders that actually exist in your repository.
If your source data is stored in Excel rather than CSV, use the actual
workbook filename in the `data/` folder.

## How to View the Dashboard

1.  Download or clone this repository.
2.  Install **Microsoft Power BI Desktop**.
3.  Open `Healthcare_Diagnostics_Dashboard.pbix`.
4.  If Power BI asks for a data-source location, point it to the source
    files included in the repository and apply the changes.
5.  Select **Refresh** if the data sources are available and configured.
6.  Explore the KPI cards and regional comparison charts.

> The `.pbix` file is the interactive dashboard. The screenshot in
> `screenshots/` is provided as a quick preview.

## Methodology

1.  Collected the relevant financial and regional information from the
    FY2023--24 and FY2024--25 annual reports.
2.  Prepared structured financial and regional datasets for Power BI.
3.  Created KPI measures for revenue, revenue growth, EBITDA, EBITDA
    margin and PAT.
4.  Built regional revenue-share visualizations to compare FY2024 and
    FY2025.
5.  Arranged the visuals and key observations into a single-page
    executive overview.

## Key Calculations

The dashboard uses the following standard calculations. The underlying
DAX measure names may differ in the `.pbix` file.

**Revenue growth**

``` text
((FY2025 Revenue - FY2024 Revenue) / FY2024 Revenue) * 100
```

**EBITDA margin**

``` text
(FY2025 EBITDA / FY2025 Revenue) * 100
```

Regional contribution is displayed as a percentage share, using the
regional share values reported or prepared from the source disclosures.

## Scope and Limitations

-   The dashboard focuses on FY2023--24 and FY2024--25; it is not a live
    financial-data feed.
-   Regional charts show **percentage contribution**, not absolute
    regional revenue in ₹ crore.
-   The dashboard is an analytical summary of published information, not
    investment advice.
-   The key insights are descriptive observations based on the displayed
    data.
-   Forecasting, DCF valuation, competitor benchmarking and market-entry
    analysis are outside the scope of this dashboard.

## Disclaimer

This is an independent academic/personal analytics project created for
learning and portfolio demonstration. It is not affiliated with,
endorsed by, or prepared on behalf of Dr. Lal PathLabs Ltd. All company
information should be checked against the original annual reports.

## Author

**Sumit Kosta**\
B.Tech, Electrical Engineering -- NIT Rourkela

-   GitHub: [sumitkosta001](https://github.com/sumitkosta001)
