## Stock Market Predictions based on Daily News
Based on the World Daily News, can you predict with confidence to buy or sell a stock with better
accuracy and precision when you focus on certain GICS sectors?

### Motivation
Many of the machine learning algorithms look at the stock market as a whole rather than analyzing the data in specific sectors.  Will you find better correlation to oil price fluctuation with Middle East news or China news and consumer staples?

### Datasets
Plan is to combine the News articles from Aaron7sun’s Daily News for Stock Market Prediction dataset
and Dominik Gawlik’s dataset from New York Stock Exchange. Only gather data from the same date
ranges (i.e. 1/4/2010-7/1/2016).

News Dataset: RedditNews.csv
- Source: https://www.kaggle.com/lseiyjg/use-news-to-predict-stock-markets
- Dimensions: 73608 x 2.
- Columns: Date, Label (DJIA went up) and 25 columns for the top 25 news of the day.
- Description: The top 25 world news from Reddit
- Usage: Group all the news articles by date then see if there is correlation between the news
sentiment and the daily stocks

News Dataset: prices-split-adjusted.csv
- Source: https://www.kaggle.com/dgawlik/nyse
- Dimensions: 851264 x 7.
- Columns: Date, Symbol, Open, Close, Low, High and Volume.
- Description: NYSE stocks on a daily basis for the S&P 500. The opening and closing bell.
- Usage: Used to aggregate stock market changes by GICS sectors. Calculate positive change (1) if
stock went up for 1 sigma. Calculate negative change (-1) if stock went down by 1 sigma. Label
zero (0) if stock had no discernible change.

### Features
- Utilize Bag of Words (BOW) and Term Frequency (TF-IDF) to determine features that best correlate to certain sectors
- Similar to Dow Jones, combine and average the top 500 stocks by GICS sector and average it by number of stocks
- Setup control thresholds to classify labels:  2 sigma or standard deviations away.
    "-1" drop in price 2 sigmas down
    "1" increase in price 2 sigmas up
    "0" change in between 2 sigmas away
- Run undersampling algorithms to level the positive/negative results
- Test different time-based splits to test future stock prices based on historical data such as expanded and rolling window
- Utilize Sentiment to determine polarity and subjectivity of each article
	
### Models
Utilize XGBoost and Decision Tree algorithm to train and fit the data

## Author
Patrick Salazar