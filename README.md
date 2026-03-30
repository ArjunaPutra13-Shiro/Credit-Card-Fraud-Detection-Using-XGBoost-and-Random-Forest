# Credit Card Fraud Detection

## Overview
This project builds a machine learning system to detect fraudulent credit card transactions using a highly imbalanced dataset.

The focus is not just on training a model, but on handling extreme class imbalance and optimizing for meaningful fraud detection metrics.

---

## Problem Statement
Fraud detection is a classic imbalanced classification problem where fraudulent transactions are extremely rare but high-impact.

A naive model can achieve over 99% accuracy by predicting all transactions as legitimate, making accuracy an invalid metric.

The goal is to:
- Detect as many fraudulent transactions as possible
- Maintain reasonable precision to limit false alarms

---

## Dataset

This project uses the **Credit Card Fraud Detection dataset** containing transactions made by European cardholders in September 2013.

- Total transactions: 284,807  
- Fraud cases: 492  
- Fraud rate: 0.172%  

### Features
- `V1`–`V28`: PCA-transformed features (anonymized)
- `Time`: Seconds elapsed between transactions
- `Amount`: Transaction value
- `Class`: Target variable  
  - `0` → Legitimate  
  - `1` → Fraud  

Due to confidentiality, original feature names are not available.

---

## Core Challenge

The dataset is **extremely imbalanced**:
- Fraud cases < 0.2% of total data

Implications:
- Accuracy is misleading
- Models tend to ignore the minority class
- Special handling is required to detect fraud effectively

---

## Approach

### 1. Data Processing
- Removed duplicates
- Split data into training and test sets
- Scaled numerical features

### 2. Feature Engineering
- Standardization using `StandardScaler`
- Consistent transformation applied to train and test sets

### 3. Model
- XGBoost Classifier
- Random Forest Classifier
- Handles non-linear relationships and feature interactions

### 4. Evaluation Metrics
- Precision
- ROC-AUC

## Results

XGBoost
- Precision: 0.836
- ROC-AUC: 0.975

RANDOM FOREST
- Precision: 0.82
- ROC-AUC: 0.936

### Interpretation
- The model successfully detects a high percentage of fraud cases
- Some false positives are expected due to prioritizing recall
- Performance reflects a trade-off between catching fraud and minimizing unnecessary alerts

---
