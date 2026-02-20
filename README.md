## Team ID-LTVIP2026TMIDS87096
### Project - Online Payments Fraud Detection using ML
### Team Members 1 Alikepalli Harsha Vardhan Reddy(22BFA05004)  2 Gurusai Gudi (22BFA05044)    3 Vamsi Hari Krishna Pandra (22BFA05053) 

---
# LINKS:
- Video link:  https://1drv.ms/v/c/fcf39855090e6d41/IQDLh79RAdgoQ6IG0v8U5AuzAfhqbbnU-tfuBgldHErN2Jw?e=Houzmg
- datasetlink: https://www.kaggle.com/datasets/rupakroy/online-payments-fraud-detection-dataset
# 🛡️ Online Payments Fraud Detection using Machine Learning

A complete Machine Learning + Flask web application that detects fraudulent online payment transactions using multiple ML algorithms and deploys the selected model for real-time prediction.

---

## 🎯 Project Overview

This project builds a fraud detection system using historical online transaction data.  
Multiple machine learning models were trained and compared, and the selected model was deployed using a Flask web application for real-time fraud detection.
After comparison, the Support Vector Machine (SVC) model was selected and deployed using a Flask web application for real-time fraud prediction.
---

## 🚀 Key Features

- Real-time fraud prediction using Flask
- Trained 5 ML models:
  - Random Forest
  - Decision Tree
  - Extra Trees
  - Support Vector Machine (SVC)
  - XGBoost
- Model comparison using Accuracy & Cross Validation
- Stratified train-test split
- Class imbalance handling
- Model saved using Pickle
- Clean Flask-based UI (Home → Predict → Result)
- Final deployed model: Support Vector Machine (SVC)
---

## 📊 Dataset Features

Dataset: Online Payments Fraud Detection (Kaggle)

Features used:

| Feature | Description |
|----------|-------------|
| step | Time unit of transaction |
| type | Transaction type (Encoded 0–4) |
| amount | Transaction amount |
| oldbalanceOrg | Sender balance before transaction |
| newbalanceOrig | Sender balance after transaction |
| oldbalanceDest | Receiver balance before transaction |
| newbalanceDest | Receiver balance after transaction |
| isFraud | Target (0 = Not Fraud, 1 = Fraud) |

---

## 🧠 Machine Learning Models Trained

The following models were trained and evaluated:

- RandomForestClassifier
- DecisionTreeClassifier
- ExtraTreesClassifier
- Support Vector Machine (SVC with StandardScaler)
- XGBoostClassifier (with scale_pos_weight for imbalance)

---

## 📈 Model Evaluation

Evaluation metrics used:

- Accuracy
- Confusion Matrix
- Classification Report
- 5-Fold Cross Validation

### Example Performance (Approximate)

| Model | Accuracy |
|--------|----------|
| Random Forest | ~99% |
| Decision Tree | ~99% |
| Extra Trees | ~99% |
| SVC | ~94% |
| XGBoost | ~99% |

⚠ Note: Dataset is highly imbalanced (Fraud ≈ 0.2%), so precision and recall were also analyzed.

---

## 🏗️ Project Structure

```
online_payments_fraud_detection/
│
├── data/
│   └── PS_20174392719_1491204439457_log.csv
│
├── model/
│   └── payments.pkl
│
├── templates/
│   ├── home.html
│   ├── predict.html
│   └── submit.html
│
├── app.py
├── training.py
└── README.md
```

---

## 🔧 Technical Implementation

### 1️⃣ Data Preprocessing

- Dropped unnecessary columns:
  - nameOrig
  - nameDest
  - isFlaggedFraud
- Label Encoding applied to `type`
- Stratified train-test split (80% / 20%)

---

### 2️⃣ Handling Class Imbalance

- Used:
  - `class_weight='balanced'`
  - `scale_pos_weight` (XGBoost)

---

### 3️⃣ Model Saving

```python
pickle.dump(svc, open("model/payments.pkl", "wb"))
```

---

## 🌐 Running the Flask Application

### Step 1: Navigate to project folder

```bash
cd online_payments_fraud_detection
```

### Step 2: Run Flask app

```bash
python app.py
```

### Step 3: Open Browser

```
http://127.0.0.1:5000/
```

---

## 🖥️ Web Application Flow

1. Home Page → Introduction  
2. Click Predict  
3. Enter 7 transaction details  
4. Click Detect Fraud  
5. View Result:
   - ✅ Not Fraud
   - ⚠ Fraud Transaction  

---

## 🔍 Confusion Matrix Meaning

| Term | Meaning |
|------|---------|
| True Positive | Fraud correctly detected |
| True Negative | Normal correctly detected |
| False Positive | Normal marked as Fraud |
| False Negative | Fraud missed |

---

## 📦 Requirements

Install dependencies:

```bash
pip install pandas numpy scikit-learn flask xgboost
```

Or install using:

```bash
pip install -r requirements.txt
```

---

## ⚠ Important Notes

- Dataset is highly imbalanced.
- Accuracy alone is not enough for fraud detection.
- Precision & Recall are critical metrics.

---

## 📚 Learning Outcomes

- Handling Imbalanced Datasets
- Comparing Multiple ML Models
- Using Stratified Train-Test Split
- Deploying ML model using Flask
- Building End-to-End ML Pipeline

---
##  👥 Contributing
- Contributions are welcome! Please feel free to submit a Pull Request.

## 📜 License

This project is for educational purposes only.
