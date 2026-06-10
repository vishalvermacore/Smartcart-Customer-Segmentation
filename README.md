# SmartCart Customer Segmentation System

An end-to-end unsupervised machine learning project that segments 2,240 e-commerce customers into 4 distinct behavioural clusters using K-Means and Agglomerative Clustering — enabling personalised marketing, targeted retention, and data-driven business decisions.

---

## Problem Statement

SmartCart, a growing e-commerce platform, was applying the same generic marketing strategy to every customer regardless of their behaviour, income, or engagement level. This resulted in inefficient spend, missed retention opportunities, and no visibility into high-value segments.

**Goal:** Discover hidden customer patterns using unsupervised ML and group customers into meaningful segments based on purchasing behaviour, engagement levels, and loyalty indicators.

---

## Dataset

| Property | Detail |
|---|---|
| Records | 2,240 customers |
| Features | 22 attributes |
| Domain | Demographics, Purchase Behaviour, Channel Activity, Customer Feedback |

**Key Features Used:**
- `Income`, `Age`, `Customer_Tenure_Days`
- `Total_Spendings`, `Total_Children`
- `NumWebPurchases`, `NumStorePurchases`, `NumCatalogPurchases`
- `NumWebVisitsMonth`, `Recency`, `Response`, `Complain`
- `Education`, `Living_With`

---

## Project Workflow
Raw Data
│
▼
Data Preprocessing        → Handle missing values (Income median imputation)
│
▼
Feature Engineering       → Age, Tenure, Total Spend, Total Children,
│                         Education grouping, Living situation
▼
Outlier Removal           → Age < 90, Income < 600,000
│
▼
Encoding & Scaling        → OneHotEncoder + StandardScaler
│
▼
Dimensionality Reduction  → PCA (3 components)
│
▼
Cluster Optimisation      → Elbow Method + Silhouette Analysis
│
▼
Clustering                → K-Means + Agglomerative Clustering (Ward)
│
▼
Cluster Profiling         → Business interpretation of each segment

---

## Tech Stack

| Category | Tools |
|---|---|
| Language | Python 3 |
| Data Manipulation | Pandas, NumPy |
| Visualisation | Matplotlib, Seaborn |
| Machine Learning | Scikit-learn |
| Dimensionality Reduction | PCA (Scikit-learn) |
| Cluster Validation | KneeLocator, Silhouette Score |

---

## Results — 4 Customer Segments

| Cluster | Segment | Avg. Income | Avg. Spend | Living With | Avg. Children | Campaign Response |
|---|---|---|---|---|---|---|
| 0 | Budget Families | £39,681 | £222 | Partner | 1.24 | 7.6% |
| 1 | Affluent Families | £72,808 | £1,237 | Partner | 0.51 | 16.7% |
| 2 | Struggling Singles | £36,960 | £166 | Alone | 1.27 | 14.2% |
| 3 | High-Value Singles | £70,723 | £1,190 | Alone | 0.46 | 32.0% |

### Segment Breakdown

**Cluster 0 — Budget Families**
Low-income couples with children. High web traffic but low conversion — price is the barrier, not intent. Best approached with family bundle deals and discount-led campaigns.

**Cluster 1 — Affluent Families**
High-income couples, heavy multi-channel shoppers spending 5× more than Cluster 0. Full-price buyers — discount campaigns are wasted here. Target with premium loyalty and early-access offers.

**Cluster 2 — Struggling Singles**
Lowest income, likely single parents, highest website visit frequency yet lowest spend. Conversion gap driven by financial constraints. Respond well to BNPL options and time-limited offers.

**Cluster 3 — High-Value Singles**
32% campaign response rate — 4× higher than Cluster 0. Longest-tenured, highest-spending, living alone with no children. The VIP segment that was invisible before segmentation.

---

## Key Insight

> **High web visits ≠ high spend.**

Cluster 2 visited the site the most every month yet had the lowest spending across all segments. Using visit frequency as a success metric without conversion context would lead to costly misallocated marketing budgets.

---

## Project Structure
SmartCart-Customer-Segmentation/
│
├── smartcart.ipynb        # Full notebook — EDA, modelling, profiling
└── README.md

---

## How to Run

**1. Clone the repository**
```bash
git clone https://github.com/vishalvermacore/Smartcart-Customer-Segmentation.git
cd Smartcart-Customer-Segmentation
```

**2. Install dependencies**
```bash
pip install pandas numpy matplotlib seaborn scikit-learn kneed
```

**3. Add the dataset**

Place `smartcart_customers.csv` in the project root directory.

**4. Run the notebook**
```bash
jupyter notebook smartcart.ipynb
```

---

## Author

**Vishal Verma**
Aspiring AI/ML Engineer | Building one project at a time

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat&logo=linkedin)](https://linkedin.com/in/vishalvermacore)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black?style=flat&logo=github)](https://github.com/vishalvermacore)
