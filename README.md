## Overview

It's implementation of Q-learning applied to (short-term) stock trading. The model uses n-day windows of closing prices to determine if the best action to take at a given time is to buy, sell or sit.
As a result of the short-term state representation, the model is not very good at making decisions over long-term trends, but is quite good at predicting peaks and troughs.

## Results

Some examples of results on test sets:

S&P 500, 2015. Profit of $431.04.

Alibaba Group Holding Ltd, 2015. Loss of $351.59.

Apple, Inc, 2016. Profit of $162.73.

Google, Inc, August 2017. Profit of $19.37.

## Running the Code

To train the model, download a training and test csv files from [Yahoo! Finance](https://ca.finance.yahoo.com/quote/%5EGSPC/history?p=%5EGSPC) into `data/`
```
mkdir model
python train ^GSPC 10 1000
```

Then when training finishes (minimum 200 episodes for results):
```
python evaluate.py ^GSPC_2011 model_ep1000
```