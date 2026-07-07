# IDX Exchange – MLS Data Analyst Internship
 
A 12-week data analytics pipeline focused on transforming raw real estate MLS transaction data into interactive market intelligence dashboards and reports.
 
- **Primary Tools:** Python (Pandas), Tableau Desktop Public Edition, FileZilla (FTP)
- **Data Source:** CoreLogic Trestle API via IDX Exchange pipeline
- **Dataset Types:** Monthly MLS Listing & Sold transaction CSV files
- **Final Deliverable:** Tableau Dashboards + 1-Page Market Intelligence Report + Presentation
---
 
## Environment Setup
 
- **IDE:** Python IDLE
- **Tableau:** Tableau Desktop Public Edition
- **Data Retrieval:** FileZilla Client connected to the IDX Exchange FTP server
---
 
## Progress Tracker
 
### ✅ Week 0: MLS Data Pipeline Orientation
- [x] Established FTP connection via FileZilla using provided credentials.
- [x] Downloaded all available `CRMLSListing` and `CRMLSSold` CSV datasets (January 2024 through May 2026).
- [x] Reviewed Trestle Property Metadata document for field definitions and data types.
### ✅ Week 1: Monthly Dataset Aggregation
- [x] Loaded individual monthly CSV files from January 2024 through May 2026.
- [x] Concatenated all monthly files using Pandas into unified `listings` and `sold` DataFrames.
- [x] Filtered both datasets to `PropertyType == 'Residential'` only.
- [x] Documented row counts before and after concatenation and filtering.
- [x] Saved aggregated files as analysis-ready CSVs.
### ✅ Weeks 2–3: Dataset Structuring, Validation & Mortgage Enrichment (FINISHED)
- [x] Performed EDA to evaluate rows, columns, and data types.
- [x] Identified columns with >90% missing values.
- [x] Generated numeric distribution statistics (min, max, mean, median, percentiles) for `ClosePrice`, `LivingArea`, and `DaysOnMarket`.
- [x] Answered key market questions: median/mean close price, Days on Market distribution, sold above vs. below list price, date consistency issues, and top counties by median price.
- [x] Fetch live 30-year fixed mortgage rates (`MORTGAGE30US`) from the St. Louis Federal Reserve (FRED).
- [x] Resample weekly FRED data into monthly averages.
- [x] Merge mortgage rates onto both combined datasets via a `year_month` key.
- [x] Validate zero null rate values after merge.
- [x] Save both enriched datasets as new CSVs.


## Key Milestone Metrics
 
### Week 1 – Concatenation & Filter Summary
 
| Dataset | Pre-Filter Row Count | Post-Residential Filter Row Count | Notes |
| :--- | ---: | ---: | :--- |
| Sold Transactions | 681,599 | 458,336 | Filtered out non-residential property types |
| Active Listings | 860,898 | 547,162 | Filtered out non-residential property types |
 
### Weeks 2–3 – EDA Highlights
 
| Question | Result |
| :--- | :--- |
| Sold Residential share before filtering | 67.24% |
| Listing Residential share before filtering | 63.56% |
| Sold dataset shape after Week 1 filter | 458,336 rows × 84 columns | 
| Listings dataset shape after Week 1 filter | 547,162 rows × 84 columns | 
| Median sold close price | $820,000 | 
| Average sold close price | $1,186,149 | 
| Median Days on Market | 18 days |
| Sold above list price | 40.7% | 
| Sold below list price | 42.0% | 
| Sold at list price | 17.31% |
| Columns with >90% missing values | 10 columns  |
| Min DaysOnMarket (data quality flag) | -288 days | 
| Max LivingArea (data quality flag) | 17,021,321 sq ft | 


---
