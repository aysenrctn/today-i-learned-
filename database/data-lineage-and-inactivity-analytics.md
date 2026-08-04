# 🗄️ SQL Analytics: Data Lineage Mapping & Customer Inactivity Analysis

Today, I investigated data lineage within the corporate data dictionary and constructed time-series analytical queries to segment inactive customers over rolling date windows.

### 🚀 Key Technical Deliverables
* **Data Lineage & Dictionary Analysis:** Analyzed system-wide data dictionary definitions to trace source-to-target field mappings (identifying origin tables, columns, and relation joins).
* **Time-Window Filtering:** Constructed optimized date-range queries (`DATEDIFF` / `INTERVAL` / `ADD_MONTHS`) to dynamically slice transaction histories.
* **Customer Inactivity Segmentation:** Identified inactive customer segments by filtering accounts with zero transaction records within relative 3-month, 6-month, and 12-month lookback windows.

### 💡 Insight
Traceability (Data Lineage) is essential before writing complex analytical queries. Understanding exactly which column originates from which upstream table prevents incorrect join logic, while relative date filtering ensures automated, repeatable churn and inactivity reporting.
