# Comparison of Classifiers
The objective of this exercise is to compare the performance of the following classifiers: K Nearest Neighbor, Logistic Regression, Decision Trees, and Support Vector Machines.

We do this by comparing their performance against a sample data set provided. The data set is from a direct-marketing campaign carried out on behalf of a bank, with the objective to get customers to sign up for a long-term bank deposit. The target feature - yes or no - indicated whether or not a customer that received one or more phone calls from a bank representative signed up for the deposit. The purpose of the accompanying study was to increase efficiency of directed campaigns for long-term deposit subscriptions by reducing the number of contacts to do.

The modeling and analysis is done in [this notebook](./practical_application_3.ipynb).

## Overview
The analysis begins by establishing a baseline model, which essential returns the majority class (no by 88%). Next, a series of classifiers are developed and optimized later comparing the performance.

### Modeling Approach
A logistic regression model is established using all default parameters. It achieves just slightly higher performance than the simple, baseline, model.

### Comparing Non-Optimized Classifiers
The performance from the logistic regression is compared to the performance of 3 classifiers - K Nearest Neighbor, Decision Trees, and Support Vector Machines. Train Time, Train Accuracy, and Test Accuracy are compared across the 4 models.

### Optiziming the Classifiers
Finally, these same 4 classifiers are subject to a hyperparameter search using grid search, over a range of specified hyperparameter values. Performance attributes are collected and compared across the 4 hyperparameter tuned models. We lower the feature space by identifying important features and limiting to those. This minimizes fit times while not compromising efficacy of the models.


## Findings
Decision Tree Classifier was the best model of choice considering fit time, score time and accuracy score (`test_ROC_AUC`).

SVC and KNeighborsClassifier were the least performant models considering fit time and score time.

Logistic regression was the fastest model with comparable performance as the more expensive (time-wise) SVC.

## Future Work
### Feature Engineering
* We dropped the feature `pdays` because 96% of it defaulted to the same value. It would be better to verify the importance of this feature before dropping it.

### Feature Selection
To improve computational efficiency, we determined and used a set of important features for hyperparamter tuning based on logistic regression estimator.
It would be better to repeat feature selection for each of the classifiers to use the most important features per classifier.

### Hyperparameter Tuning and GridSearch
Lastly, the hyperparameters parameters such as max_depth and n_neighbors can be changed to see if better performance can be achieved.