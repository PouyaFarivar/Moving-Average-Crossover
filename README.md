# Moving-Average-Crossover
Analysis of moving average crossover method for Securities. commodities and BTC price action

This repository is an attempt to analyze the MA crossover algorithm for daily BTC price action. Performance of all MA pairs ranging from one-day to 500-day moving averages are calculated. This calculation also happens for different risk tolerances, meaning that the model finds the best position size and leverage based on the transaction and futures fees and lets you decide about the final model with your risk tolerance. The model includes both long-short and long-only methods.

Explanations of each Notebook are as follows:

### Profits complete Notebook
In this notebook, I have tried to simulate a futures trading platform like https://www.kucoin.com/. This includes implementing the taker/maker fees, the futures funding rate, and how leverage affects the overall position. All of these aspects are implemented in different functions.

### final_BTC Notebook
In this Notebook, I use the functions from the last notebook to calculate the performance of the cross-over algorithm for different MA pairs, position sizes, and leverages. The overall code takes a long time to run so they are implemented in a parallel way.

Due to the high futures rates at Kucoin, the futures trading platform I am using, the best methods end up being not using leverage and futures contracts at all. This means that the best model is a long-only method that works with the 20-60 60-day MA pairs. these two pairs are chosen from 1-500 day moving averages. The heatmap plotted in the notebook shows the performance of all of the MA pairs. Performance here means the profits generated based on the backtest made in the virtual trading environment cloning the price action of BTC for the last 5 years.

### plain sp500/Gold/BTC Notebooks
These Notebooks try to find the best Ma pairs for the underlying mentioned in their name.

The models here are long-only models because we realized that due to the high futures funds rate and the nature of the strategy which stays in a trade for around 25 days on average, it is better from a risk management point to not use leverage and futures contracts.

Thus here we find the best MA pairs for long-only strategies of the labeled underlying. The best-performing MA pairs and a heatmap that shows the performance of each of the MA pairs are included in each notebook. Performance here means the profits generated based on the backtest made in the virtual trading environment cloning the price action of underlying for the last 5 years.

### Day/Daily Notebooks
These notebooks are the final scripts in the form of notebooks. By running these notebooks every day the model stays up to date with recent price action and suggests trades for BTC price action based on the best MA pairs chosen in the notebooks before. The model gives you a liquidation price and an entry price for each trade. Trades take 25 days on average for the best-performing 20-60-day MA pair.

There is also PCA and LDA analysis of all of the trades suggested by the strategy in the last 5 years to better choose whether to take the position or not. These graphs show the winning and losing positions in a 2D plane and where the new trade is located. This is more visulizable and makes the decision to whether take the trade or not, alot easier.

## Contributers
Pouya Farivar        pouyam.fr@gmail.com
