# 🗄️ SQL Governance: Automated Soft-Delete Auditing & DWH ID Deduplication

Today, I engineered metadata audit scripts to detect missing soft-delete filters across ODS and CDP layers, researched automated AST/SQL-parsing mechanisms for dynamic filter injection, and validated surrogate vs. source key integrity in the DWH.

### 🚀 Key Technical Execution

#### 1. Soft-Delete Filter Audit (`is_deleted = 0`)
* **Automated Discrepancy Audit:** Developed SQL metadata and script-scanning logic to identify queries and views targeting ODS/CDP layers that lack the mandatory `WHERE is_deleted = 0` clause.
* **Audit Reporting:** Isolated non-compliant queries into a structured audit report to prevent deleted legacy records from corrupting downstream reporting pipelines.

#### 2. Automated Filter Injection Research
* **AST & Alias-Aware Injection:** Researched automated techniques for injecting `is_deleted = 0` conditions into existing SQL queries without breaking syntax.
* **Complex JOIN & Font/Syntax Handling:** Evaluated rules for detecting table aliases in multi-table `JOIN` statements (e.g., ensuring `t1.is_deleted = 0` vs `t2.is_deleted = 0`) while maintaining strict font, casing, and encoding compatibility across different database platforms.

#### 3. DWH Key Integrity & Anomaly Detection
* **Surrogate vs. Source Key Deduplication:** Conducted data integrity checks to detect cases where multiple distinct DWH IDs (`dwh_id`) shared the same Source ID (`src_id`).
* **Critical Anomaly Analysis:** Evaluated whether source key collisions across distinct surrogate keys represented valid historical SCD (Slowly Changing Dimensions) behavior or critical data duplication defects within source integrations.

### 💡 Insight
Automating SQL code audits for mandatory business rules like soft-deleting (`is_deleted = 0`) prevents logic leaks before queries reach production. When attempting automated filter injection on complex SQLs, parsing table aliases correctly is essential to avoid ambiguous column errors in multi-table JOINs.
