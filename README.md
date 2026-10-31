# Churn Analysis & Customer Intelligence: OTT Subscription Platform

## Business Problem
In the competitive OTT market (Netflix, Hotstar, Prime), retention is critical. This project identifies **who** churns, **why** they churn, and **when** the danger zone occurs, using customer, subscription and support data.

## Tech Stack
Python · SQLite (`sqlite3`) · pandas · NumPy · matplotlib · seaborn · Jupyter

## Dataset
SQLite database `customer_churn` with 3 related tables (joined on `customerid`):

| Table | Key columns |
|---|---|
| `db_customer` | customerid, country, state, gender, dob, interests |
| `db_subscription` | subscription_start_date, plan_type, contract_type, cancellation_date, cancellation_reason, monthly_charges, cltv, churn_score |
| `db_support` | complaint_date, escalations, csat_score, comment |

## Workflow
1. Connect SQLite to Python (`sqlite3` + pandas)
2. Import data with SQL queries and joins
3. Clean data (data types, renaming, nulls, QC checks)
4. Feature engineering (tenure, churn flag, customer age, risk tiers)
5. EDA (group by, pivot tables, aggregation)
6. Visualization (matplotlib, seaborn)
7. Insights and recommendations

## KPIs Calculated
Churn rate · Retention rate · Churn by plan / state / contract type · ARPU · Average tenure · Revenue at risk (churn_score > 70) · Escalation rate · Avg complaints per customer · Escalation-to-churn correlation

## Key Findings
- Overall churn **28.6%** | retention **71.4%**
- Monthly contracts churn at **55.6%** vs **8.3%** for annual, about **6.7x higher**
- Churn is concentrated in the **Basic plan**
- Peak churn in **Sep 2024**; most affected state: **Karnataka**
- Average tenure: **1,451 days**
- Revenue loss from churn: **18%** | CLTV lost: **2,047**

## Recommendations
- Investigate the Karnataka and Sep 2024 spike (pricing, tech issues, complaints)
- Migrate monthly subscribers to annual contracts
- Prioritise High/Medium churn-risk customers by CLTV and proactively contact them
- Track competitor activity, since cancellation reasons include competitor switching

## How to Run
```bash
git clone https://github.com/<your-username>/ott-churn-analysis.git
cd ott-churn-analysis
pip install -r requirements.txt
jupyter notebook notebooks/churn_analysis.ipynb
```
> Update the database path in the notebook to `../data/customer_churn.db`.

## Author
**<Your Name>** · [LinkedIn](<your-link>)
*Project guided by the tutorial from Rishabh Mishra.*
