# A2 — PathMNIST image classification

The public snapshot brings together the random-forest and MLP work from the school main branch and the CNN work from its separate committed `a2/cnn` branch.

## Choose a model

| Model | Notebook | Supporting results |
| --- | --- | --- |
| Random forest | [a2-random_forest.ipynb](a2-random_forest.ipynb) | [Tuning CSV](rf_tuning_results.csv), [final CSV](rf_final_results.csv) |
| MLP | [a2-mlp.ipynb](a2-mlp.ipynb) | [Tuning CSV](mlp_tuning_results.csv), [final CSV](mlp_final_results.csv) |
| CNN | [a2-code-group217.ipynb](a2-code-group217.ipynb) | Search and final-evaluation outputs inside the notebook |

The original CNN filename is retained for traceability. It is the committed CNN-focused notebook, not a claim that an uncommitted final combined submission was imported.

## Environment and data

The [requirements.txt](requirements.txt) file comes from the CNN branch and provides pinned versions of TensorFlow, NumPy, Matplotlib, pandas, scikit-learn, ipykernel and nbclient. The original CNN environment was Python 3.10 on Windows with CPU TensorFlow.

From the repository root, for example in PowerShell:

```powershell
py -3.10 -m venv .venv-a2
.\.venv-a2\Scripts\python.exe -m pip install -r A2/requirements.txt
```

Select this interpreter in a notebook-capable editor. JupyterLab itself is not included in the pinned requirements; install it separately if using that interface.

Obtain the supplied arrays as described in [data/README.md](data/README.md). Start notebooks with **`A2/` as the working directory**. They load `Assignment2Data/X_train.npy`, `y_train.npy`, `X_test.npy`, and `y_test.npy`.

Images must be 28 x 28 RGB arrays. The notebooks expect one-dimensional integer labels 0 through 8. The saved experiments used 32,000 supplied training images and 8,000 test images; 20% of the supplied training set was reserved through a stratified split for validation.

## Execution

Inspect the saved outputs before launching new training. Run setup, data loading, validation, preprocessing, and model-definition cells first. Section 3 performs hyperparameter search; it is intentionally separate from the final-model cells. When skipping search, also skip its result-plot cells, then run the final-model section in sequence. Read each notebook's headings because model-specific cell layouts differ.

CNN search uses eight configurations, a fixed 6,000-image training subset and a maximum of five epochs per candidate. Final CNN training uses the full 25,600-image training split, validation-based early stopping and a separate test evaluation. The MLP and RF use their own parameter searches. Model-search validation scores and final test scores are not a controlled before/after comparison.

No datasets, trained weights or checkpoints are bundled. This publication did not rerun all searches or retrain every model. [Validation](../docs/VALIDATION.md) records the checks actually performed.

## Results and attribution

See the [recorded comparison and limitations](../docs/RESULTS_AND_LIMITATIONS.md). These are coursework-split results, not official MedMNIST benchmark numbers or clinical performance claims. Data and embedded example-image outputs are attributed in [THIRD_PARTY_NOTICES.md](../THIRD_PARTY_NOTICES.md); model authorship is recorded in [CONTRIBUTIONS.md](../docs/CONTRIBUTIONS.md).
