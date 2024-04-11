# HR Analytics: Attrition Rate Prediction

In this project, we act as **HR Consultant who is responsible for solving Human Resources (HR) problems** in one of our client companies, namely PT Goras. PT Goras is a company engaged in the pharmaceutical industry, in Indonesia.

## Problem Statement

- Currently, PT Goras is losing money due to the issue of **massive employee attrition** due to retirement and resignation reasons.
- It cause in many projects being delayed or even unfinished, requiring replacement employees for vacant positions.
- **The attrition rate at PT Goras was 16.4%**, while the effective attrition rate in the Indonesian pharmaceutical industry in 2017 was 6.3%.

## Goal

**Reduce the attrition rate by 2–3% annualy** based on a realistic decision between us and PT Goras.

## Dataset Preview

The dataset have 35 columns and 1470 rows, which is contains:

- **Classification Target**: Attrition (yes/no)
- **Attributes**:
    - **Employee Profile**: Age, Gender, Marital Status, Education, etc.
    - **Employee Status**: Job Role, Job Level, Department, Years at Company, etc.
    - **Employee Performance**: Performance Rating, Job Involvement, Job Satisfaction, Overtime, etc.

Dataset Source: [Kaggle | Employee Attrition - Fictional dataset on HR Employee attrition and performance](https://www.kaggle.com/patelprashant/employee-attrition)

## Machine Learning Modeling

Before doing the modeling, we did preprocessing to clean the data and did some feature engineering.

There are 6 algorithm that we use for modeling:
- Logistic Regression (LRegression)
- K-Nearest Neighbor (KNN)
- Support Vector Machine (SVM)
- Decision Tree (DTree)
- Random Forest (RForest)
- XGBoost

We also apply 3 dataset scenarios to each algorithm:
- Dataset 1 contains 84 features
- Dataset 2 contains 20 features
- Dataset 3 contains 24 features

## Model Evaluation

The model were evaluated with **F1-Score**.

| # | Model (Dataset) | Accuracy | Precision | Recall | F1 | AUC |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | LRegression (1) | 0.848921 | 0.761905 | 0.50000 | 0.603774 | 0.726636 |
| 2 | SVM (1) | 0.791367 | 0.548387 | 0.53125 | 0.539683 | 0.700204 |
| 3 | LRegression (3) | 0.726619 | 0.434783 | 0.62500 | 0.512821 | 0.691005 |
| 4 | LRegression (2) | 0.676259 | 0.385965 | 0.68750 | 0.494382 | 0.680199 |
| 5 | XGBoost (1) | 0.805755 | 0.619048 | 0.40625 | 0.490566 | 0.665742 |
| ... | ... | ... | ... | ... | ... | ... |
| 16 | XGBoost (2) | 0.748201 | 0.400000 | 0.18750 | 0.255319 | 0.551694 |
| 17 | XGBoost (3) | 0.762590 | 0.454545 | 0.15625 | 0.232558 | 0.550088 |
| 18 | DTree (3) | 0.697842 | 0.272727 | 0.18750 | 0.222222 | 0.518984 |

## Simulation

We tried to predict 1470 employees using a predefined model (logistic regression). The result is the possibility of employees who have the potential to leave the company as many as 190 people (12.93%). It is assumed that previously did not know the truth.

We perform several treatments for employees who have the potential to leave the company based on the predicted results.

- For employees with a performance rating above average (excellent and outstanding) which means they deserve to be promoted, but have not received promotions for years, the value transformation that is carried out is:
    - adding one job level, ex: from 1 to 2, 2 to 3, etc. 
    - changing the years since last promotion attribute to 0 
- For employees who work overtime, but have low job involvement, the value transformation that is carried out is:
    - adding one job involvement, ex: from 1 to 2, 2 to 3, etc.

![alt text](https://github.com/faisalydth/hr-analytics/blob/main/fig/hr-analytics-simulation.jpg "HR Analytics Simulation")

If this scenario can be realized, the attrition rate will decrease from 12.93% to 9.73% (a decrease of 3.2%), where the remaining 143 employees have the potential to leave the company.

## Recommendation

- Pay attention to the performance of your employees who are entitled to a promotion
- Improve the job involvement of your employees:
    - Coaching or mentoring, and give positive feedback
    - Employee involvement programs
    - Open-communication and suggestion boxes
- Reduce your employee's overtime:
    - Cross-train your employees 
    - Try flexible work schedules

## Team Behind the Project

In completing our studies at [Rakamin Academy](https://rakamin.com/), we formed a team called **Pythagoras**.

| Role | Name | Email | LinkedIn URL |
| --- | --- | --- | --- |
| **Leader** | **Faisal A. Yudithia (me)** | **first.yudithia@gmail.com** | **https://www.linkedin.com/in/faisal-yudithia** |
| Member | Anoga R. Novaldi | anogarizky@gmail.com | https://www.linkedin.com/in/anoga-rizkynovaldinovaldi |
| Member | Danienta Aqmarrazza | danienta.a@gmail.com | https://www.linkedin.com/in/danientaaqmarrazza |
| Member | Esa Tauran | esatauran@gmail.com | https://www.linkedin.com/in/esatauran |
| Member | Jehezkiel N. Krispratomo | jehezkielnatan@gmail.com | https://www.linkedin.com/in/jehezkielnatan |

Our mentor: Ade Irawan (https://www.linkedin.com/in/ade-irawan-5042a411b/)