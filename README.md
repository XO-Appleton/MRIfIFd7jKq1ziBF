# ValueInvestor


## Problem Statement

Given the stock data of companies in 2020, predict their price change in the first quarter of 2021 and make recommendations.

## Data Description

The stock data are stored as google sheets.

Features are as follows:

Date - The date of the record.

Price - The closing price of the day.

Open - The opening price of the day.

High - The highest price reached on the day.

Low - The lowest price reached on the day.

Vol. - The transaction volume of the day.

Change% - The price change in percentage.

For the price prediction and plotting only the `Date` and `Price` columns were used.

## Approach

To generate predictions for the stocks, we first trained models on the price data from 2020 and then predicted the price change in the first quarter of 2021. To make recommendations based on the predictions, we generated Bollinger Bands from the predictions using a 20-entry window and 2 times standard deviation. Then the actual price was compared against the prediction, if the price was higher than the upper band, we recommend selling the stock, and if the price was lower than the lower band, we recommend buying the stock.

Three models were tried for the project:
    1.  A baseline model using a moving average of a 20-day window.
    2.  An RNN model with one CNN, two LSTM, and three Dense layers.
    3. Meta's Prophet model

## Final Model

The final model chosen was the Prophet model. It was able to achieve a reasonably low MAE score without giving results that converges to a single value like the moving average model.

## Evaluation Metrics

The models were evaluated using MAE (Mean Absolute Error). 

## Results

The Prophet model achieved 9.2 MAE on the PAMP stock which is around 10% off from the actual values over the course of three month.


## Screenshots
Sample output of the Prophet model's prediction on PAMP stock.

![pamp_sample](https://github.com/XO-Appleton/MRIfIFd7jKq1ziBF/assets/41369365/99403f56-7a69-493e-8bc7-cbb24dee5ca8)
