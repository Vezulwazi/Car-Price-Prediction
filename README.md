# 🚗 Car Price Prediction

A beginner-level regression machine learning project that predicts the resale price of used cars in the Indian market using the CarDekho dataset.

---

## 📌 Problem Statement

Given a used car’s attributes such as:

- Year of manufacture  
- Present (ex-showroom) price  
- Kilometers driven  
- Fuel type  
- Seller type  
- Transmission  
- Number of previous owners  

The goal is to predict the **Selling Price (in lakhs INR)**.

---

## 📊 Dataset

- **Source:** CarDekho used car dataset (Krish Naik mirror)  
- **Samples:** 301 cars  
- **Features:** 8 input variables  

---

## 🧾 Features

- Car_Name → Dropped due to high cardinality  
- Year → Manufacturing year  
- Present_Price → Ex-showroom price (lakhs INR)  
- Kms_Driven → Total kilometers driven  
- Fuel_Type → Petrol / Diesel / CNG  
- Seller_Type → Dealer / Individual  
- Transmission → Manual / Automatic  
- Owner → Number of previous owners  

---

## 🔧 Feature Engineering

- Car_Age = 2020 - Year  
- Kms_per_Year = Kms_Driven / Car_Age  

---

## ⚙️ Workflow

- Exploratory Data Analysis (EDA)  
- Data cleaning and preprocessing  
- Feature engineering  
- Model training and comparison  
- Hyperparameter tuning (GridSearchCV)  
- Model evaluation  

---

## 🤖 Models Used

- Linear Regression  
- Ridge Regression  
- Lasso Regression  
- K-Nearest Neighbors (KNN)  
- Decision Tree Regressor  
- Random Forest Regressor  
- Gradient Boosting Regressor  

---

## 📈 Model Performance

| Model | MAE | RMSE | R² | MAPE |
|------|-----|------|----|------|
| Decision Tree | 1.05 | 2.04 | 0.839 | 0.314 |
| KNN (k=3) | 1.28 | 2.36 | 0.784 | 1.031 |
| Lasso | 1.44 | 2.47 | 0.763 | 1.138 |
| Ridge | 1.51 | 2.59 | 0.739 | 1.667 |
| Linear Regression | 1.51 | 2.60 | 0.737 | 1.694 |
| Gradient Boosting | 1.24 | 2.73 | 0.710 | 0.341 |
| Random Forest (Tuned) | 1.44 | 3.43 | 0.542 | 0.387 |
| Random Forest | 1.49 | 3.56 | 0.508 | 0.386 |

---

## 🏆 Key Insights

- Present_Price is the strongest predictor (~0.88 correlation with target)  
- Car_Age performs better than raw Year in tree models  
- Diesel cars generally have higher resale value than petrol/CNG  
- Individual sellers get lower prices than dealers  
- Small dataset (301 rows) causes variance between test and cross-validation results  

---

## 🧠 Best Model

- Random Forest (GridSearchCV tuned)  
- Parameters:
  - max_depth = None  
  - min_samples_leaf = 2  
  - n_estimators = 100  
- Cross-validation R² ≈ 0.867  

---

## 🛠 Tech Stack

- Python  
- pandas, numpy  
- matplotlib, seaborn  
- scikit-learn  

---

## 🚀 Getting Started

```bash
pip install -r requirements.txt
jupyter notebook 01_eda.ipynb
