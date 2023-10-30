# machine_learning_project-supervised-learning

## Objective
The main goals of the project are to explore a diabetes data set and to build more than one supervised learning binary classification model and determine which one will be best suited to classify whether or not an individual has diabetes.

## The Dataset
The data set for this project is the "Diabetes" dataset from the National Institute of Diabetes and Digestive and Kidney Diseases. It consists of entirely numerical data, and contains the following information:
- The number of pregnancies an individual has had
- Glucose levels
- Blood pressure
- Thickness of skin
- Insulin levels
- Body mass index (BMI)
- Diabetes pedigree function measurement, which has to do with the likelihood the individual may be diagnosed with diabetes based on familial history
- Age
- Outcome (0 is diabetic, 1 if not diabetic)
The data set had errenous outliers (such as BMI of 0) that were filtered out prior to creating correlation heatmaps and model building.

For a detailed breakdown of the EDA, please refer to the Supervised Learning notebook file (Supervised Learning - Project.ipynb).

## Modeling
First model built was a logistic regression model. Doing so gave a reasonable scores (0.74 accuracy, 0.61 precision, 0.60 recall, 0.60 F-score, 0.71 ROC-AUC score and AUC of 0.79).
Second model was a random forest model. Using default parameters, this one scored slightly worse (and it mistakenly labeled two less diabetic individuals as non-diabetic).
Using a grid search with k-fold cross validation on the random forest model and using a list of parameters that start within the range of the parameter values from the previous model, and then using the best parameters that the grid search gave, the resulting model gave much better results which made it an even better classifier than the logistic regression model.

For detailed model evaluations, please refer to the Supervised Learning notebook file (Supervised Learning - Project.ipynb).

## Conclusion
Based on EDA, the three most important factors that are correlated to a diagnosis of diabetes are glucose levels, age and body mass index in that order, which is somewhat surprising as the diabetes pedigree function should've in theory played a bigger contributor but didn't. And as for predicting, a random forest model using parameters that were found after conducting a grid search seems to be better than a logistic regression model as the one that was created managed to correctly predict one more non-diabetic patient and correctly predict three more diabetic ones.
