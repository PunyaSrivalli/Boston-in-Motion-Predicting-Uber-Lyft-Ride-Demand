# Boston in Motion: Predicting Uber & Lyft Ride Demand

## Overview
This project explores the dynamics of the ride-sharing industry, focusing on Uber and Lyft. Using a Kaggle dataset with over 690,000 ride records, we built predictive models to analyze ride prices and optimize profitability while maintaining customer satisfaction.

---

## Table of Contents
1. [Objectives](#objectives)
2. [Dataset](#dataset)
3. [Key Methodologies](#key-methodologies)
    - [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
    - [Feature Engineering](#feature-engineering)
    - [Machine Learning Models](#machine-learning-models)
4. [Classification Strategy](#classification-strategy-ride-price-categorization)
5. [Results](#results)
6. [Future Scope](#future-scope)
7. [Tools & Libraries](#tools--libraries)

---

## Objectives
- Develop machine learning models to predict ride prices with high accuracy.
- Understand factors influencing pricing and demand patterns.
- Enhance customer experience and revenue for ride-sharing platforms.

---

## Dataset
- **Source**: Kaggle
- **Scope**: Uber and Lyft ride data (November–December 2018)
- **Size**: 693,071 rows and 57 columns
  - Numerical: 46 features
  - Categorical: 10 features
  - Target: `price`

---

## Key Methodologies
### Exploratory Data Analysis (EDA)
- Analyzed correlations between features and price.
- Performed time-series analysis of surge multipliers and ride distributions.
- Identified popular source-destination combinations and cab type usage trends.

### Feature Engineering
1. **Handling Missing Values**: Removed 0.139% of missing records.
2. **Feature Selection**: 
   - Correlation matrix for numerical features.
   - ANOVA for categorical features, reducing to key predictors.
3. **Encoding**: Applied One-Hot Encoding for selected categorical features.
4. **Scaling**: Standardized features using `StandardScaler`.

### Machine Learning Models
#### Regression
- **Linear Regression**: Baseline model for continuous predictions.
- **Polynomial Regression**: Captured non-linear relationships (best degree: 3).
- **Ridge & Lasso Regression**: Reduced overfitting with regularization techniques.
- **Support Vector Regression (SVR)**: Modeled non-linear relationships with optimal parameters (C=100, gamma=0.1).
- **Decision Tree**: Tuned for depth (max_depth=20).
- **Random Forest**: Best performance with RMSE = 1.79 (150 estimators, max_depth=19).

## Classification Strategy: Ride Price Categorization

To better analyze and predict ride prices, the continuous price variable was classified into six distinct categories based on price ranges. This approach simplifies the prediction problem, making it easier to identify patterns and trends in ride pricing. The classification scheme is as follows:

| **Class**        | **Price Range** |
|-------------------|-----------------|
| **Very Low**      | $0–$5           |
| **Low**           | $5–$10          |
| **Below Average** | $10–$15         |
| **Average**       | $20–$25         |
| **High**          | $25–$30         |
| **Very High**     | Above $30       |

### Purpose of Classification
- **Simplified Insights**: By grouping the price into categories, the analysis reveals insights into ride trends, such as the factors contributing to "High" or "Very High" price ranges.
- **Improved Model Performance**: Classification models like Decision Tree, Random Forest, and XGBoost can effectively work with these categorical labels, enabling accurate prediction of price categories.
- **Enhanced Decision-Making**: Ride-sharing companies can target specific customer segments by understanding the distribution of rides across these categories.

---

## Results
- **Best Regression Model**: Random Forest Regressor (RMSE = 1.79)
- **Best Classification Model**: XGBoost
- Feature correlations revealed:
  - Strong influence of `distance`, `surge_multiplier`, and `visibility`.
  - Source and destination had significant categorical impacts.

---

## Future Scope
- Incorporate NLP techniques to analyze trip summaries and improve model insights.
- Perform time-series analysis for hourly, daily, and monthly revenue predictions.
- Extend models to predict real-time ride demand and optimize dynamic pricing.

---

## Tools & Libraries
- **Programming**: Python
- **Libraries**: Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn, XGBoost, Folium
- **Editor**: Jupyter Notebook

