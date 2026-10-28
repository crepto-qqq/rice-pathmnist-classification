# COMP5318 Assignment 2 - Image Classification

This directory contains the shared work for Assignment 2 using the PathMNIST
dataset. Keep Assignment 2 changes inside this directory so that the completed
Assignment 1 submission remains unchanged in `A1/`.

## Source Materials

- `COMP5318-assignment2-Sem2-2026-2.pdf`: official assignment specification
- `COMP5318-assignment2-template-notebook-1.ipynb`: unmodified notebook template
- `data/README.md`: local dataset setup instructions

The original template is kept unchanged as a reference. Create the group working
notebook from this file when implementation begins, then use the required final
filename before submission.

## Team Responsibilities

| Owner | Primary responsibility |
| --- | --- |
| Member A | Data exploration, preprocessing, validation split, and shared evaluation utilities |
| Member B | First-six-weeks classifier and hyperparameter search |
| Member C | MLP implementation and hyperparameter search |
| Member D | CNN implementation and hyperparameter search |

All members review the final comparison, discussion, conclusion, references,
and submission files. Each member writes their own reflection.

## Working Conventions

1. Create a feature branch from the latest `main` before starting a task.
2. Keep one primary owner for each notebook section to reduce merge conflicts.
3. Do not commit datasets, virtual environments, checkpoints, or trained models.
4. Use fixed random seeds and a shared stratified train/validation split.
5. Keep the supplied test set untouched until final model evaluation.
6. Record every tuning combination, validation result, and runtime.
7. Keep expensive tuning cells independent from final-model cells.
8. Before merging, restart the kernel and run all non-search cells in order.

Suggested branch names include `a2/data-pipeline`, `a2/classical-model`,
`a2/mlp`, and `a2/cnn`.

## Submission Outputs

The final group submission requires three files:

- `A2-report-SID1-SID2-SID3-SID4.pdf`
- `a2-code-SID1-SID2-SID3-SID4.ipynb`
- `a2-code-SID1-SID2-SID3-SID4.pdf`

The report and notebook must both include the required AI acknowledgement.

## MLP Implementation

The MLP implementation is provided in `a2-mlp.ipynb`, including
hyperparameter tuning, final-model training, and evaluation.

### Files

- `a2-mlp.ipynb`: notebook with code, explanations, and saved outputs.
- `mlp_tuning_results.csv`: validation results and runtimes for eight configurations.
- `mlp_final_results.csv`: final test metrics and runtime measurements.

### Setup and execution

Required packages: tensorflow, numpy, pandas, matplotlib, and scikit-learn.

Place the assignment dataset in `A2/Assignment2Data/`, containing
`X_train.npy`, `y_train.npy`, `X_test.npy`, and `y_test.npy`.
The dataset is not included in Git.

Run the notebook from top to bottom. To skip hyperparameter search,
run the setup and Section 1, then the MLP cells in Section 2 and
Section 4. Skip both the search and tuning-plot cells in Section 3.

### Selected configuration

- Hidden layers: 256 and 128 units, with ReLU activation
- Output: 9 units, with softmax activation
- Optimiser: Adam
- Learning rate: 0.001
- Batch size: 64
- Maximum epochs: 20
- Early stopping: validation accuracy, patience 3, best weights restored

### Results

- Best validation accuracy: 53.44%
- Test accuracy: 53.84%
- Test macro F1-score: 0.5023
- Trainable parameters: 636,425

The final MLP was successfully rerun after restarting the kernel
and skipping Section 3, confirming that final training and
evaluation do not depend on the hyperparameter-search cells.