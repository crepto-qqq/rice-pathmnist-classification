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
