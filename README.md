## 🍕 Domino’s USA – Power BI Sales Analytics Dashboard

A fully interactive, insight-driven **Power BI dashboard** designed to analyze Domino’s USA’s sales performance using advanced **DAX measures**, data modeling, and modern visualization techniques. This project helps business teams explore **store-wise, product-wise, and date-wise** sales behavior, supported by dynamic filters, tooltips, and KPI indicators.

### ⭐ Project Highlights

- Near real-time sales monitoring  
- Drill-down analysis by store, category & product  
- KPI summary with performance matrices
- Dynamic slicers, tooltips & drill-through pages  
- Fully optimized star schema model  
- Professional, business-ready visuals

### 📊 Key Dashboard Pages
- **Overview** — High-level KPIs and summary matrices, store-wise comparisons, rankings
- **Sales Performance** — Daily, monthly, seasonal patterns and trendlines
- **Category Analysis** — Source, Type, Hour, Day part, Tier wise analysis
- **Product Performance** — top-selling items, low performers, category analysis  
- **Performance Comparison** — daily, monthly, store-wise, sales & Kpi comparison  
- **Help Center** - Explaining key terms. KPI s and navigation guidelines

### 🧠 Data Model — Snowflake Schema

This Power BI model is built using a **Star Schema** structure with **All Orders** as the central fact table and three directly connected dimensions.

### **📌 Fact Table**
| Table | Description |
|-------|-------------|
| **All Orders** | Main fact table containing order-level sales data, including store, product, date, quantity, order type, and revenue values. |

### **📌 Dimension Tables**
| Table | Description |
|-------|-------------|
| **Calendar** | Full date table used for time intelligence (YTD, MoM, YoY). |
| **Product Category** | Category details connected to products (e.g., Pizza, Sides, Beverages). |
| **Target vs Actuals** | Monthly / Daily Sales Target Values. |

### **📌 Measure Table (DAX)**
| Table | Purpose |
|-------|---------|
| **Measure** | Stores all DAX measures for KPIs, calculations, and visual-driven insights. |

### 🧮 Key DAX Measures Used in the Dashboard

```dax
Number of Orders = DISTINCTCOUNT('All Orders'[UniqueKey_Table1])

Net Sale = 
SUMX (
    'All Orders',
            IF ('All Orders'[Date] < DATE ( 2024, 1, 1 ),
                78 / 92,
                IF (
                    'All Orders'[Date] >= DATE ( 2025, 8, 1 ),
                    97.875 / 118,
                    97.5 / 118
                )
            )
    )
)

Average Bill Value (ABV) = DIVIDE([Net Sale], [Number of Orders], 0)
```

### 🧱 Technologies Used

- Power BI Desktop
- DAX
- Power Query
- Star Schema Dimensional Modelling

![Dashboard Preview] (https://github.com/SHALIKAPRAMOD/PowerBI/blob/main/Sales%20Dashboard.png)
