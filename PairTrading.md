# Introduction to Pair Trading
## Objective
1. Understand advantage of a pair of stock versus a signle stock
2. Identify patterns of price movements that cause a pair trade to be profitable
3. Construct a beta-hedged pair strategy

Pair Trading focus on relative performance rather than absolute performance

# Trading Pairs
1. Understand the role of correlation in selecting pairs within an industry sector
2. Create a hierarchical clustering using a daily return matric
3. Construct a scree plot using principal component

## Use Correlation to select pairs

Measuring Correlation

## Identify Hierarchical clusters of stocks and create a cluster plot
How? -- Clustering analysis

Hierarchical Clustering Matrix
    
    Use matrix containing daily returns for each stock in OLK
    1. Columns contain data for a particular stock
    2. Rows contain data for a particular trading day

    Computing disance between returns
    1. Calculate using Euclidean method
    2. Iteractively cluster stocks based on minimizing distance

    Principal Components analysis on stocks in XLK

## Construct a scree plot for stocks within an industry sector

    Scree Plot:
        Cliff
        Scree

## Pair Trading Strategy
1. Loadings in PCA
2. Use PCA loadings for the first two components to select a pair
3. Design a beta weighted pair strategy for two stock in SLK

Pair Strategy
1. When to get in?
2. How do you define your entry signal?

## Evalute Pair Trade Strategy
1. Construct a trade blotter to record entry and exit data
    * Pair
    * Direction
    * Entry date
    * Entry level
    * Exit Level
    * Exit category
2. Quantify and implement a trading rule

Entry signal, profit target, stop-loss


3. Identify six key performance metrics for pairs trading

Evalute REsults of a Pair Trade

* Backtest and evalute trading rule
    * Apply trading rules to historical dataset
    * Create hypothetical trade blotter to record results of trading rule
    * Measure hypothetical performance of trading rule


Key performance metrics
1. Win Percentage
    * HIt target = Win
    * Hit Stop Loss = Looss
        
        Win % = Wins/Losses * 100

    *75% - 80% puts odds in your favor and covers trading costs
2. Total return
    * Total invested capital and how much gained/lossed when trade closed
    * Subtract trading costs (fees, commissions)
    * Market impact costs 
3. Avg. Win'Loss amount
4 Extreme Win/LOss amount
5. Variance of returns
    * Information Ratios
6. Total Portfolio Value
    * linear trend of portfolio value against market value
    * Prefer a return that is not bumpy

# Backtesting and Avoid Overfitting

