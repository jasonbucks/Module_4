# Module_4 Challenge - Risk Return Analysis

This project examines some historical data on the investment returns for four whale fund managers for the period October 1, 2014 through September 11, 2020.  The aim is to find the one fund with the most investment potential based on the key risk_management metrics: daily returns, standard deviations, Sharpe ratios, and betas.  These metrics will be compared to the S&P 500 Index to help evaluate their risk and return relative to the market as a whole.

---

## Technologies

This project leverages python 3.7.11 with the following packages:

* [pandas](https://pandas.pydata.org) - Use the Pandas library, along with JupyterLab, to collect, prepare and analyze data.

* [matplotlib](https://matplotlib.org) - For plotting the data on line graphs and box plots.

---

## Installation Guide

Before running the application first import the following libraries:

```python
  import pandas as pd
  from pathlib import Path
  %matplotlib inline
```

---

## Usage and Summary Analysis

To run the loan Crypto Arbitrage analysis, simply clone the repository and then run Jupyter Lab to open the Jupyter notebook.

Upon launching, the Jupyter notebook flows as follows:

1.  Collects the data stored in the Resources folder and stores in dataframes, using the Timestamp for an index.

2.  Prepares the data by dropping records with missing values, removing any $ signs in order to convert those records from strings to floats, and finally by confirming that there were no duplicated records.

3.  Analyzing the data by creating summary statistics for each dataframe as well as initial data visualizations, including the following plot overlay showing prices for both the Bitstamp and Coinbase exchanges for the entire 3 month period.  The areas showing blue over yellow indicate time where the price for Bitcoin is higher on Bitstamp than it is on Coinbase, indicating possible arbitrage opportunites. 

![Sample Bitcoin Price Plot](Images/Bitstamp_vs_Coinbase_2018_Jan_to_Mar.png)

4. Following this preliminary data analysis, each month was looked at separately in order to get an even better look at the data.  From there, three separate dates were chosen (one for each month) to represent the most likely days for successul Bitcoin arbitrage.  Each of these dates were analyzed in more detail, with the hopes of being able to draw conclusions as to any patterns or trends for arbitrage opportunities on the two Bitcoin exchanges.  

5. Key finding for each of the three dates selected:
    * January 28 - Bitstamp prices were more than 1 percent higher than Coinbase prices for 1,378 minutes, nearly 23 hours!  The average arbitrage profit spread, net of transaction fees, was $140 per Bitcoin on this day.
    
    ![January 28 Cumulative Returns](Images/Cumulative_Returns_20180128.png)
    
    * February 6 - Arbitrage opportunites existed for just 110 minutes on this day.  And the average profit spread had dropped to about $30 per Bitcoin.
    
    ![February 6 Cumulative Returns](Images/Cumulative_Returns_20180206.png)
    
    * March 14 - A very brief 4 minutes worth of arbitrage trading opportunites existed.  At least the average net profit per Bitcoin trade was up a bit to $35.
    
    ![March 14 Cumulative Returns](Images/Cumulative_Returns_20180314.png)
    

6. While the opportunities for Bitcoin arbitrage situations still existed in early 2018, these situations decreased drastically from January through the end of March of that year.  On top of that, when arbitrage situations did pop up, they lasted for only a few minutes.  On one of the best Bitcoin arbitrage days from January or 2018 (the 28th), one could make almost $200,000 just by buying one Bitcoin on Coinbase and then immediately selling it on Bitstamp.  And doing this once a minute pretty much uninterrupted for the entire day.  By February of that year, on the 6th, there were only a few hours throughout the day that one could do this.  And the amount of profit per trade was much smaller than it had been in the previous month.  Daily profits had dropped to just over $3000.  And in March, there were only a handful of minutes, throughout the entire month, where one could profit through Bitcoin arbitrage.  Perhaps the best day of March was on the 14th, and only $138 of profit could be made.  The arbitrage period lasted just 3 minutes that day.  Still worth it if these trades are entirely automated, but not worth the cost of having a paid employee monitor and exact the trades.

7. Of course, these cumulative profit sums are somewhat constrained by a few assumptions we have used throughout our analysis.  First, we are not technically limited to buying and selling just one Bitcoin at a time.  Each time an arbitrage opportunity presents itself, we could buy and sell much more in order to maximize profits.  However, the more we buy and sell, the faster the prices on Coinbase and Bitstamp will converge and the arbitrage opportunity will be gone that much sooner.  Secondly, we could use any profits realized from arbitrage buying opportunities to immediately reinvest in current or future arbitrage opportunities.  This would allow for a more robust compounding of investment returns.

---

## Contributors

Starter code was provided by UW Fintech Bootcamp.  Updates and analysis by Jason Buckholt.  A significant departure from the instructions listed was to reduce any and all profits per trade by the 1 percent transaction fees.  For example, if Bitcoin was listed at 10,000 on Coinbase, the instructions correctly pointed out that only prices above 10,100 (1 percent higher) on Bitstamp would be profitable enough to cover the transaction fees.  However, if the price on Bitstamp was 10,200, the instructions as written would have this giving us a profit of 200 when it should be only 100 - 10,200 (Bitstamp) minus 10,000 (Coinbase) minus 100 (1 percent transaction fee).  I assumed this was an oversight so I added in an extra calculation to back out the transaction cost. 

---

## License

When you share a project on a repository, especially a public one, it's important to choose the right license to specify what others can and can't with your source code and files. Use this section to include the license you want to use.

For now, only a License to Ill is needed.
