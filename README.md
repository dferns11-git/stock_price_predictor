# Stock Price Prediction with GUI Interface

## Project Overview

This project demonstrates how to predict the next day's stock price based on historical stock data using machine learning models. The core model is based on **Support Vector Regression (SVR)**, and the prediction process is enhanced with a simple, interactive **GUI** for ease of use. The GUI allows users to input stock tickers, select date ranges, and view predictions directly in the Jupyter notebook.

The model uses historical data from **Yahoo Finance** and predicts the stock price change for the following day. It employs **SVR** to predict the closing price, using features like the 5-day moving average, 10-day moving average, and volume change. The user interface is built with **ipywidgets**, allowing for an interactive and seamless experience within a Jupyter notebook.

## Features

- **Interactive User Interface**: Built using `ipywidgets`, allowing users to input stock tickers and select date ranges directly within the notebook.
- **Stock Price Prediction**: Predicts the next day's stock price using historical stock data from Yahoo Finance.
- **Model**: The machine learning model is built using **Support Vector Regression (SVR)**, a regression technique suitable for predicting continuous values like stock prices.
- **Mean Squared Error Calculation**: Displays the Mean Squared Error (MSE) to help assess the model's performance.
- **Visualization**: Outputs predictions and MSE directly within the notebook for easy interpretation.

## Installation and Setup

### Requirements
- Python 3.x
- Install the required libraries by running the following command:
  ```bash
  pip install yfinance ipywidgets scikit-learn pandas
  ```

### Running the Notebook

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/stock-price-prediction.git
   cd stock-price-prediction
   ```

2. Launch the Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

3. Open the notebook file (`stock_price_prediction_gui.ipynb`).

4. Follow the instructions inside the notebook to interact with the GUI. You can:
   - Enter a stock ticker (e.g., "AAPL" for Apple).
   - Select a start and end date for the historical data range.
   - Click the **Predict** button to get the predicted stock price for the next day and the Mean Squared Error (MSE).

## How the Model Works

### Data Fetching
The model fetches historical stock data from Yahoo Finance using the `yfinance` library. The data includes:
- **Closing Price**: Used to calculate moving averages and to predict the target (next day's price).
- **Volume**: Used to calculate volume change, which may impact stock prices.

### Feature Engineering
We create the following features:
- **5-day Moving Average**: The average of the last 5 days' closing prices.
- **10-day Moving Average**: The average of the last 10 days' closing prices.
- **Volume Change**: Percentage change in trading volume from one day to the next.

### Model Training and Prediction
The model is trained using the **Support Vector Regression (SVR)** algorithm, which is a regression technique ideal for predicting continuous variables, such as stock prices. The model is trained on historical stock data, and predictions are made for the next day's closing price.

### Model Evaluation
The model performance is evaluated using **Mean Squared Error (MSE)**, a standard metric for regression models. This helps assess the accuracy of the model's predictions.

## Example

### User Interface Workflow:

1. **Ticker Input**: The user enters the stock ticker symbol (e.g., "GOOGL" for Google).
2. **Date Range**: The user selects a start and end date for the historical data.
3. **Prediction**: Upon clicking the **Predict** button, the model will output:
   - The predicted stock price for the next day.
   - The Mean Squared Error (MSE), which indicates the model's prediction accuracy.

### Example Output:
```bash
Predicted Next Day Price: $222.83
Mean Squared Error: 0.0321
```

## Future Improvements

- **Advanced Feature Engineering**: Incorporating more complex features such as technical indicators (RSI, MACD) to improve prediction accuracy.
- **Hyperparameter Tuning**: Fine-tuning the SVR model to optimize performance.
- **Expanded Data Sources**: Integrating additional financial data sources to increase the robustness of predictions.
- **Deployment**: Deploying the model and GUI into a web application for easier access and usage.
