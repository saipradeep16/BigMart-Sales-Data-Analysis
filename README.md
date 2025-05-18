# 🛒 BigMart Sales Data Analysis

## 📌 Introduction

To support data-driven decision-making in retail, this project analyzes BigMart’s sales dataset to identify key trends and patterns. Our goal is to uncover factors that influence store performance, product sales, and revenue across various outlet types and product categories.

---

## 🎯 Objectives

- Analyze BigMart's sales data across product types, outlet types, and locations  
- Identify high-performing products and underperforming outlets  
- Provide data-driven insights to improve retail operations and strategic planning

---

## 🧾 Dataset Overview

- **Dataset Name**: BigMart Sales Dataset  
- **Source**: [Kaggle](https://www.kaggle.com/datasets/lokeshmendake/big-mart-sales-dataset)  
- **Rows**: 8,523  
- **Columns**: 12  

---

## ☁️ Data Storage

- Platform: **Google Cloud Platform (GCP)**  
- Tools:
  - **Google Cloud Storage** – for uploading raw CSV  
  - **Google BigQuery** – for querying  
  - **Looker Studio** – for reporting  

---

## 💻 SQL Query Examples

### 📌 Query 1: Outlet with Highest Total Sales
```sql
SELECT Outlet_Identifier, SUM(Item_Outlet_Sales) AS Total_Sales
FROM BigMart
GROUP BY Outlet_Identifier
ORDER BY Total_Sales DESC;
```
**Insight**: Outlet `OUT027` recorded the highest total sales.

---

### 🔝 Query 2: Top 10 Products by Total Sales
```sql
SELECT Item_Identifier, SUM(Item_Outlet_Sales) AS Total_Sales
FROM BigMart
GROUP BY Item_Identifier
ORDER BY Total_Sales DESC
LIMIT 10;
```
**Insight**: Products like `FDY55` significantly outsold others.

---

### 🧺 Query 3: Best-Selling Product Categories by Average Sales
```sql
SELECT Item_Type, AVG(Item_Outlet_Sales) AS Avg_Sales
FROM BigMart
GROUP BY Item_Type
ORDER BY Avg_Sales DESC;
```
**Insight**: `Starchy Foods` had the highest average sales.

---

### 🏪 Query 4: Outlet Sales by Establishment Year
```sql
SELECT Outlet_Establishment_Year, SUM(Item_Outlet_Sales) AS Total_Sales
FROM BigMart
GROUP BY Outlet_Establishment_Year
ORDER BY Outlet_Establishment_Year;
```
**Insight**: Outlets established in **1985** showed the strongest sales performance.

---

### ⚖️ Query 5: Sales Comparison - "Low Fat" vs "Regular"
```sql
SELECT Item_Fat_Content, AVG(Item_Outlet_Sales) AS Avg_Sales
FROM BigMart
GROUP BY Item_Fat_Content;
```
**Insight**: "Regular" items slightly outperformed "Low Fat" items.

---


## ✅ Conclusion

This project successfully demonstrates how historical retail sales data can be used to extract insights that support business intelligence. We:

- Cleaned and preprocessed raw data using OpenRefine  
- Stored and queried data using Google Cloud tools  
- Identified actionable insights using SQL and visual analysis

BigMart can use these findings to improve operational efficiency, marketing strategy, and store planning. Further exploration could involve time-series forecasting or predictive modeling using machine learning.
