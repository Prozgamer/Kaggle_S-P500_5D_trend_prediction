# Kaggle_S-P500_5D_trend_prediction
Work on teaching model on dataset, which contains information on different assets, to predict 5D S&amp;P500 trend
# Project Overview
The goal of this project was to develop a machine learning binary classification model to predict the 5-day directional trend (Up/Down) of the S&P 500 Index.
Predicting financial time-series is notoriously difficult due to the high noise-to-signal ratio and market efficiency, making robust feature engineering and validation crucial.
# Data Engineering & MethodologyTarget Definition:
The target variable was engineered using a look-ahead window: Target = 1 if the closing price in t+5 days is strictly higher than the price at day t, and Target = 0 otherwise.
# Feature Engineering:
To capture market momentum and trends without data leakage, we constructed:
# Lag Features:
Historical price returns and closings from prior days (t-1, t-2, etc.)
# Moving Averages (MA):
Short-term and long-term rolling indicators to capture underlying market momentum.
# Validation Strategy:
To respect the temporal structure of the data and prevent look-ahead bias (data leakage), a strict Time-Series Split was implemented.
The model was trained exclusively on historical data and validated on a completely unseen forward-looking test set.
# Model Performance & Key InsightsBaseline Comparison:
The trained model successfully outperformed a naive random-guess baseline, showing that historical price momentum holds predictive power for short-term adjustments.
# Feature Importance:
Momentum indicators (such as recent 3-day and 5-day returns) and the distance of the current price from its long-term moving averages emerged as the most critical features for the model's decisions.
# Precision vs. Recall Trade-off:
For financial trading applications, the model was tuned to optimize Precision for the Up (1) class.
This ensures that when the model generates a "Buy" signal, the probability of an actual market increase is maximized, thereby minimizing the risk of capital loss on false positives.
# Business & Trading Implication
While financial markets cannot be perfectly timed, this model serves as a data-driven decision-support tool for risk management. It can be integrated into a broader quantitative trading strategy to dynamically adjust portfolio exposure based on the predicted probability of a positive 5-day market regime.
# Result
[Result notebook]()
