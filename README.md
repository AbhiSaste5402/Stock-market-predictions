# Stock-market-predictions
1. Data Loading and Preprocessing:

The code imports necessary libraries like pandas, numpy, matplotlib, pandas_datareader, and scikit-learn for data manipulation, visualization, and machine learning tasks.
It reads the historical stock price data of AAPL from a CSV file using pandas read_csv function.
Initial exploration of the dataset is done using head() and tail() functions to check the first and last few rows of the DataFrame.
The DataFrame is reset to have a new index and unnecessary columns ('index', 'Date', 'Adj Close') are dropped.
A training dataset (data_training) and a testing dataset (data_testing) are created by splitting the data based on a certain percentage (70% training and 30% testing).
Min-max scaling is applied to normalize the data between 0 and 1 using MinMaxScaler.
Moving Average Calculation and Visualization:

Two moving averages (MA) are calculated over the closing price data: a 100-day MA (ma100) and a 200-day MA (ma200).
These moving averages are plotted along with the original closing price data for visualization using Matplotlib.

2. Model Building and Training:

A Long Short-Term Memory (LSTM) neural network model is constructed using Keras.
The model is compiled with the Adam optimizer and Mean Squared Error (MSE) loss function.
The training data is prepared by creating sequences of 100 days of historical data as input features (X_train) and the next day's closing price as the target (y_train).
The model is trained with the training data for 100 epochs.

3.Model Evaluation and Testing:

The trained model is saved to a file named 'keras_model.h5'.
For forecasting, the last 100 days of the training data are appended with the testing data to form a larger dataset (final_df).
Similar to the training data preparation, sequences of 100 days are created as input features (x_test) for forecasting, and the corresponding next day's closing price is stored in y_test.
The model predicts the closing prices for the test data (y_predicted).
The predicted values and actual values are scaled back to their original scale for comparison.
Overall, the code demonstrates a pipeline for time series forecasting using LSTM neural networks, including data preprocessing, model training, and evaluation. Additionally, it provides visualizations to aid in understanding the data and model performance.
