# Predicting-Future-Alberta-Energy-Consumption-using-LSTM

This code essentially performs data preprocessing, explores the hourly Alberta pool price and demand dataset from AESO, prepares the data for LSTM, builds and trains an LSTM model, and visualizes the predicted energy consumption. 

## Data Preparation and Cleaning:

The hourly pool price and market demand data were extracted from the AESO website in CSV format.
Data extraction and cleaning procedures were applied to the dataset spanning the last 24 years (2020-2023).
The cleaned data is stored in a CSV file, ready for subsequent data analysis and modeling.

## Data Loading and Exploration:

Reads a CSV file containing Alberta hourly pool price, market demand, and 30-minute average data.
Prints the first five rows, basic information, and summary statistics of the dataset.
Checks for null values in the dataset.

## DateTime Column Formatting:

Converts the "Date (HE)" column to a datetime format.
Extracts and formats the date, hour, minute, and second from the "Date (HE)" column to create a new "Datetime" column.
Creates additional columns for month, year, date, time, week, and day.

## Exploratory Data Analysis (EDA):

Visualizes energy consumption over the years using line plots.
Creates subplots to show energy consumption for specific years (2004, 2005, 2006).

## Energy Distribution Plot:

Plots a distribution plot for the energy consumption.

## Energy Consumption vs Time:

Plots energy consumption against time.

## Resampling Data for LSTM:

Resamples the data to daily frequency and calculates the mean.
Prepares training and test datasets, with the training set excluding the last 60 days.

## Data Scaling:

Uses MinMaxScaler to scale the training set between 0 and 1.

## Data Preparation for LSTM:

Creates sequences of 60 time steps for training the LSTM model.
Reshapes the input data to a 3D array.

## LSTM Model Construction:

Constructs a Sequential LSTM model with four LSTM layers, each followed by dropout layers.
Compiles the model using the Adam optimizer and mean squared error loss.
Trains the model on the prepared training data for 50 epochs.

## Test Data Preparation and Prediction:

Prepares the test data by taking the last 100 days from the resampled dataset.
Uses the trained LSTM model to predict future energy consumption.

## Inverse Transform and Comparison:

Inversely transforms the predicted values to the original scale.
Compares the true and predicted energy consumption for the test data.

## Visualization of Predictions:

Plots the true and predicted energy consumption over the specified date range.

## Result Display:

Displays a DataFrame containing the true and predicted energy consumption for each date in the test set.

## Final Visualization:

Plots the true and predicted energy consumption for each date in the test set.

## Future Steps: 
The future steps of the project include predicting hourly pool price and testing the model accuracy for hourly Alberta market demand. 
