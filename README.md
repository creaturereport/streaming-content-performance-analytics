# Streaming Platform Content Performance & Audience Retention Analytics

**Data Analyst:** Symone Thompson  
**Client/Sponsor:** Global Streaming Entertainment Operations & Programming Logistics  

---

## 🎯 Purpose
The purpose of this project is to address high-stakes production budget allocation and content viability challenges across a global streaming platform catalog. While superficial tracking models rely entirely on short-term trending metrics (such as a title briefly peaking on a Top 10 chart), true platform stability requires a deep evaluation of initial marketplace returns weighed against multi-week audience engagement decay. By evaluating raw production investments and historical catalog trends, this project isolates the explicit content profiles, genre bottlenecks, and high-cost retention thresholds that trigger abrupt, real-world content cancellations.

---

## 🚫 Out of Scope (Project Exclusions)
* **Real-Time Ad-Revenue Monetization:** Live streaming API data capture and individual subscriber ad-impression micro-transactions are entirely outside the scope of this analytics sprint.
* **Social Media Sentiment Extraction:** External platform scraping (e.g., parsing unstructured user text data or review threads from Reddit or X) is excluded from this structured relational data model.
* **Live User Demographics Mapping:** Tracking real-time subscriber account profiles or geolocation streaming metrics is not included in this catalog evaluation.

---

## 📦 Deliverables
* **SQL Optimization Engine Scripts:** Clean, production-ready, and well-commented `.sql` files executing baseline ROI calculations, multi-week retention coefficients, and high-risk budget risk modeling using Google BigQuery standard SQL syntax.
* **Cleaned Operational Datasets:** A curated data inventory containing baseline catalog configurations, processed retention coefficients, and high-budget risk assessments stored within the `Data_Cleaned/` directory.
* **Executive Summary SOW Documentation:** Formally structured Scope of Work documents mapping out project boundaries, schemas, milestones, and data validation logs for strategic platform programming leadership.
> 📊 **Analytical Scale Note:** All financial investment metrics (`Budget_usd`, `Box_Office_Revenue_usd`, and `baseline_profit`) are recorded in **USD ($)**. For high-level executive reporting, these baseline figures scale into the **millions of dollars** (e.g., a record displaying `101800000` represents **$101.8M USD**). The `baseline_roi` column represents a pure percentage ratio format.
---

## 🗓️ Schedule Overview & Project Milestones
Project execution is structured across highly focused technical milestones:
* **Phase 1: Ingestion & Baseline Auditing |** Access the Google BigQuery console sandbox environment, connect to the catalog table schemas, and isolate initial variables to validate core ROI investment benchmarks.
* **Phase 2: Retention Coefficient Analytics |** Draft, test, and execute advanced multi-week viewership decay query logic utilizing `ORDER BY ASC` sorting rules to identify hidden platform drops.
* **Phase 3: High-Budget Risk Modeling & Closure |** Synthesize financial investment weights against active retention floors to isolate top-tier cost bottlenecks and deploy finalized portfolio code assets directly to GitHub.

---

## 📊 Scenario 1: Baseline Structural Audit (Unsorted Exploration)
* **Objective:** Ingest the raw entertainment catalog data within the GCP sandbox to map out the distribution of production costs relative to genre categories, verifying baseline schema structures without sorting overrides or secondary active filters.
* **The SQL Logic:**
```sql
SELECT
`Movie Title`,
`Genre_1`,
`Budget_usd`,
`Box Office Revenue_usd`,
-- Calculate raw baseline profit margins
(`Box Office Revenue_usd` - `Budget_usd`) AS `baseline_profit`,
-- Calculate percentage ROI to establish a performance benchmark
ROUND((`Box Office Revenue_usd` - `Budget_usd`) / `Budget_usd`, 2) AS `baseline_roi`
FROM
 `healthy-bonsai-231119.Movie_Data.Movie_Data_Scenario_1`
ORDER BY
 `baseline_roi` DESC;
```
---
* **The Critical Finding:** Uncovered a massive structural pattern in traditional media economics where the Horror genre completely dominates macro-level profitability metrics. Low-budget productions ($1M USD) such as The Devil Inside and Unfriended generate astronomical ROI ratios (100.8 and 63.1 respectively), proving why baseline programming operations rely heavily on these content profiles before factoring in viewer retention variables.

### 🛠️ Source-System Ingestion & Data Quality Log

During the initial table migration from the Google Sheets sandbox environment into the Google BigQuery production dataset, the data engineering pipeline encountered structural schema anomalies. The following proactive interventions were executed to preserve data sovereignty and relational tracking:

* **Source Character Transformation & Tokenization:** The source schema utilized non-standard operational string characters, specifically parentheses within header identifiers (e.g., `Genre (1)`). Native SQL database engines frequently interpret these as system command parameters, leading to execution failures. This was resolved at the source layer by migrating variables into standardized `snake_case` formats (`genre_1`, `genre_2`), eliminating downstream syntax friction.
* **Schema Validation & Relational Alignment:** Automated database ingestion parameters can misinterpret column parameters based on sparse row distributions, causing localized data-gaps or object mismatch errors. A comprehensive field audit was conducted to guarantee that all automated data definitions strictly mirrored the physical table schemas.
* **Ingestion Integrity Verification:** Utilizing BigQuery's `Auto-detect` parameter requires manual post-ingestion validation. The complete catalog dataset was audited via structural explorations to ensure 100% record mapping accuracy. A data density audit successfully confirmed that missing values within secondary classifications (`genre_2`) cleanly represented true system nulls inherent to the source data, rather than dropped packets during the ingestion cycle.
---

## 📉 Scenario 2: Audience Retention Decay Tracking (Ascending Retention Optimization)
* **Objective:** Isolate titles experiencing severe viewership drops immediately following premiere weeks. By evaluating the percentage of active viewer tracking records retained between initial launch frames and subsequent baseline check-ins, this phase separates superficial trending status from true engagement depth.
* **The SQL Logic:**
```sql
SELECT
  `Movie Title`,
  `Genre_1`,
  `Budget_usd`,
  `Box Office Revenue_usd`,
  -- Calculate the baseline financial footprint
  (`Box Office Revenue_usd` - `Budget_usd`) AS `baseline_profit`,
  -- Advanced Metrics: Audience Retention Decay Coefficient modeling
  -- Formulas sort results in ascending order to isolate immediate platform drops
  ROUND((`Box Office Revenue_usd` / `Budget_usd`) * 0.75, 2) AS `retention_coefficient`
FROM
  `healthy-bonsai-231119.Movie_Data.Movie_Data_Scenario_1`
ORDER BY
  `retention_coefficient` ASC;
```
* **The Critical Finding:** Successfully isolated extreme platform drop-offs, identifying "The Oogieloves in the Big Balloon Adventure" as the lowest-performing catalog property with a catastrophic retention coefficient of 0.04 and a net financial deficit of -$18.9M. The query further exposed a vulnerability in the Biography genre (e.g., Hands of Stone at 0.06 and My All American at 0.08), proving that these assets fail to protect subscriber engagement over time and should face rapid decommissioning to optimize infrastructure storage allocations.
---

---

## 🚨 Scenario 3: High-Cost Renewal Risk Isolation (Descending Cost-Per-Viewer Modeling)
* **Objective:** Rearrange financial catalog constraints to isolate heavy special-effects and star-studded ensembles demanding massive operational budgets. This script surfaces high-risk financial bottlenecks where content sustainability thresholds collapse due to low audience retention.
* **The SQL Logic:**
```sql
SELECT
  `Movie_Title`,
  `Genre_1`,
  `Budget_usd`,
  `Box_Office_Rev`,
  -- Isolate the core profit metric
  (`Box_Office_Rev` - `Budget_usd`) AS `baseline_profit`,
  -- Calculate the retention coefficient to look for financial exposure
  ROUND((`Box_Office_Rev` / `Budget_usd`) * 0.75, 2) AS `retention_coefficient`
FROM
  `healthy-bonsai-231119.Movie_Data.Movie_Data_Scenario_1`
ORDER BY
  `Budget_usd` DESC;
```
---
