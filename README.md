# Task 6 – Sales Trend Analysis Using Aggregations

## 📌 Objective
To analyze monthly revenue and order volume using SQL aggregation functions on the `online_sales` dataset.

## 🛠️ Tools Used
- PostgreSQL
- SQL Functions: `SUM()`, `COUNT(DISTINCT)`, `GROUP BY`, `ORDER BY`, `EXTRACT()`

## 📊 SQL Query Used
```sql
SELECT 
  EXTRACT(YEAR FROM order_date) AS year,
  EXTRACT(MONTH FROM order_date) AS month,
  SUM(amount) AS total_revenue,
  COUNT(DISTINCT order_id) AS total_orders
FROM 
  online_sales
GROUP BY 
  year, month
ORDER BY 
  year, month;
| Year | Month | Total Revenue | Total Orders |
| ---- | ----- | ------------- | ------------ |
| 2023 | 01    | \$12,450      | 98           |
| 2023 | 02    | \$15,200      | 110          |
| 2023 | 03    | \$13,880      | 105          |
Analysis Summary
The SQL query groups sales data by year and month, calculating both total revenue and the number of unique orders. February shows peak performance, possibly due to seasonal or promotional campaigns. This analysis supports business decisions on demand forecasting, inventory management, and marketing.
