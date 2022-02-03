---
id: WXoYpLmbGZWi9gVX
title: How to Collect Market Data (stocks/crypto)
desc: ''
updated: 1643865864172
created: 1626513463054
---
# How do I get stocks/crypto trading data

Ref: [Towards Data Science](https://towardsdatascience.com/best-5-free-stock-market-apis-in-2019-ad91dddec984), [Algotrading101](https://algotrading101.com/learn/yfinance-guide/), [awesome-quant | Data Sources](https://github.com/wilsonfreitas/awesome-quant#data-sources)

Paid official data sources:
- [IEX Cloud](https://iexcloud.io/)
    - [Pricing](https://iexcloud.io/pricing/) starts at USD 19/month. Has free plan 
- [Alpha Vantage](https://www.alphavantage.co/)
    - Has [addon](https://www.alphavantage.co/spreadsheets/) for spreadsheet apps
    - [Premium plan](https://www.alphavantage.co/premium/) starts at USD 50/month. It also has Free API key for consumers
- [polygon.io](https://polygon.io/)
    - Different [Pricing](https://polygon.io/pricing) for stocks, currencies and options. Has free plan
- [Alpaca](https://alpaca.markets/)
    - [Pricing](https://alpaca.markets/data) starts at USD 9/month. Has free plan
    - US stocks and etf only
    - [Paper trading](https://alpaca.markets/docs/trading-on-alpaca/paper-trading/) is a real-time simulation environment where you can test your code. You can reset and test your algorithm as much as you want using free, real-time market data. Paper trading simulates crypto trading as well. Paper trading works the same way as live trading end to end - except the order is not routed a live exchange

Free unofficial community package:
- manually download historical data from <https://www.investing.com/> or use [investpy](https://github.com/alvarobartt/investpy)
- [pandas-datareader](https://pydata.github.io/pandas-datareader/) Python package
- and many other can be found in this list [awesome-quant | Data Sources](https://github.com/wilsonfreitas/awesome-quant#data-sources)

## Resources

[awesome-quant](https://github.com/wilsonfreitas/awesome-quant)
- curated list of libraries, packages and resources for Quants

[QuantStats](https://github.com/ranaroussi/quantstats)
- Portfolio analytics, allowing quants and portfolio managers to understand their performance better by providing them with in-depth analytics and risk metrics

[TradeKit](https://github.com/hackingthemarkets/tradekit)
- list of various Python libraries and frameworks used for financial applications

[Algotrading101 | Yahoo Finance API Guide](https://algotrading101.com/learn/yahoo-finance-api-guide/)

[Algotrading101 | Alpha Vantage API Guide](https://algotrading101.com/learn/alpha-vantage-guide/)

[Algotrading101 | IEX API Guide](https://algotrading101.com/learn/iex-api-guide/)

[IEX cloud blog | How to Get Market Data in Python](https://iexcloud.io/community/blog/how-to-get-market-data-in-python)

[Analyzing Alpha | Get Historical Price Data from Polygon.io](https://analyzingalpha.com/get-historical-price-data-polygon)

[Analyzing Alpha | Insert Crypto Price Data Using SQLAlchemy, Python & Pandas](https://analyzingalpha.com/insert-crypto-price-data-sqlalchemy)

[Analyzing Alpha | Query Price Data Using SQLAlchemy, Python & Pandas](https://analyzingalpha.com/query-price-data-sqlalchemy)

[Analyzing Alpha | How to Create an Equities Database](https://analyzingalpha.com/create-an-equities-database)

[Analyzing Alpha | How to Create a Financial Statement Database](https://analyzingalpha.com/financial-statement-database)

[Thecleverprogrammer | Pandas Datareader using Python](https://thecleverprogrammer.com/2021/03/22/pandas-datareader-using-python-tutorial/)

[Algovibes | Pandas Dataframes and SQL - How to write dataframes into a sql database/get sql table to dataframe](https://www.youtube.com/watch?v=OjMDXTlVOYU)

[Algovibes | How to connect Python with a SQL database SQLITE](https://www.youtube.com/watch?v=pU53JUhSnkY)

[[Analyze cryptoassets using PostgreSQL and TimescaleDB|notes.reading.timescaledb-analyze-cryptoassets]]

[Part Time Larry | Create Tables with PostgreSQL and TimescaleDB](https://www.youtube.com/watch?v=P-flYBbmCws&list=PLvzuUVysUFOsrxL7UxmMrVqS8X2X0b8jd&index=4)

[Part Time Larry | Alpaca API, PostgreSQL, and TimescaleDB](https://www.youtube.com/watch?v=RAIqlK5K7-s)
- the author demonstrate how he initialized TimescaleDB using docker, get stock data from Alpaca API and populate them into the database 

[TimescaleDocs | Analyze historical intraday stock data](https://docs.timescale.com/timescaledb/latest/tutorials/analyze-intraday-stocks/)

[Erol Aspromatis | Get Stock Pricing Data From The Polygon.io API For Algo-Trading Using Python](https://www.youtube.com/watch?v=sTlBQ3nVuJE)

[[PythonForFinance - Build Financial Data Database with Python|notes.reading.build-financial-database-with-python]]

[Part Time Larry | QuantStats: Portfolio Analytics with Python Tutorial](https://www.youtube.com/watch?v=Dm8GaSYZPF8)

[Part Time Larry | IEX Cloud API - Stock Fundamentals Dashboard](https://www.youtube.com/watch?v=bPPJTc3JoMI)

[Part Time Larry | TradeWell Backtesting App](https://www.youtube.com/watch?v=zxI97CmYGh0)

## Getting started

Initially I intended to use Sqlite or PostgreSQL as the database engine. After reading about [[BigQuery|notes.tutorial.google-bigquery]], I incline to this solution, since its free tier offers 10GB storage and I don't need to manually manage the database. BigQuery is also integrated directly into [Deepnote](https://deepnote.com/) or Jupyter notebook.

1. Create a new Google account for BigQuery