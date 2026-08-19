# 🗄️ SQL Governance: Advanced View DDL Rewriter & Complex Edge-Case Handling

Today, I reviewed and enhanced an automated script designed to inject soft-delete filters (`WHERE is_deleted = 0`) across complex SQL view definitions, focusing on extreme edge cases.

### 🚀 Key Technical Deliverables
* **Script Optimization:** Audited the core logic responsible for parsing and mutating database view definitions across relational schemas.
* **Complex Edge-Case Resolution:**
  * **Nested Subqueries & CTEs:** Handled Common Table Expressions (`WITH` clauses) and deeply nested derived tables to ensure filter injection targets the appropriate scope without mutating subquery logic.
  * **Set Operators (UNION / UNION ALL):** Ensured each independent query block within compound SQL statements receives appropriate soft-delete validation.
  * **Explicit Table Aliasing:** Resolved ambiguous column references in multi-join views by dynamically detecting source table aliases.

### 💡 Insight
Automating SQL DDL modifications across varied codebases requires defensive parser design. Accounting for compound operators like `UNION` and multi-layered CTEs ensures automated schema governance does not break production view definitions.
