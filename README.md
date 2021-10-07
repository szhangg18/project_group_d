# Portfolio Optimizer
## A portfolio optimizer with share and cryptocurrency integration utilising the efficient frontier and modern portfolio theory

# Use cases
* This tool is helpful for an investor who has chosen a range of stocks they are bullish on but unsure how to allocate it efficiently 
* Users may choose both an optimum risk portfolio (lowest volatility) or a most efficient portfolio (maximum Sharpe ratio)
* It is recommended to include at most 8 assets at any time

# APIs
* This program currently utilises the Alpaca and Cryptowatch APIs (Binance)
* Since the program has been written in separate functions, any programmer can easily update which API they want to use, however depending on the output data from the API the data transformation process may need slight alterations. 
* Since Binance has only been operational since 2017, it can only retreieve the past 4 years worth of data. 

# Instructions 
* The program may be ran by calling the function `start_program(years=n)`, where n is the number of years the user wants to analyse for past data. We reommend 4 years as mentioned earlier. 
* Once the program is running, please input the cryptos you need, followed by the shares you need. 
* You may also enter the following commands when required:
    * "!done": please input command this once you have finished entering your desired asset class.
    * "!restart": please input this command if you wish to restart selection of the current asset class.
    * "!view": please input this command to view the current selected assets for the current asset class. 
* If there are any issues with the selected asset, different errors messages will appear based on the problem. 

# Process 
* Once you have entered your requested assets, the program will automatically output the weights for the lowest volatility portfolio and also the maximum sharpe ratio portfolio given the requested assets. 

# Limitations
* Due to our data cleaning process, outliers and missing data will be removed. Due to this, it is not recommended to input more than 8 assets at once as this may cause unreliable results. 
* Since crypto does not technically have a close price at the end of each day, we have treated the close price to be exactly in 24 hour intervals as of when the data was generated. We found this may cause significant changes in our returns each time the same portfolio was ran, depending on which precise second we generated our data. We believe this issue stemmed from slight differences in the prices each time we generated the data, which could cause ripple effects in which outliers were removed, thus affecting other share and cryptocurrency data.
* Lastly, due to the data cleaning process, we believe our correlation coefficients may have been effected. This is because during massive spikes or crashes, the market typically moves in the same direction. This may cause massive high correlation events to be removed as they may be considered outliers, thus underestimating the correlation coefficients. 