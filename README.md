# Cancelled-Orders-Analysis-and-Prediction-
Predicting and analyzing Amazon order cancellations with EDA, statistical tests, and a high-recall ML model

Dataset- https://www.kaggle.com/datasets/zahidmughal2343/amazon-sales-2025

## Introduction 
Cancelled orders are a challange for e-commerce platforms, impacting revenue, logistics, and customer satisfaction. 
This project explores a Kaggle dataset of Amazon orders to analyze predictors of cancellations using exploratory data analysis, statistical testing, and machine learning classification.

## Objectives 
- Explore trends in each predictor
- Build a predictive model to flag orders at risk of cancellation and improve logistics planning

  ## Methods
  - **Data Cleaning**- Remove irrelavent fields
  - **Exploratory Analysis**: Cancellation rates by product category and payment method, cancellation vs. price.  
- **Statistical Testing**: Performed chi-square tests for categorical predictors and Pearson correlation for numerical variables  
- **Modeling**: Logistic Regression with preprocessing pipeline (imputation + one-hot encoding); threshold tuned to prioritize recall

  ## Insights
  - **Product Category** - Electronics and home appliances appeared in most cancelled orders but the chi-square test indacted there was no statistically significant association between product type and order cancellation. (p-value = 0.77)
  - **Payment Methof**- Debit cards and Gift cards appeared most in cancelled orders and the chi-square test indicates there is a tatistically significant association between payment method and order status.(p-value = 0.0041)
    - **Price**- No meaningful relationship between price and cancellation likelihood (R² = 0.0049)
    - **Model** - Logistic Regression flagged ≈93% of cancelled orders (high recall) by lowering the decision threshold from 0.5 to 0.25. This was intentional to prioritize recall over precision, ensuring fewer cancellations are missed and giving operations teams early warning to manage logistics.
   
  **Tech Stack**
  - Language - Python
  - Data Handling: pandas, numpy
  - Visualization- matplotlib, seaborn
  - Statistical testing- SciPy ('chi2_contingency','pearsonr')
  - Machine Learning-  scikit-learn (Logistic Regression, preprocessing pipeline)  
