# 🗄️ Data Engineering: Granularity Mismatches, Discrepancy Root-Cause Analysis & ETL Debugging

Today, I investigated data discrepancy issues across relational tables, analyzed schema column mismatches, and debugged data flow mappings within Oracle Data Integrator (ODI 12c).

### 🚀 Key Technical Deliverables
* **Root-Cause Analysis on Data Discrepancies:** Identified that numerical variances between target and source tables stemmed from multi-key join operations involving granular attributes (`firmcode` combined with `payment_type`).
* **Granularity Mismatch Resolution:** Determined that joining tables on composite attributes created naturally expanded or filtered result sets due to differing cardinality levels between datasets.
* **Column Mismatch Investigation:** Executed schema comparison checks across target and staging tables to isolate structural column differences and datatype mismatches.
* **ETL Pipeline Inspection:** Conducted visual mapping and logical flow reviews in **ODI 12c** to isolate execution bugs and ensure upstream-to-downstream transformation integrity.

### 💡 Insight
Data discrepancies during ETL or staging processes are often not system bugs, but rather a reflection of differing aggregation levels. Understanding dataset granularity—such as how composite key joins affect row cardinality—is essential before declaring data errors in data pipelines.
