# EV Resale Price Prediction (CRISP-DM Capstone)

## Overview

This project applies the CRISP-DM framework to build a machine learning model for predicting the resale price of electric vehicles (EVs). The goal is to support data-driven pricing decisions in the used EV market.

---

## Business Problem

Accurate pricing of used EVs is challenging due to rapid technological changes and limited historical data. This project aims to estimate fair resale prices based on available vehicle attributes.

---

## Dataset

* Source: Provided CSV dataset (`car_price_prediction_.csv`)
* Total records: 2500
* EV records after filtering: 614
* Features include:

  * Brand, Model
  * Year, Engine Size
  * Mileage
  * Fuel Type
  * Transmission
  * Condition
  * Price (target variable)

---

## Methodology (CRISP-DM)

### 1. Business Understanding

Defined the objective of predicting EV resale prices to improve pricing accuracy and transparency.

### 2. Data Understanding

* Explored dataset structure and distributions
* Identified numerical and categorical features
* Visualized relationships (price vs mileage, year, brand, etc.)

### 3. Data Preparation

* Filtered dataset to include only EVs
* Removed irrelevant columns (e.g., Car ID)
* Applied preprocessing:

  * Missing value imputation
  * One-hot encoding for categorical variables
  * Feature scaling for numerical variables
* Train/test split (80/20)

### 4. Modeling

Trained and evaluated three models:

* Linear Regression (baseline)
* Random Forest Regressor
* XGBoost Regressor

### 5. Evaluation

| Model             | MAE      | RMSE     | R²    |
| ----------------- | -------- | -------- | ----- |
| Linear Regression | 23562.91 | 27812.98 | -0.10 |
| Random Forest     | 22952.72 | 26491.87 | 0.00  |
| XGBoost           | 23303.68 | 26971.21 | -0.03 |

**Key Findings:**

* All models showed low predictive performance
* High error rates (~$23k MAE)
* R² scores indicate poor variance explanation

### 6. Deployment

* Prototype prediction function created
* Potential deployment via web app or API
* Not production-ready due to low accuracy

---

## Key Insights

* Traditional vehicle features (mileage, engine size) are weak predictors for EV pricing
* Lack of EV-specific features (battery health, range) limits model performance
* Dataset size (614 EVs) restricts generalization

---

## Limitations

* Small EV-specific dataset
* Missing critical EV features
* Potential brand/model imbalance

---

## Future Work

* Collect richer EV-specific data (battery metrics, range, charging history)
* Apply advanced feature engineering
* Perform hyperparameter tuning
* Use cross-validation for robustness

---

## Technologies Used

* Python
* Pandas, NumPy
* Scikit-learn
* XGBoost
* Matplotlib, Seaborn

---

## Conclusion

This project demonstrates a complete machine learning workflow using CRISP-DM. While the current model performance is limited, the analysis highlights key challenges in EV price prediction and provides a strong foundation for future improvements.
