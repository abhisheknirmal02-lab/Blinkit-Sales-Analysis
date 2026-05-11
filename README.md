# 🛒 Blinkit Sales Analysis Dashboard
**Power BI · SQL · DAX · India's Last Minute Grocery App**

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=mysql&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-7B2D8B?style=flat)

---

## 📌 Project Overview

A full-stack business intelligence project analysing **8,523 product listings** across Blinkit's grocery outlet network. The pipeline covers SQL-based data validation, DAX measure creation in Power BI, and an interactive dashboard surfacing sales performance, outlet-level profiling, item category breakdowns, and fat-content segmentation.

---

## 📊 Key Metrics

| Metric | Value |
|---|---|
| Total Sales | $1.20M |
| Avg Sales / Item | $141 |
| No. of Items | 8,523 |
| Avg Rating | 3.9 |

---

## 🧮 DAX Measures

```dax
Total Sales  = SUM(blinkit_data[Sales])
Avg Sales    = AVERAGE(blinkit_data[Sales])
No.of Items  = COUNTROWS(blinkit_data)
Avg Rating   = AVERAGE(blinkit_data[Rating])
```

---

## 🗄️ SQL Validation Queries

```sql
-- KPI Validation
SELECT ROUND(SUM(sales), 2)  AS total_sales FROM retail_sales;
SELECT ROUND(AVG(sales), 2)  AS avg_sales   FROM retail_sales;
SELECT COUNT(*)              AS no_of_items FROM retail_sales;
SELECT ROUND(AVG(rating), 2) AS avg_rating  FROM retail_sales;

-- Filter-level validation (Dairy · Tier 1 · Medium)
SELECT ROUND(AVG(sales), 2) AS avg_sales
FROM   retail_sales
WHERE  item_type            = 'Dairy'
  AND  outlet_location_type = 'Tier 1'
  AND  outlet_size          = 'Medium';
```

---

## 🔍 Analytical Findings

- **Supermarket Type 1** dominates with $787.5K (65%+ of total revenue)
- **Tier 3 outlets** lead all location tiers at $472.13K
- **Fruits & Vegetables** top item category at $178K; Seafood lowest at $9K
- **Low Fat items** outsell Regular nearly 2:1 ($776K vs $425K)
- Sales stabilised at ~$130K/yr from 2012 onwards after a 1998 peak

---

## 💡 Business Recommendations

- Prioritise **Tier 3 outlet expansion** — highest revenue despite lower-tier classification
- Invest in **Supermarket Type 1** inventory depth — drives 65%+ of total revenue
- Boost **Seafood & Breakfast** shelf visibility — combined under $25K signals poor placement
- Leverage the **Low Fat preference trend** for health-focused marketing campaigns
- Investigate **Grocery Store underperformance** — lowest sales & item count

---

## 🛠 Tools & Techniques

`Power BI Desktop` `SQL (MySQL)` `DAX Measures` `Data Modelling` `Data Validation`
`KPI Cards` `Donut Charts` `Bar Charts` `Line Charts` `Matrix Table` `Slicers & Filters`

---

## 📁 Repository Files

| File | Description |
|---|---|
| [blinkit.pbix](https://github.com/abhisheknirmal02-lab/Blinkit-Sales-Analysis/blob/main/blinkit.pbix) | Power BI dashboard — main report file |
| [blinkit_data.csv](https://github.com/abhisheknirmal02-lab/Blinkit-Sales-Analysis/blob/main/blinkit_data.csv) | Raw dataset — 8,523 rows × 12 columns |
| [Blinkit DAX Code.xlsx](https://github.com/abhisheknirmal02-lab/Blinkit-Sales-Analysis/blob/main/Blinkit%20DAX%20Code.xlsx) | All 4 DAX measures documented |
| [Blinkit Sql Query.docx](https://github.com/abhisheknirmal02-lab/Blinkit-Sales-Analysis/blob/main/Blinkit%20Sql%20Query.docx) | SQL validation queries for all KPIs |

---

## 🖼️ Dashboard Preview

![Blinkit Dashboard](https://github.com/abhisheknirmal02-lab/Blinkit-Sales-Analysis/blob/main/Blinkit.png?raw=true)

---

📁 `.pbix` included &nbsp;|&nbsp; 🗄️ SQL validated &nbsp;|&nbsp; 🧮 4 DAX measures &nbsp;|&nbsp; 📦 8,523 records · 12 columns
