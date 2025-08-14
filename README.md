# ☕ Regional Coffee Shop Sales Analysis  
**MySQL + Power BI Project**

## 📄 Project Overview  
This project delivers a full end-to-end analysis of regional coffee shop sales, leveraging **MySQL** for data cleaning, transformation, and KPI computation, and **Power BI** for interactive data visualization. The analysis focuses on uncovering sales patterns, customer behavior, and performance trends across locations, product categories, and time periods.

## 📄 Read the Full Project Article on LinkedIn  
[**Regional Coffee Shop Sales Analysis — MySQL + Power BI**](https://www.linkedin.com/pulse/regional-coffee-shop-sales-analysis-mysql-power-bi-daniel-groza-qfmae/)  
In this article, I walk through the complete analytics process for my final Sales Sector portfolio project — from SQL data preparation to building an interactive Power BI dashboard — before transitioning into my Financial & Banking analytics projects.


---

## 🛠 Tools & Technologies  
- **MySQL** – Data extraction, cleaning, type transformation, and business rule application  
- **Power BI** – Data modeling, DAX measures, and dynamic dashboards  
- **DAX** – Time intelligence functions and calculated measures for Month-over-Month (MoM) analysis

---

## 📌 Business Requirements & KPIs  
**KPI Analysis:**
1. **Total Sales Analysis**  
   - Monthly sales totals  
   - Month-over-Month % change  
   - Sales difference from previous month  

2. **Total Orders Analysis**  
   - Monthly total orders  
   - MoM % change  
   - Difference from previous month  

3. **Total Quantity Sold Analysis**  
   - Monthly quantity sold  
   - MoM % change  
   - Difference from previous month  

**Chart Requirements:**
- Calendar Heat Map (daily sales, orders, quantity)  
- Sales by Weekday vs Weekend  
- Sales by Store Location  
- Daily Sales with Average Line  
- Sales by Product Category  
- Top 10 Products by Sales  
- Sales by Day & Hour Heat Map  

---

## 💾 SQL Development  
**Key Steps in MySQL:**
1. **Data Walkthrough & Preparation** – Reviewed raw transactional data for completeness and accuracy.  
2. **Database & Table Creation** – Structured schema to store sales data.  
3. **Data Import & Cleaning** – Removed nulls, standardized formats, and resolved inconsistencies.  
4. **Data Type Transformation** – Converted date, time, and numeric values for analysis.  
5. **Business Rule Queries** –  
   - Aggregated sales, orders, and quantity by month, weekday/weekend, location, and product category.  
   - Implemented MoM difference calculations using **LAG()** and **CASE** statements.  
   - Created datasets for Power BI visualizations including heat maps and top-product rankings.

---

## 📊 Power BI Development  
**Data Model:**
- **Transactions Table** – Sales, orders, quantity, product details, store locations, timestamps  
- **Date Table** – Full calendar table with relationships for time intelligence (month, weekday, week number)  

**Key Visuals & Features:**
- **KPI Cards** – Total Sales, Total Orders, Total Quantity Sold with MoM metrics  
- **Calendar Heat Map** – Color-coded sales performance per day  
- **Weekday vs Weekend Analysis** – Sales proportion comparison  
- **Sales by Location** – Store-level performance and MoM trends  
- **Category & Product Analysis** – Best/worst performing categories and top products  
- **Sales by Day & Hour Heat Map** – High-traffic sales periods for staffing & marketing  
- **Dynamic Tooltips** – Hover-based deep dive into specific days/hours  

---

## 📈 Insights  
**1. Sales Trends**  
- Highest sales recorded in **June 2023** ($166K), with consistent MoM growth from February onwards.  
- January–February saw a dip (-6.8% sales, -5.5% orders) before recovering sharply in March (+29.8% sales).  

**2. Store Performance**  
- **Hell’s Kitchen** consistently leads in sales, followed by **Astoria** and **Lower Manhattan**.  
- All stores show similar growth patterns, suggesting regional demand consistency.  

**3. Category Insights**  
- Coffee and tea dominate revenue, followed by bakery and chocolate drinks.  
- Barista Espresso and Brewed Chai Tea are top-selling products, showing strong customer preference.  

**4. Time-Based Insights**  
- Weekdays contribute ~70–75% of sales; weekends ~25–30%.  
- Peak hours: **8–10 AM** and **5–7 PM**, ideal for promotions and staffing boosts.  

---

## 💡 Recommendations & Solutions  
1. **Targeted Promotions** – Focus marketing campaigns on top-selling products during peak hours.  
2. **Customer Retention Strategies** – Implement loyalty programs for repeat customers to drive weekday traffic.  
3. **Product Mix Optimization** – Expand on high-performing categories and review underperforming SKUs.  
4. **Store-Level Initiatives** – Replicate high-performing store strategies across locations with lower MoM growth.  
5. **Operational Planning** – Align staffing and inventory levels with peak-hour demand to optimize costs.  

---

## ✅ Conclusion  
This project demonstrates **full-stack analytics capability** from data preparation in SQL to advanced visualization in Power BI. It delivers actionable insights for **sales optimization, operational efficiency, and customer engagement strategies**. The methodology ensures scalability for future datasets and business needs, making it a strong case study for data-driven decision-making.
