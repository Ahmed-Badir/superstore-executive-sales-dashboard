# 📊 Superstore Executive Sales Dashboard | Power BI

An interactive, multi-page Power BI dashboard designed to transform raw sales data into actionable business insights and support data-driven decision-making.

## 📸 Dashboard Preview

![Superstore Executive Sales Dashboard](<to share/Screenshot 2026-10-29 025914.png>)

---

## 📌 Business Case & Overview

The goal of this project is to transform raw sales data into an interactive business intelligence solution using **Power BI**.

The dashboard enables stakeholders to monitor key performance indicators (KPIs), explore seasonal sales trends, identify top-performing product categories, and analyze regional and customer performance.

## 🛠️ Tools & Technologies

- **Power BI Desktop:** Interactive dashboards, data visualization, and report navigation.
- **Power Query:** Data cleaning, transformation, and preparation.
- **DAX:** KPI calculations, year-over-year growth, and time intelligence.
- **Data Modeling:** Star Schema design for structured and efficient analysis.

---

## 🏗️ Data Model Architecture

The data model follows a **Star Schema** approach, connecting the central `Fact_Sales` table with dimension tables for product, customer, region, shipping, and date analysis.

![Data Model Architecture](<to share/Screenshot 2026-10-29 013153.png>)

### Key Model Entities

- **`Fact_Sales`** — Sales transactions, order IDs, sales amounts, quantities, discounts, and related keys.
- **`Dim_Product`** — Product categories, sub-categories, and product names.
- **`Dim_Customer`** — Customer information and segments.
- **`Dim_Region`** — Geographic attributes, including city, state, postal code, and region.
- **`Dim_Date`** — Calendar table for time intelligence calculations.
- **`Dim_Ship_Mode`** — Shipping methods and related analysis.

---

## 🚀 Dashboard Pages & Key Features

### 1. Executive Overview

Provides a high-level view of business performance.

- **KPI Cards:** Total Customers, Total Orders, Total Sales, Average Order Value (AOV), and YoY Sales Growth.
- **Sales Trends:** Monthly sales compared with the previous year.
- **Category Analysis:** Sales distribution across product categories and customer segments.

![Executive Overview](<to share/Screenshot 2026-10-29 025914.png>)

---

### 2. Product & Category Performance

Explores product-level performance and shipping patterns.

- **Hierarchy Drill-Down:** Interactive category and sub-category analysis.
- **Product Scatter Plot:** Examines the relationship between sales and order volume.
- **Shipping Analysis:** Sales breakdown by category and shipping mode.

![Product & Category Performance](<to share/Screenshot 2026-10-29 030725.png>)

---

### 3. Customer & Regional Analytics

Evaluates geographic sales distribution and customer performance.

- **Geographic Analysis:** Sales distribution across states and regions.
- **Customer Rankings:** Identifies top customers by sales.
- **Regional Performance:** Highlights key markets, including California and New York, when supported by the data.

![Customer & Regional Analytics](<to share/Screenshot 2026-10-29 025946.png>)

---

### 4. Time Intelligence & Growth Analytics

Tracks sales performance over time and identifies seasonal patterns.

- **YoY Growth:** Compares sales performance across years.
- **Year-to-Date (YTD):** Tracks cumulative sales throughout the year.
- **Seasonality Analysis:** Examines monthly trends and fourth-quarter performance.

![Time Intelligence & Growth](<to share/Screenshot 2026-10-29 030003.png>)

---

## 🧮 Key DAX Calculations

### Total Sales

```dax
Total Sales =
SUM(Fact_Sales[Sales])
```

### Previous Year Sales

```dax
PY Sales =
CALCULATE(
    [Total Sales],
    SAMEPERIODLASTYEAR(Dim_Date[Date])
)
```

### Year-over-Year Sales Growth %

```dax
YoY Sales Growth % =
DIVIDE(
    [Total Sales] - [PY Sales],
    [PY Sales],
    0
)
```

### Year-to-Date Sales

```dax
YTD Sales =
TOTALYTD(
    [Total Sales],
    Dim_Date[Date]
)
```

---

## 💡 Key Business Insights

- **Product Performance:** Evaluate Technology and Furniture categories, along with products such as Phones and Chairs, to identify revenue and profitability opportunities.
- **Seasonality:** Analyze November and December sales patterns to improve inventory planning and logistics readiness.
- **Regional Opportunities:** Use state-level performance to support targeted marketing and regional growth strategies.

*Business insights should be validated against the dashboard results and underlying dataset.*

---

## 🎯 Project Objectives

- Transform raw data into meaningful business insights.
- Build an interactive, multi-page analytical report.
- Apply dimensional modeling and DAX time intelligence.
- Support business decisions through clear data visualization.

---

## 👨‍💻 Author

**Ahmed Bedir**  
Data Analyst | Power BI | SQL | Python

