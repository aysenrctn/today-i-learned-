# 🔍 Data Warehouse ETL Debugging: Root Cause Analysis & Metadata Querying

Today, I investigated data discrepancy issues between staging/source and target Data Warehouse (DW) structures, focusing on ODI 12c mapping execution patterns, SQL difference techniques, and metadata dictionary exploration.

### 🚀 Key Technical Concepts
* **Discrepancy Analysis Techniques:**
  * **Duplicate Detection:** Identified phantom/extra rows causing data inflation across pipeline stages.
  * **Group By vs. MINUS Extraction:** Benchmarked set-difference queries (`MINUS`) against aggregated checks (`GROUP BY`) to pinpoint row-level missing or unmatched records.
* **ODI 12c Mapping Inspection:** Analyzed ETL transformations to locate failure points originating from aggressive join conditions or erroneous filter logics.
* **Surrogate Key Tracking:** Investigated why system-generated surrogate keys (`src_id`) mutated or shifted across DW layer updates.
* **Data Dictionary & Lineage Querying:** Constructed schema-qualified SQL scripts (`ALL_TAB_COLS`, `ALL_COL_COMMENTS`) to dynamically trace source-to-target column origins and field ownership.

### 💡 Insight
Data mismatch in DW pipelines rarely stems from corrupted source data alone; it is frequently caused by implicit join behavior (e.g., INNER vs. LEFT JOIN dropping valid records) or duplicate source records breaking group-by expectations. Tracing metadata directly via dictionary queries combined with systematic `MINUS` operations provides a sub-second pinpointing mechanism for ETL bugs.

### 🛠️ Practical Example

```sql
-- 1. Finding data discrepancies between Source/ODS and Data Warehouse (MINUS technique)
SELECT customer_id, transaction_date, amount FROM ods_transactions
MINUS
SELECT customer_id, transaction_date, amount FROM dwh_fact_transactions;

-- 2. Querying Oracle Data Dictionary to trace column ownership and schema lineage
SELECT 
    owner,
    table_name,
    column_name,
    data_type,
    data_length
FROM all_tab_columns
WHERE column_name = 'SRC_ID'
  AND owner IN ('STAGE_LAYER', 'DWH_LAYER')
ORDER BY owner, table_name;
