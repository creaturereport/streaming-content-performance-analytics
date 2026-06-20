# movie 

**I ran into a need to do some data cleaning to transpose the data from Google Sheets > Google BigQuery that I thought were important to document (from a learners standpoint).Here are troublehooting notes taken to troubleshoot :

+ Source Data Sovereignty: Resolving complex characters like () with standard snake_case _ at the source spreadsheet saves hours of syntax debugging later.

+ Exact Relational Mapping: Ensuring naming conventions match your physical schemas exactly eliminates false errors like that location glitch.

+ Schema Ingestion Awareness: Trusting Auto detect but actively auditing the result keeps your data clean.

> 📊 **Analytical Scale Note:** All financial investment metrics (`Budget_usd`, `Box_Office_Revenue_usd`, and `baseline_profit`) are recorded in **USD ($)**. For high-level executive reporting, these baseline figures scale into the **millions of dollars** (e.g., a record displaying `101800000` represents **$101.8M USD**). The `baseline_roi` column represents a pure percentage ratio format.

🔍 Analyzing the Baseline Reality - Phase 1
Looking closely at the top 11 rows, the baseline query just exposed a massive strategic pattern in traditional media economics:

+ The Micro-Budget Phenomenon: Look at The Devil Inside and Unfriended. With tiny $1M budgets (Budget_usd), their box office returns yielded astronomical ROI ratios (100.8 and 63.1).

+ Genre Dominance: Notice how Horror completely dominates the top rankings. From an operational standpoint, this proves why studio executives rely heavily on low-risk, high-return genre formulas for baseline platform profitability.
sql
```
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
**Question: The foundation to layer on the real-world streaming twist: What happens to these highly profitable titles when audience retention decay hits?
