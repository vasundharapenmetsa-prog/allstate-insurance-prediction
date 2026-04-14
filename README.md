# Allstate Insurance Cost Prediction

Developed predictive models to understand and forecast insurance quote pricing for Allstate, analyzing 15,000+ customer quotes with extensive feature engineering and missing data handling.

![R](https://img.shields.io/badge/R-276DC3?style=flat&logo=r&logoColor=white)
![ggplot2](https://img.shields.io/badge/ggplot2-276DC3?style=flat)
![Statistics](https://img.shields.io/badge/Statistics-4B8BBE?style=flat)

---

## Business Problem

Allstate, one of the largest U.S. insurance providers, prices its quotes based on dozens of customer and vehicle attributes. Understanding the **drivers of insurance pricing** and building accurate cost prediction models helps both the insurer (optimize pricing strategies) and consumers (make informed purchasing decisions). This project analyzes Allstate's quoting behavior to predict the cost a customer will be quoted.

## Dataset

- **15,483 insurance quotes** across multiple customer interactions
- Features include: car age, car value, risk factor, state, homeowner status, marital status, coverage options (A through G), and previous policy details
- Significant missing data in risk_factor, duration_previous, and C_previous requiring careful imputation

## Methodology

### 1. Data Preparation & Missing Data Strategy
- Identified systematic missing data patterns (same observations missing across multiple fields)
- Created **dummy indicator variables** for missingness rather than simply dropping rows
- Converted categorical variables (car_value, state, risk_factor) to proper factor encoding
- Handled zero-inflated duration_previous values separately from true missing data

### 2. Exploratory Data Analysis
- Built interactive visualizations of car age vs. car value vs. coverage relationships
- Analyzed state-level pricing variation
- Examined correlation between risk factor, homeowner status, and quoted cost

### 3. Predictive Modeling
- **Linear Regression:** Baseline model with feature selection informed by EDA
- **LASSO Regression:** Regularized model to handle multicollinearity and perform automatic feature selection
- **Classification Trees:** Non-parametric approach to capture interaction effects between features
- Applied cross-validation for model comparison and selection

### 4. Business Insights
- Identified which features most strongly drive Allstate's pricing algorithm
- Quantified the premium associated with risk factors, car characteristics, and demographics
- Analyzed how previous policy details (duration, coverage) influence new quotes

## Project Structure

```
allstate-insurance-prediction/
|-- scripts/
|   |-- 01_data_preparation.R
|   |-- 02_eda_and_visualization.R
|   |-- 03_predictive_modeling.R
|-- data/
|   |-- ALLSTATEcost.csv
|-- reports/
|   |-- case_writeup.pdf
|-- README.md
```

## Tools Used

**Language:** R
**Libraries:** ggplot2, dplyr, caret, glmnet (LASSO), rpart
**Techniques:** Linear Regression, LASSO, Decision Trees, Cross-Validation, Missing Data Imputation
**Domain:** Insurance Analytics, Pricing Optimization, Risk Modeling

## Key Takeaways

- Missing data in insurance datasets is often **informative, not random** — the fact that a field is missing (e.g., no prior policy duration) signals something about the customer, making dummy indicators valuable features
- State-level variation in pricing reflects regulatory environments and competitive dynamics, not just risk
- Tree-based models captured important **interaction effects** (e.g., young car + high risk factor) that linear models missed

---

*Duke University — MQM Program | Data Science for Business*
