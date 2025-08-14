☕ Regional Coffee Shop Sales Analysis — MySQL + Power BI
Overview

This project delivers an end-to-end sales performance analysis for a multi-store coffee chain, covering January–June 2023.
It uses MySQL for data cleaning, transformation, and KPI computation, and Power BI for an interactive, insight-rich dashboard.
The goal: empower store managers and regional leadership with clear visibility into sales patterns, month-over-month trends, and actionable levers for growth.

Business Requirements

The analysis was designed to:

Track Total Sales, Total Orders, and Total Quantity Sold with Month-over-Month (MoM) Δ and %.

Visualize daily and hourly performance patterns.

Compare Weekday vs Weekend sales contribution.

Rank store locations and product categories/types.

Enable granular drill-ins with interactive tooltips for quick operational insights.

Key Questions to Answer:

Which months, stores, and product categories drive growth or decline?

What times of day generate the highest sales, and do these patterns differ by weekday/weekend?

How do changes in performance compare month-to-month, and what operational adjustments can be made?

SQL (Data Preparation & KPI Logic)

Role: Transform raw transaction data into clean, aggregated, business-ready datasets for Power BI.

Key Steps

Data Cleaning & Typing

Converted date and time strings into native DATE and TIME formats using STR_TO_DATE.

Removed BOM artifacts from column names to ensure consistent query execution.

Ensured all numeric fields (e.g., unit_price, transaction_qty) are properly typed for aggregation.

KPI Calculation

Sales = SUM(unit_price * transaction_qty)

Orders = COUNT(transaction_id)

Quantity = SUM(transaction_qty)

Month-over-Month Logic

Used LAG() with window functions to calculate MoM change and percentage for each KPI.

Safeguarded calculations to avoid division-by-zero for the first month in the dataset.

Visual Feeds

Built targeted aggregates:

Daily Totals for trend lines and tooltips.

Weekday vs Weekend splits using DAYOFWEEK.

Store Rankings and Category Rankings for side-by-side comparisons.

Day × Hour Heatmap Data using HOUR(transaction_time) and DAYOFWEEK(transaction_date).

Impact: The SQL layer delivers clean, ready-to-visualize data, ensuring Power BI refreshes are fast, accurate, and semantically aligned with the business logic.

Power BI (Data Model & Dashboard Design)

Role: Transform the SQL outputs into an interactive and decision-oriented sales performance dashboard.

Data Model

Fact Table: Transactions at the transaction level (date, time, store, product, qty, price).

Date Table: Includes Month, Month Number, Day Name, Week Number, and Weekday/Weekend flag.

Relationship: One-to-many from Date Table to Transactions for consistent time intelligence.

Core Measures

Total Sales, Total Orders, Total Quantity.

MoM Δ and MoM % for each KPI.

Daily Average Sales (dynamic, respects filters).

Weekday vs Weekend totals and share %.

Visuals & Features

KPI Cards with MoM Δ and % indicators.

Daily Trend Chart with an average sales reference line.

Calendar Heat Map for daily sales patterns with interactive tooltips showing sales, orders, quantity, and MoM changes.

Store Location Bar Charts with MoM performance.

Product Category & Type Rankings with MoM %.

Day × Hour Heat Map highlighting peak traffic periods.

Rich Tooltips for in-context drill-ins without page changes.

Impact: The dashboard allows leadership to pinpoint trends, compare stores, assess category performance, and adjust operations in near real-time.

Insights (Jan–Jun 2023)

Revenue Growth

Sales nearly doubled from $82K (Jan) to $166K (Jun).

Biggest MoM jumps: March (+29.8%) and May (+31.8%).

Only contraction: February (-6.8%).

Weekday vs Weekend Split

Weekdays consistently account for ~70–75% of sales.

April saw the largest weekend share (~33%), suggesting seasonal or promotional impact.

Store Performance

All three stores trend together—no persistent underperformer.

Hell’s Kitchen leads consistently, followed closely by Astoria and Lower Manhattan.

Category & Product Leaders

Coffee leads by volume and revenue; Tea and Bakery follow.

Barista Espresso and Brewed Chai Tea are top-selling product types.

Time-of-Day Patterns

Strongest hours: 8–10am daily.

Midweek (Wed–Thu) often posts the highest daily totals.

Secondary bumps on late afternoons, especially on Fridays.

Recommendations & Solutions

Staffing & Scheduling

Prioritize labor during 7:30–11:00am; add a smaller bump 4–6pm.

Allocate extra weekend staff during months like April where weekend share spikes.

Promotions

Bundle offers: Pair top drinks (Espresso, Chai) with bakery items to lift average ticket value.

Test micro price increases (+3–5%) on peak-hour SKUs, offset with off-peak discounts.

Inventory Management

Set ingredient par levels by hour using the Day × Hour heat map.

Reduce waste by baking in smaller, more frequent batches during slower hours.

Store Strategy

Use Hell’s Kitchen as the pilot store for new drinks and promotions.

Replicate proven winners across other locations.

Ongoing Monitoring

Create a Monthly Pulse Page:

MoM performance for each store.

Top 3 SKU movers.

Days that underperformed relative to average.

Conclusion

This project demonstrates the full analytics pipeline: from raw transactional data to business-ready insights that drive operational decisions.
The SQL layer ensures data accuracy, efficiency, and repeatability, while the Power BI dashboard translates that into a visual narrative for quick, confident decision-making.
The insights lead directly to actionable changes—staffing, promotions, and inventory control—that can lift revenue, reduce waste, and optimize labor.
