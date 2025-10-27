# 🧭 AdventureWorks Sales Analytics Dashboard

### 📈 Power BI | Data Visualization | Business Insights

---

## 📋 **Overview**

The **AdventureWorks Sales Analytics Dashboard** is a data-driven Power BI project built to analyze sales, customer, and product performance of the AdventureWorks company.  
It focuses on uncovering insights into **revenue trends, profit margins, product returns, customer behavior, and regional performance** using advanced DAX measures and interactive visuals.

---

## 🎯 **Problem Statement**

AdventureWorks, a global retail company, wanted to **track and analyze its overall performance** across multiple categories, subcategories, and regions.  
The goal was to create a **dynamic and interactive dashboard** that helps decision-makers identify trends, improve forecasting accuracy, and monitor KPIs like total sales, orders, profit, and returns.

---

## 🧩 **Dataset**

The project uses **AdventureWorks CSV datasets**, including:

- `Adventureworks_Calendar`
- `Adventureworks_Customers`
- `Adventureworks_Product_Categories`
- `Adventureworks_Product_Subcategories`
- `Adventureworks_Products`
- `Adventureworks_Returns`
- `Adventureworks_Sales_2015`
- `Adventureworks_Sales_2016`
- `Adventureworks_Sales_2017`
- `Adventureworks_Territories`

> Note: All 3 yearly sales tables were combined into one unified **Sales table** in Power BI using Power Query.

---

## ⚙️ **Tools & Technologies Used**

- **Power BI** → Data modeling, DAX measures, visualizations  
- **Power Query** → Data transformation & cleaning  
- **DAX (Data Analysis Expressions)** → Calculated measures, KPIs, time intelligence  
- **CSV Files** → Source data  

---

## 🔍 **Methods & Workflow**

1. **Data Loading & Cleaning:**  
   Imported CSV datasets and removed duplicates, blanks, and inconsistencies in product, customer, and sales data.

2. **Data Modeling:**  
   Built relationships between fact and dimension tables — Customers, Calendar, Products, Territories, and Returns.

3. **Measure Creation (DAX):**  
   Created custom measures for KPIs such as Total Revenue, Profit, Orders, Return Rate, Target Orders, and Average Price.

4. **Dashboard Design:**  
   Designed three key analytical views:
   - **Category Analysis**
   - **Product Analysis**
   - **Customer Analysis**

5. **Visualization:**  
   Used bar charts, cards, donut charts, maps, and KPI cards with slicers and tooltips for interactivity.

---

## 📊 **Key Metrics & Insights**

### **Category Analysis**
- Total Revenue & Total Quantity Sold  
- Return Rate per Category  
- Highest Return Categories & Subcategories  
- Orders split by Weekend vs Weekday  
- % of Total Orders per Category  
- High-Ticket Orders (price > overall average)

### **Product Analysis**
- Most Ordered & Most Profitable Products  
- Weekly Profit & Product Returns  
- Target Orders vs Actual (Gauge Chart)  
- Country-wise Orders (Geo Map with Category Tooltip)  
- Time Intelligence Metrics (Month Start, Week Start)

### **Customer Analysis**
- Revenue & Order Count per Customer (with conditional formatting)  
- Annual Income Segmentation (Low, Average, High)  
- Orders by Gender & Income Category  
- Top Customer Revenue & Occupation  
- Monthly Revenue & Growth Trends  
- Orders by Age Group (Tree Map)

---

## 🧮 **Important DAX Formulas Used**

```DAX
Order Target = [Prev Month Orders] * 1.1

Prev Month Orders = 
    CALCULATE([Total Orders], DATEADD('Calendar'[Date], -1, MONTH))

Income Level = 
    IF(Customers[AnnualIncome] <= 30000, "Low",
        IF(AND(Customers[AnnualIncome] > 30000, Customers[AnnualIncome] <= 80000), 
            "Average", "High"))
