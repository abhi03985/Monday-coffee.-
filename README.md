# ☕ Monday Coffee Expansion Strategy Analysis | SQL Project

![MySQL](https://img.shields.io/badge/mysql-%2300f.svg?style=for-the-badge&logo=mysql&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-Data%20Analysis-orange?style=for-the-badge)
![Analytics](https://img.shields.io/badge/Business-Intelligence-brightgreen?style=for-the-badge)

## 📌 Project Overview
**Monday Coffee**, a fast-growing coffee chain, aimed to expand into new cities across India 🇮🇳. However, making expansion decisions based on intuition alone could lead to sky-high operational costs 💸 and poor market penetration. 

This project delivers a data-driven solution by leveraging advanced **SQL analytics** to evaluate business performance across multiple cities, transforming raw transactional data into actionable insights for strategic expansion.

---

## ❓ Problem Statement
The core challenge was to identify cities with the strongest combination of **customer demand 📈, revenue potential 💰, and operational profitability** to maximize ROI and reduce expansion risks.

---

## 🛠️ Key Analyses Conducted

* **💰 Revenue Contribution:** Assessed city-wise sales performance and overall revenue share.
* **👥 Market Potential:** Estimated market size using customer acquisition metrics and purchasing behavior.
* **☕ Engagement Trends:** Analyzed average revenue per customer and order frequencies.
* **📉 Profitability Margins:** Compared operational costs against revenue generation to protect the bottom line.
* **🏆 High-Growth Ranking:** Identified breakout cities through trend and window-function ranking analysis.

---

## 💡 Code Showcase: High-Value Customer Ranking

To rank cities by long-term customer value rather than just total volume, the following query uses **CTEs** and **Window Functions** to isolate customers in the top spending tier (75th percentile) and rank the cities based on their high-value customer density:

```sql
WITH CustomerSpending AS (
    SELECT 
        c.city_id,
        c.customer_id,
        SUM(o.total_amount) AS total_spent,
        NTILE(4) OVER (ORDER BY SUM(o.total_amount) DESC) AS spending_tier
    FROM customers c
    JOIN orders o ON c.customer_id = o.customer_id
    GROUP BY c.city_id, c.customer_id
)
SELECT 
    ci.city_name,
    COUNT(cs.customer_id) AS high_value_customer_count,
    RANK() OVER (ORDER BY COUNT(cs.customer_id) DESC) AS city_rank
FROM CustomerSpending cs
JOIN cities ci ON cs.city_id = ci.city_id
WHERE cs.spending_tier = 1
GROUP BY ci.city_name;

🚀 Business Impact & Recommendations
🎯 Precision Expansion: Identified the top 3 target cities showing the highest average order value (AOV) and lowest customer acquisition costs (CAC).

🛡️ Risk Mitigation: Highlighted underperforming regions where high operational costs outweigh transaction volume, saving potential capital waste.

🗺️ Decision Framework: Provided a structured, scalable framework for future location-based business planning.

📂 Repository Structure
```text
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
🧠 Skills Demonstrated
MySQL • CTEs • Window Functions • Data Joins & Aggregations • Business Intelligence • Data Storytelling 🎨
