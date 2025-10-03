# task---6
Task 6: Sales Trend Analysis Using Aggregations
📌 Objective

Analyze monthly revenue and order volume trends from the online_sales dataset to understand sales patterns over time.

🛠️ Tools & Technologies

Database: PostgreSQL / MySQL / SQLite

Concepts: SQL Aggregations, GROUP BY, ORDER BY, Date Functions

📂 Dataset

Table: online_sales
Columns:

order_id – Unique ID of each order

order_date – Date of the order

amount – Revenue from the order

product_id – ID of the purchased product

(Optional: product_quantity if available)

📜 SQL Script
-- Task 6: Sales Trend Analysis Using Aggregations

SELECT
    EXTRACT(YEAR FROM order_date) AS order_year,
    EXTRACT(MONTH FROM order_date) AS order_month,
    SUM(amount) AS total_revenue,
    COUNT(DISTINCT order_id) AS total_orders,
    AVG(amount) AS avg_order_value
    -- If product_quantity exists:
    -- SUM(product_quantity) AS total_products_sold
FROM
    online_sales
GROUP BY
    order_year, order_month
ORDER BY
    order_year, order_month;

📊 Results Example (Detailed)
order_year	order_month	total_revenue	total_orders	avg_order_value	total_products_sold
2024	1	152,300	1,120	136.0	2,980
2024	2	134,500	980	137.2	2,540
2024	3	178,250	1,240	143.7	3,150
2024	4	162,000	1,050	154.3	2,890
2024	5	185,900	1,310	141.9	3,420
🎯 Key Learnings

How to aggregate sales data by time (month, year).

Use of SUM(), COUNT(DISTINCT), and AVG() to generate insights.

Filtering by specific time periods using WHERE.

Presenting results in a structured format for trend analysis.

📁 Deliverables

sales_trend_analysis.sql → SQL script for trend analysis.

sales_trend_results.pdf → Sample results table (basic version).

sales_trend_results_detailed.pdf → Extended version with Avg Order Value & Total Products Sold.

README.md → This documentation file.
