# 📊 IT Expenditure Dashboard – Power BI

## 🚀 Project Overview
The **IT Expenditure Dashboard** is an interactive **Power BI solution** designed to track, analyze, and visualize IT spending across multiple dimensions such as **business areas, IT functions, cost categories, countries, and months**.

### 🎯 Key Objectives
- Identify **overspending or underspending** quickly.  
- Analyze **spending trends over time**.  
- Evaluate **cost performance** across departments, IT areas, and countries.  
- Support **data-driven decision-making** for cost optimization and resource allocation.  

---

## 📂 Dataset Description
The dataset is sourced from **Excel (Dataset.xlsx)** and contains IT expenditure details.

### 🔑 Columns
- **Plan** – Budgeted IT expenditure.  
- **Actual** – Actual IT expenditure incurred.  
- **Forecast** – Updated estimate of IT expenditure.  
- **Business Area** – (Infrastructure, Manufacturing, Office & Admin, R&D, Distribution, BU).  
- **IT Area** – (BU Support, Enablement, Functional, Infrastructure, Governance).  
- **Cost Element** – (Salaries, Services, Hardware, Depreciation, Labor, Shared Services, Others).  
- **Country** – (UK, France, Germany, Brazil, India, etc.).  
- **Month/Date** – (Jan, Feb, Mar, etc.).  

### 🛠 Data Preparation
- Cleaned with **Power Query** (removed nulls, duplicates, corrected data types).  
- Created **Calendar Table** for time-based analysis.  
- Star Schema Model:  
  - **Fact Table** – Expenditure (Plan, Actual, Forecast).  
  - **Dimension Tables** – Business Area, IT Area, Cost Element, Country, Date.  

---

## 📊 Dashboard Visuals
- **KPI Cards** → Total Actual, Total Forecast, Variances & % differences.  
- **Clustered Column Chart (By Month)** → Plan vs Actual vs Forecast trends.  
- **Clustered Bar Chart (By Business Area)** → Overspending/underspending by department.  
- **Donut Chart** → Variance breakdown by cost elements.  
- **Stacked Bar Chart** → Spending contribution by categories.  
- **Clustered Bar Chart (By IT Area)** → IT division performance against budget.  
- **Table (By Country)** → Geographic view of Plan vs Actual variance.  

---

## 📐 DAX Measures
```DAX
Total Actual = SUM(Data[Actual])
Total Forecast = SUM(Data[Forecast])
Plan VS Actual Variance = SUM(Data[Plan]) - SUM(Data[Actual])
Plan VS Actual Variance % = DIVIDE(SUM(Data[Plan]), SUM(Data[Actual])) - 1
Plan VS Forecast Variance = SUM(Data[Plan]) - SUM(Data[Forecast])
Plan VS Forecast Variance % = DIVIDE(SUM(Data[Plan]), SUM(Data[Forecast])) - 1
