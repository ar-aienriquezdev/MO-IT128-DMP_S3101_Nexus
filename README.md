# FinMark Customer Segmentation Project (MO-IT128)

Customer segmentation analytics project for **MO-IT128 - Data Mining Principles** focusing on end-to-end data preparation, feature engineering, exploratory analysis, and clustering-based segmentation.

> **Current Status:** ✅ **Milestone 1 Completed** + ✅ **Milestone 2 Completed (Customer Segmentation & Cluster Profiling)**

---

## Course Information
- **Course Code:** MO-IT128 - Data Mining Principles  
- **Section:** S3107  

---

## Team Nexus

**Authors/Analysts:**
- **Abegail Imee Enriquez** — Lead Developer & Data Analyst  
- **Francisco Cabangon** — MS 1 Team Leader & Data Analyst  
- **Alvin Tubtub** — Quality Assurance Analyst  

---

## Project Overview

FinMark’s business case centers on understanding customer behavior using transaction and feedback signals. This project builds a clean, model-ready dataset and a well-structured feature table that supports customer segmentation and business-ready customer personas.

**Primary objectives:**
- Prepare and clean multi-source company datasets (transactions, products, customer feedback)
- Engineer meaningful customer-level features (spending, engagement, temporal behavior, experience)
- Use EDA + visualization to validate data quality, detect patterns, and support segmentation decisions
- Perform clustering, profiling, and recommendations for actionable customer segments (Milestone 2)

---

## Milestone 1 Summary (Completed ✅)

Milestone 1 delivers an analysis-ready pipeline that converts raw inputs into structured outputs for segmentation.

### What was built in Milestone 1
**1) Data Preparation & Cleaning**
- Standardized formats (data types, naming, datetime parsing)
- Handled missing values and duplicates
- Consolidated datasets into clean, reliable tables
- Exported clean datasets for reproducibility and submission

**2) Feature Engineering (Customer-Level)**
- Spending intensity and stability: `total_spend`, `avg_spend`, `txn_count`
- Temporal behavior: `pct_business_hours_txn`, `pct_weekend_txn`, time-of-day shares, average transaction hour
- Satisfaction & engagement signals: winsorized/capped satisfaction and recommendation metrics, feedback counts
- **Income grouping using quartiles (Q1/Q3)** derived from transaction-based spend features (Low/Medium/High)

**3) EDA & Visualization Suite**
A complete visual storyline was created to support segmentation readiness, including:
- **Income Group Analysis (Quartile Segmentation)**
- **Customer Spending Behavior Analysis**
- **Customer Temporal Behavior Analysis**
- **Customer Satisfaction & Advocacy Analysis**
- **Transaction Type Distribution**
- **Feature Correlation Matrix (selected features)**

### Key findings (Milestone 1)
- **Spending is right-skewed**, meaning a smaller segment contributes disproportionately higher spend (useful for segmentation).
- **Transaction frequency strongly aligns with total spend** (behavioral driver for revenue).
- **Quartile-based income tiers show clear separation**, validating an interpretable segmentation proxy.
- Customers transact mostly **outside business hours** and primarily on **weekdays**, offering operational and campaign timing opportunities.
- Satisfaction and recommendation signals are **largely independent** of spend/frequency, which makes them valuable as additional segmentation dimensions.

---

## Milestone 2 Summary (Completed ✅)

Milestone 2 completes the **Customer Segmentation** stage using clustering and turns segments into **business-friendly personas** with recommendations.

### What was built in Milestone 2
**1) Pre-model checks**
- Confirmed feature readiness for clustering (numeric selection, ID exclusions)
- Applied standard scaling for fair distance-based clustering
- Used PCA for stability/noise reduction (interpretation still based on original business features)

**2) Clustering workflow**
- Evaluated a range of **k** values using:
  - **Elbow (Inertia)**
  - **Silhouette**
  - **Davies–Bouldin**
  - **Calinski–Harabasz**
- Selected **k = 4** to balance **statistical quality** with **business interpretability**
- Visualized clusters in PCA space (PC1 vs PC2) with centroids

**3) Segment profiling & business interpretation**
- Produced cluster-size distribution and cluster profile comparisons vs overall averages
- Created business-friendly segment names based on:
  - **Monetary (Total Spend)**
  - **Frequency (Txn Count)**
  - **Recency (Recency Days)**
  - **Satisfaction (Satisfaction Mean)**
- Added stakeholder-ready recommendations per segment (retain, grow, win-back, service recovery)

**4) Exports (Milestone 2 outputs)**
- Saved customer assignments and cluster profile tables to a dedicated folder:
  - `Milestone 2/Clusters/`

---

## Repository Structure

This repository is organized by milestone to keep work modular and submission-ready.

.
├─ Milestone 1/
│  ├─ Data/
│  │  ├─ Raw/
│  │  └─ Cleaned/
│  ├─ Features/
│  ├─ Notebook/
│  └─ Documentation/
├─ Milestone 2/
│  ├─ Notebook/
│  ├─ Clusters/
│  └─ Documentation/
└─ README.md


> See `Milestone 1/Documentation/README.md` for detailed MS1 workflow, decisions, and output descriptions.  
> See `Milestone 2/Documentation/README.md` for detailed MS2 workflow, segment definitions, and recommendations.

---

## How to Run

### Milestone 1
1) Open:
- `Milestone 1/Notebook/FinMark_Milestone1_Preprocessing_FeatureEngineering_EDA.ipynb`

2) Ensure the raw datasets exist in:
- `Milestone 1/Data/Raw/`

3) Run the notebook top-to-bottom.
- Cleaned outputs will be saved to: `Milestone 1/Data/Cleaned/`
- Engineered features will be saved to: `Milestone 1/Features/`

---

### Milestone 2 (Customer Segmentation)
1) Open:
- `Milestone 2/Notebook/FinMark_Milestone2_Clustering_Segmentation.ipynb`

2) Ensure Milestone 1 outputs are available (cleaned/features) in their expected folders:
- `Milestone 1/Data/Cleaned/`
- `Milestone 1/Features/`

3) Run the notebook top-to-bottom.
- Cluster outputs will be saved to: `Milestone 2/Clusters/`
  - `customer_cluster_assignments.csv`
  - `cluster_profiles_means.csv`

---

## Notes
- This project is designed for reproducibility: all key exports (cleaned + features + clusters) are saved and versionable.
- Naming conventions and documentation are included for academic and GitHub readiness.

---

## License
Academic project for MO-IT128. Reuse or distribution should follow course and institutional guidelines.