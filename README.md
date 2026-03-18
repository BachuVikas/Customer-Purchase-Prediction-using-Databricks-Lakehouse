# 🚀 Customer Purchase Prediction using Databricks Lakehouse

## 📌 Project Overview

This project demonstrates an end-to-end Data & AI pipeline built using **Databricks Lakehouse**.

The goal is to predict customer purchasing behavior by analyzing historical transaction data and identifying high-value customers.

The solution follows the **Medallion Architecture (Bronze → Silver → Gold)** and integrates data engineering with machine learning.

---

## 🎯 Problem Statement

E-commerce businesses want to identify customers who are likely to generate higher revenue.

Instead of targeting all customers, companies can improve marketing efficiency by focusing on **high-value customers**.

This project builds a machine learning system to classify customers based on their purchasing behavior.

---

## 🏗️ Architecture

```
Raw Data (CSV)
        ↓
Bronze Layer (Raw Delta Table)
        ↓
Silver Layer (Cleaned Data)
        ↓
Gold Layer (Customer Features)
        ↓
Machine Learning Model (Random Forest)
        ↓
Predictions Stored in Delta Table
```

---

## ⚙️ Tech Stack

- Databricks
- PySpark
- Delta Lake
- MLflow
- Python
- Spark ML

---

## 📂 Dataset

- Online Retail Dataset
- Contains transaction-level data including:
  - InvoiceNo
  - CustomerID
  - Quantity
  - UnitPrice
  - InvoiceDate

---

## 🧱 Medallion Architecture Implementation

### 🔹 Bronze Layer
- Raw data ingestion
- Stored as Delta table  
- Table: `bronze_online_retail`

### 🔹 Silver Layer
- Data cleaning and preprocessing:
  - Removed cancelled transactions
  - Handled missing values
  - Removed invalid quantities and prices
  - Converted date column to timestamp  
- Table: `silver_online_retail`

### 🔹 Gold Layer
- Feature engineering at customer level:
  - total_orders
  - total_spent
  - avg_order_value
  - total_quantity
  - unique_products  
- Table: `gold_customer_features`

---

## 🤖 Machine Learning Pipeline

- Feature Vector Creation using VectorAssembler
- Train-Test Split (80/20)
- Model: Random Forest Classifier
- Evaluation Metric: Accuracy

---

## 📊 Model Performance

- Accuracy: **~98%**

---

## 🔬 MLflow Experiment Tracking

MLflow is used to track:
- Model parameters
- Evaluation metrics
- Model artifacts

---

## 🔮 Prediction Pipeline

- Batch predictions generated using trained model
- Results stored in:
  - `gold_customer_predictions`

---

## 💡 Business Impact

This solution helps businesses:

- Identify high-value customers
- Improve targeted marketing campaigns
- Increase customer retention
- Optimize revenue generation strategies

---

## 📁 Project Structure

```
databricks-customer-prediction
│
├── notebooks
│   ├── 01_problem_definition
│   ├── 02_bronze_data_ingestion
│   ├── 03_silver_data_cleaning
│   ├── 04_gold_feature_engineering
│   └── 05_ml_customer_purchase_model
│
├── dataset
│   └── online_retail.csv
│
├── architecture
│   └── architecture_diagram.png
│
└── README.md
```

---

## 📌 Conclusion

This project demonstrates how to build a scalable data pipeline and integrate it with machine learning using Databricks Lakehouse.

It highlights the importance of combining data engineering and AI workflows for real-world business solutions.

---
