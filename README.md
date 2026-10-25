# Machine Learning Basics Course

Welcome to the **Machine Learning Basics Course**! This course is designed to provide you with a solid foundation in key machine learning algorithms and techniques. Each topic in the course is covered in a dedicated module, with explanations, code examples, and exercises to reinforce your understanding.

## Table of Contents

1. [Introduction](#introduction)
2. [Course Structure](#course-structure)
3. [Requirements](#requirements)
4. [Installation](#installation)
5. [Modules](#modules)
6. [Neural Networks](#neural-networks)
7. [Data](#data)

## Introduction

This course is designed for beginners who are new to machine learning. It will walk you through the fundamental concepts and algorithms that are widely used in the industry. By the end of this course, you should be able to understand, implement, and apply these algorithms to real-world problems.

The modules cover supervised and unsupervised learning. Neural networks are covered separately.

## Course Structure

Modules 01–07 and HS2026 Neural Networks Lectures 1-4 use the same three-notebook structure:

- `<topic>_concept.ipynb`: the idea in plain language, the most important formulas, a small worked example and provided demonstration code.
- `<topic>_exercise.ipynb`: guided practice with one data set. Data preparation and plots are provided; fill a few marked code gaps and interpret the results.
- `<topic>_solution.ipynb`: the same steps with complete code and short explanations.

Read the concept notebook first. Run the exercise cells from top to bottom, replacing each `None` marked with a `# TODO` comment with the expression requested above its cell. These gaps are intentional; the affected cells cannot be used until completed. Write one or two sentences for each interpretation question, then use the solution to check your work.

Basic Python knowledge is enough: variables, arithmetic, selecting data columns and calling a function. Loops for plots, cross-validation and small parameter comparisons are supplied. Mathematical symbols are explained beside the formulas; lengthy derivations are not required.

Tabular data sets and the Fashion-MNIST reference images are stored in [00_Data](00_Data/). Run each notebook from its own directory. Most module notebooks use `../00_Data/`; the HS2026 lecture notebooks use `../../../00_Data/`. Lecture 3 uses the separate official MNIST digits dataset, downloaded and cached by Keras on first use under `~/.keras/datasets/`.

## Requirements

To follow along with this course, you will need a GitHub account and knowledge about how to work with GitHub Codespaces and Visual Studio Code (IDE).

## Installation

**Fork the following repository into your GitHub account:**

https://github.com/mario-gellrich-zhaw/python_machine_learning_basics

Create a new GitHub Codespaces environment based on the fork. The Codespace uses Python 3.11 and installs all required
packages automatically (from `requirements.txt`) when it is created.

**Working on your own computer instead:** install Python 3.11 and then the required packages with

```bash
pip install -r requirements.txt
```

## Modules

Each exercise notebook works with one data set.

| Folder | Data | Core topics |
|---|---|---|
| [01_Model_Training_Evaluation](01_Model_Training_Evaluation/) | Car fuel consumption 2025 | ML paradigms and history; loss, objective and metric; MSE/RMSE/MAE; train/test; 5-fold CV; under-/overfitting and bias–variance |
| [02_Linear_Regression](02_Linear_Regression/) | Zurich rental apartments | OLS; coefficients; simple and multiple regression; R²/RMSE; confidence and prediction intervals; assumptions and residual diagnostics; maximum likelihood and gradient descent |
| [03_Regression_Trees_Ensembles](03_Regression_Trees_Ensembles/) | Car fuel consumption 2025 | SSE splits and leaf means; tree parameters and pruning; bagging and OOB; random forest and permutation importance; boosting; CV comparison |
| [04_Logistic_Regression_Evaluation](04_Logistic_Regression_Evaluation/) | Swiss avalanche accident records | Linear score and sigmoid; log-loss; confusion matrix; accuracy, precision, recall, F1 and FPR; fixed thresholds and error costs; ROC/AUC; input availability |
| [05_Classification_Trees_Ensembles](05_Classification_Trees_Ensembles/) | Titanic | Gini split; tree rules and leaf probabilities; pruning; random forest and boosting; fully provided small GridSearchCV example |
| [06_kNN_Naive_Bayes_SVM](06_kNN_Naive_Bayes_SVM/) | Titanic | Neighbours and distance; scaling; a small k comparison; Bayes calculation and categorical Naive Bayes; SVM margin, support vectors, C and kernels |
| [07_Clustering_PCA](07_Clustering_PCA/) | Car fuel consumption 2025 | Unsupervised learning; a k-means update; scaled car features; elbow plot and cluster interpretation; dendrogram; PCA outlook and explained variance |

The worked calculations, guided exercises and interpretation questions cover the learning objectives of each module. Topics such as cross-validation, grid search and plotting have complete example code so that students can focus on the model and its results.

The avalanche notebook models fatal outcomes **among recorded accidents** with burial information available after an accident. It does not predict avalanche occurrence before a trip. Titanic examples use rows with known age and fare for simple preparation; excluding missing rows may affect representativeness.

**Further reading:** Li, H. (2024). *Machine Learning Methods*. Springer. – scikit-learn user guide: https://scikit-learn.org/stable/user_guide.html

## Neural Networks

The folder [08_Neural_Networks](08_Neural_Networks/) contains notebooks on simple neural networks, multi-layer perceptrons and convolutional neural networks.

**HS2026 Part I: From Logistic Regression to a Neural Network** follows the concept/exercise/solution structure:

- [Concepts](08_Neural_Networks/HS2026/lecture1/logistic_regression_to_neural_network_concept.ipynb): sigmoid outputs, hidden ReLU units, shared inputs, baselines, validation and business costs, with provided small demonstrations.
- [Exercise](08_Neural_Networks/HS2026/lecture1/logistic_regression_to_neural_network_exercise.ipynb): one email dataset, supplied preparation and plots, four marked code gaps and interpretation questions.
- [Solution](08_Neural_Networks/HS2026/lecture1/logistic_regression_to_neural_network_solution.ipynb): the same numbered steps with complete code, short answers and self-check criteria.

These notebooks accompany SW07 Lecture 1. One worked step fits its 10-minute demonstration slot; the complete guided exercise is separate practical work. Both models use the same 16 prepared features and fixed historical partitions. Settings and thresholds are selected on validation data, not test results. Optional XGBoost, model persistence, embeddings and deeper-network comparisons are not prerequisites for the core notebooks; additional packages and authorized raw text are needed for the relevant extensions.

**HS2026 Part II: How Neural Networks Learn** uses the same structure in `08_Neural_Networks/HS2026/lecture2/`:

- [Concepts](08_Neural_Networks/HS2026/lecture2/how_neural_networks_learn_concept.ipynb): loss, backpropagation, simultaneous updates, checkpoints, learning rate and regularization, with provided small demonstrations.
- [Exercise](08_Neural_Networks/HS2026/lecture2/how_neural_networks_learn_exercise.ipynb): five activities, four marked code gaps, supplied training/plotting helpers and interpretation prompts without saved answers or outputs.
- [Solution](08_Neural_Networks/HS2026/lecture2/how_neural_networks_learn_solution.ipynb): matching activities with complete code, worked answers and self-check criteria.

These accompany SW07 Lecture 2. Activities 1-3 are alternative 10-minute demonstrations; choose only one for a 45-minute lecture. Capacity and regularization are optional practicals. The full sequence takes about 60 minutes plus execution time. Real-data comparisons use the same 1,000 training and 1,200 validation emails, training-fitted scaling and an 80-epoch budget. Learning-rate results use final models; capacity and regularization results use best-validation-BCE checkpoints. The test set remains untouched.

**HS2026 Part III: Neural Networks for Image Processing** uses the same structure:

- [Concepts](08_Neural_Networks/HS2026/lecture3/cnn_mnist_concept.ipynb): shared filters, ReLU, pooling, tensor shapes, parameter counts and evaluation boundaries, with a small worked filter example.
- [Exercise](08_Neural_Networks/HS2026/lecture3/cnn_mnist_exercise.ipynb): MNIST digits, supplied loading/training/plots, four marked code gaps and seven interpretation prompts.
- [Solution](08_Neural_Networks/HS2026/lecture3/cnn_mnist_solution.ipynb): matching steps with completed code, worked answers and self-check criteria.

These accompany SW07 Lecture 3. One worked filter or prepared-results discussion fits the 10-minute demonstration slot; the full sequence is a separate approximately 60-minute practical plus execution. Both models use the same 54,000 training and 6,000 validation images, seed 7, Adam, batch 128 and five-epoch budget. A training-prior baseline and a raw-pixel linear softmax model precede the CNN comparison. Validation log loss selects between final-epoch models; the 10,000 official test images remain outside selection. The CNN retains two 3 x 3 convolutions (32/64 filters), pooling and dropout 0.5. Keras downloads MNIST on first use; subsequent runs use its cache. Use the separate [pinned TensorFlow environment](08_Neural_Networks/HS2026/requirements-cnn-mnist.txt), not the PyTorch environment below.

**HS2026 Part IV companion: Learned Representations and Transfer Learning** uses the same structure:

- [Concepts](08_Neural_Networks/HS2026/lecture4/transfer_learning_concept.ipynb): learned representations versus autoencoders, frozen encoders, supervised heads, label budgets and cache validity.
- [Exercise](08_Neural_Networks/HS2026/lecture4/transfer_learning_exercise.ipynb): Fashion-MNIST, supplied feature extraction/training/plots, four marked code gaps and seven interpretation prompts.
- [Solution](08_Neural_Networks/HS2026/lecture4/transfer_learning_solution.ipynb): matching steps, completed code, worked answers and self-check criteria.

These accompany the transfer-learning example in SW07 Lecture 4. This is supervised feature reuse, not an autoencoder or a replacement for the lecture's unsupervised-learning content. Compare guessing, a raw-pixel linear head and a frozen ResNet-18 plus a new head on five Fashion-MNIST categories. Keep the same balanced 5,000 training, 5,000 validation and 5,000 official test images; validation chooses best-accuracy head checkpoints and the pipeline, never test results. One prepared comparison fits the 10-minute lecture demonstration; the full sequence is a separate approximately 60-minute practical plus feature extraction. Use [the pinned PyTorch requirements](08_Neural_Networks/HS2026/requirements-neural-networks-transfer-learning.txt). Dataset downloads are disabled and images must be present under `00_Data/FashionMNIST/raw/`; pretrained weights have a separate first-use download. Generated features are cached in `00_Data/resnet18-features/`. Prepare caches before class, and do not interpret the target training-label budget as the total annotation or pretraining cost.

- **Introduction:** Overview of neural networks and their biological inspiration.
- **Mathematical Foundations:** Understanding perceptrons, activation functions, backpropagation, and gradient descent.
- **Implementation:** Building simple neural networks from scratch and using frameworks like TensorFlow or PyTorch.
- **Practical Applications:** Applying neural networks to classification and regression tasks.
- **Exercises:** Exercises to build, train, and evaluate neural networks.

- **Mathematical Foundations:** Li, H. (2023). Machine Learning Methods. Springer Nature.
- **In scikit-learn:** https://scikit-learn.org/stable/modules/neural_networks_supervised.html

## Data

The tabular data sets and Fashion-MNIST images are stored in the folder [00_Data](00_Data/), so no Kaggle account or dataset download is needed for those examples. Lecture 3's separate MNIST digits dataset is downloaded by Keras on first use. The script
[00_Data/prepare_data.py](00_Data/prepare_data.py) documents how the files were created from the original sources and can be
used to re-create the downloadable tabular data (`python 00_Data/prepare_data.py`). Fashion-MNIST preparation uses the separate command below. The CSV files in the repository are the reference versions
used in the notebooks; the original sources may change or become unavailable over time.

| File | Content | Source |
|---|---|---|
| `rental_apartments_canton_zh.csv` | 774 rental apartments in the canton of Zurich (rooms, living area, rent, municipality data) | ZHAW course data (web-scraped rental listings) |
| `titanic.csv` | 891 passengers of the Titanic | [Kaggle](https://www.kaggle.com/datasets/yasserh/titanic-dataset) |
| `car_fuel_consumption_2025.csv` | 701 new car models of model year 2025 (make, model, vehicle class, engine size, cylinders, transmission, fuel type, fuel consumption city/highway/combined in L/100 km, km per litre, CO₂ emissions) | Natural Resources Canada, [Fuel consumption ratings](https://open.canada.ca/data/en/dataset/98f1a129-f628-4ce4-b24d-6f16bf24dd64); [Open Government Licence – Canada](https://open.canada.ca/en/open-government-licence-canada) |
| `avalanche_accidents_switzerland.csv` | 4'188 avalanche accidents in Switzerland since 1970/71 (location, terrain, danger level, activity, persons caught, buried and killed) | WSL Institute for Snow and Avalanche Research SLF, [EnviDat](https://www.envidat.ch/dataset/avalanche-accidents-in-switzerland-since-1970-71); [SLF terms of use](https://www.slf.ch/en/services-and-products/data-and-monitoring/slf-data-service.html) |
| [FashionMNIST/raw/](00_Data/FashionMNIST/raw/) | 60,000 official training images and 10,000 test images, each 28 x 28 grayscale pixels, with ten-category labels in four uncompressed IDX files | Zalando Research, [Fashion-MNIST](https://github.com/zalandoresearch/fashion-mnist) |

### Fashion-MNIST image data

The transfer-learning notebook reads the provided files with `torchvision.datasets.FashionMNIST(root=DATA_ROOT, download=False)`, where `DATA_ROOT` is the repository's `00_Data` directory. It preserves the official train/test boundary and selects its balanced 5,000 training, 5,000 validation and 5,000 test examples from five categories with seed 7.

To recreate only the reference image files, install the transfer-learning dependencies and run from the repository root:

```bash
python 00_Data/prepare_data.py --fashion-mnist
```

The preparation command downloads the official archives, checks their published checksums through torchvision, and extracts them into `00_Data/FashionMNIST/raw/`. It does not regenerate the other datasets. The notebook itself does not download images; pretrained ResNet-18 weights are a separate model dependency.
