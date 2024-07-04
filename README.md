# Fraudulent Transaction Detection

## Overview
This project aims to detect fraudulent online payment transactions using various machine learning models. The dataset used in this project contains details about different transactions and whether they are identified as fraudulent or not.

## Dataset Description
The dataset contains the following columns:
- **step**: Number of steps taken to perform the transaction.
- **type**: Type of online transaction.
- **amount**: The amount of the transaction.
- **nameOrig**: ID of the customer initiating the transaction.
- **oldbalanceOrg**: Balance of the origin account before the transaction.
- **newbalanceOrig**: Balance of the origin account after the transaction.
- **nameDest**: ID of the recipient customer.
- **oldbalanceDest**: Initial balance of the recipient account.
- **newbalanceDest**: New balance of the recipient account.
- **isFraud**: Indicates if the transaction is fraudulent.
- **isFlaggedFraud**: Indicates if the transaction is flagged as fraudulent.

## Data Preprocessing
1. **Loading the Data**: The dataset is loaded using pandas.
2. **Handling Missing Values**: Checked for missing values and confirmed there are none.
3. **Balancing the Dataset**: The dataset is highly imbalanced, so the number of non-fraudulent cases is reduced to match the number of fraudulent cases.
4. **Feature Engineering**: Converted the `type` column into dummy variables and dropped irrelevant columns (`nameOrig`, `nameDest`, `isFlaggedFraud`).

## Exploratory Data Analysis (EDA)
- **Distribution of Transaction Types**: Created bar plots to understand the distribution of transaction types.
- **Scatter Plots**: Visualized relationships between various features like `amount`, `step`, `oldbalanceOrg`, and `newbalanceDest`.
- **Crosstabs**: Identified predominant types of fraudulent transactions, primarily `CASH_OUT` and `TRANSFER`.

## Machine Learning Models
Three machine learning models were applied:
1. **Support Vector Machine (SVM)**
2. **Logistic Regression**
3. **Random Forest Classifier**

### Model Evaluation
The models were evaluated based on their accuracy scores, confusion matrices, and classification reports. The Random Forest Classifier outperformed the other models with the highest accuracy.

### Hyperparameter Tuning
Used GridSearchCV for hyperparameter tuning for each model:
- **SVM**: Best parameters were `{'C': 30, 'gamma': 'scale', 'kernel': 'rbf'}`.
- **Random Forest**: Best parameters were `{'n_estimators': 5}`.
- **Logistic Regression**: Best parameters were `{'C': 1, 'multi_class': 'auto', 'solver': 'lbfgs'}`.

## Results
- **SVM**: Accuracy - 90.36%
- **Logistic Regression**: Accuracy - 91.92%
- **Random Forest**: Accuracy - 98.58%

## Conclusion
The Random Forest Classifier provided the best results for detecting fraudulent transactions with the highest accuracy and well-balanced precision and recall.

## Confusion Matrix and Classification Report

### SVM

          precision    recall  f1-score   support
       0       0.85      0.98      0.91      2487
       1       0.97      0.83      0.90      2441
accuracy                           0.90      4928


### Logistic Regression


          precision    recall  f1-score   support
       0       0.99      0.98      0.99      2487
       1       0.98      0.99      0.99      2441
accuracy                           0.99      4928



## How to Run
1. Clone the repository.
2. Install the required libraries.
3. Run the notebook to reproduce the results.



