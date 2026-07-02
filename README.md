<div align="center">

# ☕ Monday Coffee Expansion Strategy Analysis

<img src="https://readme-typing-svg.demolab.com?font=Poppins&weight=700&size=30&pause=1000&color=D2691E&center=true&vCenter=true&width=900&lines=SQL+Business+Analysis;Market+Expansion+Strategy;Advanced+SQL+Project;Data-Driven+Business+Decisions" />

<p>
<img src="https://img.shields.io/badge/MySQL-Database-orange?style=for-the-badge&logo=mysql&logoColor=white"/>
<img src="https://img.shields.io/badge/SQL-Analytics-blue?style=for-the-badge"/>
<img src="https://img.shields.io/badge/Business-Intelligence-success?style=for-the-badge"/>
<img src="https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge"/>
</p>

<img src="https://capsule-render.vercel.app/api?type=waving&color=D2691E&height=120&section=header"/>

</div>

---

# 📌 Project Overview

<img align="right" width="320" src="https://media.giphy.com/media/LmNwrBhejkK9EFP504/giphy.gif"/>

**Monday Coffee** is a rapidly growing coffee chain looking to expand into new cities across India.

Instead of relying on assumptions, this project uses **Advanced SQL Analytics** to identify the best expansion opportunities based on:

- 📈 Revenue Performance
- 👥 Customer Demand
- 💰 Profitability
- ☕ Customer Engagement
- 📍 Market Potential

The goal is to help stakeholders make **data-driven expansion decisions** while minimizing business risk.

<br clear="right"/>

---

# 🎯 Business Problem

> Which cities should Monday Coffee expand into to maximize ROI while minimizing operational costs?

The analysis evaluates multiple KPIs including:

- 💰 Revenue Contribution
- 👥 Customer Growth
- 📦 Order Volume
- ☕ Average Revenue Per Customer
- 📈 High Value Customers
- 🏆 City Rankings

---

# 🛠 SQL Concepts Used

<p align="center">

<img src="https://img.shields.io/badge/CTE-✓-blue?style=for-the-badge"/>
<img src="https://img.shields.io/badge/Window_Functions-✓-orange?style=for-the-badge"/>
<img src="https://img.shields.io/badge/Aggregations-✓-green?style=for-the-badge"/>
<img src="https://img.shields.io/badge/CASE_When-✓-yellow?style=for-the-badge"/>
<img src="https://img.shields.io/badge/JOINS-✓-red?style=for-the-badge"/>
<img src="https://img.shields.io/badge/Subqueries-✓-purple?style=for-the-badge"/>

</p>

---

# 📊 Key Business Analysis

| 📌 Analysis | 📈 Objective |
|------------|--------------|
| 💰 Revenue Contribution | City-wise sales comparison |
| 👥 Market Potential | Estimate customer demand |
| ☕ Engagement Analysis | Revenue per customer |
| 📉 Profitability | Cost vs Revenue |
| 🏆 City Ranking | Best expansion cities |

---

# 💡 SQL Query Showcase

```sql
WITH CustomerSpending AS (
    SELECT
        c.city_id,
        c.customer_id,
        SUM(o.total_amount) AS total_spent,
        NTILE(4) OVER (
            ORDER BY SUM(o.total_amount) DESC
        ) AS spending_tier
    FROM customers c
    JOIN orders o
        ON c.customer_id=o.customer_id
    GROUP BY
        c.city_id,
        c.customer_id
)

SELECT
    ci.city_name,
    COUNT(cs.customer_id) AS high_value_customer_count,
    RANK() OVER(
        ORDER BY COUNT(cs.customer_id) DESC
    ) AS city_rank
FROM CustomerSpending cs
JOIN cities ci
ON cs.city_id=ci.city_id

WHERE spending_tier=1

GROUP BY ci.city_name;
```

---

# 📷 Project Preview

## Dashboard

<p align="center">
<img src="1.Monday Coffee.png" width="900">
</p>

---

## Objective

<p align="center">
<img src="2.Objective.png" width="900">
</p>

---

## SQL Questions

<p align="center">
<img src="3.Easy and Medium Question.png" width="900">
</p>

---

## Medium Questions

<p align="center">
<img src="4.Medium Questions.png" width="900">
</p>

---

## Advanced Analysis

<p align="center">
<img src="5.Advanced Question & Analysis.png" width="900">
</p>

---

## Recommendations

<p align="center">
<img src="6.Recommendation & Reason.jpg" width="900">
</p>

---

# 🚀 Business Recommendations

<img align="right" width="280" src="https://media.giphy.com/media/f3iwJFOVOwuy7K6FFw/giphy.gif"/>

### 🎯 Precision Expansion

Identify the Top 3 cities with:

- Highest Average Order Value
- Lowest Customer Acquisition Cost
- Strong Customer Growth

### 🛡 Risk Mitigation

Avoid cities where:

- High operating cost
- Low transaction volume
- Weak customer retention

### 📍 Strategic Planning

Develop a scalable framework for future expansion using SQL-driven insights.

<br clear="right"/>

---

# 📁 Repository Structure

```text
📦 Monday-Coffee-SQL
│
├── 📷 1.Monday Coffee.png
├── 📷 2.Objective.png
├── 📷 3.Easy and Medium Question.png
├── 📷 4.Medium Questions.png
├── 📷 5.Advanced Question & Analysis.png
├── 📷 6.Recommendation & Reason.jpg
├── 📄 README.md
├── 📊 city.csv
├── 📊 customers.csv
├── 📊 products.csv
├── 📊 sales.csv
└── 💾 mysolution.sql
```

---

# 🧠 Skills Demonstrated

<div align="center">

| SQL | Business |
|-----|----------|
| ✔ MySQL | ✔ Business Intelligence |
| ✔ CTE | ✔ Data Storytelling |
| ✔ Window Functions | ✔ Decision Making |
| ✔ Aggregations | ✔ KPI Analysis |
| ✔ Ranking | ✔ Strategic Planning |

</div>

---

# ⭐ Support

If you found this project useful,

⭐ Star this repository

🍴 Fork it

💬 Share your feedback

---

<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Poppins&size=24&pause=1000&color=D2691E&center=true&width=700&lines=Thanks+for+Visiting!;Happy+Learning!;Keep+Building+Amazing+Projects!" />

<img src="https://capsule-render.vercel.app/api?type=waving&color=D2691E&height=120&section=footer"/>

</div>
