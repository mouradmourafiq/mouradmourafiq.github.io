---
layout: post

type: "article"

title: "A simple python object to get stock data!"
subtitle: "A python interface to get stock related data from yahoo."
cover_image: posts/stock-market.jpg
cover_image_caption: "Stock market."

excerpt: "YahooFinance is a python interface that lets you get stock related data from yahoo."

author:
  name: Mourad Mourafiq.
  twitter: mmourafiq
  bio: Maths, Technology, Philosophy, Startups, ...
  image: logo.png
---

YahooFinance is a python interface that lets you get stock related data from yahoo.

The object executes queries and returns set of quotes data of stocks, indices or currency exchanges.

To use YahooFinance is quite easy:

{% highlight python linenos %}
yf = YahooFinance('GOOG,MSFT')
    print yf.get_symbols()
>> GOOG+MSFT
    yf.add_symbol('AAPL')
    print yf.get_symbols()
>> GOOG+AAPL+MSFT
    yf.remove_symbol('GOOG')
    print yf.get_symbols()
>> AAPL+MSFT
    print yf.get_ask()
>> 585.37
>> 26.45
    print yf.get_previous_close()
>> 585.28
>> 26.615
    print yf.get_52_week_high()
>> 705.07
>> 32.95
    for d in yf.get_historical_prices('20120101', '20120201', 'w'):
        print d
>> ('s=AAPL', [['Date', 'Open', 'High', 'Low', 'Close', 'Volume', 'Adj Clos'], ['2012-01-30', '445.71', '458.99', '445.39', '456.19', '12393700', '452.1'], ['2012-01-23', '422.67', '454.45', '419.55', '447.28', '17397900', '443.3'], ['2012-01-17', '424.20', '431.37', '419.75', '420.30', '10673200', '416.6'], ['2012-01-09', '425.50', '427.75', '418.66', '419.81', '9327900', '416.1'], ['2012-01-03', '409.40', '422.75', '409.00', '422.40', '10283900', '418.6']])
>> ('s=MSFT', [['Date', 'Open', 'High', 'Low', 'Close', 'Volume', 'Adj Clos'], ['2012-02-01', '29.79', '30.05', '29.76', '29.89', '67409900', '29.0'], ['2012-01-31', '29.66', '29.70', '29.23', '29.53', '50572400', '28.7'], ['2012-01-30', '28.97', '29.62', '28.83', '29.61', '51114800', '28.8'], ['2012-01-27', '29.45', '29.53', '29.17', '29.23', '44187700', '28.4'], ['2012-01-26', '29.61', '29.70', '29.40', '29.50', '49102800', '28.6'], ['2012-01-25', '29.07', '29.65', '29.07', '29.56', '59231700', '28.7'], ['2012-01-24', '29.47', '29.57', '29.18', '29.34', '51703300', '28.5'], ['2012-01-23', '29.55', '29.95', '29.35', '29.73', '76078100', '28.9'], ['2012-01-20', '28.82', '29.74', '28.75', '29.71', '165902900', '28.8'], ['2012-01-19', '28.16', '28.44', '28.03', '28.12', '74053500', '27.3'], ['2012-01-18', '28.31', '28.40', '27.97', '28.23', '64860600', '27.4'], ['2012-01-17', '28.40', '28.65', '28.17', '28.26', '72395300', '27.4'], ['2012-01-13', '27.93', '28.25', '27.79', '28.25', '60196100', '27.4'], ['2012-01-12', '27.87', '28.02', '27.65', '28.00', '49370800', '27.2'], ['2012-01-11', '27.43', '27.98', '27.37', '27.72', '65582400', '26.9'], ['2012-01-10', '27.93', '28.15', '27.75', '27.84', '60014400', '27.0'], ['2012-01-09', '28.05', '28.10', '27.72', '27.74', '59706800', '26.9'], ['2012-01-06', '27.53', '28.19', '27.53', '28.11', '99455500', '27.3'], ['2012-01-05', '27.38', '27.73', '27.29', '27.68', '56081400', '26.9'], ['2012-01-04', '26.82', '27.47', '26.78', '27.40', '80516100', '26.6'], ['2012-01-03', '26.55', '26.96', '26.39', '26.77', '64731500', '26.0']])
{% endhighlight %}