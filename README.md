# House Price Prediction & Quality Classification

## Project Overview

This project explores residential housing data to understand the factors that influence property values and to build predictive models for house prices and overall property quality.

The analysis covers the complete machine learning workflow, including data preprocessing, exploratory data analysis, feature selection, regression modeling, classification, class imbalance handling, and model evaluation.

Two predictive problems are addressed:

1. Predicting house sale prices using regression models.
2. Classifying houses by overall quality using machine learning classification.

## Business Problem

Property values are influenced by multiple characteristics such as lot size, garage area, finished basement area, number of bathrooms, fireplaces, and overall construction quality.

The goal of this analysis is to use these property characteristics to:

- Identify important factors associated with house prices
- Build models capable of predicting sale prices
- Classify houses based on overall quality
- Compare multiple machine learning approaches
- Evaluate model performance using appropriate regression and classification metrics

## Dataset

The project uses separate training and test datasets containing residential property information.

Key variables include:

- Lot Area
- Year Sold
- Remodel Year
- Finished Basement Area
- Full Bathrooms
- Half Bathrooms
- Bedrooms
- Total Rooms
- Garage Area
- Fireplaces
- Overall Quality
- Sale Price

The training dataset contains **900 observations**, while the test dataset contains **90 observations**.

## Tools & Technologies

- R
- R Markdown
- Data Visualization
- Multiple Linear Regression
- Random Forest
- XGBoost
- Feature Engineering
- Statistical Analysis
- Predictive Modeling
- Model Evaluation

## Data Preparation

Before modeling, the data was reviewed and prepared for analysis.

The preprocessing workflow included:

- Checking for missing values
- Checking for duplicate observations
- Removing unnecessary variables
- Transforming selected variables
- Converting categorical variables to factors
- Preparing features for regression and classification
- Evaluating relationships among predictors for potential multicollinearity

No missing values or duplicate observations were identified in the provided datasets.

## Exploratory Data Analysis

Exploratory analysis was performed to better understand housing characteristics and their relationships with sale price and overall quality.

The analysis examined:

- Distribution of house sale prices
- Garage area and finished basement area
- Distribution of overall house quality
- Remodel year patterns
- Number of bathrooms
- Overall quality versus finished area
- Sale prices across years
- Relationships between property characteristics and sale price

### Key EDA Findings

- Most house sale prices were concentrated roughly between **$150K and $250K**.
- Larger lot sizes generally showed higher property values.
- Larger garage areas were associated with higher sale prices.
- Houses with two full bathrooms generally commanded higher prices than houses with one.
- Properties with fireplaces tended to have higher sale prices.
- Higher overall property quality was generally associated with larger finished areas.
- Sale prices did not show substantial variation across the observed sale years.

## Modeling Approach

### 1. House Price Prediction

Two regression approaches were evaluated for predicting `SalePrice`:

- Multiple Linear Regression
- Random Forest Regression

Model performance was evaluated using:

- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R-squared

### Regression Model Results

| Model | MSE | RMSE | R-squared |
|---|---:|---:|---:|
| Multiple Linear Regression | 562,829,945 | 23,724.04 | 85.26% |
| Random Forest | 737,299,256.28 | 27,153.25 | 81.20% |
| Tuned Random Forest | 737,299,256.28 | 27,153.25 | 81.20% |

Among the evaluated regression models, **Multiple Linear Regression produced the strongest performance**, achieving the lowest RMSE and the highest R-squared value.

## House Quality Classification

The second modeling problem focused on classifying `OverallQual`.

Properties with an overall quality rating of **7 or above** were treated as the positive class, while lower ratings were assigned to the other class.

An **XGBoost classifier** was evaluated under three conditions:

- Without sampling
- With oversampling
- With undersampling

Sampling strategies were evaluated because the target classes were imbalanced.

### Classification Results

| Model | Accuracy | Sensitivity | Specificity |
|---|---:|---:|---:|
| XGBoost - No Sampling | 75.56% | 42.86% | 96.36% |
| XGBoost - Oversampling | 84.44% | 74.29% | 90.81% |
| XGBoost - Undersampling | 84.44% | 82.86% | 85.45% |

The undersampling approach provided the strongest balance between accuracy, sensitivity, and specificity.

This demonstrates how addressing class imbalance can significantly improve a model's ability to identify the minority class.

## Key Insights

The analysis produced several practical findings:

- House prices are influenced by a combination of property characteristics rather than a single factor.
- Lot size, garage area, finished area, bathrooms, bedrooms, fireplaces, and overall quality contribute to property value.
- Feature selection plays an important role in developing reliable predictive models.
- Multiple Linear Regression performed better than the evaluated Random Forest models for sale-price prediction.
- Class imbalance substantially affected classification performance.
- Sampling techniques improved XGBoost classification performance, particularly sensitivity.

## Repository Structure

```text
house-price-prediction-machine-learning/
│
├── house_prices_train.csv
├── house_prices_test.xlsx
├── house_price_modeling.Rmd
├── .gitignore
└── README.md
