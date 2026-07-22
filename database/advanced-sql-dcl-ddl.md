# 🗄️ Advanced SQL: Access Control, Schema Alterations & Constraints

Today, I practiced advanced Database Administration (DBA) concepts and solved hands-on challenges on HackerRank covering Database Security (DCL) and Data Definition Language (DDL).

### 🚀 Key Technical Concepts

#### 1. User Access & Security (DCL)
* **Role-Based Access Control (RBAC):** Created custom roles, granted specific system/object privileges, and assigned roles to users to enforce the Principle of Least Privilege.
* **Privilege Delegation:** Explored passing privileges with GRANT options and managed database authentication/passwords safely.

#### 2. Schema Management & Table Alteration (DDL)
* **Table Mutation:** Executed `ALTER TABLE` operations including adding, dropping, and modifying columns.
* **Optimization:** Used `SET UNUSED` for efficient column removal in large tables without locking resources during peak hours.

#### 3. Advanced Constraint Management
* **Constraint Lifecycle:** Practiced adding, enabling, disabling, dropping, and cascading constraints.
* **Deferred Evaluation:** Handled transaction-level validation using `DEFERRABLE` constraints (`INITIALLY DEFERRED` vs. `INITIALLY IMMEDIATE`) to allow temporary constraint violations within atomic transactions.

### 💡 Insight
Using `SET UNUSED` instead of directly dropping columns on large production databases is a crucial DBA practice to avoid performance degradation. Understanding deferrable constraints allows for seamless complex bulk insertions where relational dependencies are resolved at commit time rather than statement time.
