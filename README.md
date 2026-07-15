https://colab.research.google.com/github/R-WEB-netizen/tutedude.6/blob/main/forecasting.ipynb

 Model Performance Comparison

Among the four forecasting models evaluated, **Linear Regression achieved the best performance with an R² score of 0.16**, indicating that it explained approximately 16% of the variation in coffee sales. Although this level of predictive accuracy is modest, it outperformed all of the time-series models evaluated in this study.

Both **ARIMA** and **Prophet** produced slightly negative R² scores (-0.0077), indicating that they performed marginally worse than a simple mean prediction. This suggests that the sales series did not contain strong temporal patterns such as trend or autocorrelation that these models could effectively exploit.

**SARIMA** performed the worst (R² = -1.048). This indicates that the assumed seasonal structure did not match the characteristics of the dataset, resulting in forecasts that were substantially less accurate than the baseline mean prediction.

Overall, Linear Regression was the most suitable model for this dataset because the available calendar-based features provided more useful predictive information than the historical time-series structure alone. However, the relatively low R² also indicates that additional business variables—such as promotions, holidays, weather, pricing, or customer traffic—would likely be needed to achieve more accurate forecasts.


# Coffee Sales Forecasting

## Project Overview

This project analyzes a coffee sales dataset to identify sales trends, seasonality, and forecast future sales using time-series forecasting techniques.

## Dataset

* **Dataset:** Coffee Sales Dataset
* **Features:** Date, Money (Sales), Coffee Name, Cash Type, Card

## Data Preprocessing

* Checked the dataset for missing values.
* Converted the **Date** column to the datetime format.
* Extracted time-based features including **Year**, **Month**, **Day**, **Week**, **Quarter**, and **Is_Weekend**.
* Sorted the dataset chronologically for time-series analysis.

## Exploratory Data Analysis

* Visualized the sales trend over time.
* Examined monthly average sales to identify seasonal patterns.
* Checked for missing values using summary statistics and visualizations.

### Findings

* No missing values were found in the dataset.
* Daily sales showed noticeable fluctuations over time.
* Monthly average sales showed only minor differences between months, indicating **no strong seasonal pattern** in the available data.
* The dataset did not exhibit a clear long-term upward or downward sales trend.

## Models Implemented

* Linear Regression
* ARIMA
* SARIMA
* Prophet

## Model Evaluation

The models were evaluated using:

* Mean Absolute Error (MAE)
* Root Mean Squared Error (RMSE)
* R² Score

### Results

* The forecasting models produced relatively high prediction errors.
* The R² scores were negative, indicating that the models performed worse than predicting the average sales value.
* This suggests that the available features and historical data were insufficient to accurately model the sales behavior.

## Conclusion

The project demonstrates the complete workflow for time-series forecasting, including data preprocessing, visualization, model development, and evaluation. Although the models did not achieve strong predictive performance, the analysis highlights the importance of feature engineering, longer historical datasets, and model tuning. Future improvements could include incorporating external factors such as holidays, promotions, weather, and customer demand, as well as optimizing forecasting model parameters.


### Discussion of Negative R² Scores

All forecasting models produced a **negative R² score**, indicating that their predictions were less accurate than simply predicting the average sales value for every observation. This suggests that the models were unable to capture the underlying patterns in the dataset effectively.

Several factors may have contributed to this result:

* The dataset may not contain a strong trend or seasonal pattern, making future sales difficult to predict.
* The model used only basic date-based features (such as Year, Month, and Day), while important factors influencing coffee sales (e.g., promotions, holidays, weather, customer traffic, or product type) were not included.
* The sales data contains high day-to-day variability or random fluctuations that simple forecasting models cannot explain.
* The dataset may be relatively small or cover a limited time period, reducing the model's ability to learn meaningful patterns.
* Some forecasting models, particularly ARIMA and SARIMA, require careful parameter tuning. Using default parameters (such as ARIMA(1,1,1) or SARIMA(1,1,1)(1,1,1,12)) may not produce the best results for the dataset.

To improve forecasting performance, future work could include collecting a larger historical dataset, incorporating additional explanatory variables, identifying the appropriate seasonal period, tuning model parameters using methods such as grid search or AIC/BIC optimization, detecting and handling outliers, and experimenting with more advanced forecasting models such as XGBoost, LightGBM, LSTM, or Prophet with tuned seasonal settings.

Overall, the negative R² scores indicate that the current models are not suitable for accurately forecasting this dataset without further feature engineering and model optimization.


## Model Comparison and Recommendation

Four forecasting models were evaluated: **Linear Regression, ARIMA, SARIMA, and Prophet**. Their performance was compared using **MAE**, **RMSE**, and **R² Score**.

* **Linear Regression:** Simple and fast to train, but it assumes a linear relationship and is not well suited for complex time-series patterns.
* **ARIMA:** Effective for capturing trends in non-seasonal time-series data but requires careful selection of model parameters.
* **SARIMA:** Extends ARIMA by modeling seasonal effects, making it more suitable when the data contains recurring seasonal patterns.
* **Prophet:** Designed for business time-series forecasting and can automatically model trend and seasonality with minimal manual tuning.

The best-performing model should be the one with:

* **Lowest MAE**
* **Lowest RMSE**
* **Highest R² Score**

In this project, all models produced relatively poor performance (including negative R² scores), indicating that none of them captured the underlying sales patterns effectively. Therefore, **no single model can be recommended as a highly accurate forecasting solution for this dataset in its current form**.

Among the evaluated models, the recommended model should be the one that achieved the **lowest RMSE and MAE and the highest R² score**, even if its performance was still limited. Future improvements could include additional feature engineering, a longer historical dataset, parameter tuning, and incorporating external variables such as holidays, promotions, weather, or customer demand to improve forecasting accuracy.



### Statistical Validation of Model Assumptions

Before fitting the ARIMA/SARIMA model, the stationarity assumption was evaluated using the **Augmented Dickey-Fuller (ADF) test**. The ADF test checks whether the time series has a constant mean and variance over time.

* **Null Hypothesis (H₀):** The time series is non-stationary.
* **Alternative Hypothesis (H₁):** The time series is stationary.

The test results were interpreted using the p-value:

* If **p < 0.05**, the null hypothesis is rejected and the series is considered stationary.
* If **p ≥ 0.05**, the series is considered non-stationary, and first-order differencing was applied before fitting the ARIMA/SARIMA model.

This validation ensures that the model assumptions are checked before forecasting, improving the reliability of the analysis.

## Feature Selection and Importance

The Linear Regression model was trained using the following features extracted from the **Date** column:

* **Year:** Captures long-term changes in sales over multiple years.
* **Month:** Helps identify monthly or seasonal variations in sales.
* **Day:** Represents daily changes that may influence sales.
* **Week:** Captures weekly patterns in customer purchasing behavior.
* **Quarter:** Represents broader seasonal business cycles.
* **Is_Weekend:** Indicates whether a transaction occurred on a weekend, which may affect customer demand.

These features were selected because they are commonly used in time-series forecasting when only historical date information is available. They allow the model to learn temporal patterns without requiring additional external variables.

However, the model does not include other factors that can significantly affect coffee sales, such as:

* Promotions or discounts
* Holidays and festivals
* Weather conditions
* Store location
* Customer footfall
* Product category or coffee type

The absence of these variables may reduce the predictive accuracy of the Linear Regression model.

### Feature Importance

For Linear Regression, the importance of each feature can be assessed by examining the model coefficients. Features with larger absolute coefficient values have a greater influence on the predicted sales, while coefficients close to zero indicate a smaller impact.

Overall, the selected features provide a basic representation of time-related patterns, but incorporating additional business-related variables would likely improve forecasting performance.

plt.figure(figsize=(12,5))

plt.plot(residuals)

plt.axhline(0, color='red', linestyle='--')

plt.title("Residuals Over Time")
plt.xlabel("Observation")
plt.ylabel("Residual")

plt.grid(True)
plt.show()****

