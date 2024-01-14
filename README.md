# Predicting-Future-Alberta-Energy-Consumption-using-LSTM

This code essentially performs data preprocessing, explores the hourly Alberta pool price and demand dataset from AESO, prepares the data for LSTM, builds and trains an LSTM model, and visualizes the predicted energy consumption. 

## Data Preparation and Cleaning:

1. The hourly pool price and market demand data were extracted from the AESO website in CSV format.
2. Data extraction and cleaning procedures were applied to the dataset spanning the last 24 years (2020-2023).
3. The cleaned data is stored in a CSV file, ready for subsequent data analysis and modeling.

## Data Loading and Exploration:

1. Reads a CSV file containing Alberta hourly pool price, market demand, and 30-minute average data.
2. Prints the first five rows, basic information, and summary statistics of the dataset.
3. Checks for null values in the dataset.

## DateTime Column Formatting:

1. Converts the "Date (HE)" column to a datetime format.
2. Extracts and formats the date, hour, minute, and second from the "Date (HE)" column to create a new "Datetime" column.
3. Creates additional columns for month, year, date, time, week, and day.

## Exploratory Data Analysis (EDA):

1. Visualizes energy consumption over the years using line plots.
2. Creates subplots to show energy consumption for specific years (2004, 2005, 2006).

## Energy Distribution Plot:

Plots a distribution plot for the energy consumption.

## Energy Consumption vs Time:

Plots energy consumption against time.

## Resampling Data for LSTM:

1. Resamples the data to daily frequency and calculates the mean.
2. Prepares training and test datasets, with the training set excluding the last 60 days.

## Data Scaling:

Uses MinMaxScaler to scale the training set between 0 and 1.

## Data Preparation for LSTM:

1. Creates sequences of 60 time steps for training the LSTM model.
2. Reshapes the input data to a 3D array.

## LSTM Model Construction:

1. Constructs a Sequential LSTM model with four LSTM layers, each followed by dropout layers.
2. Compiles the model using the Adam optimizer and mean squared error loss.
3. Trains the model on the prepared training data for 50 epochs.

## Test Data Preparation and Prediction:

1. Prepares the test data by taking the last 100 days from the resampled dataset.
2. Uses the trained LSTM model to predict future energy consumption.

## Inverse Transform and Comparison:

1. Inversely transforms the predicted values to the original scale.
2. Compares the true and predicted energy consumption for the test data.

## Visualization of Predictions:

Plots the true and predicted energy consumption over the specified date range.

## Result Display:

Displays a DataFrame containing the true and predicted energy consumption for each date in the test set.

## Final Visualization:

Plots the true and predicted energy consumption for each date in the test set.

## Future Steps: 
The future steps of the project include predicting hourly pool price and testing the model accuracy for hourly Alberta market demand. 
