# Verve Group Task

Thoughts and Assumptions about the given data:

The given data has **app, bid_price ,win, events**  as the columns.  The bid_price is a continuous column in nature. In practical scenario, we can bid with any continuous value > 0. 

Naturally,

bid_price > 0 ( bid_price will always be greater 0 otherwise it does not makes sense )

bid_price < 9 ( since we already got win_rate of 100% with this bid_price) 

Note : 100% win_rate would mean at this bid, there is a 100% chance we will win.

In practical scenario, we can bid for any price but in the given table we have price in [0.01, 0.1, 0.2, 0.4, 0.5, 0.75, 1, 2, 5, 9] . 

Observations (for app A):

1. There is a 10x change in number of events with every every bid_price.
2. The most competing bid_prices are ~ 0.2.

Assumption:

1. Maximum number of bids are at 0.2 bid_price i.e. we are considering 0.2 has the value with maximum bids that were made 

### Answer 1:

Here is the table which has the win_rate for the price mentioned :

| app | bid_price | winrate | total_events |
| --- | --- | --- | --- |
| A | 0.01 | 0 | 100000 |
| A | 0.1 | 0.3 | 10000 |
| A | 0.2 | 0.2 | 10000000 |
| A | 0.4 | 0.3 | 1000000 |
| A | 0.5 | 0.2 | 100000 |
| A | 0.75 | 0.3 | 10000 |
| A | 1 | 0.6 | 1000 |
| A | 2 | 0.7 | 100 |
| A | 5 | 0.8 | 10 |
| A | 9 | 1 | 1 |

### Answer 2:

The simple answer is to **maximize** the *net_revenue ,* we have to **minimize**  the *bid_price.* 

In the original table and considering the win_rate. 0.2 bid_price has just win_rate of 20%, but the *total_events* =  10,000,000. So basically, we won 2,000,000 times. 

The most optimal *bid_valuation* that we should send ~ 0.2 because even if the advertiser is willing to pay 0.21$ we get *net_revenue as* 0.01 * 2000000 = **20,000$ .**

Having said that, I would also investigate more around 0.1$ bid_price by doing more bids around the value to see how the *winrate* changes  ****if we increase the number of *total_events.*
