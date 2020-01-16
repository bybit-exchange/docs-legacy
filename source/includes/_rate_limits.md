# API Rate Limits
### Understanding Your Request Rate Limit
Every request to the API returns the fields shown in the code panel:

```
"rate_limit_status": 119,
"rate_limit_reset_ms": 1572114055663815,
"rate_limit": 120
```

* `rate_limit_status` - your remaining requests
* `rate_limit` - your current limit
* `rate_limit_reset_ms` - the timestamp indicating when your request limit resets if you have exceeded your rate_limit. Otherwise, this is just the current timestamp.


### Rate Limits For All Endpoints
<table class="custom_table">
  <tr>
    <th>limit</th>
    <th>path</th>
  </tr>
  <tr>
    <td rowspan="10">100/min</td>
    <td>open-api/order/create </td>
  </tr>
  <tr><td>open-api/order/cancel       </td></tr>
  <tr><td>open-api/stop-order/create  </td></tr>
  <tr><td>open-api/stop-order/cancel  </td></tr>
  <tr><td>open-api/order/replace      </td></tr>
  <tr><td>open-api/stop-order/replace </td></tr>
  <tr><td>v2/private/order/create     </td></tr>
  <tr><td>v2/private/order/cancel     </td></tr>
  <tr><td>v2/private/order/cancelAll  </td></tr>
  <tr><td>v2/private/stop-order/cancelAll </td></tr>
  <tr>
    <td rowspan="3">600/min</td>
    <td>open-api/order/list </td>
  </tr>
  <tr><td>open-api/stop-order/list </td></tr>
  <tr><td>v2/private/order </td></tr>
  <tr>
    <td>120/min</td>
    <td>v2/private/execution/list</td>
  </tr>
  <tr>
    <td rowspan="3">75/min</td>
    <td>user/leverage/save  </td>
  </tr>
  <tr><td>position/change-position-margin </td></tr>
  <tr><td>position/trading-stop           </td></tr>
  <tr>
    <td rowspan="2">120/min</td>
    <td>position/list  </td>
  </tr>
  <tr><td>user/leverage</td></tr>
  <tr>
    <td rowspan="3">120/min</td>
    <td>open-api/funding/prev-funding-rate  </td>
  </tr>
  <tr><td>open-api/funding/prev-funding      </td></tr>
  <tr><td>open-api/funding/predicted-funding </td></tr>
  <tr>
    <td rowspan="2">120/min</td>
    <td>open-api/wallet/fund/records  </td>
  </tr>
<tr><td>open-api/wallet/withdraw/list </td></tr>
<tr>
    <td rowspan="1">600/min</td>
    <td>open-api/api-key  </td>
  </tr>
</table>

### Order Limits
The number of orders per instrument that can be held entirely simultaneously:

* Active orders: 500
* Conditional orders: 10

### How to Raise Your API Limit
* Please read <a href="#understanding-bybit-39-s-liquidity-system">Understanding Bybit's Liquidity System</a> to understand how our system automatically allocates rate limits for users placing over 2000 orders per day.
* Please send your application email to <a href="mailto:api@bybit.com">api@bybit.com</a>. We will reply in 1-4 working days.


### Understanding Bybit's Liquidity System
Bybit uses an `Order Fill Ratio (OFR)` and `Liquidity Contribution Points (LCP)` to measure customers' contribution to our executable liquidity.

The `LCP` and `OFR` of different symbols are calculated separately.

#### Order Fill Ratio (OFR) Threshold
If you place more than `2000` orders per day on Bybit, please maintain your 7-day OFR above a `Minimum OFR threshold`, or Bybit may reduce your API request frequency limit.

##### Order Fill Ratio (OFR)
* `Order Fill Ratio (OFR)`: `Orders Filled` to `Orders Submitted to Bybit` to Bybit.
* `Orders Submitted to Bybit`: any order sent to Bybit.
* `Orders Filled`: any order that has been filled for any amount.
* `OFR = (number of orders filled / number of orders submitted to Bybit)`

##### Order Fill Ratio Example
User A submitted a limit order request which contains 4 bids and 4 asks, and these orders are placed in the orderbook at different price levels. Then, User A cancelled 2 bids and submits a new limit order request which contains 2 new bids.

At this time, User B submits a market order request, and matches with 2 of A's bids.

The OFR of this period is calculated as follows:

<pre class="center-column-nonindent">
User A:
Orders Filled = 2
Orders Submitted to Bybit = 8
QFR = 2/8 = 25%
</pre>

<pre class="center-column-nonindent">
User B:
Orders Filled = 1
Orders Submitted to Bybit = 1
QFR = 1/1 = 100%
</pre>


##### Minimum OFR Threshold
7-day OFR must be kept above 0.1%.


#### API Request Frequency Limits

Your API request frequency limit is based on your min `Liquidity Contribution Points (LCP)` of `7` days.


`LCP` and API request frequency threshold:

|  LCP     | Frequency Limit |
|  ----    | ----  |
| 20-100  | 800 times per minute |
| 10-20   | 600 times per minute |
| 5-10    | 400 times per minute |
| 2-5     | 200 times per minute |
| <2      | 100 times per minute |

##### Liquidity Contribution Points (LCP)

* `Liquidity Contribution Points (LCP) = POU * POA * 100`

##### Explanation
###### Effective Price Range

* `effective price range`: 6 tick sizes range around middle of best bid price and best ask price.

* Min `effective price`:  (best bid price + best ask price) / 2 - (3 * tick_size)

* Max `effective price`:  (best bid price + best ask price) / 2 + (3 * tick_size)

###### Effective Price Range example
<pre class="center-column-nonindent">
BTC best bid = 10000
BTC best ask = 10001
Effective Price Range: [(10000 + 10001) / 2 - 3* 0.5, (10000 + 10001) / 2 + 3* 0.5] = [9999,10002]
</pre>


###### POU
* `POU`: the proportion of your orders within `effective price range` to all your orders in orderbook

Bybit calculates your amount of orders within `effective price range` / amount of all your orders in orderbook, and then performs a 1-Day Time-Weighted-Average over the series of seconds rates.

###### POU example
User C bids 2000 contracts for $9995 and bids 8000 contracts for $9999, while effective price range is [9999,10002]

<pre class="center-column-nonindent">
amount of User C's orders within effective price range = 8000
amount of all User C's orders = 2000 + 8000 = 10000
POU = 8000 / 10000 = 0.8
</pre>


###### POA
* `POA`: the proportion of your orders within `effective price range` to all orders within `effective price range` in orderbook.

Bybit calculates your amount of orders within `effective price range` / amount of all orders within `effective price range` in orderbook, and then performs a 1-Day Time-Weighted-Average over the series of seconds rates.

###### POA example
User C only has 8000 contracts within effective price range, while Bybit have 200000 contracts within effective price range in orderbook.

<pre class="center-column-nonindent">
amount of User C's orders within effective price range = 8000
amount of all orders within effective price range = 200000
POA = 8000 / 200000 = 0.04
</pre>

<aside class="notice">
Prior notice will be given via the website if we update this mechanism.
</aside>
