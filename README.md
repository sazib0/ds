# Exploring Trends and Anomalies in Construction Financial Data
## Introduction
- The goal of this project is to analyze and visualize the transaction data of a construction company, from September 2022 to October 2023.
- The data contains information about the date, amount, mode, and type of each transaction, as well as the project name, receiver, item, and description.
- The data was obtained from an Excel file named `xy.xlsx`, which has 10974 rows and 11 columns.

## Data Cleaning and Preprocessing
- The data was loaded into a Pandas DataFrame for further processing and analysis.
- Missing values in various columns were imputed with the mean for numerical columns and the mode for categorical columns.
- Incorrect data types were converted to the appropriate types using the `pd.to_datetime` and `pd.to_numeric` functions.
- The data was sorted by date and indexed by the Date column for time-series analysis.

## Exploratory Data Analysis (EDA): Visualizations
- Visualized the distribution of numerical variables (`Received Amount`, `Payments Amount`, and `Cu.Balance Amount`) using histograms and box plots.
- Visualized the distribution of categorical variables (`Main Head`, `Sub Head (Payment Type)`, and `Payment Mode`) using count plots.
- Visualized the time series of payments using a line plot, showing the fluctuations and trends over time.
- Resampled the data to a monthly frequency and plotted the monthly received and payment amounts.

## Descriptive Statistics
- Calculated summary statistics for numerical variables using the `describe` method.
- Calculated summary statistics for categorical variables using the `describe` method with the `include='all'` parameter.

## Feature Engineering
- Extracted relevant date features from the `Date` column, such as the day of the week, month, and quarter.
- These features can be used for further analysis or modeling, such as grouping, aggregating, or filtering the data by different time periods
- Created a new column named `Transaction_Amount` by subtracting the `Payments Amount` from the `Received Amount`, representing the net amount of each transaction.

## Financial Analysis
- Calculated cumulative received and payment amounts using the `cumsum` method.
- Calculated cumulative balance by subtracting cumulative payments from cumulative received amounts.
- Plotted cumulative balance over time and monthly trends of received and payment amounts.

## Anomaly Detection
- Calculated Z-scores for the `Transaction_Amount` column to detect anomalies.
- Used a threshold of 3 for anomaly detection.
- Identified anomalies and visualized them using scatter plots.
- Employed Isolation Forest, a machine learning algorithm, for anomaly detection based on the `Transaction_Amount` column.
- Compared the results with the Z-score method.
