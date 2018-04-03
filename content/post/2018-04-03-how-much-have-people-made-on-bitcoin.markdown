
---
title: "How Much Have People Made on Bitcoin?"
author: "Sam Weiss"
date: "2018-04-03"
tags: R
output: html_document
---

## Intro:

How much has bitcoin made Society? This post will calculate the realized gains of bitcoin (up to year 2013) as a measure of how much society has made off of bitcoin.

## How are realized gains different from market capitalization?

Realized gains measure the amount of money people can claim to have made off of bitcoin. This can be markedly different from the market capitalization. 

For instance suppose we have two stocks A and B both with 100 shares and both with a price of $1 at time t_0. Assume the price of both went up to $2 at time t_1. However, suppose all of shares in stock A traded to new people while only one share of stock B traded to new people. The change in realized gains for stock A is $100 while the realized gains in stock B is $1 (assuming everyone for both stocks paid a price of $1 initially).


The example illustrates how market cap and realized gains are different depending on distribution of shares respective previously traded prices.



## Does Realized Gains Mean Anything Else?

The above example illustrates why researching realized gains might be interesting in its own right. For instance: it's much easier to find only one person to believe high prices are valid as opposed to 100 people who do. It may be that increasing prices without corresponding increase in realized gains may lead to evidence of a bubble.



## Why Calculate on Bitcoin?


The block chain allows anyone to see the previous time a user purchased a bitcoin and the amount. We can therefore calculate the average price purchased for each user. Since we do not have this information in stocks or currency we cannot calculate it directly for those assets.


There is one heavy assumption on this: that all ID's (bitcoin address) stay the same. However, it's common practice that a user his ID when making a trade. This means that the realized gains calculated below are an upper bound since many transactions are self-traded.


## Calculations / Results:

I obtained bitcoin transaction data with a package called [BlockSci](https://github.com/citp/BlockSci). I calculated the average purchase price of a particular user's bitcoin holding calculate the realized / unrealized gains accordingly. 

Below is a time series chart of market capitalization, realized gains, and unrealized gains up to December 31 2012. 



```
## Warning: package 'ggplot2' was built under R version 3.3.2
```

```
## Warning in as.POSIXlt.POSIXct(x): unknown timezone 'zone/tz/2018c.1.0/
## zoneinfo/America/Denver'
```

<img src="/post/2018-04-03-how-much-have-people-made-on-bitcoin_files/figure-html/unnamed-chunk-1-1.png" width="672" />

It's interesting to note how realized gains does not increase or decrease significantly during the 'bubble' of mid 2012. 

By the end of 2012 people have made ~ $79 million dollars of realized gains on bitcoin. This compares with market capitalization of ~ $142 million. 

## Example Data
Below is an example transaction history for user_id = 1

|time       | block_creater| id| height|  num_traded|   price| cumulative_shares| avg_purchase_price|
|:----------|-------------:|--:|------:|-----------:|-------:|-----------------:|------------------:|
|2012-12-31 |             0|  1| 214411|  -0.0005000| 13.5100|         -58.00118|          0.8648193|
|2012-12-19 |             0|  1| 212748|   0.0000000| 13.5990|         -58.00068|          0.8647103|
|2012-11-28 |             0|  1| 210000|  -0.2500000| 12.3477|         -58.00068|          0.8647103|
|2012-11-02 |             0|  1| 206133|  -0.0100000| 10.4688|         -57.75068|          0.8150009|
|2012-10-14 |             0|  1| 203236|  -0.0331232| 11.7389|         -57.74068|          0.8133290|
|2012-10-03 |             0|  1| 201702|  -0.0001000| 12.8900|         -57.70756|          0.8070579|
|2012-09-11 |             0|  1| 198260|  -0.0441112| 11.3308|         -57.70746|          0.8070370|
|2012-09-11 |             0|  1| 198259|  -0.0582112| 11.3308|         -57.66334|          0.7989865|
|2012-09-11 |             0|  1| 198258|  -0.0110001| 11.3308|         -57.60513|          0.7883439|
|2012-09-01 |             0|  1| 196682|  -1.0101010|  9.9654|         -57.59413|          0.7863304|
|2012-08-07 |             0|  1| 192712|  -0.0005000| 11.1000|         -56.58403|          0.6224716|
|2012-08-06 |             0|  1| 192534|   0.0000000| 10.8552|         -56.58353|          0.6223790|
|2012-08-03 |             0|  1| 192056|  -0.0003995| 10.9700|         -56.58353|          0.6223790|
|2012-07-28 |             0|  1| 191184|  -0.0005000|  8.8881|         -56.58313|          0.6223060|
|2012-07-28 |             0|  1| 191157|  -0.0005000|  8.8881|         -56.58263|          0.6222329|
|2012-07-24 |             0|  1| 190453|  -0.0026534|  8.6000|         -56.58213|          0.6221599|
|2012-07-20 |             0|  1| 189913|  -0.1000000|  8.5200|         -56.57948|          0.6217858|
|2012-07-18 |             0|  1| 189695|  -0.0220000|  9.1098|         -56.47948|          0.6078015|
|2012-07-15 |             0|  1| 189170|  -0.0010000|  7.6210|         -56.45748|          0.6044885|
|2012-07-15 |             0|  1| 189169|  -0.0624000|  7.6210|         -56.45648|          0.6043643|
|2012-07-02 |             0|  1| 187212|  -0.1153000|  6.7600|         -56.39408|          0.5966004|
|2012-06-28 |             0|  1| 186641|  -0.1234500|  6.6059|         -56.27878|          0.5839732|
|2012-06-12 |             0|  1| 184132|  -1.2343210|  5.7000|         -56.15533|          0.5707348|
|2012-06-12 |             0|  1| 184127|  -1.2345600|  5.7000|         -54.92101|          0.4554573|
|2012-06-07 |             0|  1| 183423|  -0.0010000|  5.5910|         -53.68645|          0.3348551|
|2012-06-01 |             0|  1| 182508|  -0.0040000|  5.2748|         -53.68545|          0.3347572|
|2012-05-25 |             0|  1| 181523|  -0.0020000|  5.1455|         -53.68145|          0.3343891|
|2012-05-23 |             0|  1| 181286|  -0.0010000|  5.1397|         -53.67945|          0.3342098|
|2012-05-18 |             0|  1| 180618|  -0.0010000|  5.1180|         -53.67845|          0.3341203|
|2012-05-10 |             0|  1| 179528|  -0.0000100|  4.8500|         -53.67745|          0.3340312|
|2012-05-10 |             0|  1| 179525|   0.0000000|  4.8500|         -53.67744|          0.3340303|
|2012-04-26 |             0|  1| 177317|  -0.0000019|  5.0976|         -53.67744|          0.3340303|
|2012-04-14 |             0|  1| 175621|  -0.0010000|  4.9597|         -53.67744|          0.3340302|
|2012-04-03 |             0|  1| 174138|  -0.0000004|  4.9520|         -53.67644|          0.3339440|
|2012-04-03 |             0|  1| 174128|  -0.1234568|  4.9520|         -53.67644|          0.3339439|
|2012-03-27 |             0|  1| 173046|  -0.5000000|  4.8113|         -53.55298|          0.3232978|
|2012-03-23 |             0|  1| 172435|  -0.0424242|  4.6860|         -53.05298|          0.2810005|
|2012-03-21 |             0|  1| 172202|  -1.0000067|  4.8149|         -53.01055|          0.2774752|
|2012-03-21 |             0|  1| 172165|  -0.0100000|  4.8149|         -52.01055|          0.1902341|
|2012-03-21 |             0|  1| 172153|  -0.0268877|  4.8149|         -52.00055|          0.1893448|
|2012-03-07 |             0|  1| 170060|   0.0040000|  4.9375|         -51.97366|          0.1869518|
|2012-03-07 |             0|  1| 170052|  -0.0040000|  4.9375|         -51.97766|          0.1869518|
|2012-02-11 |             0|  1| 166365|   0.0000000|  5.6005|         -51.97366|          0.1865862|
|2012-02-03 |             0|  1| 165214|  -1.0000000|  5.9593|         -51.97366|          0.1865862|
|2012-02-03 |             0|  1| 165084|   0.0100000|  5.9593|         -50.97366|          0.0733372|
|2012-01-30 |             0|  1| 164467|  -0.0100000|  5.4905|         -50.98366|          0.0733372|
|2012-01-13 |             0|  1| 161943|  -0.0010000|  6.4100|         -50.97366|          0.0722745|
|2011-11-24 |             0|  1| 154568|  -0.8426597|  2.4321|         -50.97266|          0.0721502|
|2011-10-02 |             0|  1| 147782|  -0.0001004|  5.0270|         -50.13000|          0.0324806|
|2011-09-26 |             0|  1| 146964|   0.0000000|  4.8697|         -50.12990|          0.0324706|
|2011-08-11 |             0|  1| 140494|  -0.0023000|  9.4625|         -50.12990|          0.0324706|
|2011-07-08 |             0|  1| 135235|  -0.0010000| 14.3140|         -50.12760|          0.0320379|
|2011-07-06 |             0|  1| 134995|  -0.0666000| 14.7835|         -50.12660|          0.0317530|
|2011-06-17 |             0|  1| 131408|  -0.0100000| 15.6810|         -50.06000|          0.0121272|
|2011-06-04 |             0|  1| 128554|  -0.0100000| 18.8900|         -50.05000|          0.0089966|
|2011-06-01 |             0|  1| 127943|  -0.0100000|  9.5700|         -50.04000|          0.0052234|
|2011-06-01 |             0|  1| 127909|   0.0000000|  9.5700|         -50.03000|          0.0033116|
|2011-05-28 |             0|  1| 127280|  -0.0100000|  8.3001|         -50.03000|          0.0033116|
|2011-05-13 |             0|  1| 123723|  -0.0100000|  8.1980|         -50.02000|          0.0016529|
|2010-07-29 |             0|  1|  71036|  -0.0100000|  0.0699|         -50.01000|          0.0000140|
|2009-01-03 |             1|  1|      0| -50.0000000|  0.0000|         -50.00000|          0.0000000|
