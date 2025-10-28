# 🚕 Trip Price Prediction using Multiple Linear Regression

## 📝 Project Overview

This project focuses on predicting the **Trip Price** for a ride-sharing or taxi service using a dataset containing various trip characteristics. The primary goal is to build a robust **Multiple Linear Regression (MLR)** model and utilize **Recursive Feature Elimination (RFE)** to select the most impactful features for accurate prediction.

-----

## 📊 Dataset

The analysis is based on a dataset with **1000 observations** and **11 features**. The target variable is `Trip_Price`.

### **Feature Description**

| Feature Name | Description | Data Type | Notes |
| :--- | :--- | :--- | :--- |
| `Trip_Distance_km` | Total distance of the trip in kilometers. | Numerical | Contains missing values (NaN). |
| `Time_of_Day` | Categorical time frame (e.g., Morning, Afternoon, Evening). | Categorical | |
| `Day_of_Week` | Categorical day of the week (Weekday, Weekend). | Categorical | |
| `Passenger_Count` | Number of passengers on the trip. | Numerical | |
| `Traffic_Conditions` | Level of traffic (Low, Medium, High). | Categorical | |
| `Weather` | Weather conditions during the trip (e.g., Clear, Rainy). | Categorical | Contains missing values (NaN). |
| `Base_Fare` | The fixed starting cost of the trip. | Numerical | Contains missing values (NaN). |
| `Per_Km_Rate` | Cost charged per kilometer traveled. | Numerical | |
| `Per_Minute_Rate` | Cost charged per minute of the trip duration. | Numerical | |
| `Trip_Duration_Minutes` | Total time taken for the trip. | Numerical | |
| **`Trip_Price`** | **The final cost of the trip (Target Variable).** | Numerical | Contains missing values (NaN). |

-----

## 🛠️ Methodology and Analysis

### 1\. Exploratory Data Analysis (EDA)

  * **Initial data inspection:** Checked data types, unique values, and identified missing data points (NaNs) in columns like `Trip_Distance_km`, `Weather`, `Base_Fare`, and `Trip_Price`.
  * **Distribution Analysis:** Visualized the distribution of key numerical variables (e.g., `Trip_Distance_km`, `Trip_Price`, `Trip_Duration_Minutes`).
  * **Bivariate Analysis:** Examined relationships between independent variables and the target variable, `Trip_Price`, using techniques like box plots for categorical features and scatter plots for numerical features.

### 2\. Data Preprocessing

  * **Handling Missing Values:** Applied appropriate imputation techniques (e.g., mean/median for numerical, mode for categorical) to address the NaN values.
  * **Feature Encoding:** Converted categorical features (e.g., `Time_of_Day`, `Day_of_Week`, `Traffic_Conditions`, `Weather`) into numerical format using **One-Hot Encoding** to prepare them for the MLR model.
  * **Data Splitting:** Divided the processed data into training and testing sets.

### 3\. Model Building: Multiple Linear Regression (MLR)

  * A baseline **Multiple Linear Regression** model was established using all available processed features to predict `Trip_Price`.
  * The model aims to find a linear relationship in the form:
    $$\text{Trip Price} = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + \dots + \beta_n X_n + \epsilon$$

### 4\. Feature Selection: Recursive Feature Elimination (RFE)

  * To combat potential **multicollinearity** and improve the model's **interpretability and generalization**, **Recursive Feature Elimination (RFE)** was applied.
  * **RFE** works by repeatedly fitting the MLR model and removing the weakest feature (based on coefficients/p-values) until the desired number of features is reached.
  * The optimal number of features was determined by tracking the model's performance (e.g., $R^2$ or Adjusted $R^2$) on a cross-validation set.
  * The final, selected features represent the **most critical factors** influencing the trip price.

-----
