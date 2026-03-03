**SaaS Churn & Revenue Intelligence Project**

End-to-end churn analytics pipeline for a SaaS cybersecurity company, combining SQL data modelling, Tableau BI dashboards, and Python-based predictive modelling to quantify revenue at risk and prioritise retention.

Kaggle Dataset used: [Kaggle Dataset](/2b1295641bb180ca867afac2d927e043?pvs=25)

**Business Objective**

- Build a production-style analytics framework to:

- Identify behavioural and operational drivers of churn

- Quantify revenue exposure from at-risk accounts

- Develop a predictive churn scoring system

- Enable revenue-weighted retention prioritisation

The goal was to move from descriptive reporting (“what happened”) to predictive intelligence (“who is likely to churn next”).

**Architecture & Tools**

SQL → Tableau → Python → Revenue Risk Framework

- SQL – Data modelling, staging layer, aggregation, risk feature engineering

- Tableau – Executive dashboards, KPI design, churn segmentation

- Python (scikit-learn, XGBoost) – Predictive modelling, validation, explainability


**Data Modelling (SQL Layer)**
Output: A master account table used for BI and predictive modelling.

- Designed an analytics-ready data mart from raw relational tables:

- Built staging tables to standardise dates, flags, categorical fields

- Created account-level aggregations for revenue, usage, and support metrics

- Engineered behavioural indicators (downgrades, auto-renew, engagement intensity)

- Implemented rule-based early warning scoring (baseline model)


**Business Intelligence (Tableau)**

- Developed executive dashboards covering:

- Overall churn rate (22%)

- Revenue distribution by plan and industry

- Churn by tenure segment

- Upgrade / downgrade behaviour

- Support performance (SLA, escalations, CSAT)

- Risk-tier segmentation

**Key operational findings:**

- Churn increases with tenure

- Pro downgrades signal pre-churn contraction

- 3.5+ day first response time and 19% escalation rate correlate with churn

- Engagement and product reliability are stronger predictors than demographics

**Predictive Modelling (Python)**

- Built and benchmarked:

- Logistic Regression (baseline)

- Random Forest

- XGBoost (best performance)

**Techniques applied:**

- Feature engineering (tenure, engagement, contract behaviour)

- Handling class imbalance

- Stratified train/test split

- ROC-AUC and Precision-Recall evaluation

- Model comparison & benchmarking

- XGBoost selected for production-style risk scoring due to improved minority-class discrimination.

**Model Explainability**

Used SHAP to:

- Identify systemic churn drivers

- Explain individual account risk predictions

- Translate model outputs into actionable business insights

**Top churn drivers included:**

- Revenue size (ARR / MRR)

- Usage intensity

- Error frequency

- Support load

- Response time

- CSAT

- Tenure

- Geographic segment (France)

**Revenue-at-Risk Framework**

Instead of binary predictions, implemented probability-based scoring:

- Revenue at Risk = P(Churn) × MRR

Demonstrated that a small subset of high-MRR accounts drives disproportionate revenue risk.

**Key Insights**

- Churn is structurally high (22%)

- Retention weakens with tenure

- Downgrades act as early warning signals

- Operational friction materially increases churn probability

- Revenue risk is concentrated among high-value accounts
