## End to End Machine learning project

This repository contains a machine learning project to predict student performance based on various factors. The project utilizes Python and popular machine learning libraries to train a predictive model and make predictions on student performance.

## Introduction

The goal of this project is to develop a model that can predict student performance based on different attributes such as demographic information, socioeconomic factors, and previous academic achievements. This predictive model can be helpful for educators, schools, and policymakers to identify students who may need additional support and intervention.

## Dependencies
To run the project, you need to have the following dependencies installed:

Python 3.7 or above
pandas
scikit-learn
matplotlib
numpy
seaborn

You can install these dependencies by running the following command:

$ pip install -r requirements.txt

The dataset consists of the following columns:

age: student's age (numeric)
gender: student's gender (categorical: 'male' or 'female')
race/ethnicity: student's race/ethnicity (categorical: 'group A', 'group B', 'group C', 'group D', or 'group E')
parental level of education: student's parents' education level (categorical: 'some high school', 'high school', 'some college', "bachelor's degree', "master's degree', or 'associate's degree')
lunch: student's lunch type (categorical: 'standard' or 'free/reduced')
test preparation course: student's test preparation course completion status (categorical: 'none' or 'completed')
math score: student's math score (numeric)
reading score: student's reading score (numeric)
writing score: student's writing score (numeric)

# Approach for the project 

1. Data Ingestion : 
    * In Data Ingestion phase the data is first read as csv. 
    * Then the data is split into training and testing and saved as csv file.

2. Data Transformation : 
    * In this phase a ColumnTransformer Pipeline is created.
    * for Numeric Variables first SimpleImputer is applied with strategy median , then Standard Scaling is performed on numeric data.
    * for Categorical Variables SimpleImputer is applied with most frequent strategy, then ordinal encoding performed , after this data is scaled with Standard Scaler.
    * This preprocessor is saved as pickle file.

3. Model Training : 
    * In this phase base model is tested . The best model found was catboost regressor.
    * After this hyperparameter tuning is performed on catboost and knn model.
    * This model is saved as pickle file.

4. Prediction Pipeline : 
    * This pipeline converts given data into dataframe and has various functions to load pickle files and predict the final results in python.

5. Flask App creation : 
    * Flask app is created with User Interface to predict the gemstone prices inside a Web Application.


## Run from terminal:

docker build -t testdockermuradh.azurecr.io/mltest:latest .

docker login testdockermuradh.azurecr.io

docker push testdockermuradh.azurecr.io/mltest:latest
