# 🚲 Bike Sharing Assignment - Linear Regression Model

## Project Overview

This project focuses on building a **Linear Regression** model to predict the daily demand for shared bikes in the American market. The data is sourced from a bike-sharing system and includes various features like **season**, **weather conditions**, **temperature**, and **humidity** that may influence bike rentals.

The goal is to:
- **Model the demand** for shared bikes based on given features.
- **Identify significant factors** affecting bike demand.
- **Predict future demand** to help BoomBikes optimize operations.

---

## Dataset Description

The dataset used is **`day.csv`**, which includes daily bike rental counts along with various independent variables.

### Key Variables:
- **`cnt`**: Total count of bike rentals (target variable).
- **`temp`**: Normalized temperature in Celsius.
- **`atemp`**: "Feels-like" temperature in Celsius.
- **`hum`**: Humidity level.
- **`windspeed`**: Wind speed.
- **`season`**: Categorical (1: Spring, 2: Summer, 3: Fall, 4: Winter).
- **`weathersit`**: Weather situation (1: Clear, 2: Mist, 3: Light Snow/Rain, 4: Heavy Rain).
- **`yr`**: Year (0: 2018, 1: 2019).
- **`holiday`**: Whether the day is a holiday (1) or not (0).
- **`workingday`**: Whether the day is neither a weekend nor a holiday (1) or not (0).

---

## ⚙️ Methodology

1. **Data Preprocessing:**
   - Conversion of categorical variables into dummy variables using **`drop_first=True`** to avoid multicollinearity.
   - Dropping unnecessary columns like **`instant`**, **`dteday`**, **`casual`**, and **`registered`**.

2. **Exploratory Data Analysis (EDA):**
   - Distribution plots and pair plots to understand variable relationships.
   - Correlation heatmaps to identify strongly correlated variables.

3. **Feature Engineering:**
   - Handling multicollinearity by calculating **Variance Inflation Factor (VIF)** and removing variables with high VIF.
   - Iteratively dropping **`atemp`**, **`hum`**, and **`mnth`** to reduce multicollinearity.

4. **Model Building:**
   - Building a **Linear Regression** model using **`statsmodels.OLS`**.
   - Evaluating the model using **R-squared** and **RMSE**.

5. **Model Validation:**
   - Checking linear regression assumptions:
     - Linearity
     - Normality of residuals (Q-Q Plot)
     - Homoscedasticity
     - Independence of errors (Durbin-Watson test)
     - Multicollinearity (VIF)

---

## Model Performance

- **R-squared (Test Set):** 0.8293  
- **RMSE (Test Set):** 794.64  

The model explains ~83% of the variance in bike rentals, indicating strong predictive power.

---

## Key Insights

- **Temperature (`temp`)** has the highest positive impact on bike rentals.
- **Adverse weather conditions** (e.g., **`weathersit_light_snow_rain`**) significantly reduce demand.
- **Seasonality** plays a major role, with **spring** having the lowest rentals.
- **Year-on-Year growth** is evident, as bike usage increased significantly in 2019.

---
