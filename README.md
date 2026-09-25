# Real-Time UPI Fraud Pattern Detection for Small Banks

## Overview

This project focuses on detecting potentially fraudulent UPI transactions using machine learning. The system analyzes transaction-level and customer-level behavioral features to identify unusual transaction patterns and generate a fraud score.

The current implementation covers the offline machine learning pipeline. Real-time transaction streaming and dashboard integration are planned for the next phase.

## Dataset

The dataset contains **550,000 banking transactions**.

* Genuine transactions: 545,127
* Fraudulent transactions: 4,873
* Fraud rate: approximately 0.89%
* Train-test split: 80:20
* Training transactions: 440,000
* Testing transactions: 110,000

## Methodology

The project follows these steps:

1. Data collection and inspection
2. Data preprocessing
3. Transaction-level feature engineering
4. Customer behavioral feature engineering
5. Stratified train-test splitting
6. Numerical and categorical preprocessing
7. Machine learning model training
8. Model evaluation and comparison
9. Feature importance analysis
10. Fraud pattern analysis
11. Fraud score generation

## Features

### Transaction Features

* Transaction amount
* Account balance
* Transaction type
* Transaction direction
* Merchant category
* State
* Credit score
* Transaction hour
* Channel
* KYC status
* Amount-to-balance ratio
* Balance after transaction
* High-value transaction indicator
* Night transaction indicator
* Weekend transaction indicator

### Customer Behavioral Features

* Customer average transaction amount
* Amount deviation
* Customer transaction count

## Machine Learning Models

The following models were implemented and compared:

* Logistic Regression
* Random Forest
* XGBoost

## Model Results

| Model               | Accuracy | Precision | Recall | F1-Score |
| ------------------- | -------: | --------: | -----: | -------: |
| Logistic Regression |   75.59% |     1.10% | 29.95% |    2.13% |
| Random Forest       |   96.73% |     3.58% | 10.36% |    5.32% |
| XGBoost             |   88.10% |     1.44% | 18.36% |    2.66% |

Additional evaluation metrics include ROC-AUC and PR-AUC.

Random Forest is currently used as the working model based on the obtained evaluation results.

## Fraud Score

The Random Forest model generates an estimated fraud score using its probability output.

A baseline threshold of 0.5 is currently used:

* Score >= 0.5 → potentially suspicious
* Score < 0.5 → not flagged

The threshold can be tuned in future work according to the required precision-recall trade-off.

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* XGBoost
* Matplotlib
* Seaborn
* Google Colab / Jupyter Notebook

## Project Status

### Completed

* Dataset preprocessing
* Transaction feature engineering
* Behavioral feature engineering
* ML model training
* Model evaluation
* Feature importance analysis
* Fraud pattern analysis
* Fraud score generation

### Future Work

* Apache Kafka for real-time transaction streaming
* FastAPI for model serving
* Real-time fraud prediction
* React-based monitoring dashboard
* Real-time alerts and transaction verification

## Repository Structure

```text
UPI-Fraud-Detection/
│
├── notebooks/
│   └── UPI_Fraud_Detection.ipynb
│
├── README.md
├── requirements.txt
└── .gitignore
```

## Team

* Meka Hamsa Gayathri
* Vaddi Indu Sree
* Sinchana MM

Department of Computer Science and Engineering
Presidency University, Bengaluru
