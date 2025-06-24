# 📊 E-Commerce Returns & Profitability Dashboard

This project is a complete **end-to-end data analysis case study** that focuses on return trends in an e-commerce business. The dashboard was built using **Power BI**, with data processing and modeling done in **MySQL**.

![E-Commerce Returns   Profitability Dashboard](https://github.com/user-attachments/assets/76565b77-8285-491f-b71e-77bb3f292199)

---

## 🧠 Project Objective

To help an e-commerce business understand:
- Which product categories have the most returns
- What reasons lead to returns
- How much revenue is lost due to returned products
- How delivery delays affect return rates
- What geographic regions are most affected

---
##🧾 Key Insights
Home & Living had the highest number of returns
Most common return reason: Not as Described
Returns significantly increase when delivery delay exceeds 5 days
Lost revenue from returns: ₹91.68K
Southern and Western regions showed higher return activity

## 🔧 Tools Used

| Tool | Purpose |
|------|---------|
| **MySQL** | Data cleaning, joining, and preparation |
| **Power BI** | Dashboard building and data visualization |
| **DAX** | Calculated measures and KPIs |
| **Excel** | Initial data creation and verification |

---

## 📂 Datasets Used

The project consists of 5 CSV files:

- `customers.csv` – customer profiles and locations
- `orders.csv` – order details including date and total price
- `products.csv` – product category and brand
- `delivery.csv` – delivery status, delay days, courier info
- `returns.csv` – return reasons and dates

---

## 📈 KPIs & Visuals

### 🟦 Key KPIs
- ✅ Total Orders
- 🔁 Total Returns
- 📉 Return Rate %
- 💸 Lost Revenue from Returned Orders

### 📊 Visualizations
- Monthly Return Trend (Line Chart)
- Returns by Category (Bar Chart)
- Top Returned Products (Bar Chart)
- Return Reasons (Pie Chart)
- Delivery Delay vs Returns (Bar Chart)
- Geographic Distribution of Returns (Map)

---

## 🧮 DAX Highlights

```dax
Return Rate % = 
DIVIDE(DISTINCTCOUNT(returns[ReturnID]), DISTINCTCOUNT(orders[OrderID])) * 100

Lost Revenue = 
CALCULATE(SUM(orders[TotalPrice]), FILTER(orders, orders[OrderID] IN VALUES(returns[OrderID])))
