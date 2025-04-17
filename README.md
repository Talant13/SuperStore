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

SELECT
State as state,
COUNT(\*) AS total_transactions,
ROUND(SUM(Sales), 2) AS total_sales,
ROUND(SUM(Profit), 2) AS total_profit,
ROUND(AVG(Profit), 2) AS avg_profit_per_order
FROM SuperStoreDataset.store_data
group by state
order by ROUND(SUM(Profit), 2) desc

![KPI Overview](Visuals/KPI_Overview_1.png)

- **Total Customers**: Number of unique customers
- **Total Transactions**: Total sales entries
- **Total Sales**: Total revenue across all sales
- **Total Profit**: Combined profit
- **Average Profit per Transaction**: Average profitability per sale

🛠 Tools: SQL (Google BigQuery)
