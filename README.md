# Sales Performance Dashboard – Power BI

## 📌 Overview
This Power BI dashboard analyzes sales performance across regions, products, and time.  
It helps business stakeholders track revenue, profit, YoY growth, and identify high-performing segments.

## 🎯 Objectives
- Monitor total sales, profit, and growth over time
- Compare performance across regions and product categories
- Identify top and bottom performing products
- Provide management with an interactive view of sales KPIs

## 🧰 Tech Stack
- Power BI
- Power Query
- DAX
- Excel / CSV as data source

## 🗂 Data Model
- **Fact table:** Sales (Date, Product, Region, Customer, Sales Amount, Profit, Quantity)
- **Dimension tables:** Date, Product, Region, Customer

Modeled in a **star schema** for better performance and clarity.

## 🧮 Key DAX Measures

```DAX
Total Sales = SUM(Sales[SalesAmount])

Total Profit = SUM(Sales[Profit])

YoY Sales =
CALCULATE(
    [Total Sales],
    DATEADD('Date'[Date], -1, YEAR)
)

YoY Growth % =
DIVIDE([Total Sales] - [YoY Sales], [YoY Sales])
