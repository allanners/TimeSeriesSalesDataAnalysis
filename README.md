# Store Sales Time Series Forecasting

## Objective

This project aims to predict future sales by utilizing historical sales data from the Kaggle dataset: [Store Sales - Time Series Forecasting](https://www.kaggle.com/competitions/store-sales-time-series-forecasting). The primary focus is to analyze data and develop a simple machine learning model using **XGBoost** to forecast future sales based on past trends and patterns.

## Project Overview

Sales forecasting is essential for businesses to anticipate demand, manage inventory, and optimize supply chain operations. In this project, a **time series forecasting** model is built to predict future sales by leveraging past data and patterns. The data has been preprocessed, engineered, and used to train an XGBoost model, which is a powerful gradient boosting framework.

## Dataset

The dataset includes daily sales for various stores. It includes several features like:

- Date of the sales
- Store ID
- Sales data for each store

The data is cleaned and transformed as part of the preprocessing step. Missing values are handled, and additional features are created for better model performance, including:

- Lag features (previous day's sales, previous week's sales)
- Rolling averages (for smoothing trends)
- Time-based features (day, month, year, etc.)

## Model: XGBoost

The core of the project is the **XGBoost** model. XGBoost is an efficient and scalable implementation of gradient boosting that has been widely used for various machine learning tasks, including time series forecasting.

### Key Hyperparameters:
- **n_estimators**: The number of boosting rounds. This determines the number of trees in the model. A higher value might lead to overfitting if not controlled by other parameters.
- **learning_rate**: The step size to update weights at each boosting step. A smaller learning rate requires more boosting rounds.
- **max_depth**: Controls the maximum depth of trees. Deeper trees can capture more patterns but might also lead to overfitting.
- **subsample**: The fraction of samples used for training each tree. This helps to prevent overfitting by introducing randomness.
- **colsample_bytree**: The fraction of features to consider for each tree. Reducing this can help the model generalize better.

### Model Training and Evaluation

The dataset is split into training and validation sets, and the XGBoost model is trained using the training data. Various metrics, including **RMSE** (Root Mean Squared Error), are used to evaluate the performance of the model.

## Exploratory Data Analysis (EDA)

EDA was performed to visualize the underlying trends, seasonality, and correlations in the dataset. Several important insights were uncovered through the following visualizations:

- **Line plots**: Displaying sales trends over time for different stores.
- **Correlation heatmaps**: Identifying relationships between features like time, store ID, and sales.
- **Lag plots**: Helping to understand autocorrelations in the dataset, which are crucial for time series modeling.
- **Rolling averages**: Smoothing out short-term fluctuations to show long-term trends.

## Findings

1. **Seasonality**: The sales data shows a clear seasonal pattern, with certain months having consistently higher sales across multiple stores.
2. **Autocorrelation**: There is a significant autocorrelation in sales, indicating that past sales are a strong predictor of future sales.
3. **XGBoost Performance**: The model shows strong performance in capturing the trends and making accurate sales predictions, with the tuned hyperparameters improving accuracy and reducing overfitting.

## Conclusion

The project demonstrates that machine learning models like XGBoost can effectively forecast sales in a time series context. This kind of analysis can be extended to optimize inventory, staffing, and marketing strategies in a real-world retail environment.
