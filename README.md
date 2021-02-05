## Algorithmic Trading with Linear Regression

1.  Understanding of the Trading Problem  
      
    Forecasting financial asset returns has been one of the central topics for researchers across academia and the financial industry. In this project, our goal is to build machine learning models using the daily stock data of 50 companies to predict stock returns, and use the models to trade in the market.  
      
    The data consists of the daily stock data of a 756 day period. Data from Day 1 to Day 504 is for model training and testing. On Day 504 after the market closed, we received $1,000,000 to invest in the 50 stocks. Throughout the trading period Day 505 to Day 756, we made decisions on when and how much we buy or sell the stocks. By the end of Day 756, which is the last trading day, we sold off all of the stocks to cash in on our investments.  
      
    The following are the assumptions we held for this project:  
      
    

-   We take a no short sale rule.
    
-   We make a trading decision after the market closes on a day, and we buy and sell each stock at the next day’s adjusted closing price. For example, after the market closes on Day 600, we make a decision regarding whether to trade stock X on Day 601. If we decide to trade stock X on Day 601, we will trade at stock A’s adjusted closing price on Day 601.
    
-   We take the t+1 rule, which means if we buy a share of stock A at time t, we can only sell it at t+1.
    
-   We take two kinds of transaction costs into consideration: stamp duty (the tax charged by the government when we trade stock) and slippage (the difference between the expected execution price of an order and the actual execution price).
    

  

We took a three-step approach to this problem. First, we selected a trading strategy so that we can build our model accordingly. The trading strategy we selected based on industry research is Bollinger Bands trading. It looks for relatively extreme stock prices and seeks to profit by buying in at a low point and selling at a high point. Based on this strategy, we customized our portfolio - six stocks that have high variance and big price range, since Bollinger Bands trading will yield the most benefit when prices have plenty of large range fluctuations. Second, we built machine learning models to predict future stock return for our portfolio. We used existing expert variables and newly engineered variables, including a customized target y variable, to build the models. To maximize prediction accuracy, we performed feature and model selection for each stock in our portfolio, and selected the best rolling training window for each stock as well. Third, we wrote an automatic Bollinger Bands trading program with the prediction models incorporated to do trading, and calculated our performance metrics in the end.
