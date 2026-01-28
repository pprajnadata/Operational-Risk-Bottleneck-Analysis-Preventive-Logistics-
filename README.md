# Operational-Risk-Bottleneck-Analysis-Preventive-Logistics
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

🧪 Phase 2: Root Cause Analysis (Python)
Using Python, I performed a correlation study. The data proved that delays weren't random; they were highly correlated with a specific Volume-to-Staff ratio.

Finding: A negative correlation between Staff_Level and Overdue_Flag confirmed that staffing gaps during peak hours (Volume > 400) were the primary bottleneck.

🚀 Phase 3: The "24-Hour" Preventive Flag
I implemented a predictive logic layer that assigns a Risk Category to every order. This allows management to intervene before a delay occurs.

Critical Risk: High Volume (>400) + Low Staff (<5).

Moderate Risk: High Volume (>350).

Outcome: A standardized reporting structure that allows for proactive staff reallocation.

📂 How to Run
Ensure you have the operational_overdue_data.csv in the root folder.

Run operational_analysis.py to generate the SQL audit and the Predictive Report.

View the generated final_operational_risk_report.csv for the intervention list.

Author: Prajna Priyadarshini

---
