# 🗄️ SQL Analytics: BI Metric Reconciliation & Loyalty/Retail KPIs

Today, I performed an end-to-end data reconciliation between the **Qlik** BI reporting layer and raw SQL query outputs for an enterprise retail partner, validating 15+ core commercial and loyalty KPIs.

### 🚀 Key Technical Deliverables

#### 1. Metric Reconciliation Workflow
* **Qlik vs. SQL Cross-Validation:** Verified that front-end dashboard figures aligned with underlying database aggregations to eliminate data discrepancies and ensure dashboard reporting accuracy.
* **Granularity & Filter Alignment:** Ensured date intervals, currency conversions, and transaction status filters in SQL matched Qlik's internal set analysis logic.

#### 2. Calculated Commercial & Loyalty KPIs
* **Volume & Revenue Metrics:** Total Revenue (`SUM(amount)`), Transaction Count, Daily Average Revenue, Daily Average Transaction Volume, and Average Basket Size / AOV (`Total Revenue / Total Orders`).
* **Customer Acquisition & Activity:** Total Customers, Purchasing/Active Customers, Daily Average New Member Acquisition Rate, and Purchase Frequency (`Total Orders / Unique Active Customers`).
* **Discount & Loyalty Dynamics:** Total Discount Amount, Points Earned vs. Points Burned (Redeemed), Burn-to-Earn Ratio, and Payment Method to Total Turnover Ratio.

### 💡 Insight
Reconciling raw SQL outputs with BI dashboards like Qlik is a vital quality assurance step. Discrepancies often uncover hidden dashboard filters (e.g., handling returns, excluded test accounts, or specific date boundary offsets) rather than underlying database anomalies.
