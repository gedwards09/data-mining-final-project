# Data Mining: Final Project
Final project for data mining and statistical learning course.

The goal for the project is to build a two-class classification model to predict the probability that the target variable, 'y', is in class 1. The training data consists of 40,000 observations with a total of 100 features. There are both continuous and categorical features in the data, and many observations have missing data as well. The project requires two models to be submitted: one logistic regression model, and one non-GLM model. Once built, the models are applied to 10,000 test observations, generating the predicted probabilities that each observation is in class 1. The accuracy of the models, and the overall score, are evaluated based on ROC-AUC score of the test predictions.

Files:

'Instructions -Classification Exercise (40).txt' contains the instructions for the assignment and the criteria for evaluation.

exercise_40_train.csv contains the training data csv file with header for column labels.

exercise_40_test.csv contains the testing data csv file with columns labels.

EDA_main.ipynb contains the main exploratory data analysis for the features as well as data scrubbing and preprocessing. Continuous features are scaled to mean zero and unit standard deviation, and missing entries are filled with the median value for training observations. For categorical features, midding data is either combined with other categories or treated as a category on its own.

ModelSelection.ipynb contains the analysis of different types of models, and their mean 10-fold cross validation ROC-AUC scores are used to determine fit of each model. Three GLM models are considered: logisting regression with feature selection using p-value thresholding, cross validated recursive feature elimination, and LASSO regulatization using cross validated parameter grid search. Ultimately, cross validated recursive feature elimination performed the best. From the non-GLM family, two models are considered: random forests and AdaBoost, with AdaBoost performing the best.

TestPredictions.ipynb contains the code generating the predicted probabilities for classifiying the training data using the two chosen models. Here continuous features for the test data are preprocessed in the same manner as the training data, with missing values filled with the training median and scales standardized by the training parameters.

glmresults.csv contains the final predicted probabilities for the test data using logistic regression with recursive feature elimintation fit to the training data.

nonglmresults.csv contains the final predicted probabilities for the test data using the best performing AdaBoost model fit to training data.
