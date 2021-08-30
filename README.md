# Holmusk Healthcare Data Challenge

The task is to analyze the clinical and financial data of patients hospitalized for a certain condition. Some variable names and patient_id's have been anonymized in this dataset. We are required to join the data given in different tables, and find insights about the drivers of cost of care.

## Problem Statement

In order to combat the issue of high hospitalisation bills, the Ministry of Health (MOH) wants to understand the drivers of cost of care for patients hospitalised for a certain condition.

## Executive Summary

In this project, we analysed various datasets and built a linear model to assess important predictors in determining a patient's cost of care. After processing and performing exploratory analysis of the data to gather insights, we used a Multiple Linear Regression (MLR) model to assess which features were the most important. Various recommendations were then provided for MOH to tackle the issue of high hospitalisation bills.

### Methodology

The methodology used during this project is as follows:

1. Data Exploration & Cleaning
- Datasets are cleaned & null imputation is performed
- Merge the data in 4 separate tables into 1 dataframe
- Adjust data to prepare for analysis

2. Feature Engineering
- Create new features to extract more useful information from our data

3. Exploratory Data Analysis
- Visualise relationships between features and target variable (`bill_amount`)
- Perform feature selection for modelling

4. Modelling
- Create OLS model to predict target variable from group of features
- Analyse model coefficients

5. Conclusion
- Provide recommendations to MOH based on analysis
- Identify limitations of project

## Conclusion

The MLR model built performs quite well in predicting the log of `bill_amount`, with an adjusted R-square score of 0.941 and a RMSE of 2236.6. 17 of the 19 predictors were found to be significant, with `race`, `resident_status`, `total_med_hist` and `total_symptoms` having greater effects on the predicted bill amount. This is in line with the EDA performed on the mentioned features.

### Recommendations

In order to tackle the problem of high hospitalisation bills for this particular condition, some recommendations can be drawn from the analysis of the data given:

#### Conduct further studies into race-specific differences

Although we mentioned that exploring racial differences was not the focus of this project, the results indicate that `race` plays a big role in a patient's cost of care. Malay patients were predicted to have 56% higher bills than Chinese patients, while the value for Indian and Others patients were 22% and 10% respectively. These are not insignificant numbers and further studies should be conducted to look into the underlying cause, be it social, cultural or other aspects related to race. Targeted measures can then be developed to tackle these underlying causes and equalise the cost of care for all races.

#### Target `symptom_5`, `medical_history_1` & `medical_history_6` for early intervention

A [study by the British Medical Association](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&ved=2ahUKEwivye721djyAhWRXisKHTrwCB4QFnoECBoQAQ&url=http%3A%2F%2Fsentpressrelease.com%2Fpressrelease%2Fattachment%2F73108%2F79fbe4f4-c323-4f1e-a7df-9abe85930d12%2F90d6fdbe-bd30-4f4b-8557-9250948a642c%3FfileDisplayName%3DExploring%2520the%2520cost%2520of%2520early%2520intervention.pdf&usg=AOvVaw0mokqOBV381ha6EGn-vBpC) has shown that early intervention and preventions were largely cost effective and cost saving. Mass-media campaigns can be formulated specifically targeting these 3 features as they were found to have the greatest effect on a patient's cost of care. When the patients are admitted to the hospital with these symptoms/history, it is already too late and they would likely lead to higher bills. However, lowering the general occurrences of these in the public would definitely improve the overall cost of care for this condition.
