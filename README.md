# STROKE-PREDICTION-USING-MACHINE-LEARNING


## Introduction
In recent years, strokes have been one of the leading causes of death globally. According to the World Health Organization (WHO), stroke is the 2nd leading cause of death, responsible for approximately 11% of total deaths.

Technological progress made in the field of medicine has afforded us the opportunity to make predictions regarding the likely occurrence or otherwise of stroke using machine learning. Machine learning algorithms have the capability of increasing the accuracy of stroke predictions through the identification of related risk factors of stroke. 

## Objective
This project aims to explore a number of given risk factors and identify the leading risk factors of stroke using machine learning.

## Dataset
The dataset was comprised of 5,110 records or rows of data and 12 attributes.

##  Data pre-preprocessing
#### Missing Values
In the pre-processing data stage, a summary of the data collected brought to the fore, missing values for only one variable, ‘bmi’. A total of 201 ‘bmi’ values were missing accounting for 3.93% of the total ‘bmi’ feature values. This issue was solved by replacing the missing values with the mean ‘bmi’ value.

#### Outliers
After creating some boxplots, a few outliers were detected and removed from the variable ‘bmi’.

#### Feature Scaling
Scaling was applied to certain features like age, bmi and average glucose level. Scaling was done due to the variations in ranges of the selected features. It was done to change the range of values but without changing the shape of distribution. This was done because of one of the selected algorithms to be used for this project

#### Encoding
The categorical features were converted to integers for the various models created. Dummies were created from variables from the five categorical variables. For the avoidance of multicollinearity, one of each of the dummy variables had to be dropped.

#### Imbalanced dataset
Synthetic Minority Over-Sampling Technique (SMOTE) was applied in this instance by using each sample from the minority class and adding synthetic data points. This strategy is done to oversample the minority class and create a balance.

#### Imbalanced dataset
After completing data pre-processing and handling the imbalanced dataset, the next stage was to build three different models. The oversample data was now split into training and testing data using a ratio of 80% training data and 20% testing data.

#### Feature Selection
Backward feature selection method used to investigate the most important features or predictors of stroke. Back elimination was done by first including all the features in the model and dropping them until the model picked the feature(s) with the highest accuracy in predicting the target variable. Age was selected as the only predictor of stroke with an accuracy of 94.04% Another backward elimination was done for the model to select the six highest predictors of stroke. An accuracy of 90.1% was obtained for the following features: age, average glucose level, bmi, gender (Male), work type (Private), and Residence type (Urban).
Based on the results, the feature ‘age’ was therefore selected as the only variable to be used in building the various machine learning models

## Model Selection
#### K Nearest Neighbour (KNN)
Following the feature selection results, age was selected as the only feature using the K Nearest Neighbour algorithm. The independent variable, age, had to be converted to an array in order to be used in the various algorithms. The number of K nearest neighbours selected for the initial model was four (4). This model produced an overall accuracy of 92%. In terms of stroke (class label = 1) predictions for patients, the models’ score for Precision, Recall, and F1 score were 98%, 87%, and 92%, respectively

#### Decision Tree
The decision tree was built using the pre-processed data using the same 80/20 training and testing data split and with a maximum depth of 3. The decision tree achieved an overall accuracy of 78% and Precision, Recall and F1 score of 75%, 84% and 79%, respectively

#### Random Forest
The Random Forest algorithm was built using the number of estimators. The model was initially built using 10 trees. This model achieved an overall accuracy of 95% and Precision, Recall and F1 score of 98%, 92% and 95%, respectively for stroke predictions.

## Evaluation
For all the models, hyper-parameter tuning was done after building the initial models. Thus, the overall accuracy of the KNN, the Decision tree, and the Random Forest models were obtained to be 93%,93%, and 95%, respectively after tuning.
In interpreting the results of the confusion matrix for the KNN model, the results showed that the number of true negatives and false negatives were 917 and 96, respectively. Thus, this indicates that, out of 1,013 predictions, 917 correct predictions were made for patients who did not develop a stroke. However, although 96 patients were predicted to be normal patients, in actuality, the patients suffered a stroke. Similarly, the number of true positive and false positive predictions were 883 and 47, respectively. Thus, out of 930 predictions, 883 patients were correctly predicted to have suffered a stroke. Also, although the model predicted that 47 patients suffered a stroke, in actuality, they did not suffer a stroke.

## Conclusion
The task involved examining a number of given risk factors in an attempt to identify the leading risk factors of stroke using machine learning. The dataset was first explored to gain some insights into the given features before taking the dataset through pre-processing. The backward elimination method was used in selecting the relevant features. While different combinations of the various features gave high accuracies in predicting the target variable, ‘age’ alone scored the highest as being the most influential factor out of the eleven (11) independent variables. Accordingly, the selected feature was fed into three machine learning algorithms: KNN, Decision tree, and Random Forest. Based on the selected evaluation metrics, the Random Forest model was adjudged the best based on its accuracy, precision, recall, and f1 score. The objective of the project was achieved by firstly identifying the highest risk factor in predicting the possible occurrence or otherwise of stroke through analysis and the use of three machine learning models. 







