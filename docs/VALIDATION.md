# Validation of the public snapshot

Verified on **15 November 2026** against the public checkout after the filtered main and CNN branches were combined.

| Check | Result |
| --- | --- |
| Notebook schema | All four implementation notebooks valid |
| Code-cell syntax | All 60 code cells compiled successfully |
| Stored execution errors | No saved error outputs in the four notebooks |
| A1 preprocessing | Synthetic-input checks passed for mean imputation, scaling, labels and variable feature counts |
| A1 display helper | Short-table printing check passed |
| A2 helpers | Class-distribution and prediction-label conversion checks passed |
| MLP constructor/inference | Real TensorFlow forward pass on two synthetic samples passed; output `(2, 9)`, 636,425 parameters |
| Default CNN constructor/inference | Real TensorFlow forward pass on two synthetic images passed; output `(2, 9)`, 106,089 parameters |
| Saved result consistency | RF/MLP CSV metrics agree with the corresponding notebook output |
| Source fidelity | Current code-cell sources and all 22 embedded image payloads match their committed originals |
| Rice data fidelity | Included CSV matches committed source bytes; all 1,400 rows matched the official dataset's nonmissing features in the provenance audit |

The model outputs were finite and normalised probability vectors. These are constructor/forward-pass checks, not trained-model accuracy tests. The CNN smoke check uses the default 16-filter constructor; it is distinct from the selected 32-filter final model recorded in the notebook.

The runtime checks used Python 3.10.8, TensorFlow 2.21.0, NumPy 2.2.6, pandas 2.3.3 and scikit-learn 1.7.2. Existing notebook functions were extracted for small bounded checks; the notebooks themselves were not rewritten or saved by test execution.

No full notebook, hyperparameter search, model training or complete image-dataset evaluation was rerun. The table of model scores elsewhere in the repository remains based on the original saved runs. Successful schema and forward-pass checks do not establish that every cell can reproduce all prior results in another environment.

The privacy audit examined retained history as well as the current files. Original student identifiers and unredacted home paths were absent; known API-token/private-key checks found no retained matches. Reports and separate course-specification/template files were excluded. See [SOURCE_ORIGIN.md](../SOURCE_ORIGIN.md) for the publication boundary and [RESULTS_AND_LIMITATIONS.md](RESULTS_AND_LIMITATIONS.md) for methodological limitations.
