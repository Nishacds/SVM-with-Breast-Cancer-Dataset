# SVM-with-Breast-Cancer-Dataset

#  Breast Cancer Detection using Support Vector Machine (SVM)

This project uses Support Vector Machine (SVM) models to classify breast tumors as **Malignant (M)** or **Benign (B)** based on diagnostic measurements. The dataset used is from the [Breast Cancer Wisconsin Dataset](https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+(Diagnostic)).


##  Dataset

- **Filename:** Breast Cancer.csv
- **Target:** diagnosis (M = malignant, B = benign)
- **Features:** 30 numerical features including:
  - radius_mean, texture_mean, perimeter_mean, area_mean, smoothness_mean, etc.


## Project Objectives

- Load and preprocess the breast cancer dataset.
- Train **SVM** classifiers with different kernels: linear, rbf.
- Visualize performance using **confusion matrix**, **classification report**, and **decision boundaries**.
- Perform **hyperparameter tuning** (C, gamma) using **GridSearchCV**.
- Use **k-fold cross-validation** to evaluate the best model.


##  Exploratory Data Analysis (EDA)

- Checked for missing values and dataset info.
- Converted diagnosis from categorical (M, B) to numeric (1, 0).
- Removed irrelevant columns (ID, unnamed).
- Plotted class distribution:

![Class Distribution](images/class_distribution.png)

##  Model Training and Kernels

###  Linear Kernel

- Fast and interpretable.
- Works well with linearly separable data.

###  RBF (Radial Basis Function) Kernel

- Suitable for nonlinear data.
- Captures complex relationships between features.

>  Polynomial kernel was tested but not included in final tuning due to overfitting or lower performance.


##  Hyperparameter Tuning (RBF Kernel)

Performed using **GridSearchCV**:

| Parameter | Values Tested                  |
|-----------|--------------------------------|
| `C`       | 0.1, 1, 10, 100                |
| `gamma`   | 0.001, 0.01, 0.1, 1, 10         |

> **Best Parameters:** C=10, gamma=0.01  
> **Best CV Accuracy:** ~90%


##  Cross-Validation

- **5-Fold Cross Validation**
- Final tuned model achieved:  
  **Accuracy = 90% ± 3%**


##  Visualizations

###  Decision Boundaries

Used two features: radius_mean, texture_mean

| Kernel Type | Visualization |
|-------------|---------------|
| Linear      | ![Linear](images/decision_linear.png) |
| RBF         | ![RBF](images/decision_rbf.png)       |


##  Evaluation Metrics

| Metric        | Value |
|---------------|--------|
| Accuracy      | ~90%   |
| Precision     | High   |
| Recall        | High   |
| F1-Score      | High   |
