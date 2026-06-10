<div align="center">


<br/>

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-Desktop-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.x-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Excel](https://img.shields.io/badge/Microsoft%20Excel-Advanced-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)

<br/>

![Transactions](https://img.shields.io/badge/Dataset-52%2C000%20Transactions-1E293B?style=flat-square&color=3B82F6)
![Columns](https://img.shields.io/badge/Features-20%20Columns-1E293B?style=flat-square&color=22C55E)
![Domain](https://img.shields.io/badge/Domain-Retail%20Analytics-1E293B?style=flat-square&color=A78BFA)
![Status](https://img.shields.io/badge/Status-Completed-1E293B?style=flat-square&color=22C55E)

<br/>

[Project Overview](#-project-overview) &nbsp;·&nbsp;
[Dataset](#-dataset-overview) &nbsp;·&nbsp;
[Analysis](#-sql-analysis-performed) &nbsp;·&nbsp;
[Key Insights](#-key-insights) &nbsp;·&nbsp;
[Dashboard](#-dashboard-features) &nbsp;·&nbsp;
[How to Run](#-how-to-run) &nbsp;·&nbsp;
[Author](#-author)

</div>

---

## 📌 Project Overview

This is an **end-to-end data analytics project** that analyzes **52,000 retail transactions** to uncover revenue trends, profitability drivers, regional performance gaps, SKU-level margin risks, and discount-induced profit leakage.

The project covers the **complete analytics pipeline** — from raw data validation and SQL-based analysis to an executive-level Power BI dashboard — designed to support real business decision-making in pricing, inventory, and regional strategy.

---

## 🧩 Business Problem

> *A retail chain wanted to analyze sales performance, profitability drivers, category contribution, regional trends, and discount impact on product profitability.*

Specifically, the business needed clarity on:

- Which quarters and months are driving or eroding revenue?
- Which product categories and SKUs contribute most to — or leak from — profitability?
- How do regional markets compare, and where are the weakest performers?
- At what discount level do products become loss-making?

---

## 📦 Dataset Overview

| Property | Detail |
|---|---|
| **Total Records** | 52,000 retail transactions |
| **Total Columns** | 20 |
| **Domain** | Retail — Sales, Products, Customers, Regions |
| **File** | `data/cleaned_retail_sales.csv` |

### Column Reference

| Column | Type | Description |
|---|---|---|
| `order_id` | VARCHAR | Unique order identifier |
| `order_date` | DATE | Transaction date |
| `month_num` | INT | Month number (1–12) |
| `month_name` | VARCHAR | Month name |
| `quarter` | VARCHAR | Fiscal quarter (Q1–Q4) |
| `region` | VARCHAR | Sales region |
| `store_id` | VARCHAR | Store identifier |
| `customer_id` | VARCHAR | Unique customer ID |
| `category` | VARCHAR | Product category |
| `sub_category` | VARCHAR | Product sub-category |
| `sku` | VARCHAR | Stock Keeping Unit code |
| `quantity` | INT | Units sold per order |
| `unit_price` | DECIMAL | Selling price per unit |
| `unit_cost` | DECIMAL | Cost price per unit |
| `discount_pct` | DECIMAL | Discount percentage applied |
| `revenue` | DECIMAL | Net revenue after discount |
| `cogs` | DECIMAL | Cost of Goods Sold |
| `profit` | DECIMAL | Net profit (revenue − cogs) |
| `payment_method` | VARCHAR | Payment type |
| `sales_channel` | VARCHAR | Online / In-Store |

---

## ✅ Data Validation

All quality checks were completed before analysis to ensure accuracy and integrity of results.

| Check | Result | Notes |
|---|---|---|
| Missing Values | ✅ None found | All 20 columns fully populated |
| Duplicate Records | ✅ None found | All 52,000 order IDs are unique |
| Revenue Validation | ✅ Passed | Verified against quantity, price, and discount |
| Profit Validation | ✅ Passed | Cross-checked as `revenue − cogs` |
| Category Mapping | ✅ Passed | All SKUs correctly mapped to categories |
| Quarter Mapping | ✅ Passed | Month-to-quarter alignment confirmed |
| Date Conversion | ✅ Applied | `order_date` converted to `datetime` format |

---

## 🗄️ SQL Analysis Performed

- Quarter-wise Revenue Analysis
- Category Contribution Analysis
- Regional Performance Analysis
- SKU Profitability Analysis
- Discount Impact Analysis

> Complete SQL scripts are available inside the `/sql` folder.

---

## 💡 Key Insights

| # | Area | Insight |
|---|---|---|
| 1 | 📉 Revenue Trend | Q3 revenue **declined by 2.76%** compared to Q2 |
| 2 | 🛒 Category Mix | Electronics and Furniture contribute **~88% of total revenue** |
| 3 | 🏆 Top Region | **North** is the highest-performing region |
| 4 | ⚠️ Weak Region | **Central** is the lowest-performing region |
| 5 | 📦 SKU Revenue | SKU-MOB-003 and SKU-LAP-002 generated **₹573M+ combined revenue** |
| 6 | 🚨 Margin Risk | Both SKUs operate at **margins below 1%** |
| 7 | 🔻 Discount Leakage | Discounts **above 10%** make these products loss-making |

---

## 💼 Business Recommendations

| Priority | Recommendation |
|---|---|
| 🔴 Critical | **Restrict discounts above 10%** on low-margin products to stop profit leakage |
| 🔴 Critical | **Review pricing strategy** for Electronics SKUs with sub-1% margins |
| 🟠 High | **Create margin monitoring alerts** in Power BI for real-time profitability tracking |
| 🟡 Medium | **Develop a growth strategy** for the Central region to close the performance gap |
| 🟡 Medium | **Reduce category concentration risk** — diversify beyond Electronics and Furniture |

---

## 📊 Dashboard Features

Built in **Power BI Desktop** as a single-page executive dashboard on a dark `#0F172A` theme.

| Component | Type | Description |
|---|---|---|
| KPI Cards | Cards | Total Revenue · Total Profit · Profit Margin % · Total Orders · Total Customers |
| Monthly Revenue Trend | Line Chart | Month-wise revenue across the full year |
| Monthly Profit Trend | Line Chart | Month-wise profit overlaid on revenue |
| Revenue by Region | Clustered Column | Comparative regional revenue performance |
| Revenue by Category | Donut Chart | Category share — Electronics, Furniture, Clothing |
| Quarter-wise Revenue | Column Chart | Q1–Q4 revenue with trend indicators |
| Top Revenue SKUs | Horizontal Bar | Top 10 SKUs ranked by revenue |
| Revenue vs Profit Margin | Scatter Plot | SKU-level margin vs revenue — outliers highlighted |
| Interactive Slicers | Filters | Quarter · Region · Category · Sales Channel |

> 📂 Dashboard file: `dashboard/Retail_Sales_Dashboard.pbix`

---

## 📸 Dashboard Preview

<!-- Add dashboard screenshot here -->

---

## 🔄 Project Workflow

```
Retail Dataset (52K Records)
↓
Python (Data Validation & Cleaning)
↓
PostgreSQL (Business Analysis)
↓
Power BI (Dashboard Development)
↓
Business Insights & Recommendations
```

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| **PostgreSQL** | Structured querying and business aggregations |
| **Power BI Desktop** | Executive dashboard and interactive visualizations |
| **Python 3.10+** | Data cleaning, EDA, and validation automation |
| **Pandas** | Data manipulation, groupby analysis, transformations |
| **Microsoft Excel** | Initial data profiling and pivot exploration |
| **Jupyter Notebook** | Reproducible EDA documentation |

---

## 📁 Repository Structure

```
retail-sales-profitability-analysis/
│
├── 📄 README.md
│
├── 📂 data/
│   └── cleaned_retail_sales.csv          ← Validated dataset
│
├── 📂 dashboard/
│   └── Retail_Sales_Dashboard.pbix       ← Power BI dashboard
│
├── 📂 notebooks/
│   └── retail_sales_analysis.ipynb       ← EDA and validation notebook
│
├── 📂 sql/
│   ├── 01_quarter_revenue.sql
│   ├── 02_category_contribution.sql
│   ├── 03_regional_performance.sql
│   ├── 04_sku_profitability.sql
│   └── 05_discount_impact.sql
│
├── 📂 screenshots/                       ← Dashboard screenshots
│
└── 📄 requirements.txt                   ← Python dependencies
```

---

## 🚀 How to Run

### Prerequisites

- Python 3.10+
- PostgreSQL 16
- Power BI Desktop (free)

### Step 1 — Clone the Repository

```bash
git clone https://github.com/singh-shakshi/retail-sales-profitability-analysis.git
cd retail-sales-profitability-analysis
```

### Step 2 — Install Python Dependencies

```bash
pip install -r requirements.txt
```

**`requirements.txt`**

```
pandas>=2.0.0
numpy>=1.24.0
matplotlib>=3.7.0
seaborn>=0.12.0
sqlalchemy>=2.0.0
psycopg2-binary>=2.9.0
jupyter>=1.0.0
openpyxl>=3.1.0
```

### Step 3 — Set Up PostgreSQL

```bash
# Create the database
psql -U postgres -c "CREATE DATABASE retail_analytics;"

# Import the dataset
psql -U postgres -d retail_analytics \
  -c "\COPY retail_transactions FROM 'data/cleaned_retail_sales.csv' CSV HEADER;"
```

### Step 4 — Run the Notebook

```bash
jupyter notebook notebooks/retail_sales_analysis.ipynb
```

### Step 5 — Run SQL Queries

```bash
psql -U postgres -d retail_analytics -f sql/01_quarter_revenue.sql
psql -U postgres -d retail_analytics -f sql/02_category_contribution.sql
psql -U postgres -d retail_analytics -f sql/03_regional_performance.sql
psql -U postgres -d retail_analytics -f sql/04_sku_profitability.sql
psql -U postgres -d retail_analytics -f sql/05_discount_impact.sql
```

### Step 6 — Open the Dashboard

```
1. Open Power BI Desktop
2. File → Open → dashboard/Retail_Sales_Dashboard.pbix
3. Update data source path to your local CSV if prompted
4. Click Refresh → explore the dashboard
```

---

## 🔮 Future Enhancements

- [ ] **Customer Segmentation** — RFM (Recency, Frequency, Monetary) analysis
- [ ] **Streamlit Web Dashboard** — Web-based Python dashboard
- [ ] **Automated KPI Monitoring** — Real-time margin and revenue alerts

---

## 👤 Author

**Shakshi Singh**

BCA Student | Aspiring Data Analyst

[![GitHub](https://img.shields.io/badge/GitHub-singh--shakshi-black?style=flat&logo=github)](https://github.com/singh-shakshi)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Shakshi%20Singh-blue?style=flat&logo=linkedin)](https://linkedin.com/in/shakshi-singh-752a41333)

---

<div align="center">

*If this project was helpful, please consider giving it a ⭐*

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:3B82F6,100:0F172A&height=100&section=footer" width="100%"/>

</div>
