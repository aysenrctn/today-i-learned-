# 🗄️ Database Engineering: DML Operations, Triggers & Ingestion Patterns

Today, I structured executable SQL/PL-SQL code snippets for my technical presentation, deep-diving into DML mechanisms, upsert strategies, and trigger workflows.

### 🚀 Key Technical Implementation Patterns

#### 1. Advanced Ingestion & Upsert (`MERGE`)
* Implemented idempotent data synchronization patterns using the Oracle `MERGE` statement:
```sql
MERGE INTO target_table t
USING staging_table s
ON (t.record_id = s.record_id)
WHEN MATCHED THEN
  UPDATE SET t.amount = s.amount, t.updated_at = SYSDATE
WHEN NOT MATCHED THEN
  INSERT (record_id, amount, created_at)
  VALUES (s.record_id, s.amount, SYSDATE);
