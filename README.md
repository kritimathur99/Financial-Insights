# FinSight — Financial Analysis Dashboard

> **Real-time insights into transactions, customers, and risk** | Power BI · DAX · Power Query

<img width="1409" height="794" alt="Screenshot (95)" src="https://github.com/user-attachments/assets/9d0a6793-768a-413c-a0ef-bcf776efadb2" />

<img width="1382" height="758" alt="Screenshot (97)" src="https://github.com/user-attachments/assets/36642638-e4bf-4808-95e8-4891b1dfd861" />

---

## The Business Problem

Financial institutions processing thousands of daily transactions struggle to answer three critical questions quickly:
- Which customer segments and regions are actually driving revenue?
- How reliable is our transaction processing — and where is it failing?
- Are we growing, or are YoY trends masking underlying problems?

This dashboard was built to answer all three — in a single view.

---

## Key Findings

| Finding | Insight |
|---|---|
| **₹137.53M** total transaction volume in 2025 | +1.41% YoY growth — modest but positive |
| **Retail segment dominates** at ₹76M | 3x higher than Premium (₹26M) — mass market is the core revenue engine |
| **Maharashtra leads** all states at ₹22M | Karnataka (₹16M) and Gujarat (₹15M) follow — 3 states drive ~38% of total revenue |
| **85.4% transaction success rate** | 10.4% failed, 4.2% pending — 1 in 7 transactions is not completing successfully |
| **Loan EMI is the highest-fee transaction type** at ₹64K fees | Despite being only 2.8K transactions — highest revenue-per-transaction type |
| **Male customers contribute 52.8%** vs Female 47.2% | Near-equal split — no significant gender-based revenue skew |
| **Transaction volume dipped -0.57% YoY** | Revenue grew but volume fell — average transaction value is increasing |

---

## Dashboard Architecture

### Page 1 — Executive Overview
A high-level financial performance summary for business stakeholders.

**KPIs (with YoY comparison):**
- Total Transaction Amount — ₹137.53M (+1.41%)
- Total Transactions — 14.94K (−0.57%)
- Avg Transaction Value — ₹9.20K (+1.98%)
- Total Fees Collected — ₹216.94K (−0.17%)
- Total Taxes Applied — ₹39.04K (−0.26%)

**Visuals:**
- Monthly revenue trend (Jan–Dec seasonality)
- Transaction status breakdown (Success / Failed / Pending)
- Revenue by customer segment (Retail, Premium, SME, Corporate, Wealth)
- State-wise revenue bar chart
- Transaction type matrix (Amount, Fees, Taxes, Volume per type)
- Gender-based revenue donut chart

### Page 2 — Transaction-Level Detail
Row-level drill-down for auditing, reconciliation, and operational monitoring.

**Columns:** Transaction ID · Date · Customer Name · Type · Status · Gender · Segment · Amount · Fees · Taxes

**Use cases:** Failed transaction investigation · customer-level audit · fee reconciliation

---

## Interactive Filters

| Filter | Options |
|---|---|
| Year | 2024, 2025 (YoY comparison enabled) |
| Dynamic Metric | Total Amount / Fees / Taxes / Transactions |
| Occupation | All segments |
| Category | All transaction types |

---

## DAX Measures

```
Total Revenue = SUM(Transactions[Amount])
Avg Transaction Value = DIVIDE([Total Revenue], [Transaction Count])
YoY Growth % = DIVIDE([Current Year Revenue] - [Previous Year Revenue], [Previous Year Revenue])
Transaction Success Ratio = DIVIDE(COUNTROWS(FILTER(Transactions, Transactions[Status] = "Success")), [Transaction Count])
Segment Contribution % = DIVIDE([Segment Revenue], [Total Revenue])
Total Fees = SUM(Transactions[Fees])
Total Taxes = SUM(Transactions[Taxes])
```

---

## Tools Used

| Tool | Purpose |
|---|---|
| Power BI Desktop | Dashboard development and visualization |
| Power Query | Data cleaning, null removal, type standardization |
| DAX | KPI calculations and time-intelligence measures |
| Excel / CSV | Data source |

---

## Data Preparation

- Removed null and blank values across all key fields
- Standardized transaction type and segment categories
- Validated date formats for accurate time-intelligence calculations
- Built optimized data model with defined table relationships

---

## Business Recommendations

1. **Investigate the 10.4% failed transaction rate** — this is a significant operational leak. Identifying whether failures cluster around specific transaction types, segments, or time periods could recover meaningful revenue.
2. **Double down on Retail segment** — at ₹76M it is 3x Premium. Loyalty and retention programs here will have the highest ROI.
3. **Prioritize Maharashtra, Karnataka, Gujarat** — these 3 states contribute ~38% of revenue. Region-specific campaigns and product offerings could accelerate growth.
4. **Loan EMI fee optimization** — highest fees-per-transaction type. Marginal rate adjustments here have outsized revenue impact.
5. **Monitor the volume decline (−0.57%)** — revenue grew but transaction count fell. Investigate whether this is customer churn, consolidation, or a shift to higher-value transactions.

---

## Skills Demonstrated

`Power BI` `DAX` `Power Query` `Data Modeling` `Financial Analytics` `KPI Development` `Time Intelligence` `Business Intelligence` `Dashboard Design` `Data Storytelling`

---

## Project Context

Built to simulate a real-world financial analytics platform used in banking, fintech, and enterprise finance. Dataset covers 14,940 transactions across customer segments, states, and transaction types for FY2025.



