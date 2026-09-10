
# SmartKart Customer Churn Prediction

## Overview

SmartKart Customer Churn Prediction is a machine learning project that predicts which customers are likely to leave the SmartKart platform.

The project uses a complete machine learning pipeline, starting from a messy customer dataset and ending with a business-ready churn risk report. Logistic Regression is used as the classification model because the target variable, Churn, represents a binary outcome.

## Business Objective

The main objective is to identify customers who are likely to churn so that SmartKart's retention team can take preventive action.

The model analyzes customer information such as:

* Age
* Monthly Spend
* Complaints

Customer ID is retained for identifying customers in the final report but is not used as a model feature.

## Dataset

The project uses a dataset containing 100 customer records with the following columns:

| Column        | Description                                             |
| ------------- | ------------------------------------------------------- |
| Customer_ID   | Unique customer identifier                              |
| Age           | Customer age                                            |
| Monthly_Spend | Customer's monthly spending                             |
| Complaints    | Number of complaints made by the customer               |
| Churn         | Target variable indicating whether the customer churned |

The original dataset intentionally contains real-world data quality issues, including:

* Duplicate records
* Missing values
* Incorrect data types
* Invalid age values
* Negative spending values
* Extreme outliers

## Machine Learning Pipeline

The notebook follows a 15-step machine learning workflow:

1. Data Collection
2. Data Understanding
3. Data Cleaning
4. Outlier Detection and Treatment
5. Feature Selection
6. Target Variable Definition
7. Target Encoding
8. Train-Test Split
9. Feature Standardisation
10. Model Building
11. Model Training
12. Prediction
13. Model Evaluation
14. Model Interpretation
15. Final Business Output

## Data Cleaning

The dataset is cleaned before model training by:

* Removing duplicate records
* Removing unnecessary whitespace
* Converting text values into numeric values
* Handling invalid age values
* Handling negative monthly spending
* Filling missing values using the median

After cleaning, the dataset contains 95 unique customer records.

## Outlier Treatment

Outliers are detected using the Interquartile Range (IQR) method.

Extreme values in Monthly Spend and Complaints are capped instead of removing the complete customer record. This helps prevent extreme observations from disproportionately affecting the Logistic Regression model.

## Model

### Logistic Regression

Logistic Regression is used because churn is a binary classification problem.

The model uses three features:

* Age
* Monthly Spend
* Complaints

The data is split into:

* 80% training data
* 20% testing data

Feature standardisation is performed using training data to ensure that the features are on comparable scales.

## Model Evaluation

The model is evaluated using:

* Confusion Matrix
* Accuracy
* Precision
* Recall
* F1-Score

The project particularly focuses on recall because identifying actual customers who are likely to churn is important for a customer-retention strategy.

## Key Insights

The model coefficients provide business-oriented insights into customer churn.

### Monthly Spend

Monthly Spend has a negative relationship with churn risk. Customers with higher monthly spending tend to have a lower probability of churn in this dataset.

### Complaints

Complaints have a positive relationship with churn risk. Customers making more complaints are more likely to churn.

This represents an important business opportunity for SmartKart to improve customer support and complaint resolution.

### Age

Age has a smaller positive relationship with churn risk compared with the other features.

## Business Takeaway

The analysis suggests that SmartKart should focus on reducing customer complaints and protecting relationships with high-spending customers.

Improving complaint resolution and providing targeted retention strategies for at-risk customers can help reduce customer churn.

## Project Files

```text
SmartKart/
│
├── SmartKart.ipynb
├── SmartKart_dirty_100_rows.csv
└── smartkart_churn_risk_report.csv
```

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib
* Jupyter Notebook / Google Colab

## How to Run

1. Clone this repository.
2. Open `SmartKart.ipynb` in Jupyter Notebook or Google Colab.
3. Upload `SmartKart_dirty_100_rows.csv` when prompted.
4. Run the notebook cells in order.
5. Review the model evaluation results and generated churn risk report.

## Output

The final output is a ranked churn risk report containing customers classified as:

* Likely to Churn
* Not Likely to Churn

The report can be used by a retention or marketing team to prioritise customers who may require intervention.

## Project Purpose

This project demonstrates an end-to-end supervised machine learning workflow applied to a practical business problem. It combines data preprocessing, feature selection, Logistic Regression, model evaluation, interpretation, and business decision-making.
