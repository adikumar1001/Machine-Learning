📊 Loan Default Prediction in R
This project involves predictive modeling on a cleaned loan dataset using classification algorithms: Random Forest, Gradient Boosting Machine (GBM), and K-Nearest Neighbors (KNN). The goal is to predict the likelihood of loan default based on applicant information and loan characteristics.

📁 Dataset
The dataset used in this analysis is:

loan_data_cleaned.csv
Location: C:/Users/vivekvikrams/Downloads/loan_data_cleaned.csv

Features include:

Applicant income

Loan amount

Interest rate

Demographics (gender, education, etc.)

Loan purpose

Previous defaults
The target variable is: loan_status

0 → Non-Default

1 → Default

📦 Packages Used
r
Copy
Edit
library(caret)
library(dplyr)
library(ggplot2)
library(ranger)
library(gbm)
library(corrplot)
library(pROC)
🔍 Data Exploration & Cleaning
Checked for missing values

Explored data structure and summary stats

Plotted:

Histogram for income, interest rate, and loan amount

Boxplots comparing loan status with income and interest rate

Correlation matrix of numeric features

🔀 Data Partitioning
Data split into:

70% Training

15% Validation

15% Testing
Stratification maintained on loan_status variable.

🌲 Random Forest
Trained using ranger via caret::train

Feature exclusions: person_gender, person_education, person_home_ownership, loan_intent, previous_loan_defaults_on_file

Evaluated using confusion matrix on both validation and test sets

🚀 Gradient Boosting Machine (GBM)
Trained using 5-fold CV

Used all features

Evaluated via:

Confusion matrix

ROC curve & AUC on the test set

🔍 K-Nearest Neighbors (KNN)
Applied centering and scaling

Used 3x repeated CV to tune k

ROC curve & AUC evaluated on normalized test set

📈 Model Evaluation
Each model was evaluated based on:

Confusion Matrix

Accuracy

Sensitivity / Specificity

ROC Curve

AUC Score

📌 Key Takeaways
Exploratory plots help understand skewness and variable impact on loan default.

GBM and Random Forest generally outperform KNN in imbalanced classification tasks.

ROC and AUC are essential metrics, especially in cases of class imbalance.

