# 🗄️ Advanced SQL: Data Integrity, Constraints & CTAS

Today, I explored advanced SQL data integrity mechanisms and dynamic table creation techniques using subqueries.

### 🚀 Key Technical Concepts
* **Referential Integrity Actions:** Practiced `ON DELETE CASCADE` (deleting child records automatically) and `ON DELETE SET NULL` (setting foreign key references to NULL upon parent deletion).
* **Domain Integrity:** Applied `CHECK` constraints to enforce business rule validations directly at the column level.
* **CTAS (Create Table As Select):** Utilized subqueries to dynamically instantiate new tables prepopulated with specific query result sets.

### 💡 Insight
Selecting between `CASCADE` and `SET NULL` is a critical architecture choice. `CASCADE` maintains absolute relational hygiene, while `SET NULL` preserves historical transaction logs when parent entities are decommissioned.
