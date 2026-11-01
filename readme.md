Telco Customer Churn Prediction –  V2 

This repository contains the V2 version of the Telco Customer Churn Prediction project. Moving beyond basic machine learning.

this version implements production-grade ML practices.

What's New in V2? 
1. SMOTE

Implemented SMOTE (Synthetic Minority Over-sampling Technique) to address class imbalance in the dataset. Balanced the minority class (churners) to improve model learning.
Increased the training dataset from 5,625 rows to 8,260 rows after oversampling.

2. Boosters Benchmarking
Trained and benchmarked powerful gradient boosting algorithms:

XGBoost
LightGBM
CatBoost

Compared their performance using multiple evaluation metrics to identify the most effective model.

3. Hyperparameter Optimization

Implemented RandomizedSearchCV and GridSearchCV with 5-fold cross-validation (cv=5).

Extracted optimal hyperparameters for the model:

4. Model Explainability

Integrated SHAP (SHapley Additive exPlanations) to interpret model predictions.

Generated: Global Feature Importance Bar Plots & SHAP Beeswarm Plots

Made the model's decision-making process more transparent and interpretable.

5. Issue Faced : Version Conflict,here's how i resolved it 

Resolved compatibility issues between modern XGBoost and SHAP.

Fixed the [5E-1] string parsing bug.

Established a stable machine learning pipeline using XGBoost 2.1.4.

## 📊 Key Findings & Results

### Top Churn Drivers (SHAP Analysis)

The SHAP analysis highlighted the following major factors influencing customer churn:

* **Tenure:** Customers with longer subscription periods are generally more likely to stay with the company.
* **InternetService_Fiber optic:** Fiber optic customers demonstrated a comparatively higher tendency to churn.
* **MonthlyCharges:** Higher monthly bills significantly influence customer churn, suggesting that pricing and affordability play an important role in customer retention.

### Final Model Performance Metrics (Tuned XGBoost)

To provide a clear benchmark for production deployment, the final optimized model was evaluated on the untouched test set ($N = 1,407$ rows):

* **Test ROC-AUC:** `0.8081`
* **Test Accuracy:** `75.48%` (`0.7548`)
* **Precision (Churn Class):** `0.5320`
* **Recall (Churn Class):** `0.6444`
* **F1-Score (Churn Class):** `0.5828`


