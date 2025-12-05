# Elevate-labs-internship-task-6
# Sales Trend Analysis Using SQL (MySQL)

This project performs **monthly sales trend analysis** using **MySQL aggregation functions** on a real **E-commerce CSV dataset (10,000 records)**.

## Objective
To calculate:
- Monthly **Total Revenue**
- Monthly **Order Volume**

## Tools Used
- MySQL 8.0
- Kaggle E-commerce Dataset (CSV)

## Key SQL Operations
- `LOAD DATA INFILE` for CSV import  
- `YEAR()` and `MONTH()` for date extraction  
- `SUM()` for revenue calculation  
- `COUNT(DISTINCT)` for order volume  
- `GROUP BY` and `ORDER BY` for aggregation and sorting  

## Main Query
```sql
SELECT 
    YEAR(order_date)  AS year,
    MONTH(order_date) AS month,
    SUM(quantity * unit_price) AS total_revenue,
    COUNT(DISTINCT order_id)   AS order_volume
FROM orders
GROUP BY year, month
ORDER BY year, month;


