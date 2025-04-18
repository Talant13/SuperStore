# 🏬 Sample Superstore Sales Analysis

This project explores the "Sample Superstore" dataset to uncover trends in sales, profit, shipping, and regional performance across the United States. The goal is to identify business insights that can drive better decision-making in areas like product strategy, regional investment, and customer targeting.

### 🔍 Key Questions Explored:

- Which product categories and sub-categories are the most/least profitable?
- How do sales and profits vary by region and state?
- Are there shipping modes or segments associated with high returns or losses?
- What strategies could improve overall profitability?

### 🧰 Tools & Technologies:

- Python
- Jupyter Notebook
- PowerBI
- BigQuery
- Data cleaning and exploratory data analysis (EDA)

The insights from this analysis can support strategic planning in retail, especially for optimizing logistics and maximizing profit margins.

## 📊 Executive Summary - Business KPIs

This query calculates key metrics from the Sample Superstore dataset to provide a quick overview of business performance:

<pre> ```
SELECT State as state,
       COUNT(\*) AS total_transactions,
       ROUND(SUM(Sales), 2) AS total_sales,
       ROUND(SUM(Profit), 2) AS total_profit,
       ROUND(AVG(Profit), 2) AS avg_profit_per_order
  FROM SuperStoreDataset.store_data
 group by state
 order by ROUND(SUM(Profit), 2) desc
``` </pre>

![KPI Overview](Visuals/KPI_Overview_1.png)

- **Total Customers**: Number of unique customers
- **Total Transactions**: Total sales entries
- **Total Sales**: Total revenue across all sales
- **Total Profit**: Combined profit
- **Average Profit per Transaction**: Average profitability per sale

---

---

## 🔑 Overall Performance KPIs

This executive snapshot highlights key KPIs derived from SQL analysis of the Sample Superstore dataset. It reveals patterns in sales, profitability, discount strategy, and customer segments to support smarter business decisions.

<pre>```
SELECT
  ROUND(SUM(Sales),) AS Total_Sales,
  ROUND(SUM(Profit),) AS Total_Profit,
  ROUND(AVG(Discount) * 100, 2) AS Avg_Discount_Percent
FROM SuperStoreDataset.store_data
```</pre>

---

### 🔑 Overall Performance KPIs

| Metric              | Value          |
| ------------------- | -------------- |
| 💵 **Total Sales**  | \$2,297,200.86 |
| 📈 **Total Profit** | \$286,397.02   |
| 🏷️ **Avg Discount** | 15.62%         |
| 🧾 **Orders**       | ~10,000        |

> 💡 **Profit Margin:** ~12.5% — healthy, but discounting is significantly eroding profitability.

---

### 🧠 Key Insights

- **High Discounts = Low Profit**: The average discount is **15.62%**, but profits are not scaling with sales.
- **Sales are strong**, but much of the margin is lost on overly discounted orders.
- Certain **product categories** (like _Tables_) are consistently unprofitable.
- The **Corporate** and **Home Office** segments show better profit per order than Consumer.

---

### ✅ Recommended Actions

- 🧮 Recalibrate discount strategy — aim for **≤10%** average.
- 🚫 Reduce or replace products with **chronic negative profit**.
- 📦 Prioritize **Technology** and **Office Supplies** in growth strategies.
- 🧑‍💼 Expand targeting toward **Corporate** and **Home Office** segments.

---

---

### 🌍 Regional Performance – Sales & Profit by Region

<pre>
```SELECT 
  Region,
  ROUND(SUM(Sales), 2) AS Sales,
  ROUND(SUM(Profit), 2) AS Profit
FROM SuperStoreDataset.store_data
GROUP BY Region
ORDER BY Profit DESC;```
</pre>

| Region  | 💵 Total Sales | 📈 Total Profit |
| ------- | -------------- | --------------- |
| West    | \$725,457.82   | \$108,418.45    |
| East    | \$678,781.24   | \$91,522.78     |
| South   | \$391,721.90   | \$46,749.43     |
| Central | \$501,239.89   | \$39,706.36     |

---

#### 🔎 Key Insights:

- **West** is the strongest region, leading in both sales and profit.
- **East** follows closely behind, showing balanced revenue and profitability.
- **South** has healthy revenue but a significantly lower profit margin — **possible cost or discount inefficiency**.
- **Central** has the **lowest profit** despite moderate sales, indicating room for margin improvement.

> ✅ **Actionable Step**: Conduct a cost analysis and discount review for South and Central regions to boost profitability.
