# ☕ Regional Coffee Shop Sales Analysis — MySQL + Power BI

End-to-end analysis of a multi-store coffee chain. MySQL handles data cleaning and KPI logic; Power BI delivers interactive dashboards (MoM KPIs, calendar & day–hour heatmaps, store/product views).

## Problem & Objectives
- Track **Total Sales, Orders, Quantity** with **MoM % and Δ**
- Understand **daily** and **day×hour** patterns
- Compare **Weekday vs Weekend** and **Store** performance
- Identify **product category/type** drivers and operational levers

## Data & Process
**SQL (MySQL 8)**  
- Convert strings to `DATE`/`TIME` with `STR_TO_DATE`; normalize columns (e.g., `transaction_id`).  
- Compute KPIs and MoM with window functions (`LAG`) and group-bys for each visual feed (calendar, weekday/weekend, store, category, top products, day|hour). :contentReference[oaicite:5]{index=5}

**Power BI**
- Model: `Transactions` fact ↔ `Date` dimension (Month, Week, Day, Weekday/Weekend).
- Visuals: KPI cards with MoM, daily trend + avg line, calendar heat map, weekday vs weekend donut, store & category bars with MoM labels, day×hour heat map, tooltips.

## Highlights (Jan–Jun 2023)
- Revenue **doubled**: \$82K → \$166K.  
- Feb dip (-6.8% MoM) followed by strong rebounds in Mar (+29.8%) and May (+31.8%); steady growth in Jun (+6.2%).  
- **Weekdays drive ~70–75%** of sales; **April** shows the highest weekend share (~33%).  
- **8–10am** is the dominant daypart; **Wed/Thu** often top daily totals.  
- Leaders: **Coffee** (then Tea, Bakery); top types **Barista Espresso**, **Brewed Chai Tea**, **Hot Chocolate**.

## Insights
- Morning dependency + consistent midweek strength suggest **labor and prep must be front-loaded**.
- Weekends can be grown (April proves it) via **targeted promos** and **modest staffing increases**.
- Category hierarchy is stable—**bundling** bakery with espresso/chai is a repeatable margin play.
- Stores move in sync → focus on **chain-wide programs** with light local customization.

## Recommendations
1. **Staffing:** Prioritize **7:30–11:00am**; add a small bump **4–6pm**.  
2. **Promos:** Weekend bundles (Espresso+Bakery, Chai+Bakery); test **+3–5%** price during peak with off-peak bundle offsets.  
3. **Inventory:** Set hourly **par levels** by store from the day×hour heat map; tighten bakery waste controls.  
4. **Store Playbooks:** Pilot seasonal drinks in **Hell’s Kitchen**; replicate winners to **Astoria** and **Lower Manhattan**.  
5. **Governance:** Add a monthly **Pulse** page (stores up MoM, top SKU movers, misses).
