# Supertrend
Stocks Supertrend Analysis in Python

In this project, we will place the Supertrend indicator on the price chart of a stock and observe the profit/loss situation by applying a backtest with the DCA strategy.

1. Importing Libraries: In this step, the necessary Python libraries for data processing (pandas), numerical operations (numpy), financial data fetching (yfinance) and plotting (matplotlib) were imported.
2. Supertrend Function: This function calculates the Supertrend indicator based on the provided DataFrame (df). It utilizes the Average True Range (ATR) to determine volatility and calculates the upper and lower bands for the Supertrend. The result is a DataFrame (result_df) containing Supertrend values, upper and lower bands.
3. Backtesting Function: With this function, a backtest of a trading strategy based on Supertrend with Dollar Cost Averaging (DCA) was performed. Initial investment, trading commission, DCA amount and more parameters are taken into account. The result is a DataFrame (transactions_df) containing transaction details and final equity value.
4. Downloading Financial Data: In this section, the yfinance library was used to download historical financial data for a specific symbol (in this case 'BTC-USD') starting from a specific date.
5. Applying Supertrend and Backtesting: In this step, the Supertrend function was applied to the financial data and the result was merged with the original DataFrame. The backtest function was then called to simulate trading based on the Supertrend strategy and the transaction details and final equity were obtained.
6. Plotting Results: In this section, closing prices are shown with Supertrend upper and lower bands. plt.yscale('log') was used to visualize the data on a logarithmic scale.
7. Printing Results: With the final code, transaction details and key performance metrics such as total profit and return on investment were then extracted into an Excel file.

First of all, I must say that the Supertrend and DCA backtest project is in the development phase, therefore there is no guarantee of profit when used as an investment indicator in financial markets. This project is just the first version and the strategy will be updated and continued. This section provides information on how to use the software.

There are important variables in the code that must be changed by the investor.

1. symbol = 'BTC-USD': By changing this variable, you can change the investment instrument and use the indicator on different instruments.
2. def Supertrend(df, atr_period=30, multiplier=8): By changing the atr_period and multiplier variables in this code, you can make Supertrend conform to the symbol you want.
3. initial_investment=10000: This variable determines how much money Supertrend will buy when it turns green, that is, when it gives a buying signal. (Default $10,000)
4. trading_commission=0: You can make the backtest closer to reality by entering a commission according to the commission rate of the broker you use.
5. dca_amount=1000, max_dca_count=10: According to the Dollar Cost Average strategy, the backtest tries to reduce the average by buying as the price decreases, thus minimizing the loss. Therefore, you should enter the amount of purchase for each cost average in the dca_amount section and the maximum number of times the cost average should be made in the max_dca_count variable. The default dca_amount value can be calculated as follows: (Investor's Total Capital/2)/max_dca_count.
7. dca_drop_percentage_on_long=5: Determines what percentage drop the cost averaging strategy should buy.

You can see the chart in Tableau:
https://public.tableau.com/views/SupertrendProject/Sheet1?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link

![Sheet 1](https://github.com/YavuzAkbay/Supertrend/assets/29518499/828a8829-1d1a-4448-9ff7-668e8494965a)
