# 📊 Task 6 — Sales Trend Analysis Using Aggregations

This task is part of the **Data Analyst Internship** program.  
The objective is to analyze **monthly revenue** and **order volume** using SQL aggregation techniques.

---

## 📁 Dataset Used
A sample dataset named **online_sales** was used (SQLite database format).

### Table: `online_sales`
| Column Name   | Description                        |
|---------------|------------------------------------|
| order_id      | Unique identifier of each order    |
| order_date    | Date of purchase (YYYY-MM-DD)      |
| amount        | Revenue generated per order        |
| product_id    | Product identifier                 |

---

## 🧠 Task Objective
- Extract month & year from the date
- Calculate **monthly revenue** using `SUM(amount)`
- Calculate **order volume** using `COUNT(DISTINCT order_id)`
- Group the results by month & year
- Sort results in chronological order

---

## 🛠 Tools Used
- **SQLite**
- **DB Browser for SQLite**
- SQL (Aggregation + Date Functions)

---

## 🧾 SQL Query Used

```sql
SELECT
    strftime('%Y', order_date) AS year,
    strftime('%m', order_date) AS month,
    SUM(amount) AS monthly_revenue,
    COUNT(DISTINCT order_id) AS order_volume
FROM online_sales
GROUP BY year, month
ORDER BY year, month;
