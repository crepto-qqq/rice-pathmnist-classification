# Recorded results and interpretation

The values below come from committed coursework notebooks and CSVs. Public-export checks did not retrain the models or rerun every hyperparameter search.

## Rice classification

The notebook records ten-fold cross-validation accuracy of approximately 93.86% for logistic regression and 92.64% for Gaussian naive Bayes. The best recorded holdout accuracy among the tuned models is 94.29%, shared by AdaBoost, gradient boosting and SVM. Cross-validation and holdout scores are different estimators and should not be directly treated as one leaderboard.

The original implementation fits mean imputation and MinMax scaling before splitting the data and before cross-validation. Distributional information from the evaluation rows therefore enters preprocessing. The preserved results demonstrate the coursework workflow but are not leakage-free estimates. A fresh, more rigorous comparison would fit preprocessing only on each training fold, inside a Pipeline; no corrected scores are claimed here.

## PathMNIST coursework experiments

| Model | Saved test accuracy | Saved macro-F1 | Source |
| --- | ---: | ---: | --- |
| Random forest | 0.655625 | 0.6204136563 | [rf_final_results.csv](../A2/rf_final_results.csv) |
| MLP | 0.538375 | 0.5023059747 | [mlp_final_results.csv](../A2/mlp_final_results.csv) |
| CNN | approximately 0.7542 | approximately 0.7436 | Final evaluation in [CNN notebook](../A2/a2-code-group217.ipynb) |

The CNN values are reported at the precision shown in the saved output. The course selection has 32,000 training images and 8,000 test images; the former is split into 25,600/6,400 training/validation rows. The models classify nine categories of 28 x 28 RGB images.

These figures are not official MedMNIST benchmark results because the dataset split differs. The exact reconstruction of the course subset is not specified by the repository. They are educational image-classification experiments, not validation of a clinical application.

### Search versus final training

CNN search evaluates eight configurations on a fixed 6,000-image training subset, for at most five epochs per candidate. The selected model is trained on the full training split with early stopping, and the saved run records ten training epochs. Its search validation macro-F1 of 0.5395 and final test macro-F1 of 0.7436 use different data and training budgets. Their difference is not an isolated improvement attributable to one architectural change.

The selected MLP uses hidden layers of 256 and 128 units with ReLU, a nine-unit softmax output, Adam at learning rate 0.001, batch size 64, a maximum of 20 epochs, and validation-based early stopping. Its final CSV records 19 epochs. The CSV and notebook metrics agree, but their timing values differ, so the timing records should be treated as separate runs.

RF, MLP and CNN were developed with different training budgets and search spaces. No repeated-seed confidence intervals, statistical significance or controlled runtime/hardware comparison is established here. Model rankings refer only to the saved runs.

## What was checked for this release

See [VALIDATION.md](VALIDATION.md) for notebook/schema checks, saved-output consistency and bounded runtime tests. These checks establish that the preserved code and model constructors work on small inputs; they do not reproduce the full saved experiment scores.
