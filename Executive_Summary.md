# Executive Summary

Ultimately two models were selected with the best performance in each family. In the GLM family, cross-validated recursive feature elimination was used to select the most relevent features to fit with logistic regression. In the non-GLM family the best model was AdaBoost with low learning rate.

## GLM family:
Model: Cross-validated recursive feature elimination (RFECV)

Strengths: Automatically excludes variables determined to be unimportant. Can fit the model to use only features which perform best under the selected metric (here, ROC-AUC score) with cross-validation. 

Weaknesses: Assumes feature effects are additive on log-odds probability. Does not consider any interaction terms or feature transformations for fitting the model.

## Non-GLM family
Model: AdaBoost with slow learning rate (0.1).

Strengths: Automatically adapts to non-linear effects of features and has enough variance to fit to tranformations of features as necessary. 

Weaknesses: Computationally expensive. As an ensemble method with slow learning rate, requires a large number of fitted estimators (here, 750 weak learners) to be stored in memory to evaluate new predictions.

The performance of each model on the test set can be estimated by the mean 10-fold cross validated ROC-AUC score on the training set. This provides a decent estimate for how the models will perform on data on which the models have not ben trained.

## Test ROC-AUC Estimates
RFECV: 0.7666
AdaBoost: 0.8040

Based on these estimates, AdaBoost would be expected to outperform RFECV on the test set. To demonstrate this, the model performance could be judged by their confusion matrices on a test or validation set after determining the optimal thresholds to use for classifcation.
