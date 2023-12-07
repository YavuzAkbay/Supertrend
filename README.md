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

Ilk olarak soylemeliyim ki Supertrend ve DCA backtest projesi gelistirme asamasindadir dolayisiyla finansal piyasalarda yatirim indikatoru olarak kullanildiginda hicbir sekilde kazanc garantisi verilmemektedir. Bu proje daha ilk versiyondur ve strateji guncellenerek devami gelecektir. Bu bolum yazilimin nasil kullanilacagi hakkinda bilgi vermektedir.

Kodun icerisinde yatirimci tarafindan degistirilmesi gereken muhim degiskenler bulunmaktadir.

1. symbol = 'BTC-USD' : Bu degiskeni degistirerek yatirim enstrumanini degistirebilir ve indikatoru farkli enstrumanlar uzerinde kullanabilirsiniz.
2. def Supertrend(df, atr_period=30, multiplier=8) : Bu kod icerisindeki atr_period ve multiplier degiskenlerini degistirerek Supertrend'in istediginiz sembole uygun hale gelmesini saglayabilirsiniz.
3. initial_investment=10000 : Bu degisken Supertrend yesile dondugunde, yani alim sinyali verdiginde ne kadarlik bir alim yapacagini belirler. (Varsayilan 10.000$)
4. trading_commission=0 : Kullandiginiz broker'in komisyon oranina gore bir komisyon girerek backtesti daha gercege yakin hale getirebilirsiniz.
5. dca_amount=1000, max_dca_count=10 : Dolar Maliyet Ortalama stratejisine gore backtest fiyat dustukce alim yaparak ortalamayi dusurmeye, boylece zarari en aza indirmeye calismaktadir. Dolayisiyla dca_amount kismina her maliyet ortalamada ne kadarlik bir alim yapacagini ve max_dca_count degiskenine de en fazla kac defa maliyet ortalamasi yapmasi gerektigi verisini girmelisiniz. Varsayilan dca_amount degeri su sekilde hesaplanabilir: (Yatirimcinin Toplam Sermayesi/2)/max_dca_count.
7. dca_drop_percentage_on_long=5 : Maliyet ortalama stratejisinin % kac dususte alim yapmasi gerektigini belirler. 
