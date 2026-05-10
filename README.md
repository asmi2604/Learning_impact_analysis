# Learning Outcome Prediction & Content Effectiveness Analysis

## Problem
EdTech platforms lose students to dropout without early warning systems.
By the time a student fails, the intervention window has closed.

## Dataset
Open University Learning Analytics Dataset (OULAD)
- 32,593 students across 22 modules
- 7 relational tables joined in Python
- 10M+ daily clickstream interaction logs

## Approach
1. Merged 7 CSV tables into one master dataframe 
2. Engineered 7 behavioural features from raw clickstream data:
   - early_engagement_ratio, clicks_per_day, content_variety, 
     consistent_submitter, high_engager, low_early_engagement, late_registration
3. Built Logistic Regression (AUC: 0.85) and Random Forest (AUC: 0.89)
4. Identified top predictors using feature importance analysis

## Key Findings
- Assessment submission rate is the #1 predictor of passing (importance: 0.18)
- Students who withdrew mid-module are the #2 signal — detectable weeks early
- Early engagement ratio is NEGATIVELY correlated with passing (-0.29):
  students who front-load clicks but don't sustain fail more often
- Content variety (accessing different resource types) positively predicts success

## Business Recommendations
1. Flag students with <50% assessment submission rate by Week 4 for tutor outreach
2. Build a withdrawal prediction alert — unregistration signals are detectable early
3. Redesign modules with consistently low pass rates (content issue, not student issue)
4. Reward content variety — nudge students who only use one resource type

## Results
| Model               | Accuracy | F1   | ROC-AUC |
|---------------------|----------|------|---------|
| Logistic Regression | 0.79     | 0.79 | 0.85    |
| Random Forest       | 0.82     | 0.81 | 0.89    |

## Dashboard
[Tableau Public link ]

## Tech Stack
Python · pandas · scikit-learn · matplotlib · seaborn · Tableau Public
