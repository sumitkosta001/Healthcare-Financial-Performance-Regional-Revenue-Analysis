# Data Validation Report: Dr. Lal PathLabs Financial & Operational Datasets (FY2023–24 vs FY2024–25)

## 1. Executive Summary & Validation Status
* **Validation Status:** **PASSED WITH NOTED STRUCTURAL & REGIONAL CLASSIFICATION CAVEATS**
* **Scope of Review:**
  1. [`financial_summary.csv`](file:///c:/Users/sumit/OneDrive%20-%20National%20Institute%20of%20Technology,%20Rourkela/Desktop/Healthcare-Diagnostics-BI/data/financial_summary.csv)
  2. [`operational_metrics.csv`](file:///c:/Users/sumit/OneDrive%20-%20National%20Institute%20of%20Technology,%20Rourkela/Desktop/Healthcare-Diagnostics-BI/data/operational_metrics.csv)
  3. [`region_wise_revenue.csv`](file:///c:/Users/sumit/OneDrive%20-%20National%20Institute%20of%20Technology,%20Rourkela/Desktop/Healthcare-Diagnostics-BI/data/region_wise_revenue.csv)
  4. [`source_notes.md`](file:///c:/Users/sumit/OneDrive%20-%20National%20Institute%20of%20Technology,%20Rourkela/Desktop/Healthcare-Diagnostics-BI/source_notes.md)
* **Underlying Audit Reports:**
  - `Annual-Report-2023-24.pdf` (Deloitte Haskins & Sells LLP audited, signed May 10, 2024; 336 pages)
  - `Annual-Report-2024-25.pdf` (Deloitte Haskins & Sells LLP audited, signed April 25, 2025; 348 pages)

All reported figures in the CSV files tie back to the source annual reports without fabrication or estimation. Detailed structural checks, regional comparability assessments, growth recalculations, and reporting caveats are documented below.

---

## 2. File-by-File Integrity & Structure Review

### A. Column Names, Data Types, Missing Values, and Duplicates
| Dataset | Rows / Cols | Duplicate Rows | Missing / Null Values | Format / Structural Finding |
| :--- | :--- | :--- | :--- | :--- |
| `financial_summary.csv` | 5 rows / 9 cols | 0 | 0 nulls | Headers conform to snake_case. Floating point figures represent values in ₹ crore. An empty trailing newline was detected as an empty parsing record in raw split readers. |
| `operational_metrics.csv` | 4 rows / 9 cols | 0 | 0 nulls | Headers conform to snake_case. Formats match numeric units (Millions, INR, Ratios). Trailing empty line noted. |
| `region_wise_revenue.csv` | 8 rows / 7 cols | 0 | 1 explicit `N/A` | Row 3 (`UP & UK`) contains `N/A` for `fy2023_24_revenue_reported_inr_cr`. Trailing empty line noted. |

### Structural Observations & File Cleanliness:
1. **Explicit `N/A` in `region_wise_revenue.csv`:**
   - In FY24, Dr. Lal PathLabs reported regional absolute revenue for **Rest of North India** (₹7,005M / ₹700.50 Cr) as a single consolidated block that encompassed Uttar Pradesh & Uttarakhand.
   - When UP & UK was separated into its own reporting line in the FY25 report, prior-year percentage share was restated (18.52%), but no corresponding isolated rupee figure was published in the FY24 report.
   - Preserving `N/A` rather than back-calculating or imputing values adheres strictly to the rule against fabricating missing data.
2. **Trailing Line Feed:**
   - Standard text-file trailing newlines (`\n`) are present in each CSV. Parsers expecting strict records should trim blank end lines.

---

## 3. Financial Metrics Verification against Statutory P&L and Source Notes

All financial metrics were verified against the audited **Consolidated Statement of Profit and Loss** (P&L) and the **Management Discussion & Analysis** (MD&A) tables.

| Metric | Source P&L (₹ Million) | Converted Value (₹ Crore) | Source Document & Exact Citation | Reconciliation with MD&A Disclosures |
| :--- | :--- | :--- | :--- | :--- |
| **FY24 Revenue from Operations** | ₹22,266.41M | **₹2,226.641 Cr** | AR 23-24: P. 249 (PDF) / P. 247 (Report), Note 28 | MD&A (P. 101) rounds to ₹22,266M (₹2,226.60 Cr). Reconfirmed in AR 24-25 P. 259. |
| **FY25 Revenue from Operations** | ₹24,613.95M | **₹2,461.395 Cr** | AR 24-25: P. 259 (PDF) / P. 257 (Report), Note 27 | MD&A (P. 112) rounds to ₹24,614M (₹2,461.40 Cr). |
| **FY24 Reported EBITDA** | ₹6,092.00M | **₹609.200 Cr** | AR 23-24: P. 19 & 101; AR 24-25: P. 22 & 112 | Non-GAAP operating metric directly reported by management in Financial Highlights and MD&A. |
| **FY25 Reported EBITDA** | ₹6,956.00M | **₹695.600 Cr** | AR 24-25: P. 22 & 112 (PDF) / P. 20 & 110 (Report) | Operating metric directly reported by management in Financial Highlights and MD&A. |
| **FY24 Profit Before Tax (PBT)** | ₹5,054.51M | **₹505.451 Cr** | AR 23-24: P. 249 (PDF) / P. 247 (Report) | MD&A (P. 101) rounds to ₹5,055M (₹505.50 Cr). |
| **FY25 Profit Before Tax (PBT)** | ₹6,247.99M | **₹624.799 Cr** | AR 24-25: P. 259 (PDF) / P. 257 (Report) | MD&A (P. 112) rounds to ₹6,248M (₹624.80 Cr). |
| **FY24 Profit After Tax (PAT)** | ₹3,622.93M | **₹362.293 Cr** | AR 23-24: P. 249 (PDF) / P. 247 (Report) | MD&A (P. 101) rounds to ₹3,623M (₹362.30 Cr). |
| **FY25 Profit After Tax (PAT)** | ₹4,922.52M | **₹492.252 Cr** | AR 24-25: P. 259 (PDF) / P. 257 (Report) | MD&A (P. 112) rounds to ₹4,922M (₹492.20 Cr). |
| **FY24 PAT (Owners of Company)** | ₹3,577.35M | **₹357.735 Cr** | AR 23-24: P. 249 (PDF) / P. 247 (Report) | Excludes non-controlling interest of ₹45.58M. |
| **FY25 PAT (Owners of Company)** | ₹4,871.38M | **₹487.138 Cr** | AR 24-25: P. 259 (PDF) / P. 257 (Report) | Excludes non-controlling interest of ₹51.14M. |

---

## 4. Operational Metrics Verification

| Metric | FY2023–24 Value | FY2024–25 Value | Source Document & Reference |
| :--- | :--- | :--- | :--- |
| **Patient Volume** | 27.6 Million | 28.8 Million | AR 23-24: P. 18 & 101; AR 24-25: P. 23 & 112 |
| **Sample Volume** | 78.2 Million | 85.6 Million | AR 23-24: P. 18 & 101; AR 24-25: P. 23 & 112 |
| **Revenue Per Patient** | ₹806 | ₹855 | AR 23-24: P. 101; AR 24-25: P. 112 |
| **Tests Per Patient** | 2.83 | 2.97 | AR 23-24: P. 101; AR 24-25: P. 112 |

---

## 5. Regional Categories Comparability & In-Depth UP & UK Analysis

### A. The Structural Reclassification in FY2024–25
In **FY2023–24 (AR 23-24, Page 101)**, Dr. Lal PathLabs reported its regional breakdown into **6 geographical buckets**:
1. Delhi NCR: ₹6,895M (31%)
2. Rest of North India: ₹7,005M (31%)
3. East India: ₹3,247M (15%)
4. West: ₹3,286M (15%)
5. South: ₹1,324M (6%)
6. Others: ₹508M (2%)
*Total:* ₹22,266M (100%)

In **FY2024–25 (AR 24-25, Page 112 & Page 23)**, the company altered its geographic reporting by carving out **Uttar Pradesh & Uttarakhand (UP & UK)** into an independent line item, expanding the disclosure to **7 geographical buckets**:
1. Delhi NCR: 31.08% (FY25) vs 31.11% (FY24)
2. UP & UK: **18.62%** (FY25) vs **18.52%** (FY24)
3. Rest of North India: **13.20%** (FY25) vs **12.87%** (FY24)
4. East India: 14.55% (FY25) vs 14.50% (FY24)
5. West: 14.62% (FY25) vs 14.80% (FY24)
6. South: 5.62% (FY25) vs 5.94% (FY24)
7. Others: 2.31% (FY25) vs 2.26% (FY24)
*Total:* 100.00% (FY25) vs 100.00% (FY24)

### B. Mathematical Re-Aggregation & Comparability Analysis
* Summing the restated FY24 percentages for **UP & UK (18.52%)** and **Rest of North India (12.87%)**:
  $$18.52\% + 12.87\% = 31.39\%$$
* In the FY24 Annual Report (Page 18 & 101), **Rest of North** was reported as **31%** (or $\frac{7005}{22266} = 31.46\%$).
* **Conclusion on Comparability:**
  - The historical **Rest of North India** in FY24 **cannot be directly compared** to **Rest of North India** in FY25 without aggregating UP & UK back into North India.
  - Doing a direct row-level comparison between FY24 "Rest of North India" (31% / ₹700.5 Cr) and FY25 "Rest of North India" (13.20%) would indicate an artificial, erroneous decline of ~58%. In reality, North India ex-NCR was split into UP & UK (18.62%) and Rest of North (13.20%), totaling **31.82%** in FY25 vs **31.39%** in FY24.

---

## 6. Growth Rate Recalculations & Percentage Checks

### A. Financial Growth Rates
1. **Revenue from Operations:**
   - Statutory P&L: $\frac{2461.395 - 2226.641}{2226.641} \times 100 = \mathbf{10.54\%}$
   - MD&A Reported Value: **10.5%** (AR 24-25, P. 112).
2. **EBITDA:**
   - Management Reported: $\frac{695.60 - 609.20}{609.20} \times 100 = \mathbf{14.18\%}$
   - MD&A Reported Value: **14.2%** (AR 24-25, P. 112).
3. **PBT:**
   - Statutory P&L: $\frac{624.799 - 505.451}{505.451} \times 100 = \mathbf{23.61\%}$
   - MD&A Table Figures: $\frac{6248 - 5055}{5055} \times 100 = \mathbf{23.60\%}$
   - MD&A Reported Value: **23.6%** (AR 24-25, P. 112).
4. **PAT (Total):**
   - Statutory P&L: $\frac{492.252 - 362.293}{362.293} \times 100 = \mathbf{35.87\%}$
   - MD&A Table Figures: $\frac{4922 - 3623}{3623} \times 100 = \mathbf{35.85\%}$
   - MD&A / CEO Message Reported Value: **35.9%** (AR 24-25, P. 18 & 112).

### B. Operational Growth Rates
1. **Patient Volume:**
   - Calculated: $\frac{28.8 - 27.6}{27.6} \times 100 = \mathbf{4.35\%}$
   - CEO Statement (P. 18): Mentions patient volumes increased by **4.2%** (likely computed on unrounded patient numbers).
2. **Sample Volume:**
   - Calculated: $\frac{85.6 - 78.2}{78.2} \times 100 = \mathbf{9.46\%}$
   - CEO Statement (P. 18): Mentions **9.5%** YoY growth.
3. **Revenue Per Patient:**
   - Calculated: $\frac{855 - 806}{806} \times 100 = \mathbf{6.08\%}$
4. **Tests Per Patient:**
   - Calculated: $\frac{2.97 - 2.83}{2.83} \times 100 = \mathbf{4.95\%}$

---

## 7. Inconsistencies & Discrepancies Identified in Source Reports

### 1. Typographical Transposition Error in AR 2024-25 Text (Page 112)
* **Finding:** In the narrative text under "PBT and PAT" on page 112 of the FY24–25 Annual Report, the text reads:
  > *"In FY 2025, PAT of the Company was INR 4,923 million as compared to INR 3,632 million in FY 2024, highlighting a growth of 35.9%."*
* **Analysis:**
  - The actual audited PAT for FY 2024 is **₹3,622.93 million** (reported in the same page's table as **₹3,623 million**).
  - The narrative inverted the digits to **"3,632"**.
  - Recalculating growth using 3,632 yields: $\frac{4923 - 3632}{3632} = 35.55\%$.
  - Recalculating growth using the correct ₹3,622.93M (or ₹3,623M) yields **35.87%**, which rounds exactly to the claimed **35.9%**.
* **Recommendation:** Rely strictly on the audited P&L and summary table values (₹3,622.93M / ₹3,623M) and disregard the narrative typo.

### 2. Geographic Reporting Shift (6 regions in FY24 vs 7 regions in FY25)
* **Finding:** The addition of UP & UK in FY25 without historical absolute currency reporting creates an asymmetric table in `region_wise_revenue.csv`.
* **Recommendation:**
  - Preserve `N/A` for the missing absolute rupee amount in raw source data.
  - In downstream BI dashboards, provide an aggregated **"Total North India (ex-NCR)"** metric that combines `UP & UK` and `Rest of North India` for multi-year trend charts.

---

## 8. Summary of Source References
* **Consolidated Statement of Profit and Loss (FY24):** AR 2023–24, Page 249 (PDF) / Page 247 (Report)
* **Consolidated Statement of Profit and Loss (FY25):** AR 2024–25, Page 259 (PDF) / Page 257 (Report)
* **Key Performance Indicators & MD&A (FY24):** AR 2023–24, Page 101 (PDF) / Page 99 (Report)
* **Key Performance Indicators & MD&A (FY25):** AR 2024–25, Page 112 (PDF) / Page 110 (Report)
* **Operational Highlights (FY24):** AR 2023–24, Page 18 (PDF) / Page 16 (Report)
* **Operational Highlights (FY25):** AR 2024–25, Page 23 (PDF) / Page 21 (Report)
* **CEO’s Statement (FY25):** AR 2024–25, Page 18 (PDF) / Page 16 (Report)
* **Segment Reporting Notes (Ind AS 108):** Note 39, AR 23–24, P. 294; Note 38, AR 24–25, P. 300

