# Real-Time-Credit-Card-Fraud-Detection-System

# Credit Card Fraud Detection

This project demonstrates the development of a machine learning model to detect fraudulent credit card transactions. It utilizes a dataset from Kaggle and employs a Random Forest Classifier to distinguish between legitimate and fraudulent activities.

## Table of Contents
- [About the Dataset](#about-the-dataset)
- [Methodology](#methodology)
- [Results](#results)
- [How to Run Locally](#how-to-run-locally)
- [File Descriptions](#file-descriptions)

## About the Dataset

The dataset used is the "Credit Card Fraud Detection" dataset from Kaggle. It contains transactions made by European cardholders in September 2013.

- **Source:** [Kaggle Credit Card Fraud Detection Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
- **Features:** The dataset contains 31 features. Due to confidentiality, the original features have been transformed using Principal Component Analysis (PCA). The only features that have not been transformed are `Time` and `Amount`.
- **Target Variable:** The `Class` column is the target, where `1` indicates a fraudulent transaction and `0` indicates a legitimate one.
- **Challenge:** The dataset is highly imbalanced. Out of 284,807 transactions, only 492 are fraudulent (0.173%). This makes accuracy a poor metric and requires a focus on precision and recall.

## Methodology

The project follows these key steps:
1.  **Data Loading & Exploration:** The dataset is loaded using Pandas. An initial exploratory data analysis (EDA) is performed to understand the data distribution and the extent of the class imbalance.
2.  **Data Visualization:** A correlation heatmap is generated to visualize relationships between features.
3.  **Data Preprocessing:** The data is split into features (X) and the target variable (Y). It is then divided into training and testing sets (80/20 split).
4.  **Model Training:** A `RandomForestClassifier` from Scikit-learn is chosen for this classification task due to its robustness and effectiveness with imbalanced datasets.
5.  **Model Evaluation:** The model's performance is evaluated on the test set using a variety of metrics:
    - Accuracy
    - Precision
    - Recall
    - F1-Score
    - Matthews Correlation Coefficient (MCC)
    - A Confusion Matrix is also plotted to visualize the true vs. predicted classes.

## Results

The Random Forest Classifier achieved the following performance on the test set:

- **Accuracy:** 0.9996 (or 99.96%)
- **Precision:** 0.9747 (For fraud cases, 97.5% of the predictions were correct)
- **Recall:** 0.7857 (The model successfully identified 78.6% of all actual fraud cases)
- **F1-Score:** 0.8701
- **Matthews Correlation Coefficient (MCC):** 0.8749

While the accuracy is very high, the recall indicates that the model missed about 21.4% of fraudulent transactions. The high precision shows that when the model does predict fraud, it is very likely to be correct.

## How to Run Locally

1.  Clone this repository.
2.  Download the `creditcard.csv` dataset from the Kaggle link above and place it in the `data/` directory.
3.  Create and activate a Python virtual environment.
4.  Install the required libraries: `pip install -r requirements.txt`
5.  Launch Jupyter Lab: `jupyter lab`
6.  Open and run the `ML___Credit_Card_Fraud_Detection-.ipynb` notebook.

## File Descriptions

- `ML___Credit_Card_Fraud_Detection-.ipynb`: The Jupyter Notebook containing all the code for analysis, model training, and evaluation.
- `data/creditcard.csv`: The dataset file (must be downloaded from Kaggle).
- `requirements.txt`: A list of Python libraries required to run the project.
- `README.md`: This file.
