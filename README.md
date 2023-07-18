# Module 20 Credit Risk Analysis Report

## Overview of the Analysis

The purpose of the analysis was to evaluation a couple of logistial regression models to see how well they predict customer loan worthiness based on loan size, interest rate, borrower income, debt to income ratio, number of credit accounts, derogatory marks and total debt.

Data was separated into the target variable and the feature variables and then split to do create a train_test split.
A logistric regression model was created using LogisticRegression, the test portion of the the original data was fit on the model, and predictions were made.
Predictions were compared against actual values by generating a balanced_accuracy_score, a confusion_matrix and a classification_report.

It was noted that the value_counts of healthy loan to high-risk loan are quite unbalanced with a ratio of 75036 to 2500.
Random over sampling (RandomOverSampler from imblearn.over_sampling) was used with a miniority sampling strategy to bring the two classes into balance.
The same logistical regression model and evaluation was done on the over sampled data.

## Results

The results were as follows:

* Logistical Regression with the Original Data:
  * This model has a 94% **balanced accuracy score**. There are much fewer high-risk loans than healthy loans so a balanced accuracy score is more reliable.
  * For healthy loans the **precision score** is nearly 100% (more accurately, 99.57%), meaning 99.57% of the loans predicted to be healthy loans actually are.
  * Of all the actually healthy loans, the model predicts almost 100% of them (99.64%). This is the **recall score**.
  * For high-risk loans, the **precision score** is 87%, and the **recall score** is 89% 


* Logistical Regression with Oversampled Data:
  * This model has a 99.59% **balanced accuracy score**.
  * For healthy loans the **precision score** is nearly 100% (more accurately, 99.51%), meaning 99.51% of the loans predicted to be healthy loans actually are.
  * Of all the actually healthy loans, the model predicts almost 100% of them (99.98%). This is the **recall score**.
  * For high-risk loans, the **precision score** is 87%, and the **recall score** nearly 100% (99.68%). 

## Summary

Logical Regression with over sampling performs better than logical regression without over sampling. While the healthy loans predict at nearly the same levels in both models, high-risk loan recall is greatly improved (99.68% vs. 89%) with over sampling.
This improvement is significant because it greatly reduces the number of high-risk loans that would be inadvertently made. High-risk loan precision isn't with oversampling but it's much more important to avoid making risky loans than it is to make a loan to all credit-worthly customers.
