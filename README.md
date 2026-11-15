# 机器学习分类模型对比：水稻与病理图像

**Machine Learning Classification Benchmarks — Rice & PathMNIST**

本项目包含两组完整的课程实验代码：使用八种传统分类器完成水稻品种分类，以及对病理图像进行随机森林、MLP 与 CNN 分类实验。内容涵盖缺失值处理、特征缩放、分层划分、交叉验证、超参数搜索、模型训练与多指标评估。

This public portfolio contains the team's working notebooks, retained plots and experiment outputs, rather than only a project description. It combines the committed school main branch with Tian Liao's committed CNN branch. Contributions and dataset provenance are documented separately.

## Explore the implementation

| Experiment | Main techniques | Notebook |
| --- | --- | --- |
| Rice classification | Logistic regression, Gaussian naive Bayes, KNN, decision tree, random forest, AdaBoost, gradient boosting, SVM | [A1 notebook](A1/ml-project-group217.ipynb) |
| PathMNIST random forest | Flattened image features, parameter search, multiclass evaluation | [RF notebook](A2/a2-random_forest.ipynb) |
| PathMNIST MLP | Dense neural network, early stopping, parameter search | [MLP notebook](A2/a2-mlp.ipynb) |
| PathMNIST CNN | Two convolution/pooling blocks, dropout, parameter search and final evaluation | [CNN notebook](A2/a2-code-group217.ipynb) |

**Technology:** Python, pandas, NumPy, scikit-learn, TensorFlow/Keras, Matplotlib and Jupyter notebooks.

## Recorded image-classification results

These are **saved coursework results**, not fresh training runs performed for this public release.

| Model | Test accuracy | Macro-F1 | Evidence |
| --- | ---: | ---: | --- |
| Random forest | 65.56% | 0.6204 | [Recorded metrics](A2/rf_final_results.csv) |
| MLP | 53.84% | 0.5023 | [Recorded metrics](A2/mlp_final_results.csv) |
| CNN | approximately 75.42% | 0.7436 | Final-evaluation outputs in the [CNN notebook](A2/a2-code-group217.ipynb) |

The supplied coursework data use 32,000 training images, split into 25,600 training and 6,400 validation images, plus 8,000 test images. These are not the standard MedMNIST benchmark splits. Training budgets and model-selection protocols differ; this table is a record of the team's experiments, not a controlled architecture benchmark. See [results and limitations](docs/RESULTS_AND_LIMITATIONS.md).

## Run and inspect

- [Rice setup](A1/README.md): the attributed 1,400-row course subset is included, so this experiment can be run locally.
- [PathMNIST setup](A2/README.md): obtain the authorised coursework arrays separately and place them as described in [data setup](A2/data/README.md). Saved outputs remain viewable without those arrays.
- [Validation record](docs/VALIDATION.md): separates static checks, small runtime checks and original stored results.

Open notebooks in a notebook-capable editor or Jupyter environment, selecting the environment with the corresponding requirements installed. Each notebook must run with its own assignment directory as the working directory.

## Tian Liao's contribution

The committed history identifies Tian's work on A1 data preprocessing, logistic regression and naive Bayes, model-integration work, and A2 CNN implementation and experiments. The other classifiers, shared image-data preparation, RF and MLP retain their team authorship. See [contribution evidence](docs/CONTRIBUTIONS.md).

## Provenance and updates

The original [school repository](https://github.sydney.edu.au/tlia0262/comp5318-assignment1) remains the upstream reference and may require university access.

- School main: `d8c0f3eb064bfef40cda342c26d2115bf10f0389` (29 October 2026).
- School CNN branch: `b81d6f25b90be75abc16820454c413778e79cd71`.
- Public snapshot: **15 November 2026**.

The public copy retains 37 filtered source-history commits from the 41-commit union of those branches. Student identifiers and local home paths were removed; separate course specification/template files and private report binaries were excluded. Development history retains names, dates and team attribution. The school working tree was not changed.

This is a **manual snapshot**, not an automatically synchronising fork. See [source record](SOURCE_ORIGIN.md), [publication notice](NOTICE.md), and [dataset and starter-code attribution](THIRD_PARTY_NOTICES.md).
