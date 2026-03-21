# Online Retail Customer Analytics 📊

This project provides a deep dive into the transaction data of a UK-based online retail store. Using Python, I translated raw transactional logs into actionable business strategies focusing on customer retention, lifetime value, and segmentation.

## 🚀 Key Business Insights

* **RFM Segmentation:** Identified that **26.8% of customers generate 80% of total revenue**, confirming the Pareto Principle.
* **Churn Warning:** Established a churn baseline showing that **33.3% of the database is inactive** for over 90 days, closely aligning with our "Hibernating" RFM segment.
* **Operational Anomaly:** Discovered that transaction timestamps likely represent warehouse processing hours rather than actual customer shopping times, preventing misleading marketing schedules.
* **Expansion Strategy:** Identified Germany and France as high-value markets driven by "Whale" customers, while Belgium was noted as the most stable market for testing new campaigns.

## 🛠️ Technical Workflow

1.  **Data Engineering:** Handled missing values, treated cancellations/returns separately to ensure metric integrity, and performed feature engineering (LTV, Cohort Index).
2.  **Cohort Analysis:** Built retention matrices and spending heatmaps using `Pandas` and `Seaborn`.
3.  **RFM Modeling:** Applied quintile-based scoring to segment the user base into Champions, At Risk, Newcomers, and Hibernating customers.
4.  **Market Basket Analysis:** Used `itertools` to identify products frequently bought in pairs to suggest "Frequently Bought Together" bundles.

## ⚙️ Engineering Highlights & Optimization

* **Memory Efficiency:** Optimized a potential Cartesian explosion in Market Basket Analysis (self-joins) by implementing early deduplication and `itertools.combinations`, reducing memory overhead from **~4.9 GB to ~99 MB**.
* **Statistical Integrity:** Switched from Mean to **Median-based metrics** for international ARPU and LTV tracking to neutralize the impact of "Whale" customers (outliers), significantly mitigating the skewness caused by outliers.
* **Data Robustness:** Engineered a vectorized offset logic for cancelled orders, ensuring returns do not inflate active customer counts or churn baselines.
* **Analytical Significance:** Implemented minimum sample size filters (n>=20) for geographic analysis to eliminate statistical noise from low-volume markets.

## 📈 Visualizations Included
* Cohort Retention Heatmaps (Absolute & Percentage)
* Median Monthly Spending Evolution
* Customer Distribution by RFM Segments (with percentage annotations)
* Weekly/Hourly Purchase Heatmaps

## 🧰 Tech Stack 
* **Python** (Pandas, Numpy)
* **Visualization:** Seaborn, Matplotlib
* **Algorithms:** Itertools (Combinations), Collections (Counter)