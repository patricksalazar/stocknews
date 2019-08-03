## Focused Stock Market Predictions based on Daily News
Can you make better stock market predictions if you focus on certain industries that are more affected by Daily News

### Motivation
Many of the machine learning algorithms look at the stock market as a whole rather than analyzing the data in specific sectors.  Will you find better correlation to oil price fluctuation with Middle East news or China news and consumer staples?

### Datasets
Combine the Daily news dataset with the NYSE stock exchnage data for S&P 500.  Analysis the data for particular GICS sectors.
- [Use News to Predict Stock Markets] https://www.kaggle.com/lseiyjg/use-news-to-predict-stock-markets
- [New York Stock Exchange] https://www.kaggle.com/dgawlik/nyse

### Features
- Utilize Bag of Words (BOW) and Term Frequency (TF-IDF) to determine features that best correlate to certain sectors
- Similar to Dow Jones, combine and average the top 500 stocks by GICS sector and average it by number of stocks
- Setup control thresholds to classify labels:  2 sigma or standard deviations away.
    "-1" drop in price 2 sigmas down
    "1" increase in price 2 sigmas up
    "0" change in between 2 sigmas away

### Models
Utilize the SKLearn Logistic Regression algorithm to train and fit the data

## Author
Patrick Salazar