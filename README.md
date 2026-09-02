# COMP5318 Assignment 1 - Rice Classification

## Project Overview

This repository is used for COMP5318 Assignment 1: Rice Classification.

The assignment requires us to preprocess the provided rice dataset, implement and evaluate 8 classifiers, perform hyperparameter tuning for selected models, and write a short reflection and discussion.

## Assignment Requirements

### Data Preprocessing

Use `rice-final2.csv` and complete the following preprocessing steps:

1. Replace missing values (`?`) with the mean value of each column using `SimpleImputer`.
2. Normalize feature values to `[0, 1]` using `MinMaxScaler`.
3. Convert class labels:
   - `class1 -> 0`
   - `class2 -> 1`
4. Print the first 10 rows of the processed dataset.
5. Do not hard-code the number or names of features.

The code must also work with datasets that have a different number of features.

---

## Classifiers

We need to evaluate 8 classifiers.

### Part 1 - Cross-validation without Hyperparameter Tuning

- Logistic Regression
- Naive Bayes

Requirements:

- Use 10-fold Stratified Cross-Validation.
- Use:

```python
cvKFold = StratifiedKFold(
    n_splits=10,
    shuffle=True,
    random_state=0
)