# predicting_energy_consumption

This repository contains regression analysis for predicting energy consumption using machine learning techniques.

## Objective
The primary objective was to build a regression model to predict energy consumption (**Appliances**) based on various environmental and indoor conditions such as temperature, humidity, wind speed, and visibility.

---

## Dataset
**Filename:** `energydata_complete.csv`

The dataset contains 29 columns and 19,735 rows, including:
- **Target Variable:** `Appliances` (energy consumption in Wh)
- **Features:** Temperature (T1-T9), Humidity (RH_1-RH_9), Outdoor conditions (T_out, RH_out, Windspeed, Visibility, etc.)
- **Date:** Timestamp column

**Key Steps:**
1. Parsed the `date` column.
2. Normalized numerical columns using Min-Max Scaling.
3. Dropped irrelevant columns such as `rv1` and `rv2`.

---

## Steps Performed

### 1. Data Preprocessing
- Converted the `date` column to a datetime format.
- Normalized the features to bring all values to the same scale.
- Dropped redundant columns: `rv1` and `rv2`.

### 2. Feature Selection
- Correlation analysis was performed to select the top 10 features most correlated with the target variable (`Appliances`).
- Selected features:
  - `T2`, `RH_2`, `T_out`, `RH_out`, `T6`, `Windspeed`, `Visibility`, `Tdewpoint`, `T8`, and `T1`.

### 3. Model Building
- **Model Used:** Linear Regression
- **Libraries:** Scikit-learn
- Split the data into training (80%) and testing (20%) sets.

### 4. Model Evaluation
- **Metrics:**
  - Mean Squared Error (MSE): 0.0079
  - Root Mean Squared Error (RMSE): 0.0890
  - R-Squared (R²): 0.0929
- Observations:
  - The model explains only 9.29% of the variance in the target variable.
  - Errors are relatively low, but the R² score indicates potential for improvement with advanced models or feature engineering.

---

