# Phase 1: Streaming Platform Catalog Optimization & Financial ROI Metrics

### The Portfolio Scenario
**Project Track:** Streaming Platform Catalog Optimization & Financial ROI Metrics  
**Data Analyst:** Symone Thompson  
**Client/Sponsor:** Streaming Content Platform Logistics & Financial Operations  
**Target Asset:** `01_raw_streaming_catalog_baseline.csv`

---

## Executive Summary & Objective
The objective of Phase 1 is to ingest and audit the raw, historical global entertainment catalog dataset within the Google Cloud Platform sandbox environment. By exploring the raw structural schemas of production budgets, genres, and initial box office returns, this analysis establishes an unmanipulated financial baseline. This foundational audit ensures subsequent retention optimization and operational cost-per-viewer tracks are calculated on a validated framework.

## Purpose
This phase maps out the distribution of production costs relative to genre categories without sorting overrides or secondary active filters. Establishing this baseline allows platform logistics executives to identify which media segments traditionally demand the highest capital investments and evaluate baseline market performance before introducing audience decay metrics.

---

## Scope / Major Project Activities

| Activity | Description |
| :--- | :--- |
| **Environment Setup & Data Ingestion** | Access the Google Cloud Platform sandbox, initialize a BigQuery workspace console, and ingest the raw catalog database. |
| **Schema Assessment & Data Hygiene** | Audit the technical structure of the imported catalog fields, verifying data types for numeric currencies (`Budget_usd`, `Box_Office_Rev`) and strings (`Genre_1`, `Movie_Title`) to fix any broken data types or null values. |
| **SQL Transformation & Aggregation** | Develop and execute clean, well-commented SQL scripts utilizing initial exploratory syntax to isolate variables and calculate base Return on Investment $$ROI = \frac{\text{Box\_Office\_Rev} - \text{Budget\_usd}}{\text{Budget\_usd}}$$ |
| **Insight Generation & Reporting** | Contrast unmanipulated data structures against standard relational expectations to deliver a definitive data validation report for strategic programming leadership. |

---

## This project does not include:
* **Granular Viewer Retention Tracking:** Multi-week audience decay metrics and streaming drop-off optimization rules are excluded from this baseline segment (reserved strictly for Phase 2 optimization tracks).
* **Real-Time Ad-Revenue Monetization:** Live streaming API data capture and individual subscriber billing micro-transactions are entirely outside the scope of this analytics sprint.

---

## Deliverables & Data Schema

*A specific list of fields that this project phase delivers.*

| Column Name | Data Type | Analytical Purpose |
| :--- | :--- | :--- |
| `Movie_Title` | STRING | Serves as the primary content ID to track distinct global production properties. |
| `Genre_1` | STRING | Establishes the foundational content categorization to assess macro-level financial trends. |
| `Budget_usd` | FLOAT | Represents the total initial capital investment required to produce and deliver the title. |
| `Box_Office_Rev` | FLOAT | The primary financial marketplace baseline return metric used to calculate raw project performance. |
| `baseline_profit` | FLOAT | Calculated column generated to hold the net dollar margin ($$\text{Revenue} - \text{Budget}$$). |
| `baseline_roi` | FLOAT | Calculated column created to hold macro-level percentage investment results. |

---

## Schedule Overview & Major Milestones
Project execution commences on June 20th, 2026, structured across highly focused technical milestones.

* **Milestone 1 (June 20th, 2026):** Query Drafting & Baseline Variable Validation — *Completed within 24 Hours.*
* **Milestone 2 (June 20th, 2026):** System Extraction to Google Sheets & CSV Formatting — *Completed within 48 Hours.*
* **Milestone 3 (June 21st, 2026):** Deployment of Dataset 01 to Local & Remote Project Directories — *Completed within 72 Hours.*

**Estimated date for completion:** June 22nd, 2026

---

## The Analytical Imperative
In entertainment analytics, calculating the ROI is crucial to determine the financial sustainability of continuing to produce specific content models. Analysts are relied upon to stay alert to massive variations in viewer output that directly impact platform revenue. When a sudden shift occurs, forecasts of income can be modeled proactively, ensuring that leadership can make strategic renewal or cancellation adjustments before significant capital is lost.
