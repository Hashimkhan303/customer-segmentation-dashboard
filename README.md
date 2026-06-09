# Customer Segmentation Dashboard

**Tools:** Python | Pandas | Scikit-learn | SQLite | Power BI  
**Domain:** E-Commerce | **Type:** End-to-End Analytics Project

\---

## Project Overview

This project segments **5,878 customers** from a real UK-based online retail business using RFM analysis (Recency, Frequency, Monetary) combined with K-Means clustering. The goal is to identify distinct customer groups and recommend targeted business strategies for each segment.

The final output is an interactive 3-page Power BI dashboard that allows stakeholders to explore customer behavior, compare segments, and plan marketing actions.

\---

## Business Questions Answered

* Who are our most valuable customers?
* Which customers are at risk of churning?
* How do different customer segments behave in terms of spending and frequency?
* What marketing action should we take for each segment?

\---

## Dataset

**Name:** Online Retail II  
**Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/502/online+retail+ii) — also available on [Kaggle](https://www.kaggle.com/datasets/mashlyn/online-retail-ii-uci)  
**Type:** E-commerce transactions  
**Period:** December 2009 – December 2011  
**Original Size:** 1,067,371 transactions across 40+ countries  
**After Cleaning:** 5,878 unique customers

|Column|Description|
|-|-|
|Invoice|Transaction invoice number|
|StockCode|Product code|
|Description|Product name|
|Quantity|Units purchased per transaction|
|InvoiceDate|Date and time of transaction|
|Price|Unit price in GBP|
|Customer ID|Unique customer identifier|
|Country|Customer country|

> \*\*Note:\*\* The raw data file (`raw\_data.csv`) is not included in this repository due to its large size (90MB).  
> Download it from Kaggle: https://www.kaggle.com/datasets/mashlyn/online-retail-ii-uci  
> Place it in the `data/` folder as `raw\_data.csv` before running the notebooks.

\---

## Project Structure

```
customer-segmentation-project/
│
├── data/
│   └── customer\_segmentation\_cleaned.csv
│
├── notebooks/
│   ├── customer\_segmentation\_analysis.ipynb
│   └── sql\_queries.ipynb
│
├── Dashboard/
│   └── customer\_segmentation.pbix
│
├── Screenshots/
│   ├── page1\_overview.png
│   ├── page2\_rfm\_deep\_dive.png
│   └── page3\_strategy.png
│
├── sql\_results/
│   ├── 01\_segment\_performance.csv
│   ├── 02\_customer\_tiers.csv
│   ├── 03\_recency\_status.csv
│   ├── 04\_top\_customers.csv
│   └── 05\_cluster\_analysis.csv
│
└── README.md
```

\---

## Methodology

### Step 1 — Data Cleaning

* Removed duplicates and null values
* Filtered out cancelled transactions (invoices starting with C)
* Removed negative quantities and zero prices
* Exported cleaned dataset for RFM analysis

### Step 2 — RFM Analysis

* Calculated Recency, Frequency, and Monetary values per customer
* Scored each dimension on a 1–5 scale
* Combined scores into RFM segments with business labels

### Step 3 — K-Means Clustering

* Scaled RFM features using StandardScaler
* Used Elbow Method to determine optimal k=4
* Applied K-Means clustering and validated results with cluster profiles
* Visualized clusters using Radar chart and 3D scatter plot

### Step 4 — SQL Analysis

* Ran 5 business queries using SQLite
* Queries cover: segment performance, customer tiers, recency status, top customers, and cluster analysis

### Step 5 — Power BI Dashboard

* Built 3-page interactive dashboard
* Page 1: RFM Overview — KPI cards, donut chart, revenue bar chart
* Page 2: RFM Deep Dive — combo chart, segment revenue comparison
* Page 3: Segment Strategy \& Action Plan — avg monetary chart, summary table, recommendations

\---

## Key Findings

|Segment|Customers|Avg Monetary|Avg Recency|Insight|
|-|-|-|-|-|
|Champions|1,182|$10,397|22 days|Highest value, most recent|
|At Risk|880|$2,525|276 days|High value but losing engagement|
|Hibernating|2,045|$555|411 days|Largest group, needs re-engagement|
|Potential Loyalists|540|$1,764|55 days|Recent buyers with growth potential|
|New Customers|894|$861|40 days|Recently acquired, low frequency|
|Loyal Customers|337|$1,111|13 days|Frequent buyers, lower spend|

**Key Insight:** Champions represent only 20% of customers but drive the majority of revenue. Hibernating customers are the largest segment (34%) and the biggest re-engagement opportunity.

\---

## Recommended Actions by Segment

|Segment|Recommended Action|
|-|-|
|Champions|Reward with loyalty program and early access offers|
|At Risk|Send win-back email campaign with special discount|
|Hibernating|Offer strong discount to re-engage (30%+ off)|
|Potential Loyalists|Upsell with targeted personalized offers|
|New Customers|Launch onboarding email campaign|
|Loyal Customers|Maintain with regular communication and rewards|

\---

## Dashboard Screenshots

### Page 1 — RFM Overview

!\[Page 1](Screenshots/page1_overview.png)

### Page 2 — RFM Deep Dive

!\[Page 2](Screenshots/page2_rfm_deep_dive.png)

### Page 3 — Segment Strategy \& Action Plan

!\[Page 3](Screenshots/page3_strategy.png)

\---

## Tools \& Technologies

|Tool|Purpose|
|-|-|
|Python 3|Data cleaning, RFM analysis, clustering|
|Pandas|Data manipulation|
|Scikit-learn|K-Means clustering, feature scaling|
|Matplotlib / Seaborn|Visualizations in notebooks|
|SQLite|SQL business queries|
|Power BI|Interactive dashboard|

\---

## How to Run

1. Clone this repository
2. Download raw data from Kaggle and place in `data/` folder as `raw\_data.csv`
3. Open `notebooks/customer\_segmentation\_analysis.ipynb` in Jupyter or Google Colab
4. Run all cells in order
5. Open `notebooks/sql\_queries.ipynb` to view SQL analysis
6. Open `Dashboard/customer\_segmentation.pbix` in Power BI Desktop

\---

## Author

**Hashim**  
Data Analyst | Python · SQL · Power BI .Machine Learning
Google Data Analytics Certificate | Google Advanced Data Analytics Certificate

