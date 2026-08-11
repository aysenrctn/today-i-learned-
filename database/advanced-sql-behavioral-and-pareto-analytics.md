# 🗄️ Advanced SQL: Behavioral Analytics, Window Functions & Pareto Analysis

Today, I engineered a comprehensive suite of advanced SQL queries to solve complex customer behavior, time-series, and transactional analytics problems.

### 🚀 Key Technical Solutions & Concepts

#### 1. Transaction Sequences & Intervals
* **First & Second Transaction Analysis:** Utilized `ROW_NUMBER() OVER (PARTITION BY customer_id ORDER BY transaction_date)` to isolate each customer's exact 2nd transaction following their first purchase.
* **Interval Between Transactions:** Applied `LEAD()` / `LAG()` window functions alongside `DATEDIFF` to compute the exact calendar days elapsed between consecutive purchases per user.
* **Rapid Repeat Purchases:** Filtered accounts whose 2nd transaction occurred within a 30-day window after their initial onboard date.

#### 2. Advanced Customer Segmentation & Pareto (80/20)
* **Pareto Principle (Top 80% Revenue Drivers):** Computed cumulative spend distribution using `SUM(total_spend) OVER (ORDER BY total_spend DESC)` to dynamically isolate the customer subset generating 80% of total company revenue.
* **Share of Wallet (Revenue Contribution):** Calculated each customer's spend proportion relative to total enterprise revenue (`total_customer_spend / SUM(total_customer_spend) OVER () * 100`).
* **Longest Inactive Customers:** Ranked the top 100 dormant customers with the greatest elapsed time since their last recorded transaction (`MAX(transaction_date)`).

#### 3. Temporal Patterns & Monthly Changes
* **Monthly Spend Variance:** Tracked month-over-month (MoM) spending changes per customer using `LAG(monthly_spend) OVER (PARTITION BY customer_id ORDER BY transaction_month)`.
* **Consecutive Active Months:** Constructed query logic to detect highly engaged accounts making purchases across 3 consecutive calendar months.
* **New Customer Acquisition Rate:** Evaluated the percentage of first-time buyers relative to total active users per month.
* **Volume vs. Spend Correlation:** Cross-analyzed monthly metrics to verify if the highest-frequency customer matched the highest-spending customer within the same month.
* **Fraud / Velocity Monitoring:** Flagged high-frequency transaction activity by filtering accounts executing over 5 purchases within a single calendar day.

### 💡 Insight
Applying window functions like `SUM() OVER ()` for total revenue ratio calculations and `LAG()` for month-over-month variances eliminates the need for expensive subqueries or temporary tables, drastically reducing query execution costs on massive datasets.
