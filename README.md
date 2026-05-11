# Blinkit-Sales-Analysis
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

## 🗂️ Dataset Schema

`blinkit_data.csv` — 8,523 rows × 12 columns

`Item Fat Content` `Item Identifier` `Item Type` `Item Visibility` `Item Weight` `Outlet Establishment Year` `Outlet Identifier` `Outlet Location Type` `Outlet Size` `Outlet Type` `Sales` `Rating`

---

## 🔍 Analytical Findings

**Outlet Performance**
- **Supermarket Type 1** dominates with $787.5K (65%+ of total revenue)
- **Tier 3 outlets** lead all location tiers at $472.13K — counterintuitive but significant
- **Grocery Stores** lag with $151.9K and only 1,083 items stocked

**Product Mix**
- **Fruits & Vegetables** top item category at $178K
- **Seafood** is the weakest at $9K — visibility/stocking issue likely
- **Low Fat items** outsell Regular nearly 2:1 ($776K vs $425K)

---

## 💡 Business Recommendations

- Prioritise **Tier 3 outlet expansion** — highest revenue despite lower-tier classification
- Boost **Seafood & Breakfast** shelf visibility — combined under $25K signals poor placement
- Leverage the **Low Fat preference trend** for health-focused marketing campaigns
- Investigate **Grocery Store underperformance** — candidate for category rationalisation

---

## 🛠 Tools & Techniques

`Power BI Desktop` `SQL (MySQL)` `DAX Measures` `Data Modelling` `Data Validation`
`KPI Cards` `Donut Charts` `Bar Charts` `Line Charts` `Matrix Table` `Slicers & Filters`

---

## 📁 Repository Structure

```
blinkit-sales-analysis/
├── blinkit.pbix              ← Power BI dashboard
├── blinkit_data.csv          ← Raw dataset (8,523 rows × 12 cols)
├── Blinkit_DAX_Code.xlsx     ← DAX measures documented
├── Blinkit_Sql_Query.docx    ← SQL validation queries
└── README.md
```

---

📁 `.pbix` included &nbsp;|&nbsp; 🗄️ SQL validated &nbsp;|&nbsp; 🧮 4 DAX measures &nbsp;|&nbsp; 📦 8,523 records · 12 columns
