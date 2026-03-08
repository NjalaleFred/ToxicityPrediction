# Toxicity Prediction of Molecules

## Project Overview

This project predicts whether a molecule is Toxic or Non-Toxic based on molecular descriptors. It uses machine learning with feature selection and nested cross-validation to ensure robust performance.

Type: Binary Classification

Features: 1200+ molecular descriptors

Target: Class → Toxic / Non-Toxic

## Pipeline Workflow

Raw Data
   │
   ├─ EDA → understand dataset & target distribution
   │
   ├─ Preprocessing
   │    ├─ Encode target
   │    ├─ Remove constant features
   │    └─ Scale features
   │
   ├─ Pipeline
   │    ├─ Feature selection (SelectKBest)
   │    └─ Random Forest classifier
   │
   └─ Nested Cross-Validation
        ├─ Inner loop: hyperparameter tuning
        └─ Outer loop: model evaluation
        

# Project Workflow Summary

## 1. Exploratory Data Analysis (EDA):

* Examine dataset shape, data types, missing values, and statistical summaries.

* Visualize target distribution and feature correlations to understand patterns and relationships.

## 2. Preprocessing:

* Encode the target variable (Toxic/NonToxic) into numerical labels.

* Remove constant features to reduce redundancy.

* Scale features to normalize the data for machine learning models.

## 3. Feature Selection + Random Forest Pipeline:

* Use SelectKBest to select the most relevant molecular descriptors.

* Train a Random Forest classifier on the selected features.

* Feature selection is applied inside the pipeline to prevent data leakage.

## 4. Nested Cross-Validation with Hyperparameter Tuning:

* Inner loop: tune hyperparameters (k, n_estimators, max_depth) using GridSearchCV.

* Outer loop: evaluate model performance on unseen data for unbiased accuracy and F1-score.

* Ensures robust evaluation, especially with imbalanced classes.

## Results

* Nested CV Accuracy: Mean accuracy across outer folds

* Fold-wise metrics: Precision, Recall, F1-score for Toxic and Non-Toxic classes


# Insights: Detects imbalance and identifies which features contribute most to toxicity classification.


## Future Enhancements

* Experiment with ensemble models (Random Forest + XGBoost)

* Apply SMOTE or oversampling for better minority class detection

* Analyze feature importance to identify key molecular descriptors influencing toxicity


## License

MIT License © Fred Njalale
