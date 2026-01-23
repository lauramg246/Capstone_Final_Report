# Telco Customer Churn Prediction - Final Model Metrics

## Final Model
**Gradient Boosting Classifier (Tuned)**

---

## Hyperparameters

- **learning_rate**: 0.05
- **max_depth**: 3
- **n_estimators**: 100
- **subsample**: 0.8
- **random_state**: 42

---

## Performance Metrics
*Test Set: 1,409 samples*

| Metric | Value | Percentage |
|--------|-------|------------|
| Accuracy | 0.8134 | 81.3% |
| Precision | 0.7000 | 70.0% |
| Recall | 0.5308 | 53.1% |
| F1 Score | 0.6038 | 60.4% |
| ROC-AUC | 0.8650 | 86.5% |

### Classification Report

```
              precision    recall  f1-score   support

    No Churn       0.84      0.92      0.88      1036
       Churn       0.70      0.53      0.60       373

    accuracy                           0.81      1409
```

---

## Features
*30 total features*

### Numeric Features (Scaled with StandardScaler)

1. tenure
2. MonthlyCharges
3. TotalCharges
4. SeniorCitizen

### Categorical Features (One-Hot Encoded, drop_first=True)

5. gender_Male
6. Partner_Yes
7. Dependents_Yes
8. PhoneService_Yes
9. MultipleLines_No phone service
10. MultipleLines_Yes
11. InternetService_Fiber optic
12. InternetService_No
13. OnlineSecurity_No internet service
14. OnlineSecurity_Yes
15. OnlineBackup_No internet service
16. OnlineBackup_Yes
17. DeviceProtection_No internet service
18. DeviceProtection_Yes
19. TechSupport_No internet service
20. TechSupport_Yes
21. StreamingTV_No internet service
22. StreamingTV_Yes
23. StreamingMovies_No internet service
24. StreamingMovies_Yes
25. Contract_One year
26. Contract_Two year
27. PaperlessBilling_Yes
28. PaymentMethod_Credit card (automatic)
29. PaymentMethod_Electronic check
30. PaymentMethod_Mailed check

---

## Feature Importance
*Top 10 - Ranked by Importance*

| Rank | Feature |
|------|---------|
| 1 | tenure |
| 2 | MonthlyCharges |
| 3 | TotalCharges |
| 4 | Contract_Two year |
| 5 | InternetService_Fiber optic |
| 6 | Contract_One year |
| 7 | PaymentMethod_Electronic check |
| 8 | OnlineSecurity_Yes |
| 9 | TechSupport_Yes |
| 10 | PaperlessBilling_Yes |

> **Note:** Exact importance values are computed when running the Jupyter notebook

---

## Data Split

- **Training Set**: 5,634 samples (80%)
- **Testing Set**: 1,409 samples (20%)
- **random_state**: 42

---

## Preprocessing Steps

1. **Missing Value Handling**: TotalCharges empty strings filled with MonthlyCharges
2. **Feature Encoding**: `pd.get_dummies()` with `drop_first=True`
3. **Feature Scaling**: StandardScaler on tenure, MonthlyCharges, TotalCharges

