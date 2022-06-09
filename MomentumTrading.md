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


## long-term autocorrelation of returns
* p(k) = CK^(-a)
* p(k) is an autocorreltation function
* C is a constant
* k is the number  of lags
* a is the decay parameter

## Long Memory Process (LMP)
LMP is a process with a random component, where a pas event has a decaying effect on future events
* LMP follows power law
* a ranges between 0 and 2
* 0<a<1, indicates persistencce
* a = 1, indicates random walk
* 1<a<2, indicates mean reversion
* Hurst Exponent: H = 1 - a/2 

    * Hurst = 0.5, random walk
    * Hurst > 0.5, Momentum
    * Hurst < 0.5, mean reversion

# Building a Momentum Trading Model
Using python andd open source library called backtester from Auquan
## Elements of trading system
* Trading System: market, logic, parameters by which trading logic triggered
* Backtesting system: analyze strategy's performance on historical data and remove biases
* Excution system
*Risk management system


Open source toolbox Auquan

* Open source library
* Simulates an exchange
* Backtests your algorithm
* Executes your trades
* Calculates your P/L
* Allows you to back test if any time frame you want

## Developing a Trading Strategy using ML
1. Create Features from data
    * Fundamental: P/E Ratios, EPS, Cash Flows, etc.
    * Technical based on how your chosen securities behave:
        * Momentum features, Mean reversion
        * Correlated or cointergrated features
    * Combined fundamental and technical indicators
2. Develop a trading startegy using these features
    * Which instruments are a buy, a sell, or neutural
    * When to buy/sell and 
    * How much to buy/sell

## BUilding a momentum trading model using ML
Steps:

1. Define the problem
    * Price prediction
    * Return/P&L
    * Buy/Sell signal
    * Portfolio Optimization
    * Efficient Excution

    ### How to implement Momentum Trading Strategy using ML

    Problem: Create a prediction model that can help trade price difference between two assets

        Basis = Price of Stock - Price of Future

        Basist = St - Ft

    Target: Expected Value in the next 5 minutes

        Y = feature expected value of basis = Average(basis(t1),basis(t2),basis(t3),basis(t4),basis(t5))

    Objective: Create a model so that the prediccted value is as close as possible to Y

    Evaluation Criteria: RMSE, P/L

    Features (X)

        Stock bid price
        Future Bid price
        Stock VWAP
        Futures VWAP

    stockVWAP = (BidPrice *AskVolume + AskPrice*BidVolume) / (AskVolume+BidVolume)

    Data is already cleaned for Dividends, splits, rolls

2. Collect data

* Stock price data, trade volume data
* Fundamental data, overall market indicator (ex. indexes)
* Correlated stocks data
* Similar assets price information

Remember to check for accuracy, alignment

Remberm to clean for dividends stock splits, roll, etc.

* Alternative Data is Untapped Data
    * Credit card transactions
    Email receipts
    Point of sale transactions
    Web site usage
    Obscure city hall records
    Satellite images

3. Creating Features: Feature Engineering

* Feature Selection
    * Don't randomsly choose a very large set of features without exploring reltionship with target variable
    * Little to no relationship with target will lead to overfitting
    * Rank candidate features according to Maximal Information Coefficient (MIC) or PCA and other methods

* Feature Transform/Normalize
    * Scaling
    * Centering
    * Normalization
    * Regular Normalizating
    * Caveat

4. Split data

Create training and test set for the model -> Cross validation



5. Select a ML algorithm
6. Backtest on Unseen data






