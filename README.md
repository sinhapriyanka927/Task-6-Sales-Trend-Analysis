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
