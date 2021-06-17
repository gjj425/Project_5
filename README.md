# Amazon Investment Model: IRR Efficiencies in Press Releases

Project timeframe: Two weeks

## Goals

This model examines Amazon stock outperformance as it relates to press release topicality. By linking each press release to a measure of performance against the market, the model attempts to identify press release topics that show higher instances of outperformance. Once identified, the model then establishes patterns of seasonality for topics deemed "outperforming", and uses this seasonality pattern to establish recommended buy and sell markers. 

## Content Links
1. [Running the Model: 2017-2020](https://github.com/gjj425/Amazon_Investment_Model/blob/main/amazon_trading.ipynb)
2. [Supporting Code for Python Objects](https://github.com/gjj425/Amazon_Investment_Model/blob/main/AmazonPrPatterns.py)
3. [Assumptions](#assumptions)
4. [Results](#results)
5. [Issues and Further Analysis](#issues-and-further-analysis)
6. Conclusions
7. Metis

## Assumptions
In order to compete the model, several assumptions were required to be made. The biggest of these assumptions are listed below.

1. *Topic Numbers* - It is assumed that the most efficient number of topics is somewhere between 1 and 40, although this number can be adjusted. A grid-search type of analysis is completed whereby the model finds the most efficient number of LDA topic divisions required, returning the topic division number with the highest number of outperforming topics. However, this grid-search requires an established range of LDA topic divisions.

2. *Press Release Outperformance* - A press release is considered to have "outperformed" if the Amazon daily return is higher than the return generated by the daily return on the Dow Jones multiplied by Amazon's one year beta.

3. *Topic Outperformance* - a Topic is considered to exhibit outperformance if more than 65% of the underlying press releases outperformed.

## Results
After [running through the model](https://github.com/gjj425/Amazon_Investment_Model/blob/main/amazon_trading.ipynb) the annual and total IRRs were as follows.

2018: -66.4%
2019: 3.47%
2020: 68.4%
2018, 2019 and 2020: 10.6%

If an investor were to hold for the entire year, rather than use this model, the results would be as follows:

2018: 28.3%
2019: 26.7%
2020: 76.4%

## Issues and Further Analysis
The model underperforms against a buy-and-hold strategy. There are a number of reasons why this might occur, which will need to be further tested and accounted for.

1. *Influence of the overall market* - Since the model minimizes the effects of the market by incorporating the market into its outperformance equation, any major market events can work against the model's efficiency. One example of this is at the end of 2018. While the model emphasizes the end of the year as a time with significant outperformance, market volatility impacted Amazon's stock price negatively. The best way to combat the impacts of the market is to understand under what conditions the model works best (stable growth, rapid growth, low growth, high volatility, low volatility, etc.)

2. *Create a rolling framework* - The model currently trains off of all press releases issued prior to the train/test split date, and predicts on a given period of time after the training period. Amazon has changed over time as a company. By creating a rolling framework, such as using the prior three years of press releases to predict the following quarter, the model may better reflect the company as it exists today.

## Conclusion
In conclusion, the model is able to identify outperforming topics though LDA topic analysis. However, the model underperforms when compared against a buy-and-hold strategy. Several adjustments will likely need to be made, which could include the incorporation of market conditions as a variable or a rolling framework to better reflect the company as it operates today.


        
