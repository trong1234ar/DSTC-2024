# DSTC 2024 | 2nd Place 
My very first step toward a career in Data Science.

# Overview

This repository contains the final code and representations used in the competition, where the **Crazy Chipmunk** team developed machine learning models to predict customer debt repayment behavior and built a Credit Scorecard Model to segment customers, providing tailored solutions for each customer group.

## 1. Business Understanding

### Context
The task is to differentiate between customers who repay their loans on time and those who don't, using various features from the dataset. The imbalance between these two classes requires careful handling to avoid biased predictions.

### Goal
- Segment customers into five distinct groups based on credit scores, allowing tailored insights and recommendations for each segment.

### Success Criteria
- The credit score must effectively differentiate between two customer groups, with defaulters receiving lower scores than non-defaulters.

## 2. Data Understanding

## 3. Data Preparation
- **Data Cleaning**: Checked for missing values, duplicated values, invalid values, etc.
- **EDA:** Explored the dataset and uncover the insights to differentiate 2 customer groups.
- **Feature Engineering:** Created new features to better distinguish between customers who repay and those who don't.
- **Feature Selection:** Applied Correlation Analytics, Information Value to remove redundant columns, enhancing model's processing time.
- **Feature Scaling:** Scaled data for model to learn and understand the problem better.

## 4. Modeling
1. **Gradient Boosting**
2. **XGBoost**
3. **CatBoost**
4. **LightGBM**
5. **Logistic Regression**
6. **Random Forest**

The **Gradient Boosting** and **XGBoost** models performed best based on the ROC-AUC and F1-Score.

### Results

| Model                   | ROC-AUC | F1 Score |
|--------------------------|---------|----------|
| Gradient Boosting         | 0.810   | 0.869    |
| XGBoost                   | 0.808   | 0.868    |
| CatBoost                  | 0.808   | 0.868    |
| LightGBM                  | 0.807   | 0.868    |
| Logistic Regression       | 0.805   | 0.864    |
| Random Forest             | 0.805   | 0.868    |
| Baseline Logistic Regression       | 0.738   | 0.78    |


**Gradient Boosting** showed the highest performance, with good generalization on the test set, indicating that the model is not overfitting.

### Credit Scorecard Model

This project includes a **Credit Scorecard Model** developed to calculate a credit score for each customer based on their likelihood of loan repayment. The scorecard model follows these steps:

1. **Feature Selection and Weighting**: 
   - Key features from the dataset, such as repayment history, loan amount, income level, and other financial indicators, are selected based on their predictive power.
   - Each feature is assigned a weight (or coefficient), often derived from logistic regression, reflecting its importance in predicting repayment likelihood.

2. **Score Calculation**:
   - The credit score for each customer is calculated using a formula that aggregates weighted feature scores. A typical formula might look like:

     ```
     Credit Score = α + Σ (wᵢ * xᵢ)
     ```

     where `α` is a base score, `wᵢ` represents the weight for feature `xᵢ`, and `xᵢ` is the feature value for a specific customer.

3. **Score Scaling and Segmentation**:
   - The resulting score is scaled to a 1000 range to ensure consistency.
   - Customers are then segmented into distinct groups (e.g., five groups) based on score ranges, enabling targeted solutions for each group.

## 5. Result


