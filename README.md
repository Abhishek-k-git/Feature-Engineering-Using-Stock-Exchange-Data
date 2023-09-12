## Feature Engineering using stock exchange dataset

![poster](https://github.com/Abhishek-k-git/Feature-Engineering-Using-Stock-Exchange-Data/blob/main/image/stock-exchange.jpg)

### Table of content
* [Overview](#Overview)
* [Data Source](#Data_Scource)
* [Visualization](#Visualization)
* [Evaluation](#Evaluation)

### Overview

The Japan Exchange Group, Inc. (JPX), in collaboration with AI tech firm AlpacaJapan, hosted a competition on kaggle aimed at enabling retail investors to explore quantitative trading. Participants will have to create models that can effectively analyze the Japanese financial market and formulate investment strategies. This involves ranking around 2,000 stocks based on expected returns, and participants will be evaluated on the difference in returns between the top and bottom 200 stocks. The competition offers access to comprehensive financial data from the Japanese market, thereby permitting thorough analysis.

```
├── Steps envolved in the process of model building
    ├── Data visualization using matplotlib, seaborn
    ├── Deriving market indicators
    |       ├── On-balance volume (OBV)
    |       ├── Average True Range (ATR)
    |       ├── The Money Flow Index (MFI)
    |       ├── The relative strength index (RSI)
    └── LGBM model training
```

#### Python liabraries used:

 - **General purpose** - pandas, numpy
 - **Visualization** - matplotlib, seaborn, plotly
 - **Model building** - lightgbm

### Data_Source

This dataset comprises historic data of numerous Japanese stocks and options for a forecasting competition. The competition uses the time series API. Since past stock prices aren't confidential, the data for the public leaderboard period is included in the competition dataset.

For the purpose of model building, I have selected to datasets namely:
**1. stock_list.csv :** Mapping between the SecuritiesCode and company names, plus general information about which industry the company is in.
**2. stock_prices.csv :** The core file of interest. Includes the daily closing price for each stock and the target column.

> The above two datasets can be found in the link below:
> [click to go to find above datasets](https://www.kaggle.com/competitions/jpx-tokyo-stock-exchange-prediction/data)

## Visualization

![Yearly Avg. Stock Return by Sector](https://github.com/Abhishek-k-git/Feature-Engineering-Using-Stock-Exchange-Data/blob/main/image/plot%201.png)

![Target Distribution by Sector](https://github.com/Abhishek-k-git/Feature-Engineering-Using-Stock-Exchange-Data/blob/main/image/plot%202.png)

![Most Corelated Stocks with Target variable](https://github.com/Abhishek-k-git/Feature-Engineering-Using-Stock-Exchange-Data/blob/main/image/plot%203.png)

![Stock Corelation Matrix](https://github.com/Abhishek-k-git/Feature-Engineering-Using-Stock-Exchange-Data/blob/main/image/plot%204.png)

### Evaluation

The competition is evaluated on the Sharpe ratio of daily spread returns. Participants need to rank each active stock on a given day. To calculate returns for one day, the top 200 ranked stocks are bought and the bottom 200 are shorted. Stocks are weighted according to their rankings and the total portfolio returns are computed. This assumes that the stocks are bought the day after and sold on the subsequent day. Data must be submitted using the provided Python API to ensure no forward-looking bias.

![Overall Feature Importance](https://github.com/Abhishek-k-git/Feature-Engineering-Using-Stock-Exchange-Data/blob/main/image/plot%205.png)
