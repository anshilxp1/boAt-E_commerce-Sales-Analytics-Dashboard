# 🎧 boAt E-Commerce Sales Analytics Power BI Dashboard
An end-to-end Power BI analytics project built on boAt's e-commerce sales data, covering customer behavior, revenue trends, product performance, and return analysis across India.Built during training at
CETPA Infotech Pvt. Ltd.

---

## 📊 Dashboard Pages

| Page | Focus |
|------|-------|
| Overview | KPIs, monthly trends, channel & state-wise performance |
| Revenue | Category & day-wise revenue, top 5 products |
| Product & Return | Return reasons, refund status, review sentiment |

> 📄 See `dashboard_preview.pdf` for full screenshots.

---

## 🔢 Key Metrics

| Metric | Value |
|--------|-------|
| Total Revenue | $135M |
| Total Orders | 22K |
| Total Customers | 12K |
| Total Returns | 4.5K |

---

## ⚙️ DAX Measures

```dax
Total Revenue   = 'Order_Detail csv'[unit_price] * 'Order_Detail csv'[quantity]
                  - 'Order_Detail csv'[disc_price2] * 'Order_Detail csv'[quantity]
                  * 'Order_Detail csv'[unit_price]

Total Orders    = DISTINCTCOUNT(Order_Boat[order_id])
Total Customers = DISTINCTCOUNT(Boat_Customer[customer_id])
Total Returns   = DISTINCTCOUNT(Return[return_id])
Avg Revenue     = DIVIDE([Total Revenue], [Total Orders])
Return Rate %   = DIVIDE([Total Returns], [Total Orders], 0) * 100
```

---

## 🗃️ Data Model (5 tables)

`Boat_Customer` → `Order_Boat` → `Order_Detail` ← `Product`  
`Order_Detail` → `Return`

---

## 🛠️ Tech Stack

`Power BI Desktop` · `DAX` · `Power Query (M)` · `Bing Maps` · `CSV`

---

## 🏫 Built During

**Data Analytics Training — CETPA Infotech Pvt. Ltd., Noida**

**Author:** Anshil Gautam · 📍 Lucknow, UP
