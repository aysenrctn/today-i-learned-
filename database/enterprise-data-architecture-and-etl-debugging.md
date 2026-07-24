# 🧹 Data Engineering: Enterprise Architecture & ETL Mapping Debugging

During my internship, I analyzed enterprise data warehouse layers and debugged data duplication issues within an Oracle Data Integrator (ODI 12c) pipeline.

### 🚀 Technical Execution
* **Data Dictionary & Architecture Review:** Inspected the corporate data dictionary alongside **CDP** (Customer Data Platform) and **ODS** (Operational Data Store) table structures.
* **Duplication Analysis:** Executed analytical SQL queries to identify root causes of record duplication across relational staging layers.
* **ETL Pipeline Remediation:** Analyzed mapping flows in **ODI 12c** and successfully resolved the logical error causing data multiplication in target tables.

### 💡 Insight
Data duplication in enterprise pipelines often stems from joins on unconstrained foreign keys during the ODS-to-CDP transition. Resolving these issues inside the ETL tool (like ODI) ensures downstream analytics remain accurate and reliable.
