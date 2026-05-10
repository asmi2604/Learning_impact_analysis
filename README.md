# 🎓 # Learning Outcome Prediction & Content Effectiveness Analysis

> Predicting student pass/fail 4+ weeks early using behavioural 
> engagement data — enabling targeted intervention before outcomes are set.

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

## Problem Statement
EdTech platforms globally struggle with student dropout, often identifying 
at-risk students too late to intervene. This project builds a predictive 
model to classify students as likely to pass or fail based on early 
engagement behaviour — giving educators a 4-week intervention window.

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

## How to Reproduce
```bash
# 1. Clone the repo
git clone https://github.com/asmi2604/EdTech-student-outcome-prediction

# 2. Open notebook in Google Colab
# File → Open → GitHub → paste repo URL

# 3. Download dataset from Kaggle
# kaggle datasets download -d rocki37/open-university-learning-analytics-dataset

# 4. Run all cells in order
```

---

## Tableau Dashboard
🔗 [Link coming soon — publish at public.tableau.com]

---

*Project by Asmita Rajendra | [LinkedIn](your-linkedin-url)*



