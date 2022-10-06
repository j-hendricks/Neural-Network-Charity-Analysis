# Neural-Network-Charity-Analysis
Used Deep Neural Network to determine which charities to fund

## Overview

This project aims to build a neural network that can accurately determine whether a charity will make proper use of its funding. To accomplish this, data from thousands of charities were preprocessed and read into the model. The target variable was "IS_SUCCESSFUL", which determines whether the money was used affectively. The features used were:

* AFFILIATION — Affiliated sector of industry
* CLASSIFICATION — Government organization classification
* USE_CASE — Use case for funding
* ORGANIZATION — Organization type
* STATUS — Active status
* INCOME_AMT — Income classification
* SPECIAL_CONSIDERATIONS — Special consideration for application
* ASK_AMT — Funding amount requested

## Results

To begin preprocessing, the identification columns, EIN and NAME, were removed since they provide no useful information. Then, the number of categories in "AFFILIATION" and "CLASSIFICATION" were reduced by placing all rare categories into an "Other" category. After preprocessing, a model was trained. This model consisted of:

* 2 dense layers, 400 nodes in the first, 200 in the second
* relu activation function for the hidden layers
* An output layer with one node and sigmoid activation function (binary classification)
* the model ran for 150 epochs

The accuracy of this model was 74.1%. To increase the accuracy to 75%, an additional model was run. Several aspects of this second model fitting were different:

* the model contained 3 hidden layers, with nodes 400, 200, and 100 respectively
* number of epochs was increased to 200
* a log transformation was applied to the "ASK_AMT" variable, since this veature did not initial possess a normal distribution
* For AFFILIATION and CLASSIFICATION, several categories placed in the "Other" categories were allowed to stand on their own

As a result of these modeifications, the second model achieved 75.1% accuracy. A major factor in this improvement is the log transformation on the "ASK_AMT" feature. Neural networks should ideally work with data that is normally distributed, with a low standard deviation. Data transformation helped with this.

## Summary

The final model achieved 75% accuracy after: 1) a log transformation was applied to the "ASK_AMT" feature, 2) a third hidden layer was added, 3) Less categories were placed in the "Other" category 4) epochs were increased to 200. To improve this model further, another machine learning model could be applied to the data, such as logistic regression, which can achieve similar results to neural networks when dealing with binary classification. Other data transformation techniques, such as inverse square root, could be applied to the "ASK_AMT" feature. 
