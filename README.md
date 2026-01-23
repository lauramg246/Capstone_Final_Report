# Telco Customer Churn Prediction - Capstone Project

## Project Overview

This capstone project focuses on predicting customer churn for a telecommunications company using machine learning classification models. The goal is to identify customers who are likely to cancel their service, enabling proactive retention strategies.

**Dataset**: Telco Customer Churn dataset with 7,043 customer records  
**Problem Type**: Binary Classification (Churn vs. No Churn)  
**Churn Rate**: ~27% (imbalanced dataset)

---

## Key Objectives

1. **Data Exploration**: Understand customer behavior patterns and churn drivers
2. **Feature Engineering**: Prepare and preprocess customer data for modeling
3. **Model Development**: Train and compare multiple classification algorithms
4. **Model Optimization**: Tune hyperparameters to maximize predictive performance
5. **Business Insights**: Identify actionable factors that influence customer retention

---

## Project Structure

The project is organized into four main steps:

1. **Step 1: Data Wrangling** (`Capstone_two_step_1_data_wrangling.ipynb`)
   - Data loading and initial cleaning
   - Handling missing values and data type conversions

2. **Step 2: Exploratory Data Analysis** (`Capstone_two_step_2_eda.ipynb`)
   - Statistical analysis and visualizations
   - Identification of churn patterns and correlations

3. **Step 3: Preprocessing** (`Capstone_two_step_3_preprocessing_training_data.ipynb`)
   - Feature encoding (one-hot encoding for categorical variables)
   - Feature scaling (StandardScaler for numeric features)
   - Train-test split (80/20)

4. **Step 4: Model Evaluation** (`Capstone_two_step_4_model_evaluation.ipynb`)
   - Model training and comparison (KNN, Random Forest, Gradient Boosting)
   - Hyperparameter tuning
   - Final model selection and evaluation

---

## Final Model Performance

**Selected Model**: Gradient Boosting Classifier (Tuned)

| Metric | Value |
|--------|-------|
| **ROC-AUC** | **0.865** (86.5%) |
| **Accuracy** | 0.813 (81.3%) |
| **Precision** | 0.700 (70.0%) |
| **Recall** | 0.531 (53.1%) |
| **F1 Score** | 0.604 (60.4%) |

> **Note**: The model prioritizes recall and ROC-AUC, as missing a customer who will churn is more costly than a false alarm. Retention efforts can be applied to both true positives and false positives.

---

## Key Findings & Business Insights

### Top Predictors of Churn

1. **Tenure** (33% feature importance)
   - Newer customers are at significantly higher risk of churn
   - Customer loyalty increases substantially with longer tenure

2. **Contract Type**
   - Month-to-month contracts show the highest churn risk
   - Two-year contracts provide strong retention protection
   - One-year contracts offer moderate protection

3. **Internet Service Type**
   - Fiber optic customers have elevated churn risk (likely due to higher costs or service issues)
   - Customers without internet service show lower churn rates

4. **Payment Method**
   - Electronic check payments are associated with higher churn
   - Automatic payment methods (credit card) show better retention

5. **Additional Services**
   - Customers with Online Security and Tech Support show lower churn rates
   - These services may increase customer satisfaction and stickiness

### Critical Customer Segments at Risk

- **New customers** (low tenure) on **month-to-month contracts**
- Customers with **fiber optic internet** service
- Customers paying via **electronic check**
- Customers **without** online security or tech support services

---

## Recommendations for Customer Retention

1. **Target New Customers**: Implement onboarding programs and early engagement strategies for customers in their first few months

2. **Promote Long-Term Contracts**: Offer incentives (discounts, perks) to convert month-to-month customers to annual or two-year contracts

3. **Improve Fiber Optic Experience**: Investigate service quality issues and pricing concerns for fiber optic customers

4. **Encourage Automatic Payments**: Provide incentives for customers to switch from electronic check to automatic payment methods

5. **Bundle Value-Added Services**: Promote online security and tech support as retention tools, not just revenue generators

---

## Technical Highlights

- **Models Compared**: K-Nearest Neighbors, Random Forest, Gradient Boosting
- **Ensemble Methods**: Outperformed KNN significantly on this tabular dataset
- **Hyperparameter Tuning**: GridSearchCV used to optimize model parameters
- **Feature Engineering**: 30 engineered features from original dataset
- **Data Preprocessing**: StandardScaler for numeric features, one-hot encoding for categorical variables

---

## Project Files

- **Notebooks**: Four Jupyter notebooks covering the complete ML pipeline
- **Model Metrics**: `Model_Metrics.md` - Detailed model performance and configuration
- **Data Files**: Preprocessed datasets and train/test splits
- **Instructions**: Project requirements and rubric

---

## Model Selection Rationale

Gradient Boosting was selected as the final model because it:
- Achieved the highest **ROC-AUC score (0.865)**, indicating excellent ranking ability
- Demonstrated the best **recall (53.1%)** for churn detection
- Showed strong performance on imbalanced data
- Provided interpretable feature importance rankings
- Required minimal tuning, indicating robust default parameters

The model's 53% recall on churners means it can identify over half of customers who will churn, allowing the business to proactively engage with these high-risk customers.

*For detailed model metrics, hyperparameters, and feature information, see [Model_Metrics.md](Model_Metrics.md)*