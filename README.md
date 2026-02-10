# FinMark Customer Segmentation Project (MO-IT128)

Customer segmentation analytics project for **MO-IT128 - Data Mining Principles** focusing on end-to-end data preparation, feature engineering, exploratory analysis, and clustering-based segmentation.

> **Current Status:** ✅ **Milestone 1 Completed** — Ready to proceed to **Milestone 2 (Customer Segmentation)**

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
- **Jeffrey Dollopac** — Asst. Quality Assurance Analyst  

---

## Project Overview

FinMark’s business case centers on understanding customer behavior using transaction and feedback signals. This project builds a clean, model-ready dataset and a well-structured feature table that supports customer segmentation in later stages.

**Primary objectives:**
- Prepare and clean multi-source company datasets (transactions, products, customer feedback)
- Engineer meaningful customer-level features (spending, engagement, temporal behavior, experience)
- Use EDA + visualization to validate data quality, detect patterns, and support segmentation decisions
- Progress into clustering and profiling for actionable customer segments (Milestone 2)

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

## Repository Structure

This repository is organized by milestone to keep work modular and submission-ready.

.
├─ Milestone 1/
│ ├─ Data/
│ │ ├─ Raw/
│ │ └─ Cleaned/
│ ├─ Features/
│ ├─ Notebook/
│ └─ Documentation/
└─ README.md


> See `Milestone 1/Documentation/README.md` for detailed MS1 workflow, decisions, and output descriptions.

---

## How to Run (Milestone 1)

1) Open the notebook inside:
- `Milestone 1/Notebook/FinMark_Milestone1_Preprocessing_FeatureEngineering_EDA.ipynb`

2) Ensure the raw datasets exist in:
- `Milestone 1/Data/Raw/`

3) Run the notebook top-to-bottom.
- Cleaned outputs will be saved to: `Milestone 1/Data/Cleaned/`
- Engineered features will be saved to: `Milestone 1/Features/`

---

## Milestone 2 Plan (Next Phase 🚀)

Milestone 2 will focus on **Customer Segmentation** and **cluster profiling** using the engineered feature table.

### Planned approach
**1) Pre-model checks**
- Review feature distributions and scaling strategy
- Address multicollinearity where needed (feature selection or reduction)
- Confirm stability of quartile tiers and core engineered metrics

**2) Clustering workflow**
- Standardize numeric features (e.g., StandardScaler)
- Determine optimal number of clusters:
  - Elbow method (inertia)
  - Silhouette score
  - (optional) Davies-Bouldin Index
- Apply clustering methods:
  - K-Means (primary)
  - (optional) Hierarchical clustering for validation

**3) Segment profiling & business interpretation**
- Interpret each cluster using spending + timing + satisfaction behavior
- Build a “segment profile card” per cluster (who they are, what they do, how to act)
- Provide FinMark-ready recommendations (targeting, retention, campaign timing)

---

## Notes
- This project is designed for reproducibility: all key exports (cleaned + features) are saved and versionable.
- Naming conventions and documentation are included for academic and GitHub readiness.

---

## License
Academic project for MO-IT128. Reuse or distribution should follow course and institutional guidelines.
