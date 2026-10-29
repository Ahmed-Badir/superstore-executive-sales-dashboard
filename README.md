# superstore-executive-sales-dashboard
# 📊 Superstore Executive Sales Dashboard | Power BI Project

![Superstore Dashboard](<to share/Screenshot 2026-10-29 025914.png>)

## 📌 Business Case & Overview
The goal of this project is to transform raw sales data into an interactive, multi-page business intelligence solution using **Power BI**. It allows stakeholders to monitor key business metrics, explore seasonal sales trends, identify top-performing product categories, and analyze regional and customer performance to support data-driven decision-making.

---

## 🛠️ Tools & Technologies
- **Power BI Desktop:** Dashboard design, interactive visual storytelling, and page navigation.
- **Power Query:** Data cleaning, transformation, and shaping.
- **DAX (Data Analysis Expressions):** Time intelligence functions, YTD calculations, dynamic KPIs, and growth metrics.
- **Data Modeling (Star Schema):** Designing clear dimension tables linked to a single central fact table for optimal query performance.

---

## 🏗️ Data Model Architecture
The data model follows a **Star Schema** approach, connecting the central `Fact_Sales` table with key dimension tables for seamless filtering and analysis.

![Superstore Executive Sales Dashboard](<to share/Screenshot 2026-10-29 013153.png>)

### Key Model Entities:
- **`Fact_Sales`**: Stores sales transactions, order IDs, sales amounts, order/ship dates, and foreign keys.
- **`Dim_Product`**: Contains details on categories, sub-categories, and product names.
- **`Dim_Customer`**: Tracks customer details and segments (Consumer, Corporate, Home Office).
- **`Dim_Region`**: Geographical dimensions covering city, state, postal code, and region.
- **`Dim_Date`**: Dedicated date hierarchy for Time Intelligence calculations.
- **`Dim_Ship_Mode`**: Shipping methods analysis.

---

## 🚀 Dashboard Pages & Key Features

### 1. Executive Overview
Focuses on macro-level performance metrics and overall sales trends.
- **KPI Cards:** Total Customers, Total Orders, Total Sales, Average Order Value (AOV), and YoY Sales Growth %.
- **Trend Analysis:** Total Sales vs. Previous Year (PY) Sales by Month.
- **Product & Segment Breakdown:** Sales distribution across main categories and market segments.

![Executive Overview Page](Screenshot%202026-10-29%20025914.jpg)

---

### 2. Product & Category Performance
Explores granular product metrics and shipping performance.
- **Hierarchy Drill-Down:** Expandable matrix for categories (Technology, Furniture, Office Supplies) and sub-categories.
- **Product Scatter Plot:** Order count vs. total sales per product name.
- **Shipping Logistics:** Breakdown of sales by category across shipping modes.

![Product & Category Performance Page](Screenshot%202026-10-29%20030725.png)

---

### 3. Customer & Regional Analytics
Analyzes regional geographic footprint and top customer value.
- **Geographic Visuals:** Map view of sales distribution and state rankings (Top Sales: California, New York, Texas).
- **Customer Analysis:** Top customers by total sales, order volume, and average order value.

![Customer & Regional Analytics Page](Screenshot%202026-10-29%20025946.jpg)

---

### 4. Time Intelligence & Growth Analytics
Monitors performance over time and identifies seasonality.
- **Time Analytics:** Quarter-over-Quarter and Year-over-Year growth tracking.
- **Seasonality Insights:** Cumulative sales waterfall chart highlighting fourth-quarter peaks (November & December).

![Time Intelligence & Growth Page](Screenshot%202026-10-29%20030003.png)

---

## 💡 Key DAX Calculations Example

```dax
YoY Sales Growth % = 
DIVIDE(
    [Total Sales] - [PY Sales],
    [PY Sales],
    0
)
