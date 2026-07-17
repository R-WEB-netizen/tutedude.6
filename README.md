https://colab.research.google.com/github/R-WEB-netizen/tutedude.6/blob/main/forecasting.ipynb
## Dataset Exploration

The sales dataset was successfully imported and explored. The data types, missing values, and summary statistics were examined. The date column was converted into the appropriate datetime format, enabling time series analysis. Trend and seasonality plots were generated to understand the overall sales pattern over time.

## Data Preprocessing

The dataset was cleaned by handling missing values using appropriate techniques. The date column was converted to datetime format, and additional features such as year, month, day, and day of the week were extracted for feature engineering. These preprocessing steps improved the quality of the data and prepared it for forecasting.

## Model Development

The dataset was divided into training (80%) and testing (20%) sets. Multiple forecasting models, including Linear Regression, ARIMA, SARIMA, and Prophet, were implemented to predict future sales. Each model was trained on the training data and evaluated using the testing data.

## Model Evaluatio

The forecasting models were evaluated using:

* **RMSE (Root Mean Squared Error):** Measures the average magnitude of prediction errors; lower values indicate better performance.
* **MAE (Mean Absolute Error):** Represents the average absolute difference between actual and predicted sales; lower values are preferred.
* **R² Score:** Indicates how well the model explains the variability in sales. Values closer to 1 represent better performance, while negative values suggest the model performs worse than predicting the mean.

The performance of the models varied depending on the characteristics of the dataset. Linear Regression performed well when a linear trend was present, whereas ARIMA, SARIMA, and Prophet were better suited for capturing temporal patterns such as trend and seasonality.

## Key Findings

* The dataset was successfully cleaned and prepared for forecasting.
* Converting the date column into datetime format enabled effective time-based feature extraction.
* Sales data showed a trend over time, while seasonality depended on the specific dataset.
* Time series forecasting models generally performed better when clear temporal patterns were present.
* RMSE and MAE provided a direct measure of prediction accuracy, whereas R² indicated the overall explanatory power of each model.
* Residual diagnostics for the SARIMA model helped verify whether the residuals behaved like random noise, indicating an adequate model fit.



The time series plot of Weekly Sales against Date indicates a positive trend. As time progresses, the average sales tend to increase despite short-term fluctuations. These fluctuations may be due to seasonal demand, holidays, promotions, or other market factors. Overall, the upward movement in sales suggests improving business performance and increasing customer demand.



The Walmart sales dataset exhibits seasonality, as sales follow a recurring pattern during specific periods of the year. Weekly sales tend to increase during holiday seasons and decrease during non-holiday periods. This repeating behavior indicates that customer demand is influenced by seasonal events and shopping patterns.



Cyclic Pattern: No significant cyclic pattern is observed because the dataset covers only a short time period (approximately 2–3 years). While weekly sales fluctuate, these changes are more likely due to seasonal effects rather than long-term economic cycles.



Irregular (Noise): The Walmart sales dataset contains an irregular (noise) component, represented by random fluctuations that do not follow a consistent pattern. These variations are likely due to unexpected events such as promotional campaigns, holidays, weather conditions, or changes in customer demand. The irregular component is unpredictable and cannot be explained by the underlying trend or seasonality.




Missing Values Analysis: The dataset contains missing values in one or more columns. These missing values should be handled before building forecasting models by using techniques such as removing missing records or filling them with appropriate statistics (e.g., mean, median, or mode), depending on the data type.



Relevant time-based features were extracted from the Date column, including Year, Month, Day, Day of Week, Week of Year, and Quarter. These features help identify trends, seasonal patterns, and temporal variations in sales, improving the effectiveness of time series forecasting models.


The dataset was sorted chronologically by the Date column and split into 80% training data and 20% testing data. The training set was used to build the forecasting model, while the testing set was used to evaluate its performance. Keeping the chronological order intact prevents data leakage and reflects real-world forecasting scenarios.




A Linear Regression model was applied to forecast weekly sales using features such as Store, Holiday_Flag, Temperature, Fuel_Price, CPI, Unemployment, Year, Month, and Day. The model was trained on the training dataset and used to predict sales on the testing dataset. Comparing the predicted and actual sales provides an indication of the model's forecasting performance.



MAE (Mean Absolute Error): Lower values indicate better prediction accuracy.
RMSE (Root Mean Squared Error): Lower values indicate fewer prediction errors.
R² Score:
1.0 → Perfect model
> 0.7 → Good model
0 to 0.7 → Moderate model
< 0 → Poor model (worse than predicting the average)



 ARIMA(5,1,0) model was applied to forecast weekly sales. The model was trained on 80% of the data and evaluated on the remaining 20%. Forecast accuracy was assessed using MAE, RMSE, and R² score, and the predicted sales were compared with the actual sales using a line plot.





 A Prophet forecasting model was trained using the historical weekly sales data. The model generated future sales predictions, which were compared with the actual sales in the test dataset. The forecasting performance was evaluated using MAE, RMSE, and R² score. Prophet is well suited for time series that contain trends and seasonal patterns.



 ACF (AutoCorrelation Function):
Helps determine the MA (q) order.
If the ACF cuts off after lag 1 or 2, try q = 1 or q = 2.
PACF (Partial AutoCorrelation Function):
Helps determine the AR (p) order.
If the PACF cuts off after lag 1 or 2, try p = 1 or p = 2.
d (Differencing):
Choose based on whether the series is stationary. If the data has a trend, start with d = 1.



An ARIMA(1,1,1) model was used to forecast weekly sales. The model was trained on 80% of the historical data and tested on the remaining 20%. Forecast performance was evaluated using MAE, RMSE, and R² score. The comparison between actual and forecasted sales indicates how well the ARIMA model captures the underlying sales pattern.



✅ Import and explore the dataset
✅ Check missing values
✅ Analyze trend, seasonality, cyclic, and irregular components
✅ Convert Date to datetime
✅ Extract date features
✅ Split into training and testing sets
✅ Apply Linear Regression
✅ Apply ARIMA
✅ Apply Prophet
✅ Evaluate using MAE, RMSE, and R²
✅ Plot actual vs. predicted results






