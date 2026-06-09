# 🎧 boAt Lifestyle — Sales & Returns Analytics Dashboard

> An end-to-end Power BI analytics project built on boAt's e-commerce sales data, covering customer behavior, revenue trends, product performance, and return analysis across India.

---

## 📌 Project Overview

This project analyzes **boAt Lifestyle's** sales operations using a multi-table relational dataset. The dashboard enables business stakeholders to monitor KPIs, identify top-performing products, understand return patterns, and track revenue across channels and geographies — all in a visually rich, 3-page interactive report.

Built during training at **CETPA Infotech Pvt. Ltd.**

---

## 📊 Dashboard Pages

### 1. Overview
High-level KPIs with a monthly order vs. return trend, channel-wise order distribution, category ratings, and state-wise revenue map.

### 2. Revenue
Category-wise and day-wise revenue breakdown, top 5 products by quantity sold, average revenue, and weekend revenue tracking.

### 3. Product & Return
Product count by category and review sentiment, return volume by category and reason, and refund status distribution.

---

## 🔢 Key KPIs

| KPI | Value |
|-----|-------|
| Total Revenue | $135M |
| Total Orders | 22K |
| Total Customers | 12K |
| Total Products | 379 |
| Total Returns | 4.5K |
| Total Quantity Sold | 89K |
| Weekend Revenue | $4M |
| Average Revenue per Order | $2K |

---

## 📐 DAX Measures Used

```DAX
-- Total Revenue
Total Revenue  ='Order_Detail csv'[unit_price]*'Order_Detail csv'[quantity]-'Order_Detail csv'[disc_price2]*'Order_Detail csv'[quantity]*'Order_Detail csv'[unit_price]

-- Total Orders
Total Orders = DISTINCTCOUNT(Order_Boat[order_id])

-- Total Customers
Total Customers = DISTINCTCOUNT(Boat_Customer[customer_id])

-- Total Products
Total Products = DISTINCTCOUNT(Product[product_id])

-- Total Returns
Total Returns = DISTINCTCOUNT(Return[return_id])

-- Total Quantity
Total Qty = SUM(Order_Detail[quantity])

-- Average Revenue
Avg Revenue = DIVIDE([Total Revenue], [Total Orders])

-- Weekend Revenue
Weekend Revenue = =format('Order_Boat csv'[order_date],"dddd")

-- Return Rate %
Return Rate % = DIVIDE([Total Returns], [Total Orders], 0) * 100

```

---

## 📈 Charts & Visuals

| Visual | Description |
|--------|-------------|
| KPI Cards | Total Revenue, Orders, Customers, Products, Returns |
| Line Chart | Monthly order count vs. return count comparison |
| Bar Chart | Total orders by sales channel (Amazon, Flipkart, boAt Website, etc.) |
| Pie Chart | Rating distribution by product category |
| Map Visual | State-wise revenue across India |
| Donut Chart | Refund status breakdown (Approved / Processed / Pending) |
| Bar Chart | Top 5 products by quantity sold |
| Bar Chart | Total products by category |
| Pie Chart | Product review sentiment distribution |
| Matrix Table | Return reasons by category |
| Matrix Table | Order vs. return count by category |
| Line Chart | Day-wise revenue trend |
| Pie Chart | Category-wise revenue share |

---

## 🎛️ Slicers / Filters

| Slicer | Field | Page |
|--------|-------|------|
| Payment Method | `Order_Boat[payment_method]` | Overview |
| Color | `Product[color]` | Product & Return |
| Month | `Order_Boat[order_date]` (Month) | Revenue |

---

## 🗃️ Dataset Description

| File | Description |
|------|-------------|
| `Boat_Customer.csv` | Customer demographics — name, gender, age, city, state |
| `Order_Boat.csv` | Order-level data — date, channel, payment method, shipping status |
| `Order_Detail.csv` | Line-item details — product ID, quantity, unit price, discount |
| `Product.csv` | Product catalog — name, MRP, category, rating, color, review |
| `Return.csv` | Return records — return date, reason, refund status |


## 🛠️ Tools & Technologies

- **Power BI Desktop** — Report building, DAX, data modeling
- **Power Query (M)** — Data cleaning and transformation
- **Microsoft Bing Maps** — State-wise geographic visualization
- **CSV** — Raw data source format

---

## 🏫 Training Context

This project was completed as part of a **Data Analytics training program** at [CETPA Infotech Pvt. Ltd.](https://www.cetpainfotech.com/), Noida. The goal was to demonstrate end-to-end BI skills — from raw data ingestion to dashboard storytelling.

---

## 📁 Repository Structure

```
boAt-PowerBI-Dashboard/
│
├── boat.pbix                  
├── datasets/
│   ├── Boat_Customer.csv
│   ├── Order_Boat.csv
│   ├── Order_Detail.csv
│   ├── Product.csv
│   └── Return.csv
├── dashboard_preview.pdf      #
└── README.md
```

---


**Page 1 — Overview**
![Overview](dashboard_preview.pdf)

## 👤 Author

**Anshil**  
Data Analytics Trainee | CETPA Infotech Pvt. Ltd.  
📍 Lucknow, Uttar Pradesh  

---

## 📄 License

This project is for educational and portfolio purposes only. The boAt brand and logo belong to Imagine Marketing Ltd.
