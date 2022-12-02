# Trading fx eurusd h4 with RSI and machine learning
### !!! Disclaimer: The trading strategy used here is very simple, it is used for demonstration purpose only, not for trading. If you lose money, it's your own fucking responsibility.


## Pipeline:
[backtest (create dataset).ipynb ----> Machine learning.ipynb ---> backtest (with machine learning).ipynb]


## Summary
The purpose of this project is to improve an existing trading strategy with machine learning.
By backtesting a strategy (using backtesting.py) using a eurusd data before 2022, after that we get the backtest result data that we can use next for the machine learning.


From the data, we then label which trade is a win or loss based on the 'pnl' feature, if it's less than 0 (excluding commisions, spread, etc) it's a loss, if it's more than 0 its a profit. Next we create a classification model, which we then saved to a pkl files to load for production. 

Finally, we becktest again with RSI and the new model using the eurusd data from 2022. 

By being precise on the winning, raising the percentage of winning, we also remove some of the win trades that have a lower probability. Using machine learning for classifying probability of winning or losing trades, with existing trading strategy will reduce the number of trades being made.
