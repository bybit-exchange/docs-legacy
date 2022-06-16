# t(:marketdata)
t(:market_para_auth)

### t(:orderbook)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/public/order-book/L2?category=linear&symbol=BTCUSDT'
```

```python--old
//TODO: change to v3
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Market.Market_orderbook(symbol="BTCUSD").result())
```

```python--pybit

```javascript
{
    "retCode": 0,
    "retMsg": "success",
    "result": {
        "s": "BTCUSDT",
        "b": [
            [
                "28806",
                "0.06"
            ],
            [
                "28807",
                "5.005"
            ]
        ],
        "a": [
            [
                "29004",
                "0.001"
            ],
            [
                "29012",
                "0.017"
            ]
        ],
        "ts": 1653638043149,
        "u": 4912426
    }
}
```

t(:market_para_orderbook)
t(:dv3_orderbookPara)

<aside class="notice">
t(:market_aside_orderbook)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=v3obL2>/derivatives/v3/public/order-book/L2</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#v3obL2"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|------ |
|category |<b>true</b>|string |t(:dv3_category)|
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|limit |false |int |t(:dv3_orderbookLimit) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|p |string |t(:row_comment_resp_price) |
|v |string |t(:row_comment_resp_volume) |
|b |Arrays |t(:dv3_orderbookBids) |
|a |Arrays |t(:dv3_orderbookAsks) |
|u |string |t(:dv3_orderbookUpdateId) |
|ts |int |t(:dv3_orderbookTimeStamp) |


### t(:querykline)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/public/kline?category=linear&symbol=BTCUSDT&interval=D&start=1652112000000&end=1652544000000'
```

```python--old

```

```python--pybit

```


> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "list": [
      {
        "start": "1652140800000",
        "open": "30043.5",
        "high": "32700",
        "low": "29601",
        "close": "30982.5",
        "volume": "12705.051",
        "turnover": "398739881.4375",
        "symbol": "BTCUSDT",
        "interval": "D"
      }
    ],
      "category": "linear"
  }
}
```

t(:market_para_querykline)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dv3kList>/derivatives/v3/public/kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dv3kList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:dv3_category) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|<a href="#kline-interval-interval">interval</a> |<b>true</b> |string |t(:dv3_klineInterval) |
|start |<b>true</b> |integer |t(:row_comment_startTime_ms) |
|end |<b>true</b> |integer |t(:row_comment_endTime_ms) |
|limit |false |integer |t(:row_comment_limit_200) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:dv3_category) |
|symbol |string |t(:row_comment_symbol) |
|<a href="#kline-interval-interval">interval</a> |string |t(:row_comment_interval) |
|start |integer |t(:dv3_klineRespStart) |
|open |string |t(:row_comment_open) |
|high |string |t(:row_comment_high) |
|low |string |t(:row_comment_low) |
|close |string |t(:dv3_klineRespClose) |
|volume |string |t(:dv3_klineRespVolume) |
|turnover |string |t(:dv3_klineRespTurnover) |

### t(:dv3_tickerHead)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/public/tickers?category=linear&symbol=BTCUSDT'
```

```python--old


```

```python--pybit


```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "list": [
      {
        "symbol": "BTCUSDT",
        "bidPrice": "28880",
        "askPrice": "28880.5",
        "lastPrice": "28868.50",
        "lastTickDirection": "ZeroPlusTick",
        "prevPrice24h": "29065.00",
        "price24hPcnt": "-0.00676",
        "highPrice24h": "29550.00",
        "lowPrice24h": "28232.50",
        "prevPrice1h": "28814.00",
        "markPrice": "28883.26",
        "indexPrice": "28880.64",
        "openInterest": "9559.45",
        "turnover24h": "253089983.0199994",
        "volume24h": "8782.69399999",
        "fundingRate": "0.0001",
        "predictedFundingRate": "0.0001",
        "nextFundingTime": "2022-05-28T16:00:00Z"
      }
    ]
  }
}
//t(:resp_field_option_list)
{
  "retCode": 0,
  "retMsg": "SUCCESS",
  "result": {
  "category": "option",
    "symbol": "BTC-30SEP22-400000-C",
    "bidPrice": "0",
    "bidSize": "0",
    "bidIv": "0",
    "askPrice": "20",
    "askSize": "1.1",
    "askIv": "1.4315",
    "lastPrice": "5",
    "highPrice24h": "0",
    "lowPrice24h": "0",
    "markPrice": "0.17190116",
    "indexPrice": "28770.26",
    "markPriceIv": "1.0629",
    "underlyingPrice": "29069.3",
    "openInterest": "3.31",
    "turnover24h": "0",
    "volume24h": "0",
    "totalVolume": "6",
    "totalTurnover": "43",
    "delta": "0.00004702",
    "gamma": "0.00000001",
    "vega": "0.03306874",
    "theta": "-0.0140667",
    "predictedDeliveryPrice": "0",
    "change24h": "0"
}
}
```

t(:dv3_marketTickerPara)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dv3Tickers>/derivatives/v3/public/tickers</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dv3Tickers"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:derivativesV3) |
|symbol |false |string |t(:dv3_tickerSymbol) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| category |string |t(:derivativesV3) |
| askIv |string |t(:askIv) |
| deliveryTime |string |t(:deliveryTime) |
| price24hPcnt |string |t(:row_comment_resp_price_24h_pcnt) |
| nextFundingTime |string |t(:row_comment_resp_next_funding_time) |
| predictedDeliveryPrice |string |t(:dv3_tickPredictedDeliveryPrice) |
| countdownHour |number |t(:row_comment_resp_countdown_hour) |
| indexPrice |string |t(:row_comment_resp_index_price) |
| prevPrice24h |string |t(:row_comment_resp_prev_price_24h) |
| openInterest |string |t(:row_comment_resp_open_interest) |
| openInterestValue |string |t(:dv3_openInterestRespValue) |
| underlyingPrice |string |t(:usdcUnderlyingPrice) |
| volume24h |number |t(:row_comment_resp_volume_24h) |
| symbol |string |t(:row_comment_symbol) |
| vega |number |t(:vega) |
| lastPrice |string |t(:row_comment_resp_last_price) |
| totalVolume |string |t(:row_comment_resp_total_volume) |
| bidPrice |string |t(:bidPrice) |
| totalTurnover |number |t(:row_comment_resp_total_turnover) |
| turnover24h |number |t(:row_comment_resp_turnover_24h) |
| askPrice |string |t(:askPrice) |
| fundingRate |string |t(:row_comment_funding_rate) |
| bidSize |string |t(:bidSize) |
| bidIv |string |t(:bidIv) |
| highPrice24h |string |t(:row_comment_resp_high_price_24h) |
| delta |string |t(:delta) |
| theta |string |t(:theta) |
| askSize |string |t(:askSize) |
| price1hPcnt |string |t(:row_comment_resp_price_1h_pcnt) |
| prevPrice1h |string |t(:row_comment_resp_prev_price_1h) |
| markPrice |string |t(:row_comment_resp_mark_price) |
| gamma |string |t(:gamma) |
| deliveryFeeRate |string |t(:dv3_tickDeliveryFeeRate) |
| lowPrice24h |string |t(:row_comment_resp_low_price_24h) |
| markPriceIv |string |t(:markPriceIv) |
| predictedFundingRate |string |t(:row_comment_predicted_funding_rate) |
| basisRate |string |t(:dv3_tickBasisRate) |


### t(:dv3_instrHead)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/public/instruments-info?category=linear&symbol=BTCUSDT'
```

```python--old


```

```python--pybit


```


> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "list": [
      {
        "symbol": "BTCUSDT",
        "contractType": "LinearPerpetual",
        "status": "ONLINE",
        "baseCoin": "BTC",
        "quoteCoin": "USDT",
        "priceScale": "2",
        "leverageFilter": {
          "minLeverage": "1",
          "maxLeverage": "100",
          "leverageStep": "0.01"
        },
        "priceFilter": {
          "minPrice": "0.50",
          "maxPrice": "999999.00",
          "tickSize": "0.50"
        },
        "lotSizeFilter": {
          "maxTradingQty": "20.000",
          "minTradingQty": "0.001",
          "qtyStep": "0.001",
          "postOnlyMaxTradingQty": "100.000"
        },
        "category": "linear",
        "launchTime": "1585526400000"
      }
    ],
      "cursor": "eyJmaXJzdF9zeW1ib2xfaW5fcGFnZSI6IkJUQ1VTRFQiLCJsYXN0X3N5bWJvbF9pbl9wYWdlIjoiQlRDVVNEVCJ9"
  }
}

//t(:resp_field_option_list)
{
  "retCode": 0,
  "retMsg": "success",
  "result": {
  "resultTotalSize": 1,
    "cursor": "",
    "dataList": [
    {
      "category": "option",
      "symbol": "BTC-30SEP22-400000-C",
      "status": "ONLINE",
      "baseCoin": "BTC",
      "quoteCoin": "USD",
      "settleCoin": "USDC",
      "optionsType": "Call",
      "launchTime": "1649923200000",
      "deliveryTime": "1664524800000",
      "deliveryFeeRate": "0.00015",
      "priceFilter": {
        "minPrice": "5",
        "maxPrice": "10000000",
        "tickSize": "5"
      },
      "lotSizeFilter": {
        "maxOrderQty": "200",
        "minOrderQty": "0.01",
        "qtyStep": "0.01"
      }
    }
  ]
}
}
```

t(:dv3_marketInstrPara)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dv3Symbols>/derivatives/v3/public/instruments-info</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dv3Symbols"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|catetory |<b>true</b> |string |t(:dv3_category) |
|symbol |false |string |t(:row_comment_symbol) |
|status |false |string |t(:row_response_comment_status) |
|direction |false |string |t(:dv3_pageDirection) |
|limit |false |string |t(:row_comment_limit_500_1000) |
|cursor |false |string |t(:dv3_cursor) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|catetory |<b>true</b> |string |t(:dv3_category) |
|symbol |string |t(:row_comment_symbol) |
|contractType |string |t(:dv3_instrContractType) |
|status |string |t(:row_response_comment_status) |
|baseCoin |string |t(:dv3_instrBaseCoin) |
|quoteCoin |string |t(:dv3_instrQuoteCoin) |
|settleCoin |string |t(:dv3_instrSettleCoin) |
|optionsType |string |t(:dv3_OptionType) |
|launchTime |number |t(:dv3_instrLaunchTime) |
|deliveryTime |number |t(:dv3_instrDeliveryTime) |
|deliveryFeeRate |number |t(:deliveryFeeRate) |
|priceScale |number |t(:dv3_instrPriceScale) |
|minLeverage |number |t(:minLeverage) |
|maxLeverage |number |t(:maxLeverage) |
|leverageStep |string |t(:leverageStep) |
|minPrice |string |t(:minPrice) |
|maxPrice |string |t(:maxPrice) |
|tickSize |string |t(:tickSize) |
|maxOrderQty |number |t(:dv3_instrMaxOrderQty) |
|minOrderQty |number |t(:dv3_instrMinOrderQty) |
|qtyStep |number |t(:qtyStep) |
|nextPageCursor |string |t(:dv3_cursor) |


### t(:markpricekline)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/public/mark-price-kline?category=linear&symbol=BTCUSDT&interval=D&start=1652112000000&end=1652544000000'
```

```python--old

```

```python--pybit


```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "success",
    "result": {
        "list": [
            {
                "start": "1652140800000",
                "open": "30090.77",
                "high": "32642.46",
                "low": "29752.23",
                "close": "31015.33",
                "symbol": "BTCUSDT",
                "interval": "D"
            },
            {
                "start": "1652227200000",
                "open": "31015.33",
                "high": "32157.68",
                "low": "27801",
                "close": "29110.61",
                "symbol": "BTCUSDT",
                "interval": "D"
            },
            {
                "start": "1652313600000",
                "open": "29110.61",
                "high": "30211.67",
                "low": "26731.37",
                "close": "29026.97",
                "symbol": "BTCUSDT",
                "interval": "D"
            },
            {
                "start": "1652400000000",
                "open": "29026.97",
                "high": "31062.67",
                "low": "28762.55",
                "close": "29291.4",
                "symbol": "BTCUSDT",
                "interval": "D"
            },
            {
                "start": "1652486400000",
                "open": "29291.4",
                "high": "30327.13",
                "low": "28641.42",
                "close": "30088.12",
                "symbol": "BTCUSDT",
                "interval": "D"
            }
        ],
        "category": "linear"
    }
}
```

t(:linear_query_mark_price_kline)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dv3mpk>/derivatives/v3/public/mark-price-kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dv3mpk"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:dv3_category) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|<a href="#kline-interval-interval">interval</a> |<b>true</b> |string |t(:dv3_klineInterval) |
|start |<b>true</b> |integer |t(:row_comment_startTime_ms) |
|end |<b>true</b> |integer |t(:row_comment_endTime_ms) |
|limit |false |integer |t(:row_comment_limit_200) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |<b>true</b> |string |t(:dv3_category) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
| <a href="#kline-interval-interval">interval</a> |string |t(:row_comment_interval) |
| start |integer |t(:dv3_klineRespStart) |
| open |string |t(:row_comment_open) |
| high |string |t(:row_comment_high) |
| low |string |t(:row_comment_low) |
| close |string |t(:dv3_klineRespClose) |

### t(:queryindexpricekline)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/public/index-price-kline?category=linear&symbol=BTCUSDT&interval=D&start=1652112000000&end=1652544000000'
```

```python--old

```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "list": [
      {
        "start": "1652140800000",
        "open": "30081.75",
        "high": "32647.98",
        "low": "29749.37",
        "close": "31015.33",
        "symbol": "BTCUSDT",
        "interval": "D"
      }
    ],
      "category": "linear"
  }
}
```
t(:queryindexpricekline)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dv3IndexPriceKline>/derivatives/v3/public/index-price-kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dv3IndexPriceKline"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:dv3_category) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|<a href="#kline-interval-interval">interval</a> |<b>true</b> |string |t(:dv3_klineInterval) |
|start |<b>true</b> |integer |t(:row_comment_startTime_ms) |
|end |<b>true</b> |integer |t(:row_comment_endTime_ms) |
|limit |false |integer |t(:row_comment_limit_200) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |<b>true</b> |string |t(:dv3_category) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
| <a href="#kline-interval-interval">interval</a> |string |t(:row_comment_interval) |
| start |integer |t(:dv3_klineRespStart) |
| open |string |t(:row_comment_open) |
| high |string |t(:row_comment_high) |
| low |string |t(:row_comment_low) |
| close |string |t(:dv3_klineRespClose) |


### t(:dv3_historyFundingRateHead)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/public/funding/history-funding-rate?category=linear&symbol=BTCUSDT&startTime=1652112000000&endTime=1652198400000'
```

```python--old

```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "list": [
      {
        "symbol": "BTCUSDT",
        "fundingRate": "0.0001",
        "fundingRateTimestamp": "1652198400000"
      },
      {
        "symbol": "BTCUSDT",
        "fundingRate": "0.0001",
        "fundingRateTimestamp": "1652169600000"
      },
      {
        "symbol": "BTCUSDT",
        "fundingRate": "0.0001",
        "fundingRateTimestamp": "1652140800000"
      },
      {
        "symbol": "BTCUSDT",
        "fundingRate": "0.0001",
        "fundingRateTimestamp": "1652112000000"
      }
    ],
      "category": "linear"
  }
}
```
t(:market_para_fundingRate)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dv3hfr>/derivatives/v3/public/funding/history-funding-rate</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dv3hfr"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:dv3_category) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|startTime |false |integer |t(:row_comment_from_timestamp) |
|endTime |false |integer |t(:row_comment_endTime) |
|limit |false |integer |t(:row_comment_limit_200) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:dv3_category) |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol) |
|fundingRate |string |t(:row_comment_funding_rate) |
|fundingRateTimestamp |number |t(:row_comment_funding_rate_timestamp) |


### t(:dv3_riskLimitHead)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/public/risk-limit/list?category=linear&symbol=BTCUSDT'
```

```python--old

```

```python--pybit

```

> t(:codequote_responseExample)

```javascript


```

t(:dv3_riskLimitHead)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dv3risklimit>/derivatives/v3/public/position/risk-limit/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dv3risklimit"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:dv3_category) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:dv3_category) |
|id |number |t(:row_comment_riskId)  |
|symbol|string |t(:row_comment_symbol)   |
|limit |string |t(:risklimit)    |
|maintainMargin |number |t(:row_comment_maintain_margin)  |
|initialMargin |number |t(:dv3_riskInitialMargin)  |
|section |string |t(:row_comment_section)  |
|isLowestRisk |number |t(:row_comment_is_lowest_risk)    |
|createdTime |string |t(:row_comment_created_at)  |
|updatedTime |string |t(:row_comment_updated_at)  |
|maxLeverage |string |t(:row_comment_max_leverage)  |


### t(:dv3_optionDeliveryHead)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/public/delivery-price?category=option&symbol=BTC-30SEP22-400000-C'
```

```python--old

```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

```

t(:dv3_market_option_para)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dv3optdepr>/derivatives/v3/public/delivery-price</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dv3optdepr"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:dv3_category) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|direction|false |string |t(:dv3_pageDirection) |
|limit|false |string |t(:row_comment_limit_50_200) |
|cursor|false |string |t(:cursor) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_category) |t(:row_comment_category_optionOnly) |
|symbol |string |t(:row_comment_symbol) |
|deliveryPrice |string |t(:deliveryPrice) |
|deliveryTime |number |t(:deliveryTime) |
|cursor |string |t(:cursor) |


### t(:publictradingrecords)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/public/recent-trade?category=option&symbol=BTC-30SEP22-400000-C'
```

```python--old

```

```python--pybit


```


> t(:codequote_responseExample)

```javascript

```

t(:market_para_records)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dv3retr>/derivatives/v3/public/recent-trade</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dv3retr"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:dv3_category) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|optionType |false |string |t(:dv3_OptionType) |
|from |false |int |t(:row_comment_from)|
|limit |false |int |t(:row_comment_limit_500_1000)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:dv3_category) |
|execId |string |t(:dv3_recentExecId)  |
|symbol |string |t(:row_comment_symbol) |
|price |number |t(:dv3_recentPrice) |
|size |number |t(:row_response_comment_execqty) |
|t(:row_parameter_side) |string |t(:dv3_recentSide) |
|time |string |t(:dv3_recentTime) |
|blocktradeId |string |t(:dv3_recentBlockTradeId) |


### t(:marketopeninterest)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/derivatives/v3/public/open-interest?symbol=BTCUSD&period=5min
```

```python--old

```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

```

t(:market_para_marketopeninterest)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dv3MarketOpenInterest>/derivatives/v3/public/open-interest</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dv3MarketOpenInterest"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(dv3_category) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|interval |<b>true</b> |string |t(:dv3_openInterInterval) |
|startTime |false |string |t(:dv3_openInterStartTime) |
|endTime |false |string |t(:dv3_openInterEndTime) |
|limit |false |integer |t(:row_comment_limit_50_200) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(dv3_category) |
|openInterest |number |t(:row_comment_resp_open_interest) |
|openInterestValue |string |t(:dv3_openInterestRespValue) |
|timestamp |string |t(:dv3_openInterTimestamp) |
