# Objective
1. Identify factors that contribute to the momentum feature
2. Understand how trade entries and exits are selected using moving averages
Evaluate and rank the effectiveness moving averages and moving average ribbons

# what is momentum
## Trend lines
* Straight lines that connect the temporary highs and lows in a price series
* Use trends linve abover and below a series to identify potential buy or sell signals
* volume is critical component to confirming a momentum trend
## How detect a trend?
* Slope of rolling averages or moving averages can tell you whether a stock is in an uptrend or downtrend

## Choosing Moving Average length
be aware of the the dange of overfitting

robus optimization techniques

check shape the ribbons

## Scorning Moving averages
1. Scoring: Distance metric

10dMA < 20dMA < ... < 100dMA then Score ~ 0 then buy


10dMA > 20dMA > ... > 100dMA then Score ~ 1 then sell


2. Correlation

Rank the ribbons using a Spearman's correlation and normalize the score once again.

Score ~ 1 then buy; score ~ -1 then sell;


# Introduction to Hurst
1. Recognize momentum in a time series of asset prices
2. Understand how momentum is related to serial autocorrelation
3. Use the Hurst exponent to measure long-term memory of asset prices
