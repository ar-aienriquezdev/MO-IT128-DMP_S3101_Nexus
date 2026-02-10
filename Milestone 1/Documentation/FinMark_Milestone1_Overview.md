# FinMark Milestone 1 — Documentation

This folder contains the supporting documentation for **FinMark Milestone 1** covering:
- Data preprocessing
- Feature engineering
- Exploratory Data Analysis (EDA)
- Visualization (final visual suite)
- Outputs, folder structure, and artifacts generated

---

## 1) Project Overview

**Goal:** Transform raw FinMark datasets into clean, analysis-ready tables, engineer customer-level features, and extract business insights through EDA and visual storytelling.

**Key Outputs:**
- Cleaned datasets (validated, standardized, ready for analysis)
- Customer-level feature table used for segmentation and relationship analysis
- Visual suites covering spending, segmentation, temporal behavior, satisfaction, and correlation patterns
- Summary insights supporting downstream modeling and business strategy

---

## 2) Repository Structure (Milestone 1)

> Folder naming may slightly vary depending on your local setup, but the intent remains the same.

FinMark/
├─ cleaned/ # cleaned/validated outputs from preprocessing + EDA-ready tables
├─ features/ # engineered customer-level feature tables
├─ models/ # reserved for ML artifacts (not the focus of MS1, may be empty)
├─ Documentation/ # documentation files (this folder)
│ ├─ README.md
│ └─ CHANGELOG.txt # optional progress log
├─ FinMark_Milestone1_Preprocessing_FeatureEngineering_EDA.ipynb
└─ README.md # (optional root README — short project intro)


---

## 3) Data Inputs

### Raw Inputs (source files)
- `customers_data.csv` — customer/company reference information  
- `products_data.csv` — product reference details  
- `transactions_data.csv` — transaction history  
- *(optional)* feedback or satisfaction source if provided in the dataset package

> Note: Raw files are not modified directly. All transformations occur in the notebook, producing outputs in `/cleaned` and `/features`.

---

## 4) Notebook Pipeline Summary (MS1)

### A) Preprocessing & Data Cleaning
Main actions performed:
- Loaded raw CSVs and performed basic inspection (schema, missing values, duplicates)
- Standardized column names and formatting (consistent naming and types)
- Cleaned invalid/missing records using defensible handling rules:
  - Removed duplicates where applicable
  - Imputed or excluded missing values depending on feature impact
  - Converted date/time columns into proper datetime types
- Validated dataset integrity and ensured clean joins between customer/product/transaction sources

**Outputs:**
- Cleaned transaction and reference tables saved into `/cleaned/`

---

### B) Feature Engineering (Customer-Level Table)
Built a customer-level feature table used for analysis and segmentation.

Core engineered features include (names may vary slightly):
- **Spending & frequency**
  - total_spend
  - avg_spend
  - txn_count
- **Temporal / recency**
  - tenure_days
  - recency_days
  - avg_txn_hour (customer-level average transaction hour)
  - day-of-week and time-of-day buckets (derived)
- **Behavioral proportions**
  - pct_weekend_txn
  - pct_business_hours_txn
  - pct_tod_Morning / Afternoon / Evening / Night (time-of-day shares)
- **Satisfaction / engagement**
  - satisfaction_mean (winsorized/capped where applicable)
  - ltr_mean (likelihood-to-recommend, winsorized/capped)
  - feedback_count

**Segmentation feature**
- **Income_Group**: quartile-based segmentation derived from total spend:
  - Low ≤ Q1
  - Medium Q1–Q3
  - High ≥ Q3

**Outputs:**
- Customer feature table saved in `/features/`

---

### C) Exploratory Data Analysis (EDA)
EDA focused on actionable business insight across four major themes:

1) **Income Group Analysis (Quartile Segmentation) — Visual Suite**
   - Distribution of customers by income tier
   - Mean spend comparison across tiers
   - Box plot of spend by tier to confirm separation

2) **Customer Spending Behavior Analysis**
   - Total spend distribution (mean/median)
   - Avg transaction amount distribution
   - Transaction count distribution
   - Spend vs frequency relationship (density view)

3) **Customer Temporal Behavior Analysis**
   - Business vs non-business hour activity (donut)
   - Weekday vs weekend activity (donut)
   - Transaction volume by day of week (bar)
   - Transaction volume by time-of-day bucket (bar)
   - Timing detail: avg transaction hour distribution + time-of-day mix by income group

4) **Customer Satisfaction Analysis (Winsorized)**
   - Satisfaction distribution
   - LTR distribution
   - Satisfaction by income tier
   - Satisfaction vs total spend relationship

5) **Feature Relationship Heatmap**
   - Correlation matrix of selected engineered features
   - Used a lighter/pastel-friendly heatmap style for readability

---

## 5) Visualization Style Notes
To ensure visuals are readable and consistent while still distinct:
- A pastel theme aligned with FinMark’s tone (pink / orange / purple accents)
- Improved label placements:
  - donut percentages positioned inside the rings
  - bar labels moved inside bars when needed
  - legends moved outside plots to avoid overlap

---

## 6) Key Results Snapshot (High Level)
*(Final exact values are printed directly in the notebook outputs.)*

- Spend distribution is right-skewed → supports segmentation
- Quartile-based income grouping yields clear separation across tiers
- Frequency strongly aligns with spend → strong behavioral driver
- Non-business hour activity dominates → timing has operational value
- Satisfaction signals are largely independent from spend → useful as a separate customer lens

---

## 7) How to Run
1) Create a Python environment (conda or venv)
2) Install dependencies:
   - pandas, numpy, matplotlib
3) Open and run the notebook:
   - `FinMark_Milestone1_Preprocessing_FeatureEngineering_EDA.ipynb`

> Note: If running from a fresh environment, ensure file paths to the raw CSVs match your local folder structure.

---

## 8) Deliverables Checklist (MS1)
- [x] Cleaned datasets saved
- [x] Engineered features created
- [x] EDA completed with multiple insight categories
- [x] Visualization suite finalized
- [x] Key insights summarized in notebook markdown
- [x] Documentation folder prepared for GitHub

---

## 9) Suggested Commit Message
**docs: add milestone 1 documentation (pipeline, structure, outputs)**

