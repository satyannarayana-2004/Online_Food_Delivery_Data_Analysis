# Online_Food_Delivery_Data_Analysis
SQL + AI Course by @datapencil daily challenge 
Here’s a clean, professional **GitHub README.md** file based on your project report 

---

# Online Food Delivery Business Intelligence & Performance Analysis (SQL Project)

**Domain:** Food-Tech / E-Commerce Analytics
**Tool Used:** MySQL
**Author:** Netinti Satyannarayana
**Year:** 2026

---

## Project Overview

This project focuses on analyzing an **online food delivery platform** (similar to Swiggy/Zomato) using SQL to generate meaningful business insights.

The goal is to transform raw transactional data into **actionable business intelligence** for improving:

* Revenue performance
* Customer engagement
* Restaurant productivity
* Delivery efficiency

The analysis is performed using SQL queries on a relational database consisting of multiple interconnected tables. 

---

## Problem Statement

The company generates huge amounts of data but lacks structured analysis to answer key business questions like:

* Which cities generate the most revenue?
* Who are the top customers?
* Are discounts profitable?
* Which restaurants perform best?
* How efficient are delivery agents?

This project solves these problems using **SQL-based analytics**. 

---

## Business Objectives

### Revenue Analysis

* Calculate total and monthly revenue
* Identify high-performing cities and restaurants

### Customer Analysis

* Find top customers
* Analyze signup trends and gender distribution

### Restaurant & Product Analysis

* Identify top restaurants
* Find most ordered food items

### Operational Analysis

* Measure delivery time
* Evaluate delivery agent performance
* Analyze discount usage

---

## 🗂 Dataset Overview

The project uses a **relational database with 5 tables**:

1. **customers** – Customer details
2. **restaurants** – Restaurant information
3. **orders** – Order transactions
4. **order_items** – Item-level data
5. **delivery_agents** – Delivery staff details

Data includes:

* 1,000–10,000 records
* Multi-city (India)
* Time period: 2022–2024 

---

## Database Schema (ER Concept)

* One customer → many orders
* One restaurant → many orders
* One order → many items

The **orders table acts as the central hub** connecting all entities. 

---

## Key Insights

🔹 **Revenue Growth:**

* 72.5% increase in 2024

🔹 **Top Cities:**

* Mumbai, Bengaluru, Delhi contribute ~57.8% revenue

🔹 **Customer Growth:**

* 309% growth over 3 years

🔹 **Top Product:**

* Biryani is the most ordered item

🔹 **Discount Usage:**

* 37% of orders use discounts

🔹 **Payment Trend:**

* UPI dominates with 42% usage

🔹 **Delivery Performance:**

* Mumbai has highest delivery time

These insights are derived from SQL queries and visualized using charts in the report. 

---

## SQL Concepts Used

* SELECT, WHERE, GROUP BY
* JOIN (INNER JOIN, etc.)
* Aggregate Functions (SUM, AVG, COUNT)
* Subqueries
* Window Functions
* Common Table Expressions (CTEs)

---

## Sample SQL Queries

### Total Revenue

```sql
SELECT SUM(order_amount - discount) AS total_revenue
FROM orders;
```

### Monthly Revenue Trend

```sql
SELECT DATE_FORMAT(order_date, '%Y-%m') AS month,
       SUM(order_amount - discount) AS revenue
FROM orders
GROUP BY month
ORDER BY month;
```

### Top Restaurants

```sql
SELECT r.rest_name,
       SUM(o.order_amount - o.discount) AS revenue
FROM orders o
JOIN restaurants r ON o.restaurant_id = r.restaurant_id
GROUP BY r.rest_name
ORDER BY revenue DESC
LIMIT 5;
```

---

## Performance Optimization

* Indexing on foreign keys
* Optimized JOIN queries
* Use of CTEs
* Filtering with WHERE clause
* Avoiding `SELECT *`

---

## Business Recommendations

* Expand in Tier-2 cities
* Reduce unnecessary discounts
* Promote digital payments (UPI)
* Introduce customer loyalty programs
* Improve delivery efficiency in high-demand cities

---

## Future Scope

* Real-time analytics (Kafka / AWS Kinesis)
* Dashboard integration (Power BI / Tableau)
* Machine Learning:

  * Customer churn prediction
  * Demand forecasting
* Automated ETL pipelines

---

## Project Structure (Suggested)

Food-Delivery-SQL-Project
│── README.md
│── dataset/
│── sql_queries/
│── charts/
│── report.pdf

---

## Full Report

You can view the complete project report here:

---

##  Final Note

This project demonstrates how SQL can be used to convert raw data into **business decisions**, making it highly relevant for:

* Data Analyst roles
* Business Intelligence roles
* SQL-based analytics projects
