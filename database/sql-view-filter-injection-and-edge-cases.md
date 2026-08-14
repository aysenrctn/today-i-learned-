# 🗄️ SQL Governance: View DDL Parsing & Automated Filter Injection Edge Cases

Today, I audited an automated script designed to programmatically inject `WHERE is_deleted = 0` into database view definitions and analyzed edge cases that could introduce syntax or logical defects.

### 🚀 Key Technical Deliverables
* **Automated DDL Modification Audit:** Reviewed programmatic code designed to scan, parse, and modify SQL view definitions across database schemas to enforce soft-delete compliance.
* **Edge-Case & Risk Analysis:** Identified potential points of failure during automated query rewrites:
  * **Alias Collision & Ambiguity:** Handling complex multi-table `JOIN` operations where table aliases must be accurately resolved to avoid ambiguous column references (e.g., `t1.is_deleted` vs. `t2.is_deleted`).
  * **Existing WHERE vs. HAVING Clauses:** Ensuring the script properly determines whether to append `AND is_deleted = 0` or inject a new `WHERE` clause without disrupting existing subqueries, `GROUP BY`, or `UNION` structures.
  * **View Encapsulation & Subqueries:** Preventing accidental filter placement inside inner nested subqueries rather than the outermost view projection.

### 💡 Insight
Programmatically rewriting SQL views via script automation requires deep AST (Abstract Syntax Tree) parsing rather than simple string/regex replacements. Accounting for multi-table aliases, nested CTEs, and compound queries is crucial to prevent runtime DDL invalidation.
