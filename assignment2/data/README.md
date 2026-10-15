# Dataset Setup

The assignment dataset is intentionally not stored in Git because the supplied
archive is approximately 94 MB and generated Git history would make every clone
unnecessarily large.

Each team member should download `Assignment2Data-1.zip` from Canvas and extract
it so that the repository has this local structure:

```text
assignment2/
|-- COMP5318-assignment2-template-notebook-1.ipynb
`-- Assignment2Data/
    |-- X_train.npy
    |-- y_train.npy
    |-- X_test.npy
    `-- y_test.npy
```

The supplied notebook already loads data from these relative paths. Do not
commit the archive or extracted arrays.
