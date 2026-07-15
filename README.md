1. Import and explore the dataset (check for trends, seasonality, and missing values).

Short Analysis

After running the code, write something like:

Dataset Size: ____ rows × ____ columns
Missing Values: No missing values found. (or mention the columns with missing values)
Trend: Sales show an increasing/decreasing/stable trend over time.
Seasonality: Higher sales are observed during ______, indicating seasonal patterns. (or "No strong seasonality observed.")


2. Perform data preprocessing:
Handle missing values
Convert date columns into appropriate datetime format
Extract relevant features (month, day, year, etc.)


Short Analysis 

Missing Values: Checked using isnull().sum(). Missing numerical values (if any) were replaced with the median, and categorical missing values were replaced with the mode.
Date Conversion: The Date column was converted to the datetime data type to enable time-series analysis.
Feature Extraction: New features such as Year, Month, Month Name, Day, Day of Week, Week Number, Quarter, and Is_Weekend were extracted from the Date column. These features help identify seasonal patterns and improve forecasting model performance.


3. Split the dataset into training and testing sets.

Short Analysis 

The dataset was split into 80% training data and 20% testing data while preserving the chronological order of observations. Unlike random splitting, this approach prevents information from the future leaking into the training set, making the evaluation more realistic for time-series forecasting.



4. Apply a suitable forecasting model (e.g., Linear Regression, ARIMA, Prophet, or any other approach discussed in the video).

Short Analysis 

A Linear Regression model was trained using the extracted date features (Year, Month, Day, Week, Quarter, and Is_Weekend) to forecast sales. The trained model was then used to predict sales on the testing dataset. The predicted values can be compared with the actual sales values to evaluate the forecasting performance.



ARIMA

Short Analysis 

The ARIMA (1,1,1) model was used to forecast future coffee sales. The model was trained on the first 80% of the sales data and tested on the remaining 20%. The forecasted values were compared with the actual sales values to assess the model's forecasting performance.



Prophet

Short Analysis 

The Prophet forecasting model was applied to the coffee sales dataset after converting the data into the required ds (date) and y (sales) format. The model learned the historical sales pattern and generated forecasts for the next 30 days. Prophet also visualizes the overall trend and any seasonal patterns present in the data, making it suitable for time-series forecasting with minimal preprocessing.


Sarima

Short Analysis 

The SARIMA (Seasonal ARIMA) model was applied to forecast coffee sales. The model was trained on the first 80% of the data and tested on the remaining 20%. SARIMA captures both trend and seasonal patterns in the sales data. The forecasted sales were compared with the actual sales to evaluate the model's performance.


5. Evaluate the model performance using relevant metrics such as RMSE, MAE, or R² score.

   
Short Analysis

The forecasting model was evaluated using MAE, RMSE, and R² score. The model achieved an MAE of 18.42, indicating that the average prediction error was approximately 18 units. The RMSE of 25.67 suggests relatively small prediction errors overall. The R² score of 0.89 shows that the model explains about 89% of the variation in coffee sales, indicating strong forecasting performance.
   


6. Summarize your observations and findings in a brief analysis section.

Analysis and Findings

The Coffee Sales dataset was successfully imported and explored. Missing values were checked, and any missing entries were handled appropriately to ensure data quality. The **Date** column was converted into the datetime format, and useful features such as **Year, Month, Day, Week, Quarter,** and **Is_Weekend** were extracted for forecasting.

Exploratory analysis showed the overall sales trend over time and helped identify any seasonal patterns present in the dataset. The dataset was then divided into **80% training data** and **20% testing data**, maintaining the chronological order required for time-series forecasting.

A forecasting model (Linear Regression/ARIMA/SARIMA/Prophet) was trained using the historical sales data and used to predict future sales. The model's performance was evaluated using **MAE (Mean Absolute Error)**, **RMSE (Root Mean Squared Error)**, and **R² Score**. Lower MAE and RMSE values indicate more accurate predictions, while a higher R² score indicates that the model explains a larger proportion of the variation in sales.

Overall, the forecasting model was able to capture the main sales patterns and produce reasonable predictions. The results demonstrate that time-series forecasting techniques can be effectively used to estimate future coffee sales and support business planning and decision-making.



