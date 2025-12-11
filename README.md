# 🚚 Delivery Performance Analytics Dashboard  
**Author:** Rashaad Cage  
**Role:** Data / IT Analyst  

---

## 📌 Overview  
This project analyzes delivery performance across multiple warehouses to understand shipping efficiency, delay behavior, cost patterns, and operational bottlenecks.  
It simulates a real-world logistics environment and demonstrates skills in:

- Data cleaning  
- KPI calculation  
- SQL querying  
- Visual analytics  
- Dashboard-ready reporting  

---

## 📁 Dataset Description  
The dataset includes synthetic logistics data with fields such as:

- Shipment ID  
- Warehouse  
- Region  
- Distance (miles)  
- Freight cost  
- Shipped date  
- Expected delivery date  
- Actual delivery date  

This enables analysis of delivery times, cost efficiency, and delay patterns.

---

## 🛠 Tools Used  
- **Excel** — initial data exploration and cleaning  
- **SQL** — KPI calculation, filtering, and aggregation  
- **Power BI** — dashboards and data visualizations  

---

## 📂 Files Included  
- `logistics_data.csv` — synthetic logistics dataset  
- `logistics_late_chart.png` — bar chart of on-time vs late deliveries  
- `README.md` — full project documentation  

---

## 📊 Key Metrics (KPIs)  
- **On-Time Delivery Rate**  
- **Average Delivery Time**  
- **Cost per Mile**  
- **Late Deliveries by Warehouse / Region**  

---

## 🧠 SQL Examples  

### 1️⃣ On-Time vs Late Deliveries  
```sql
SELECT
    CASE
        WHEN delivered_date <= expected_delivery THEN 'On-Time'
        ELSE 'Late'
    END AS delivery_status,
    COUNT(*) AS total_shipments
FROM logistics
GROUP BY delivery_status;
