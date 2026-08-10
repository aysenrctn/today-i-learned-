# 🗄️ SQL Analytics: Customer Performance, Transaction Baselines & TOP-N Slicing

Today, I engineered complex analytical SQL queries to compute customer transaction distributions, monthly spenders, dynamic averages, and cohort metrics.

### 🚀 Key Technical Deliverables
* **Recent Activity Profiling:** Retrieved the latest 100 transaction profiles to evaluate active account behavior.
* **Baseline Deviation Analysis:** Computed the overall corporate transaction average and segmented customers operating above vs. below this baseline (`HAVING transaction_count > (SELECT AVG(...) )`).
* **New Customer Acquisition Tracking:** Filtered new account activations across monthly timeframes to isolate customer acquisition rates.
* **Monthly High-Spender Analysis:** Sliced monthly top-spending accounts and computed TOP-N customer rankings (e.g., top 5 most active customers, top 1 spender) using window functions (`ROW_NUMBER()` / `DENSE_RANK()`).

### 💡 Insight
Using SQL window functions like `DENSE_RANK() OVER (PARTITION BY month ORDER BY total_spend DESC)` allows for seamless monthly top-spender analytics without requiring multiple temporary tables or complex nested loops.
