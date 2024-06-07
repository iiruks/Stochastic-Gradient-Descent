# Stock Price Prediction using Stochastic Gradient Descent

This repository provides a Python script to fetch historical stock data for Tesla (TSLA) from Yahoo Finance, and then use Stochastic Gradient Descent (SGD) to fit a linear regression model to the data. The model is then used to predict future stock prices.

## Prerequisites

Before running the script, ensure you have the following Python libraries installed:

- os
- warnings
- numpy
- pandas
- matplotlib
- scikit-learn
- scipy
- pandas_datareader
- yfinance

## Usage

- Fetch Stock Data
```
yfin.pdr_override()
df = pdr.get_data_yahoo('TSLA', start='2023-03-21', end='2023-04-22')
df
```

- Train the Model
```
reg = make_pipeline(StandardScaler(), SGDRegressor(max_iter=500, tol=1e-3, validation_fraction=0.1, shuffle=False, verbose=2))
reg.fit(X, y)

y_pred = reg.predict(X)
mean_squared_error(y, y_pred)
```

- Plot Predictions vs Actual Data

- Predict Future Stock Prices
```
fdf = df.append(future_dates)
fdf.describe()

X_new = fdf[future_dates.index[0]:].drop(['Close'], axis=1)
X_new

y_pred = reg.predict(X_new)
y_pred
```

## Conclusion
This script demonstrates the application of stochastic gradient descent for predicting stock prices using linear regression. The predictions for the next three months are visualized for comparison with actual historical data.
