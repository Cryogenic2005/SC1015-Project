# SC1015 Mini Project

This repository contains the Jupyter Notebook files and the data set for the Mini Project for NTU's SC1015 module.

The *data* folder contains the original data set, and the pickle files for the used to transfer DataFrames resulting from the data preparation and data exploration.

The external libraries used are indicated in the requirements.txt file. To install the required libraries, run the following command:

> pip install -r requirements.txt

---

**Table of Contents:**

1. [Group Info](#group-info)
2. [Problem Statement](#problem-statement)
3. [Data Preparation](#data-preparation)
4. [Exploratory Analysis](#exploratory-analysis)
5. [Modelling](#modelling)
6. [Conclusions](#conclusions)
7. [What we learned](#what-we-learned)
8. [References](#references)

## About our Project

Predicting the potential of contracting cardiovascular disease using the following dataset obtained from kaggle:
https://www.kaggle.com/datasets/jocelyndumlao/cardiovascular-disease-dataset

### Group Info
<u>Lab Group:</u> FCEA

Team 9:
- Ariel Kwok Dai Hui
- Liong Xun Qi
- Le Nguyen Bao Huy

### Problem Statement

Using the data set, we aim to answer the following questions:
- Which factors are indicators of cardiovascular diseases
  - Are the elderly more likely to get cardiovascular diseases
  - Does gender play a role?
  - Which medical data are we interested in?
- Can we build a model to accurately predict presence of heart disease?
  - Which model is the best performing?

### Data Preparation

The data set has 1000 rows and 14 features. Using patient IDs, we concluded there were no duplicate data in the data set. We also found that there were no missing values in the data set. 

The *patientid* feature was dropped from the data set because it was irrelevant to the analysis. Categorical variables like *slope* or *chestpain* were split using one hot encoding.

Other changes to the data set include changing column data types to boolean for compactness and clarity, as some name changes to make certain information more clear.

### Exploratory Analysis

To gain valuable insights from our data to help us identify the significant symptoms of heart disease, we decomposed our approach into 3 parts.

firstly, we wanted to find out if there are any strong correlations between the numeric variables (age, resting blood pressure, serum cholesterol, maximum heart rate, old peak and the number of major blood vessels). All the numeric variables had very weak correlation with each other, so we can safely assume they are independent of each other.

Secondly, we aimed to identify any numeric variables that shared a distinct relationship with the presence of heart disease. The following are the significant findings:
- Heart disease patients tend to have higher resting blood pressure.
- Patients with 2 or more major blood vessels are at higher risk of suffering from heart disease.

Lastly, we explored and analysed the relationship between the non-numeric variables (gender, fasting blood sugar, presence of exercise induced angia, type of chest pain, resting ECG results and slope of ST segment) with the presence of heart disease. The following are the significant findings:
- Patients who suffer from non-anginal chest pain were the most likely to have heart disease as compared to other chest pain types.
- Patients who have fasting blood sugar that exceeds 120mg/dl are more likely to have heart disease.
- Patients who had wave abnormality and left ventricular hypertrophy for their ECG results are at a high risk of having heart disease.
- Patients with a flat or downsloping ST segment are highly likely suffering from heart disease.

### Modelling

From the dataframe obtained after the data exploration process, we can build several models for predicting the presence of cardiovascular diseases.

Before that, to ensure to able to recreate the models, we initially randomly selected a seed value, and then passing to the *random_state* parameter for any models which accepted it.

We fit the data into the a Logistic Regression model, a Decision Tree Classifier model and a Random Forest Classifier model. In particular, we hypertuned the parameters of the Random Forest model using grid search and cross validation techniques.

We found that the Random Forest Classifier model had the highest accuracy out of all of them, but also took the longest to execute the underlying code.

### Conclusions

In this project we completed the data preparation and cleaning, exploration of data and visualisation techniques, and the machine learning model that to predict the presence of heart disease. 
- Data preparation and cleaning: removes duplicate and unknown data, and organising of data. 
- Explore and visualisation of data: made use of visualisation techniques to find the most significant variables for prediction. 
  - Factors like *age* and *gender* are not correlated with presence of heart disease
  - Factors like type of chest pain or number of major vessels are highly correlated with presence of heart disease
- Machine Learning: Fitted 3 different models and evaluated the results using confusion matrix. 
- **Final result:** Random forest classifier is the best performing model. 

### What we learned

Through this project we learned how to collaborate with each other effectively for a coding project and other techniques for conducting data analysis:
- Saving dataframe to pass to other members for next steps of data analysis through .pkl files
- Using GitHub to collaborate with each other effectively.
- Using Logistic Regression to predict whether subject has cardiovascular disease or not.
- Using RandomForest and hypertuning parameters to find the best model for predicting.

### References

https://www.kaggle.com/datasets/jocelyndumlao/cardiovascular-disease-dataset