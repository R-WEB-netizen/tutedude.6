
Walmart Sales Forecasting

Project Overview

This project focuses on forecasting Walmart weekly sales using time-series forecasting techniques. The dataset contains historical Walmart sales information along with factors such as store, holiday flag, temperature, fuel price, CPI, and unemployment.

The main objective is to explore historical sales patterns, preprocess the data, identify trends and seasonality, build a forecasting model, and evaluate its performance.

Dataset

The project uses the Walmart.csv dataset.

Important columns include:

Store – Store identification number
Date – Date of weekly sales
Weekly_Sales – Weekly sales amount
Holiday_Flag – Indicates whether the week is a holiday week
Temperature – Temperature during the week
Fuel_Price – Fuel price
CPI– Consumer Price Index
Unemployment – Unemployment rate

 Project Steps

 1. Dataset Exploration

The dataset was imported and explored using Python, Pandas, and visualization libraries.

The following were checked:

Dataset shape
Data types
Missing values
Duplicate records
Statistical summary
Sales trends
Seasonal patterns

2. Data Preprocessing

The data was cleaned and prepared for forecasting.

The preprocessing steps included:

Handling missing values
Converting the `Date` column into datetime format
Sorting the dataset chronologically
Extracting time-based features such as:

Year
Month
Day
Day of Week
Quarter
Week of Year

3. Exploratory Data Analysis

Time-series visualizations were created to understand the behavior of weekly sales.

The analysis showed an overall positive trend in sales with short-term fluctuations. Seasonal variations can also be observed during particular periods, especially around holiday seasons.

4. Train-Test Split

The dataset was divided chronologically into:

80% Training Data
20% Testing Data

The chronological order was maintained to avoid data leakage and to simulate a real-world forecasting situation.

5. Forecasting Model

The main forecasting approach used in this project is **Prophet**.

Prophet is suitable for time-series forecasting because it can model:

Trend
Seasonality
Holiday effects
Changes in historical patterns

The model was trained using historical sales data and then used to predict sales for the testing period.

6. Model Evaluation

The forecasting model was evaluated using:

MAE (Mean Absolute Error)
RMSE (Root Mean Squared Error)
R² Score

Lower MAE and RMSE values indicate better prediction accuracy. An R² value closer to 1 indicates that the model explains more of the variation in the target variable.

Key Findings

Walmart weekly sales show an overall upward trend over time.
Sales contain short-term fluctuations.
Holiday periods can have a significant influence on sales.
seasonal patterns are present in the dataset.
Some irregular fluctuations may be caused by promotions, holidays, weather, and changes in customer demand.
Prophet is useful for capturing the trend and seasonal components of the sales time series.

Technologies Used

Python
Pandas
NumPy
Matplotlib
Seaborn
Scikit-learn
Prophet
Jupyter Notebook / Google Colab

 Project Files

text
tutedude.6/
│
├── Walmart.csv
├── forecasting.ipynb
└── README.md









