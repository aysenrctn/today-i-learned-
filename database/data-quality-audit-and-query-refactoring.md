# 🗄️ Data Engineering: Data Quality Audit, Temporal Discrepancies & Query Refactoring

Today, I performed a comprehensive data quality audit across relational tables, investigated temporal data discrepancies, refactored SQL scripts, and developed customer-level campaign analytics.

### 🚀 Key Technical Deliverables
* **Data Quality & Consistency Audit:** Executed cross-table integrity checks to flag data discrepancies and anomaly points between source and staging layers.
* **Temporal Discrepancy Detection:** Isolated date-based record discrepancies by constructing targeted time-series validation queries to detect missing or mismatched logs.
* **Query Refactoring & Self-Correction:** Reviewed and optimized previously written SQL scripts, resolving logical flaws and edge cases to improve query accuracy and execution performance.
* **Customer Campaign Analytics:** Wrote analytical SQL queries to calculate the distinct number of campaign touchpoints applied per individual customer (`COUNT(DISTINCT campaign_id) GROUP BY customer_id`).

### 💡 Insight
Data quality issues often surface through temporal mismatches across pipeline stages. Catching logic errors through proactive audits and refactoring one's own SQL scripts ensures downstream dashboards and business decisions rely on single-source-of-truth data.
