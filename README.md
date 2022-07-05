![Bankruptcy Header](https://github.com/thegrandblooms/dsc-phase-2-project-v2-3/blob/68f06f1770bb0b4f79a4c7864f9349ed9b9a39a2/Graphics/price_map_header.jpg)
# Bankruptcy Prediction - Flatiron Data Science, Phase 3 Project
Author: Blake McMeekin

## Overview

This is the Q3 project for Flatiron School, with the main focus being Logistic regression, XGBoost, and Random Forest classifiers being incorporated into a professional level analysis and presentation. The goal was to create a predictive model to interpret 95 different features of real financial data from the Taiwan stock exchange to determine which companies were most likely to be financially insolvent. The resulting XGBoost model performed with 98.5% accuracy on unseen test data.

Additional features of this notebook include balancing data with a significant class imbalance using SMOTE oversampling, and hyperparameter tuning with cross-validation.

## Business Problem

Bankruptcy has tons of business implications, and better predicting bankruptcy can inform company partnerships, investments, and strategy. From Wikipedia, "Bankruptcy is a legal process through which people or other entities who cannot repay debts to creditors may seek relief from some or all of their debts." By identifying markers of bankrupt companies, we may be able to

## Data

Our data consists of 6819 rows and 96 columns of financial indicators from the Taiwan Stock Exchange, cleaned and provided by the Taiwan Economic Journal. Our data spans from 1999 to 2009, and is provided cleaned and normalized in entirely numeric columns. Our data has a heavy class-imbalance, with only about 3% of the data representing our prediction target of bankrupt companies.

## Methods

To build our predictive model, we do a stratified train-test split and upsample the training set using SMOTE. Then fit Logistic, XGBoost, and Random Forest models to the training data. These baselines are then iteratively improved upon using grid or random searches to tune hyperparameters and find best performing combinations.

## Validation

For model validation, much of the analysis was built around F1 scores, since accuracy is not a good measure of performance for class-imbalanced data. If we simply said every company was not bankrupt, we would have a 96.8% accurate model, since only 3.2% of companies in the dataset are bankrupt. F1 scores measure how well we can predict our target, ignoring class imbalance.

## Findings

Our most accurate model (XGBoost) had a 98.5% accuracy, while the model with the highest recall (identifying the highest number of bankrupt companies) successfully flagged more than 80% of bankrupt companies (Logistic Regression.) 

The three most important predictive features for bankruptcy were the features:
- “Fixed Assets to Assets” - Strong positive correlation
- “Accounts Receivable Turnover” - Strong negative correlation
- “Interest-bearing debt interest rate” - Strong negative correlation

## Conclusions

The biggest business recommendations from this were to use Logistic Regression to flag companies, and to use XGBoost for a confident confirmation. Our logistic Regression model found 80% of the bankrupt companies, but had many false positives. XGBoost was very precise, but missed about 50% of bankrupt targets.

Bankruptcy is not entirely predicted by numbers. We can make estimations that are a lot better than chance, but bankruptcy was not 100% correlated with the available financial data.

## Next Steps

- More data about the data
Is the financial data from the same time as the bankruptcy label? Can we identify where the noise or discrepancy is coming from? Is it a consequence of the way the data was processed before our analysis?

- More Feature Engineering
Are a high number of features reducing the accuracy of our models?

- More Access to Raw Data
There may be more information which could be recovered.

## For more information

See the full analysis in the Jupyter Notebook or review the presentation in the pdf.

For additional information, contact Blake McMeekin at blakemcme@gmail.com

## Repository Structure
```
├── Bankruptcy_Detection
│   └── data.csv
├── Graphics
├── Phase 3 Project - Bankruptcy Prediction.pdf
├── README.md
└── Bankruptcy Prediction.ipynb
```
