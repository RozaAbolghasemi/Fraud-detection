# Fraud Detection in Financial Invoices

This project presents an exploratory data analysis and anomaly detection approach for identifying suspicious invoice activity within a financial services context. The goal is to uncover patterns of potential fraud or credit abuse in customer transaction data following a system integrity issue.

## 📌 Project Overview

A system error led to a period where standard risk checks—such as internal scoring, external credit ratings, and fraud detection mechanisms—were bypassed. As a result, a large number of transactions were approved without validation. This repository contains a structured investigation into invoice-level transaction data to identify unusual patterns and behaviors that may suggest fraudulent activity.

Since no confirmed fraud cases exist, this task focuses on unsupervised anomaly detection, domain-driven insights, and exploratory methods to assess the extent of potential risk exposure.

## 🔍 Objectives

- Analyze invoice transactions to identify irregularities or high-risk behaviors.
- Define and apply custom anomaly detection criteria based on domain knowledge.
- Detect potential fraud signals, such as:
  - Unusual purchase volumes
  - Irregular address or SSN usage
  - Repeated or coordinated transactions across multiple identities
  - Signs of identity misuse or synthetic identities

## 🧰 Tools & Technologies

- **Python**
- **Pandas**, **NumPy** for data processing
- **Matplotlib**, **Seaborn** for data visualization
- **Scikit-learn**, **Isolation Forest**, **DBSCAN** for unsupervised anomaly detection
- **Jupyter Notebook** for reproducible and interactive analysis

## 📁 Project Structure

. ├── data/ │ └── invoices.csv # Sample anonymized invoice data ├── notebooks/ │ └── fraud_detection_analysis.ipynb # Main analysis notebook ├── src/ │ └── preprocessing.py # Data cleaning and feature engineering │ └── anomaly_detection.py # Custom anomaly detection functions ├── requirements.txt # Python dependencies └── README.md # Project documentation


## 📊 Data Description

Each row represents a single invoice sent to a customer. Below are selected features included in the dataset:

| Column Name               | Description                                                                 |
|--------------------------|-----------------------------------------------------------------------------|
| `invoice_no`             | Unique invoice ID                                                           |
| `email`                  | Anonymized customer email                                                   |
| `social_security_number`| Pseudonymized social security number / ID                                    |
| `customer_no`            | Internal customer ID                                                        |
| `principal_amount`       | Original invoice amount                                                     |
| `is_debt_collection_stopped` | Binary flag indicating whether collections were stopped                |
| `last_event`             | Last status or activity on the invoice                                      |
| `last_event_date`        | Date of the last event                                                      |
| `period_start`, `period_end` | Invoice period start and end dates                                     |
| `born_year`              | Extracted year of birth (ambiguous 2-digit year)                            |
| Address fields           | Includes city, postal code, street, and house number                        |
| `firstname`, `lastname`  | Pseudonymized customer names                                                |

## 🧠 Methodology

- **Exploratory Analysis**: Summary statistics, customer segmentation, time-based trends
- **Rule-Based Filters**: Manually crafted signals such as:
  - High purchase amounts in a short period
  - Duplicate SSNs or addresses across accounts
  - Unusual frequency of orders from the same city or postal code
- **Unsupervised Learning**: Applied Isolation Forest and DBSCAN to detect outliers in multidimensional feature space
- **Visualization**: Highlighted anomalous points and distribution shifts during the risk system outage

## 🚀 Key Insights

- Detection of customer groups showing bulk purchase behavior shortly after the validation checks failed.
- Identification of duplicate or suspiciously similar SSNs and email patterns.
- Clustered activities around certain geographic locations potentially linked to organized behavior.

## ✅ How to Run

1. Clone the repository  
   ```bash
   git clone https://github.com/your-username/transaction-anomaly-detection.git


2. Install the requirements
pip install -r requirements.txt


3. Run the analysis
Open the Jupyter notebook in the notebooks/ directory and follow the step-by-step analysis.

🧾 Disclaimer
This project is a demonstration of anomaly detection and exploratory techniques on synthetic, anonymized data. It is intended for illustrative and educational purposes in a financial risk analysis context. No real individuals can be identified, and no actual customer data is used.
