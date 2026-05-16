# Learning Outcome Prediction & Content Effectiveness Analysis
[![Python 3.10+](https://img.shields.io/badge/python-3.10%2B-blue.svg)](https://www.python.org/downloads/)
[![Pandas](https://img.shields.io/badge/Pandas-2.0%2B-150458.svg)](https://pandas.pydata.org/)
[![Scikit-Learn](https://img.shields.io/badge/scikit--learn-1.3%2B-F7931E.svg)](https://scikit-learn.org/)
[![Seaborn](https://img.shields.io/badge/Seaborn-0.13%2B-4C72B0.svg)](https://seaborn.pydata.org/)
[![Statsmodels](https://img.shields.io/badge/Statsmodels-0.14%2B-8CAAE6.svg)](https://www.statsmodels.org/)

> Predicting student pass/fail 4+ weeks early using behavioural 
> engagement data — enabling targeted intervention before outcomes are set.

---
## Problem Statement
EdTech platforms globally struggle with student dropout, often identifying 
at-risk students too late to intervene. This project builds a predictive 
model to classify students as likely to pass or fail based on early 
engagement behaviour — giving educators a 4-week intervention window.

---

## Results at a Glance

| Model               | Accuracy | F1 Score | ROC-AUC |
|---------------------|----------|----------|---------|
| Logistic Regression | 79%      | 0.79     | 0.85    |
| Random Forest       | 82%      | 0.81     | **0.89** |

**Top 3 predictors of student outcome:**
1. `assessments_submitted` — #1 signal by far (importance: 0.18)
2. `withdrew` — early withdrawal detectable weeks before it happens
3. `avg_assessment_score` — sustained performance, not just one exam

---

## Dataset
- **Source:** Open University Learning Analytics Dataset (OULAD)
- **Scale:** 32,593 students | 22 modules | 10M+ clickstream events
- **Tables:** 7 relational CSV files joined using pandas
- **License:** CC-BY-SA-4.0 (freely available)

---

## Key Findings

**1. Submission consistency beats raw ability**  
Assessment submission rate was the strongest predictor (importance: 0.18) 
— stronger than scores. Students who submit consistently, even with 
average scores, pass more often than high scorers who miss submissions.

**2. Early engagement ratio is NEGATIVELY correlated with passing (r = -0.29)**  
Counterintuitively, students who front-load clicks in week 1 but don't 
sustain engagement fail more often. Consistency > intensity.

**3. Withdrawal signals are detectable early**  
The `withdrew` flag was the #2 predictor. Unregistration patterns 
are visible in the data weeks before the formal dropout occurs.

**4. Pass rate varies 20%+ across modules**  
Some modules consistently underperform — pointing to content design 
issues, not just student behaviour.

---

Random Forest gave better predictive performance, especially in ROC-AUC, which indicates stronger class separation capability. However, Logistic Regression was more interpretable and helped identify which learning-content features most influenced student outcomes.

---

## Business Recommendations

| Recommendation | Impact |
|---|---|
| Flag students with <50% submission rate by Week 4 | Catches 80%+ of eventual dropouts early |
| Build tutor dashboard with pass probability score | One-click view of at-risk students |
| Redesign high-failure modules | Content fix benefits every future cohort |
| Nudge students accessing only one content type | Content variety predicts success |

---

## Feature Engineering Highlights
7 new features engineered from raw clickstream data:

- `early_engagement_ratio` — % of total clicks in first 14 days
- `clicks_per_day` — quality of daily engagement (not just volume)
- `content_variety` — number of unique content types accessed
- `consistent_submitter` — binary flag for above-median submission rate
- `high_engager` — top 25% by total clicks
- `low_early_engagement` — bottom 25% in first 2 weeks
- `late_registration` — registered after module start date

---

## Tech Stack
`Python` `pandas` `scikit-learn` `matplotlib` `seaborn` `Tableau Public`

---

## Tableau Dashboard
🔗 [Link coming soon]

---

*Project by Asmita Rajendra | [LinkedIn](https://www.linkedin.com/in/asmita-r-5b23691a1/)*



