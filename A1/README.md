# A1 — Rice classification

This notebook compares eight classical classifiers on a 1,400-row, seven-feature subset derived from UCI's Rice (Cammeo and Osmancik) dataset. It handles missing values, rescales features, applies stratified cross-validation and searches model parameters.

## Files

- [ml-project-group217.ipynb](ml-project-group217.ipynb): implementation and saved outputs.
- [clean_dataset/rice-final2.csv](clean_dataset/rice-final2.csv): supplied derivative dataset, with attribution below.
- [requirements.txt](requirements.txt): pandas and scikit-learn dependencies.

## Run locally

From the repository root, create and select a Python environment. In PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r A1/requirements.txt
```

Open the notebook in Jupyter or a notebook-capable editor using that interpreter. Ensure its working directory is `A1/`: the notebook first looks for `rice-final2.csv`, then `clean_dataset/rice-final2.csv`. Run cells in order. Parameter-search cells can take longer than preprocessing or the two baseline classifiers.

The preprocessing function treats the last column as labels (`class1` and `class2`) and the preceding columns as features. It fills `?` cells with feature means and rescales features to [0, 1]. The unverified historical `test-before.csv` fixture is not distributed.

## Methods

- Logistic regression and Gaussian naive Bayes: stratified ten-fold cross-validation.
- KNN, decision tree, random forest, AdaBoost, gradient boosting and SVM: model-specific parameter search and recorded holdout results.
- Reusable functions for preprocessing and printing arbitrary-width feature tables.

## Evaluation limitation

The original notebook fits imputation and scaling on the complete dataset before cross-validation and the train/test split. This can leak distributional information. The implementation and saved outputs are preserved as coursework evidence; the recorded scores should not be described as leakage-free generalisation estimates.

An improved future experiment would put imputation/scaling inside a scikit-learn Pipeline fitted separately within each training fold. That methodological change has not been silently applied to the original results.

## Dataset attribution

Original dataset: **Rice (Cammeo and Osmancik)**, UCI Machine Learning Repository, [DOI 10.24432/C5MW4Z](https://doi.org/10.24432/C5MW4Z), licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). See [full attribution](../THIRD_PARTY_NOTICES.md).

The included course subset has 1,400 rows, renamed labels (`class1`/Cammeo, `class2`/Osmancik), and 29 missing feature cells. All nonmissing feature values matched the official dataset in a provenance comparison. The original course column spelling is retained; the exact subset-selection/missing-value procedure is not established.
