# Bike Demand Prediction Using Multiple Linear Regression

## Table of Contents
* [General Information](#general-information)
* [Technologies Used](#technologies-used)
* [Methodology](#methodology)
* [Results](#results)
* [File Structure](#file-structure)
* [Assumptions](#assumptions)
* [Contact](#contact)

---

## General Information
This project involves predicting the daily demand for shared bikes based on various features such as weather, season, and day type. The aim is to help BoomBikes optimize their operations and enhance customer satisfaction. The dataset contains daily records of bike rentals and associated environmental and seasonal factors.

**Business Problem:**
BoomBikes seeks to identify significant factors influencing bike demand to adjust their business strategies and maximize profits.

**Dataset Highlights:**
- **Target Variable**: `cnt` - Total bike rentals per day.
- **Features**:
  - `season`, `weathersit`, `temp`, `hum`, `windspeed`
  - `holiday`, `workingday`, `weekday`, `mnth`, `yr`

---

## Technologies Used
- **Python**: Core programming language.
- **Libraries**:
  - `pandas` (1.3.0): Data manipulation and analysis.
  - `numpy` (1.21.0): Numerical operations.
  - `matplotlib` (3.4.2): Data visualization.
  - `seaborn` (0.11.2): Statistical data visualization.
  - `sklearn` (0.24.2): Model building and evaluation.
  - `statsmodels` (0.12.2): Statistical model analysis.

---

## Methodology
1. **Data Preprocessing**:
   - Mapped categorical variables (`season`, `weathersit`) to descriptive labels.
   - Dropped irrelevant columns: `instant`, `dteday`, `casual`, `registered`.
   - Created dummy variables for categorical features.

2. **Feature Engineering**:
   - Calculated Variance Inflation Factor (VIF) to address multicollinearity.
   - Retained significant features for model building.

3. **Model Building**:
   - Built and evaluated three models:
     - **Linear Regression**: Baseline model.
     - **Ridge Regression**: Tackled multicollinearity using L2 regularization.
     - **Lasso Regression**: Performed feature selection using L1 regularization.

4. **Evaluation Metrics**:
   - **R-squared**: Measures variance explained by the model.
   - **RMSE (Root Mean Squared Error)**: Measures average prediction error.

5. **Residual Analysis**:
   - Examined residuals to validate assumptions of linear regression.

---

## Results
### Model Performance
| Model            | R-squared (Test) | RMSE (Test) |
|-------------------|------------------|-------------|
| Linear Regression | 0.8291          | 796.24      |
| Ridge Regression  | 0.8290          | 796.32      |
| Lasso Regression  | 0.8260          | 800.45      |

### Key Insights
- **Significant Features**:
  - `yr`: Bike demand increased in 2019 compared to 2018.
  - `temp`: Higher temperatures positively correlate with demand.
  - `workingday`: Working days slightly increase demand.
  - `weathersit_Light Rain/Snow`: Reduces demand significantly.
- **Residual Analysis**:
  - Residuals are normally distributed, validating the model's assumptions.

---

## File Structure
- **`bike_demand_model.py`**: Contains the main Python script for data preprocessing, model building, and evaluation.
- **`README.md`**: This document describing the project.
- **`requirements.txt`**: List of required Python libraries.
- **`day.csv`**: The dataset used in the project.

---

## Assumptions
- The dataset is accurate and representative of actual bike rental demand.
- Linear relationships exist between features and the target variable.
- External factors like sudden weather changes are not accounted for in the model.

---

## Contact
Created by [Aparna G K] - feel free to contact me for questions or feedback!
- **Email**: aparna.nammi@gmail.com
- **GitHub**: [aparnaNammi](https://github.com/aparnaNammi)
