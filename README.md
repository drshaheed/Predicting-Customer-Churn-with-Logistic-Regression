# Predicting-Customer-Churn-with-Logistic-Regression
Machine Learning Project on Customer Churn with Logistic Regression
OPredicting Customer Churn with Logistic Regression

This project aims to predict customer churn for a telecommunications company using logistic regression. The dataset used for this project was obtained from Kaggle and contains information on customer demographics, account information, and usage patterns.
Data Source

The dataset used in this project can be found on Kaggle at the following link:
https://www.kaggle.com/blastchar/telco-customer-churn

The dataset contains 7,043 rows and 21 columns of data on customer demographics, account information, and usage patterns for a telecommunications company. The target variable in this dataset is "Churn", which indicates whether or not a customer has churned.

# Steps Performed in the Data Evaluation

1. Data Loading and Exploration: 
   The data was loaded into Python using the pandas library and explored using various exploratory data analysis (EDA) techniques such as summary statistics, data visualization, and checking for missing values.
2. Data Cleaning and Preprocessing: 
   The data was cleaned by addressing missing values, outliers, and incorrect data types. The data was also preprocessed by encoding categorical variables and scaling continuous variables.
3. Feature Selection: Feature selection was performed using various methods such as correlation analysis, univariate feature selection, and recursive feature elimination.
4. Model Training and Evaluation: The logistic regression model was trained using the training set and evaluated using the test set. The model's performance was evaluated using various metrics such as accuracy, precision, recall, and F1 score.
5. Model Interpretation: The model coefficients were interpreted to identify the features that were most important in predicting customer churn


This project demonstrates how logistic regression can be used to predict customer churn and provides insights into the factors that contribute to customer churn in the telecommunications industry.

# Dataset Explanation:

    customerID: Unique identifier for each customer
    gender: Gender of the customer (Male/Female)
    SeniorCitizen: Whether the customer is a senior citizen or not (1: Yes, 0: No)
    Partner: Whether the customer has a partner or not (Yes/No)
    Dependents: Whether the customer has dependents or not (Yes/No)
    tenure: Number of months the customer has stayed with the company
    PhoneService: Whether the customer has a phone service or not (Yes/No)
    MultipleLines: Whether the customer has multiple lines or not (Yes/No/No phone service)
    InternetService: Type of internet service the customer has (DSL/Fiber optic/No)
    OnlineSecurity: Whether the customer has online security or not (Yes/No/No internet service)
    OnlineBackup: Whether the customer has online backup or not (Yes/No/No internet service)
    DeviceProtection: Whether the customer has device protection or not (Yes/No/No internet service)
    TechSupport: Whether the customer has tech support or not (Yes/No/No internet service)
    StreamingTV: Whether the customer has streaming TV or not (Yes/No/No internet service)
    StreamingMovies: Whether the customer has streaming movies or not (Yes/No/No internet service)
    Contract: The contract term of the customer (Month-to-month/One year/Two year)
    PaperlessBilling: Whether the customer has paperless billing or not (Yes/No)
    PaymentMethod: The payment method of the customer (Electronic check/Mailed check/Bank transfer (automatic)/Credit card (automatic))
    MonthlyCharges: The amount charged to the customer monthly
    TotalCharges: The total amount charged to the customer over the entire tenure period
    Churn: Whether the customer churned or not (Yes/No)

The target variable in this dataset is Churn, which indicates whether or not a customer has churned. All other variables are potential predictors of customer churn.
