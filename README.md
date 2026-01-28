# Operational Risk & Bottleneck Analysis (Preventive Logistics)

## 📌 Project Overview
This project analyzes a dataset of **50,000+ operational records** to transition a logistics workflow from **reactive** to **preventive**. By identifying hidden correlations between staffing levels and volume surges, I developed an "Early Warning System" that flags at-risk operations 24 hours in advance.

## 🛠️ Tech Stack
- **Language:** Python 3.x
- **Database:** SQLite (SQL scripting within Python environment)
- **Libraries:** Pandas, Seaborn, Matplotlib, NumPy
- **Visualization:** Power BI (Reporting Layer)

## 📉 Phase 1: SQL Diagnostic Analysis
I used SQLite to aggregate historical data and identify which specific vendor segments were responsible for the most delays (SLA breaches).

**SQL Logic applied:**
```sql
SELECT Vendor_Type, COUNT(*) as total_orders, ROUND(AVG(Overdue_Flag) * 100, 2) as failure_rate_pct
FROM operations
GROUP BY Vendor_Type
ORDER BY failure_rate_pct DESC
---
