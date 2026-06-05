# Operation Clearwater — Fraud Detection & Risk Intelligence Dashboard

**Power BI · DAX · Data Modelling · Risk Analytics**

A Data with Danny cohort project. You are a Junior Data Analyst at NorthAxis Bank. The compliance hotline just recorded a 340% spike in fraud complaints. The CFO has escalated to the Board Risk Committee. They convene in 72 hours. Your Power BI dashboard is the only thing standing between the bank and a regulatory investigation.

---

## The Scenario

NorthAxis Bank is a mid-sized commercial bank operating across 12 countries, serving over 80,000 customers through branch, ATM, mobile banking, and web channels. The bank processes an average of 400,000 transactions per month.

In Q3 2024, internal audit flagged an estimated **$2.3M in suspicious outflows** concentrated in a 6-week window. The CFO has escalated to the Board Risk Committee. You have been granted read access to the bank's Gold layer data warehouse.

Your job: build a Power BI dashboard that answers the board's questions before that meeting.

> *"We need to know who, what, when, and where — before that board meeting. Your analysis is the only thing standing between us and a regulatory investigation."*
> — CFO, NorthAxis Bank

---

## Flagged Signals (Unverified)

| Signal | Description |
|--------|-------------|
| Velocity anomalies | Multiple high-value transactions within minutes from the same account |
| Geographic mismatch | Transactions from countries inconsistent with customer profiles |
| Off-hours activity | Unusual transaction volumes between 1AM and 4AM on digital channels |
| Merchant concentration | Disproportionate spend clustered in high-risk merchant categories |

---

## Your Deliverables

### 1. Transaction Overview & Baseline KPIs — Beginner
Volume, value, and channel breakdown. Establish what normal looks like before hunting anomalies. Build your headline KPI cards, monthly trend line, and channel split.

### 2. Anomaly Detection & Velocity Checks — Intermediate
Flag rapid repeat transactions, off-hours spikes, and amount outliers. This is where the fraud signal starts to emerge. Use DAX to calculate time between transactions and flag accounts that break normal patterns.

### 3. Customer Risk Profiling — Intermediate
Build behavioral baselines per customer. Surface deviations from their own transaction history. An account that normally spends $200/transaction and suddenly hits $8,000 is a signal.

### 4. Merchant & Channel Risk Scoring — Advanced
Rank merchants and channels by their concentration of flagged and suspicious activity. Which channel is the fraud entering through? Which merchants are being used as conduits?

### 5. Fraud Risk Scoring Model — Advanced
Build a composite risk score per customer using NTILE bucketing and weighted flags. Output: an actionable watchlist of accounts to freeze, ranked by risk score.

### 6. Executive Risk Report — Advanced
Board-ready summary page. Estimated total exposure, top accounts to freeze, channels to restrict, and recommended immediate actions. One page. Decision-ready.

---

## Definition of Success

A Risk Intelligence analyst can open the dashboard, select a date range, and immediately know:

- Total flagged exposure in that period
- Which accounts carry the highest composite risk score
- Which channels and merchants are implicated
- The top 10 accounts recommended for immediate freeze

Every answer the board needs is available within two clicks.

---

## Dashboard Requirements

Your dashboard must include:

- [ ] Headline KPI cards — total transactions, flagged transactions, estimated exposure, fraud rate
- [ ] Monthly trend with anomaly spike visible
- [ ] Channel breakdown (Mobile, Web, ATM, Branch)
- [ ] Off-hours activity heatmap or time distribution visual
- [ ] Customer risk score table with freeze recommendations
- [ ] Merchant risk ranking
- [ ] Executive summary page — board-ready, one screen
- [ ] Slicers for date range, channel, and risk tier
- [ ] Row Level Security (RLS) — analysts see only their assigned accounts

---

## Data Model

You will connect Power BI to the NorthAxis Bank Gold layer. The star schema includes:

| Table | Type | Description |
|-------|------|-------------|
| fact_transactions | Fact | One row per transaction |
| dim_customer | Dimension | Customer profiles and KYC status |
| dim_account | Dimension | Account types, balances, status |
| dim_merchant | Dimension | Merchant categories and risk ratings |
| dim_location | Dimension | Country, region, high-risk flag |
| dim_date | Dimension | Full date spine |

---

## Repository Structure

```
operation-clearwater-powerbi/
│
├── Dataset/
│   └── NorthAxis_Gold_Layer.xlsx       ← Connect Power BI here
│
├── Project Brief/
│   └── Operation_Clearwater_Brief.pdf  ← Full instructions
│
├── Dashboard/
│   └── Operation_Clearwater.pbix       ← Your completed dashboard goes here
│
├── Report/
│   └── Executive_Summary.pdf           ← Your board summary goes here
│
└── README.md
```

---

## Success Criteria

- [ ] Data model connected and relationships correct
- [ ] All 6 deliverables addressed in the dashboard
- [ ] Composite risk score measure written in DAX
- [ ] Executive summary page is board-ready — one screen, no scrolling
- [ ] RLS configured for at least one role
- [ ] A non-technical board member can read the dashboard and take action

---

## Tools Required

- Power BI Desktop (free)
- Microsoft Excel or SQL Server for the dataset

---

## How to Submit

1. Fork this repo or create your own public repo
2. Upload your completed `.pbix` file and executive summary
3. Update the README with your name, cohort number, and a screenshot of your dashboard
4. Share the link in the DwD community

**The goal is not just to complete the project. The goal is to build something you can show a recruiter or client.**

---

## Part of the DwD Curriculum

This is one of two Power BI projects in the **Data with Danny** cohort program — a structured 4-month curriculum covering Excel, SQL, Python, Power BI, Statistics, and AI integration.

**Cohort 9 starts June 25, 2026** → [nestuge.com/mzlik606d](https://nestuge.com/mzlik606d)

---

*Data with Danny · Power BI Project 1 · datawithdany@gmail.com*
