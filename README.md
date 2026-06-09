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
Total Revenue = SUMX(Order_Detail, Order_Detail[quantity] * Order_Detail[unit_price] * (1 - Order_Detail[discount_percent]/100))

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
Weekend Revenue = 
CALCULATE(
    [Total Revenue],
    FILTER(
        ALL(Order_Boat),
        WEEKDAY(Order_Boat[order_date], 2) >= 6
    )
)

-- Return Rate %
Return Rate % = DIVIDE([Total Returns], [Total Orders], 0) * 100

-- Month Number (for sorting)
Month Number = MONTH(Order_Boat[order_date])
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

---

## 🔗 Data Model (Relationships)

```
Boat_Customer (customer_id) ──── Order_Boat (customer_id)
Order_Boat (order_id)       ──── Order_Detail (Order_id)
Order_Detail (product_id)   ──── Product (product_id)
Order_Detail (Order_Detail_id) ── Return (order_detail_id)
```

All relationships are **one-to-many**, forming a star/snowflake schema.

---

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
├── boat.pbix                  # Power BI report file
├── datasets/
│   ├── Boat_Customer.csv
│   ├── Order_Boat.csv
│   ├── Order_Detail.csv
│   ├── Product.csv
│   └── Return.csv
├── dashboard_preview.pdf      # Exported PDF of all 3 pages
└── README.md
```

---

## 📸 Dashboard Preview

> See `dashboard_preview.pdf` for full resolution screenshots of all three pages.

**Page 1 — Overview**
![Overview](dashboard_preview.pdf)

---

## 👤 Author

**Anshil**  
Data Analytics Trainee | CETPA Infotech Pvt. Ltd.  
📍 Lucknow, Uttar Pradesh  

---

## 📄 License

This project is for educational and portfolio purposes only. The boAt brand and logo belong to Imagine Marketing Ltd.
