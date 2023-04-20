# Predicting-Customer-Churn-with-Logistic-Regression
Machine Learning Project on Customer Churn with Logistic Regression
Overview

The goal of this project is to use logistic regression to predict customer churn for a telecom company. Churn refers to customers who cancel their subscription to the company's services. By identifying customers who are likely to churn, the company can take steps to prevent them from leaving.
Dataset

The dataset used for this project is a publicly available telecom customer churn dataset from Kaggle. It contains information on 7043 customers and their usage of the company's services. The dataset can be found here: https://www.kaggle.com/blastchar/telco-customer-churn
Project Steps

   1. Load and explore the dataset
   2. Prepare the data for modeling
   3. Train the logistic regression model
   4. Evaluate the model on a test set
   5. Interpret the results

# Code Overview
## Load and Explore the Dataset

import pandas as pd

## Load the dataset
df = pd.read_csv('telco-customer-churn.csv')

## Explore the dataset
print(df.head())
print(df.info())
print(df.describe())

## Prepare the Data for Modeling
## Drop the customerID column since it is not relevant for modeling
df.drop('customerID', axis=1, inplace=True)

## Convert the binary columns to 0/1
df['gender'] = df['gender'].map({'Male': 1, 'Female': 0})
df['Partner'] = df['Partner'].map({'Yes': 1, 'No': 0})
df['Dependents'] = df['Dependents'].map({'Yes': 1, 'No': 0})
df['PhoneService'] = df['PhoneService'].map({'Yes': 1, 'No': 0})
df['PaperlessBilling'] = df['PaperlessBilling'].map({'Yes': 1, 'No': 0})
df['Churn'] = df['Churn'].map({'Yes': 1, 'No': 0})

## Convert the categorical columns to dummy variables
df = pd.get_dummies(df, columns=['MultipleLines', 'InternetService', 'OnlineSecurity', 'OnlineBackup', 'DeviceProtection', 'TechSupport', 'StreamingTV', 'StreamingMovies', 'Contract', 'PaymentMethod'], drop_first=True)

# Split the data into training and testing sets
from sklearn.model_selection import train_test_split

X = df.drop('Churn', axis=1)
y = df['Churn']

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Scale the data
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)

Train the Logistic Regression Model

from sklearn.linear_model import LogisticRegression

log_reg = LogisticRegression()
log_reg.fit(X_train_scaled, y_train)

Evaluate the Model on a Test Set

python

from sklearn.metrics import confusion_matrix, accuracy_score, precision_score, recall_score, f1_score

y_pred = log_reg.predict(X_test_scaled)

print('Confusion Matrix:')
print(confusion_matrix(y_test, y_pred))

print('Accuracy:', accuracy_score(y_test, y_pred))
print('Precision:', precision_score(y_test, y_pred))
print('Recall:', recall_score(y_test, y_pred))
print('F1 Score:', f1_score(y_test, y_pred))
