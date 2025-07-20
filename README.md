# sp500-nbeats-forecasting
SP500 forecasting using nbeats and Darts

# 📈 Stock Market Forecasting with N-BEATS and Darts

This notebook presents a simple time series forecasting project using the [Darts](https://github.com/unit8co/darts) library and the powerful N-BEATS model. The goal is to predict the future trend of the S&P 500 index based on historical data.

## 🧠 Objective

- Forecast future `Close` prices of the S&P 500 index using deep learning.
- Evaluate the quality of the predictions both quantitatively (with metrics) and visually.
- Explore the directional prediction of market movement (up/down), which is often more useful than exact price prediction.

## 📚 Tools & Technologies

- **Python** (3.11)
- **Darts** (time series forecasting library)
- **Pandas**, **NumPy**
- **Matplotlib**, **Seaborn**
- **scikit-learn** for evaluation metrics
- **yfinance** to fetch historical market data

## 🔍 Dataset

- Ticker: `^GSPC` (S&P 500 Index)
- Period: From `2020-01-01` to `2025-07-14`
- Source: [Yahoo Finance](https://finance.yahoo.com/)

## ⚙️ Project Structure
📦 stock-market-nbeats-prediction
├── 📘 notebook.ipynb
├── 📊 graphs/
│ ├── prediction_vs_actual.png
│ └── denoised_series.png


## 🔧 Methodology

1. **Data Acquisition** using `yfinance`
2. **Preprocessing**: smoothing the series using a 5-day moving average
3. **Darts Conversion**: formatting the data into `TimeSeries` objects
4. **Modeling**: training an N-BEATS model
5. **Evaluation**:
   - MAE, MAPE, RMSE
   - Directional prediction (classification): Accuracy, Precision, Recall, F1-score
   - Confusion matrix
6. **Visualization**: overlaying real vs predicted series, and separate plots for denoised data

## 📉 Example Output

![Forecast vs Actual](graphs/prediction_vs_actual.png)

## 🧪 Metrics

| Metric            | Value (Example) |
|-------------------|-----------------|
| MAE               | 78.96           |
| MAPE              | 1.39%           |
| RMSE              | 108.44                    |
| F1-score          | 50.60            |

## Interpretation of Results
The prediction model based on the N-BEATS architecture achieves a Mean Absolute Error (MAE) of approximately 79 points on the S&P 500 index, which corresponds to about 1.8% of the typical index value during the tested period (2020–2025). This level of error is reasonable given the inherent volatility and complexity of financial markets. The low Mean Absolute Percentage Error (MAPE) of 1.39% further indicates that the model performs well in relative terms.

The Root Mean Squared Error (RMSE) of around 108 points shows that while some larger errors occur, overall the model's predictions are consistent. For the directional prediction task (predicting if the market will rise or fall), the F1-score of 50.6% suggests the model is close to random guessing and could be improved by further tuning or adding more features.

Overall, these results demonstrate that the N-BEATS model can capture important patterns in stock market data and provide useful predictions, though there is still room for improvement especially in classification accuracy of market direction.

## 💡 Lessons Learned

- N-BEATS is robust for financial time series, especially when noise is reduced.
- Directional evaluation gives a more realistic view of predictive power.
- Proper train/val/test splitting is crucial in avoiding data leakage.

## 🚀 Possible Improvements

- Try other models (xLSTM, TCN, Transformer)
- Tune hyperparameters (hidden layers, epochs)
- Predict other financial indices (e.g. NASDAQ, DAX)
- Create a live forecast dashboard using `Streamlit`

## References
Espinosa, J., et al. (2024). N-BEATS: Neural Basis Expansion Analysis for Time Series Forecasting. arXiv:2408.12408

López Gil, G. (2024). xlstm-ts: eXplainable LSTM for Time Series Forecasting. GitHub repository. https://github.com/gonzalopezgil/xlstm-ts


