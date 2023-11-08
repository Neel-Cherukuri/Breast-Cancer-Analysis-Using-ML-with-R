# Breast-Cancer-Analysis-Using-ML-with-R

**Author:** Neelima  
**Date:** 2023-04-23

## Overview

This project focuses on building predictive models to classify breast cancer tumors as benign or malignant. The code includes various steps, such as data loading, exploration, preparation, modeling, and evaluation, to achieve this goal.

## Prerequisites

Before running the code, ensure you have the following prerequisites:

### R Installation

- R should be installed on your system. You can download it from [here](https://cran.r-project.org/mirrors.html).

### Required R Packages

Install the following R packages using the `install.packages()` function in R:

```R
install.packages(c(
  "tidyverse", "caret", "glmnet", "pROC", "corrplot", "ggplot2", "Hmisc", "randomForest",
  "gbm", "nnet", "rpart", "rpart.plot", "kknn", "cluster", "mice", "readr", "e1071",
  "lme4", "caretEnsemble", "skimr", "plotly", "table1", "mboost", "MLmetrics", "parallel",
  "iterators", "DT", "foreach", "gganimate", "gifski", "formatR", "gridExtra", "grid",
  "vcd", "knitr", "corrplot", "ggcorrplot", "scales", "ROCR", "PRROC"
))
```

## Data Loading

The code loads the breast cancer dataset from an external source using the following URL:

```R
url <- "https://drive.google.com/uc?id=1fgt_sIS2V6COS_E-I6n-wx7UTG5taCsz"
breast_cancer <- read.csv(url)
```

## Data Exploration

Data exploration is a crucial step in understanding your dataset. The code provides the following exploratory analyses:

### Summary Statistics

The `summary()` function displays summary statistics for each column in the dataset.

### Data Types

Using `sapply()`, the code prints the data type of each column.

### Scatter Plot

A scatter plot is generated to visualize the relationship between the "Radius Mean" and "Texture Mean" variables.

### Histograms

Histograms are created for each continuous variable to visualize their distributions.

### Box Plots

Box plots are generated for each numeric variable to identify outliers.

### Correlation Matrix

A correlation matrix is calculated to measure the relationships between numeric variables and displayed as a correlation plot using `corrplot`.

## Data Preparation

Data preparation is essential for modeling. The code performs the following steps:

### Target Variable Transformation

The "diagnosis" variable is transformed into a factor with levels "Benign" and "Malignant."

### Data Normalization

Numeric predictor variables are standardized using Z-score normalization.

## Data Modeling

Three machine learning models are trained on the prepared data:

### Random Forest

A Random Forest model is trained using the `randomForest` package. Hyperparameters like the number of trees (`ntree`) and the number of variables randomly sampled at each split (`mtry`) are specified.

### Generalized Linear Model (GLM) via glmnet

A GLM model is trained using the `glmnet` package. Cross-validation is used to select the optimal regularization parameter (`lambda`) with Lasso penalty (`alpha = 1`).

### Gradient Boosting Machine (GBM) with caret

A GBM model is trained using the `gbm` package with cross-validation and parameter tuning.

## Model Evaluation

The code evaluates the performance of the trained models using the following metrics:

### Confusion Matrices

Confusion matrices are calculated for each model to measure accuracy, precision, recall, and other classification metrics.

### ROC Curves

Receiver Operating Characteristic (ROC) curves are generated to visualize model performance.

### Variable Importance (Random Forest)

For the Random Forest model, variable importance plots are created to identify the most important predictors.

### Model Comparison

Accuracy values for all three models are extracted, and a data frame comparing the accuracies is created. The best-performing model is identified and displayed.

## Conclusion

This project aims to predict breast cancer malignancy using machine learning techniques. The GBM model demonstrates good performance in classification tasks, as supported by evaluation metrics. Further analysis and fine-tuning of models can be explored to improve predictions.

