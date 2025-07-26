# Adult Income Prediction Project

**Author:** Leonardo Cofone

## Overview

This project focuses on building a robust machine learning model for predicting whether an individual's income exceeds $50K per year based on census data. The task is a binary classification problem handled using a stacking ensemble approach, which combines multiple classifiers to improve overall performance.

## Dataset

The dataset used is the Adult Income dataset, containing various demographic and employment-related features, with the target variable `income` indicating if income is `<=50K` (0) or `>50K` (1).

## Project Steps

### 1. Data Analysis and Preparation

- Loaded data and handled missing values (represented as "?").
- Converted target labels to binary numeric values.
- Removed duplicate records.
- Checked class imbalance and applied RandomOverSampler to balance classes.
- Split data into training, validation, and test sets with stratification.
- Identified categorical and numerical features.
- Detected skewed numerical features for proper transformation.

### 2. Preprocessing Pipeline

- Built preprocessing pipelines for:
  - Numerical features with skew: median imputation, log transformation, and scaling.
  - Numerical features without skew: median imputation and scaling.
  - Categorical features: most frequent imputation and one-hot encoding.

### 3. Model Training and Evaluation

Trained and evaluated several classifiers using the validation set:

- Logistic Regression (with balanced class weights)
- Gradient Boosting Classifier
- XGBoost Classifier
- Random Forest Classifier (with balanced class weights)

Metrics evaluated include:
- Confusion Matrix
- Precision
- Recall
- F1 Score
- ROC AUC Score

### 4. Stacking Ensemble Model

- Combined the three best base models (Random Forest, XGBoost, Gradient Boosting) in a stacking ensemble.
- Used AdaBoost as the final estimator.
- Performed 5-fold cross-validation during stacking.
- Evaluated stacking model on validation set.

### 5. Final Evaluation on Test Set

- Tested the stacking model on the unseen test set.
- Reported confusion matrix, precision, recall, F1 score, and classification report.

### 6. Threshold Tuning

- Used Youden's J statistic to find the optimal decision threshold on predicted probabilities.
- Adjusted threshold to improve recall while maintaining precision.
- Re-evaluated metrics at the tuned threshold.

### 7. Model Saving

- Saved the final stacking model and tuned threshold using `joblib` for future use.
  
### Author:

**Leonardo Cofone**
Machine Learning & Deep Learning Specialist

Thabk you!!
