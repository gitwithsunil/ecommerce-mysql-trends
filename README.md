# 📊 Sales Trend Analysis using MySQL

Welcome to the **Sales Trend Analysis** project, where we explore how to extract valuable business insights from sales data using SQL queries in **MySQL Workbench 8.0**.

This project is part of a data analytics assignment to practice **aggregation**, **grouping**, and **time-based trend analysis** on eCommerce orders.

---

## 🧰 Tools & Technologies

- ✅ **MySQL 8.0 / MySQL Workbench**
- 📅 `EXTRACT()` for month/year from dates
- 🔢 `SUM()` and `COUNT()` for aggregation
- 📈 `GROUP BY` and `ORDER BY` for trend analysis

---

## 🗃️ Dataset Overview

We use a table named `online_sales_wb` with the following structure:

| Column Name | Data Type     | Description              |
|-------------|---------------|--------------------------|
| order_id    | INT           | Unique order ID          |
| order_date  | DATE          | Date of the order        |
| amount      | DECIMAL(10,2) | Revenue from the order   |
| product_id  | INT           | ID of the purchased item |

---

## 📌 Task Breakdown

Each query was executed in **MySQL Workbench**, and screenshots were taken to showcase the results.  
You can find all screenshots inside the `/screenshots` folder.

| 🔢 Step | Task Description | Screenshot |
|--------|------------------|------------|
| 1️⃣ | Create table `online_sales_wb` |
| 2️⃣ | Insert sample data | |
| 3️⃣ | Extract month from `order_date` | `3_extract_month.png` |
| 4️⃣ | Group by year/month | `4_group_by.png` |
| 5️⃣ | Calculate monthly revenue | `5_sum_amount.png` |
| 6️⃣ | Count total monthly orders | `6_count_orders.png` |
| 7️⃣ | Combine revenue + volume | `7_combined_output.png` |
| 8️⃣ | Sort results by month/year | `8_order_by.png` |
| 9️⃣ | Limit results (e.g., top 3 months) | `9_limit_results.png` |

---

## 📈 Sample Query

```sql
SELECT 
    EXTRACT(YEAR FROM order_date) AS order_year,
    EXTRACT(MONTH FROM order_date) AS order_month,
    SUM(amount) AS total_revenue,
    COUNT(DISTINCT order_id) AS order_volume
FROM online_sales_wb
GROUP BY order_year, order_month
ORDER BY order_year, order_month
LIMIT 5;
