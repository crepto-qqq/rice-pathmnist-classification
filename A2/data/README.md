# PathMNIST data setup

The four coursework arrays are not included in this public repository. If you have authorised access to the original course materials, extract the supplied archive into:

```text
A2/
  Assignment2Data/
    X_train.npy
    y_train.npy
    X_test.npy
    y_test.npy
```

Run each A2 notebook with `A2/` as the working directory. Expected image shape is `(N, 28, 28, 3)`; label arrays are one-dimensional integers from 0 to 8.

The saved experiments use a course-specific 32,000/8,000 train/test selection, with the 32,000 training rows split into 25,600/6,400 for training/validation. The original [MedMNIST PathMNIST dataset](https://medmnist.com/v2) has different default splits. Downloading the public dataset is useful for a new experiment, but it is **not** a drop-in reconstruction of the saved course results: subset selection, exact rows and split composition are not fully specified here.

Do not substitute the official default split and claim to have reproduced the same test scores. Keep any new experiment and its results clearly labelled. Data attribution and the source licence are described in [THIRD_PARTY_NOTICES.md](../../THIRD_PARTY_NOTICES.md).

The repository ignores these arrays, local datasets, checkpoints and model files. Saved notebook outputs can be viewed without downloading or training anything.
