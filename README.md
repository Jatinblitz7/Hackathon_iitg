# 🧬 Vaccine Acceptance Prediction using ML Classifiers

This project builds machine learning models to predict individual responses to two vaccines (`xyz` and `seasonal`) based on a variety of demographic, behavioral, and health-related features. The primary goal is to estimate vaccine acceptance likelihoods and generate probability-based predictions for submission.

---

## 📌 Overview

- **Dataset:** Public health survey data containing demographic and behavioral details.
- **Targets:**
  - `xyz_vaccine`: Will the respondent take the xyz vaccine?
  - `seasonal_vaccine`: Will the respondent take the seasonal flu vaccine?
- **Models Used:**
  - Logistic Regression
  - Gradient Boosting Classifier
  - Support Vector Classifier (SVC)

---

## 🔍 Project Workflow

### 1. Data Preprocessing
- Categorical encoding for columns like `age_group`, `income_poverty`, `census_msa`, etc.
- Removal of low-value and high-cardinality columns.
- Missing value imputation using `SimpleImputer` (most frequent strategy).
- Columns grouped into:
  - Ordinal
  - Binary
  - Categorical

### 2. Splitting Data
- Training and testing split for model evaluation.
- Separate outputs for `xyz` and `seasonal` vaccine columns.

### 3. Model Training and Evaluation
| Model               | XYZ Accuracy | Seasonal Accuracy |
|--------------------|--------------|-------------------|
| Logistic Regression| 0.84         | 0.78              |
| Gradient Boosting  | **0.84**     | **0.79**          |
| SVC                | 0.84         | 0.79              |

- ROC curves and AUC scores were used to evaluate model performance:
  - `AUC_xyz`: 0.70
  - `AUC_seasonal`: 0.79

### 4. Prediction on Test Set
- Test set preprocessed similarly
- Predictions made using **Gradient Boosting Classifier**
- Probabilities extracted using `.predict_proba()`
- Results saved to `Predictions_Hackathon.csv`

### 📌 Future Improvements
- Hyperparameter tuning with GridSearchCV
- Use XGBoost or CatBoost for potentially better performance
- Feature engineering for domain-specific insights

---
