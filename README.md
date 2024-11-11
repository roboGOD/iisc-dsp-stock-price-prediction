# Stock Price Prediction Model

## Project Overview
This project focuses on building a stock price prediction model using historical stock prices and additional financial indicators. The project includes data cleaning, exploratory data analysis (EDA), and model building stages to predict stock prices based on key financial and historical data.

## Table of Contents
1. [Project Structure](#project-structure)
2. [Data Pre-processing](#data-pre-processing)
3. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
4. [Model Training](#model-training)
5. [Dependencies](#dependencies)
6. [Usage](#usage)
7. [Team Members](#team-members)

## Project Structure
The project files are organized as follows:

- `datasets/`: Contains raw and cleaned datasets.
- `models/`: Stores trained model files.
- `src/`: Source code for data processing, analysis, and model functions.
- `README.md`: Project documentation.

## Data Pre-processing

To prepare the data for analysis and modeling, we apply the following pre-processing steps:

1. **Transpose Financial Data**  
   The `fin_df` DataFrame, which contains financial indicators, is transposed to make each column represent a different financial feature, and each row a unique date.

2. **Set New Header from First Row**  
   The first row of `fin_df` is set as the new header, making each column name more descriptive and meaningful.

3. **Remove Columns with All Missing Values**  
   Any columns that contain only missing (`NaN`) values are removed from `fin_df` to streamline the dataset.

4. **Reset Index and Rename Date Column**  
   The index is reset, and the original index is renamed to "date" for clarity and consistency.

5. **Standardize Column Names**  
   All column names are formatted to be lowercase and use underscores in place of spaces to ensure consistency and prevent naming conflicts.

6. **Remove Duplicate Columns**  
   Duplicate columns are removed to ensure each feature appears only once in the final DataFrame.

7. **Convert Date Columns to Datetime Format**  
   The "date" columns in both `price_data` and `fin_df` are converted to datetime format for reliable time-based operations.

8. **Merge DataFrames**  
   `price_data` and `fin_df` are merged using an "as-of" join on the "date" column in a "backward" direction, aligning each row in `price_data` with the most recent available data in `fin_df`. The resulting `merged_df` DataFrame contains a comprehensive dataset ready for analysis.

## Exploratory Data Analysis (EDA)

In this stage, we explore the merged data to gain insights into trends, patterns, and relationships between features. Key EDA steps include:

1. **Descriptive Statistics**  
   - Summary statistics of the dataset are calculated to understand the central tendencies and variances within each feature.

2. **Time Series Visualization**  
   - Stock price trends over time are visualized to identify potential seasonal patterns, volatility, and long-term trends.

3. **Correlation Analysis**  
   - Correlations between the stock price and financial indicators are analyzed using a heatmap to highlight relationships that may be useful for predictive modeling.

4. **Moving Averages and Volatility Analysis**  
   - Moving averages are computed to observe the overall trend and smooth out short-term fluctuations.
   - Volatility is examined to understand the stability of stock prices over time.

5. **Distribution Analysis**  
   - Distributions of key features are plotted to identify outliers and skewness, which could impact model performance.

## Model Training

After pre-processing and EDA, the data is used to train a predictive model. Steps include:

1. **Data Splitting**  
   The data is split into training and test sets to evaluate model performance.

2. **Feature Engineering**  
   New features are derived from existing data, such as technical indicators, to improve predictive accuracy.

3. **Model Selection and Training**  
   Various models (e.g., Linear Regression, Random Forest, and LSTM) are trained on the processed data to determine which approach yields the best results.

4. **Model Evaluation**  
   Model performance is evaluated using metrics like Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE) to measure prediction accuracy.

## Dependencies

To run the project, install the following dependencies:

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scikit-learn`
- `statsmodels`
- `tensorflow` (for deep learning models, if used)
- `yfinance` (for fetching stock price data from Yahoo Finance)

Install all dependencies using:
```bash
pip install -r requirements.txt
```

## Team Members

- [Ishwer Kumar](mailto:ishwerkumar@iisc.ac.in)
- [Manish Kumar Singh](mailto:manishsingh@iisc.ac.in)
- [Bhaskar Garg](mailto:bhaskargarg@iisc.ac.in)
- [Priti Narayan](mailto:pritinarayan@iisc.ac.in)