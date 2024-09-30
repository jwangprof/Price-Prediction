# Car Price Prediction

## Business Challenge

### Overview
The goal of this project is to **predict the price of cars** based on a wide range of attributes and features. We aim to develop a machine learning model that accurately estimates the price of different car models and understand the key factors influencing car pricing.

---

## Data Cleaning
In this section, we address issues related to the raw dataset, ensuring it is suitable for analysis and modeling.

- **Handling Missing Values**: Imputation or removal of missing data to avoid errors in model training.
- **Duplication Removal**: Identification and removal of duplicate entries in the dataset.
- **Null Value Handling**: Ensuring that all null values are appropriately dealt with to maintain data integrity.

---

## Exploratory Data Analysis (EDA)

### Univariate Analysis
- **Numerical Variables**: Frequency distribution of each numerical feature through histograms.
- **Categorical Variables**: Frequency distribution of categorical features using bar plots.

### Bivariate Analysis
- **Numerical X to Target Y**: Scatter plots and trend lines to explore relationships between numerical features and the target variable (price).
- **Categorical X to Target Y**: Box plots to analyze the impact of categorical features on the target variable (price).

### Multivariate Analysis
- **Correlation Matrix**: Analyzing the correlation between numerical features and the target variable.
- **Pair Plot**: Visualizing relationships and interactions between multiple numerical features.

---

## Data Processing and Transformation
This section covers the steps taken to prepare the data for model building.

- **Encoding**: Transforming categorical variables into numerical form using techniques such as one-hot encoding or label encoding.
- **Scaling**: Applying feature scaling to numerical variables to standardize their range.
- **Log-Transformation**: Logarithmic transformation of skewed numerical features to reduce the effect of outliers.
- **Feature Engineering**: Creating new features or modifying existing ones to improve model performance (e.g., creating `log_enginesize`, `power_to_weight_ratio`, etc.).

---

## Model Building
In this section, we compare two machine learning models: **Linear Regression** and **XGBoost**.

### Model Comparison
- **Linear Regression**: A baseline model that assumes a linear relationship between features and the target variable.
- **XGBoost**: A more advanced machine learning model that uses gradient boosting for improved performance.

### Comparison: Linear Regression vs. XGBoost

| Metric                           | Linear Regression       | XGBoost                |
|----------------------------------|-------------------------|------------------------|
| **Mean Absolute Error (MAE)**     | 3,411                   | 1,549                  |
| **Mean Squared Error (MSE)**      | 29,801,308              | 4,957,115              |
| **Root Mean Squared Error (RMSE)**| 5,459                   | 2,226                  |
| **R-squared (R²)**                | 0.622                   | 0.937                  |


### Evaluation of RMSE and MAE Relative to Price Statistics:

1. **RMSE (2,226) and MAE (1,549)** relative to the price distribution:
   - **Mean Price**: $13,276.71
   - **Median Price**: $10,295
   - The **RMSE of 2,226** indicates that, on average, the model’s predictions are off by $2,226. Given that the mean price is $13,276.71, this error represents **about 16.8%** of the average price. For the **median price of $10,295**, the RMSE is about **21.6%** of the median price.
   
   - The **MAE of 1,549** represents the average absolute error. This is about **11.7%** of the mean price, and **15%** of the median price. This is a reasonable level of error, suggesting the model performs well but still has room for improvement in terms of precision.

2. **Range of Prices**:
   - The prices range from **$5,118** to **$45,400**, so the RMSE of $2,226 is **relatively small** in comparison to the full range of prices. This means that even though the model may not predict exact values perfectly, its errors are relatively moderate given the overall range of car prices in the dataset.

3. **Variance Explained (R²)**:
   - With an **R² of 0.937**, the model explains **93.7%** of the variance in the price data. This high R² suggests that while the errors may seem noticeable, the model captures most of the underlying patterns in the data, making it highly effective in predicting prices.

### Conclusion:

- **MAE** and **RMSE** are **reasonable** relative to the price distribution. While there is some error, the model's predictions are within a range that is acceptable for many regression tasks, especially given the complexity of predicting car prices.
- The **RMSE** of 2,226 is not excessively high considering the mean and median prices. It suggests that the model is fairly accurate, especially given the wide range of prices in the dataset.
- **MAE** being lower than RMSE indicates that smaller errors are more common, but the model still makes some larger errors (which RMSE penalizes more).

Overall, the model’s performance is solid, particularly given the high R² value and the relatively low error metrics when compared to the price distribution. However, further optimization or feature engineering might reduce the error further if needed.
