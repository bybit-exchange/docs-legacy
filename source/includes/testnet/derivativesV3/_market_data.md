# t(:marketdata)
t(:market_para_auth_v3)

### t(:dv_orderbook)
> t(:codequote_curlExample)

```console
curl GET 'https://api-testnet.bybit.com/derivatives/v3/public/order-book/L2?category=future&symbol=BTCUSDT'
```

```python--pybit

```

> t(:codequote_responseExample)

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
t(:dv_orderbookPara)

<aside class="notice">
t(:market_aside_orderbook)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dvOrderbook>/derivatives/v3/public/order-book/L2</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dvOrderbook"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|------ |
|<a href="#category-category">category</a> |false|string |t(:dv3_orderbook_category) |
|symbol |<b>true</b> |string |t(:dv3_orderbook_symbol) |
|limit |false |int |t(:dv_orderbookLimit) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|s |string |t(:row_comment_symbol) |
|b |array |t(:dv_orderbookBids) |
|a |array |t(:dv_orderbookAsks) |
|ts |integer |t(:dv_orderbookTimeStamp) |
|u |string |t(:dv_orderbookUpdateId) |


### t(:dv_querykline)
> t(:codequote_curlExample)

```console
curl GET https://api-testnet.bybit.com/derivatives/v3/public/kline?category=future&symbol=BTCUSDT&interval=1&start=1668441600000&end=1668528000000&limit=2
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "symbol": "BTCUSDT",
        "category": "future",
        "list": [
            [
                "1668441660000",
                "16722.5",
                "16722.5",
                "16700",
                "16700.5",
                "3.307",
                "55233.6405"
            ],
            [
                "1668441600000",
                "16736.5",
                "16736.5",
                "16722",
                "16722.5",
                "0.255",
                "4265.2915"
            ]
        ]
    },
    "retExtInfo": {},
    "time": 1668577690514
}
```

t(:market_para_querykline)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dvkline>/derivatives/v3/public/kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dvkline"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#category-category">category</a> |false |string |t(:dv3_kline_category) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|<a href="#kline-interval-interval">interval</a> |<b>true</b> |string |t(:dv_klineInterval) |
|start |<b>true</b> |integer |t(:row_comment_startTime_ms) |
|end |<b>true</b> |integer |t(:row_comment_endTime_ms) |
|limit |false |integer |t(:row_comment_limit_200) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|symbol |string |t(:row_comment_symbol) |
|category |string |t(:dv_category) |
|list |string[] |t(:row_comment_kline_list) |


### t(:dv_tickerHead)
> t(:codequote_curlExample)

```console
curl GET 'https://api-testnet.bybit.com/derivatives/v3/public/tickers?category=future&symbol=BTCUSDT'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "category": "future",
        "list": [
            {
                "symbol": "BTCUSDT",
                "bidPrice": "19255",
                "askPrice": "19255.5",
                "lastPrice": "19255.50",
                "lastTickDirection": "ZeroPlusTick",
                "prevPrice24h": "18634.50",
                "price24hPcnt": "0.033325",
                "highPrice24h": "19675.00",
                "lowPrice24h": "18610.00",
                "prevPrice1h": "19278.00",
                "markPrice": "19255.00",
                "indexPrice": "19260.68",
                "openInterest": "48069.549",
                "turnover24h": "4686694853.047006",
                "volume24h": "243730.252",
                "fundingRate": "0.0001",
                "nextFundingTime": "1663689600000",
                "predictedDeliveryPrice": "",
                "basisRate": "",
                "deliveryFeeRate": "",
                "deliveryTime": "0"
            }
        ]
    },
    "retExtInfo": null,
    "time": 1663670053454
}
// option response
{
    "retCode": 0,
    "retMsg": "SUCCESS",
    "result": {
        "category": "option",
        "symbol": "BTC-30SEP22-35000-P",
        "bidPrice": "14600",
        "bidSize": "0.3",
        "bidIv": "0",
        "askPrice": "15180",
        "askSize": "25.6",
        "askIv": "0.8958",
        "lastPrice": "14260",
        "highPrice24h": "0",
        "lowPrice24h": "0",
        "markPrice": "14884.94173491",
        "indexPrice": "20236.14",
        "markPriceIv": "0.7185",
        "underlyingPrice": "20301.31",
        "openInterest": "1824.98",
        "turnover24h": "0",
        "volume24h": "0",
        "totalVolume": "40712",
        "totalTurnover": "280958807",
        "delta": "-0.92947392",
        "gamma": "0.00002001",
        "vega": "12.68819848",
        "theta": "-5.82971932",
        "predictedDeliveryPrice": "0",
        "change24h": "0"
    },
    "time": 1657770000604
}

```

t(:dv_marketTickerPara)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dvtickers>/derivatives/v3/public/tickers</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dvtickers"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#category-category">category</a> |false |string |t(:dv3_ticker_category) |
|symbol |false |string |t(:dv_tickerSymbol) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| category |string |t(:dv_category) |
| askIv |string |t(:askIv) |
| deliveryTime |string |t(:deliveryTime) |
| price24hPcnt |string |t(:row_comment_resp_price_24h_pcnt) |
| nextFundingTime |string |t(:row_comment_resp_next_funding_time) |
| predictedDeliveryPrice |string |t(:dv_tickPredictedDeliveryPrice) |
| indexPrice |string |t(:row_comment_resp_index_price) |
| prevPrice24h |string |t(:row_comment_resp_prev_price_24h) |
| openInterest |string |t(:row_comment_resp_open_interest) |
| underlyingPrice |string |t(:usdcUnderlyingPrice) |
| volume24h |string |t(:row_comment_resp_volume_24h) |
| symbol |string |t(:row_comment_symbol) |
| vega |string |t(:vega) |
| lastTickDirection | string |t(:row_comment_tick_direction) |
| lastPrice |string |t(:row_comment_resp_last_price) |
| totalVolume |string |t(:row_comment_resp_total_volume) |
| bidPrice |string |t(:bidPrice) |
| totalTurnover |string |t(:row_comment_resp_total_turnover) |
| turnover24h |string |t(:row_comment_resp_turnover_24h) |
| askPrice |string |t(:askPrice) |
| fundingRate |string |t(:row_comment_funding_rate) |
| bidSize |string |t(:bidSize) |
| bidIv |string |t(:bidIv) |
| highPrice24h |string |t(:row_comment_resp_high_price_24h) |
| delta |string |t(:delta) |
| theta |string |t(:theta) |
| askSize |string |t(:askSize) |
| prevPrice1h |string |t(:row_comment_resp_prev_price_1h) |
| markPrice |string |t(:row_comment_resp_mark_price) |
| gamma |string |t(:gamma) |
| deliveryFeeRate |string |t(:dv_tickDeliveryFeeRate) |
| lowPrice24h |string |t(:row_comment_resp_low_price_24h) |
| markPriceIv |string |t(:markPriceIv) |
| basisRate |string |t(:dv_tickBasisRate) |


### t(:dv_instrHead)
> t(:codequote_curlExample)

```console
curl GET 'https://api-testnet.bybit.com/derivatives/v3/public/instruments-info?category=future&symbol=BTCUSDT'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "category": "future",
        "list": [
            {
                "symbol": "BTCUSDT",
                "contractType": "LinearPerpetual",
                "status": "Trading",
                "baseCoin": "BTC",
                "quoteCoin": "USDT",
                "launchTime": "1584230400000",
                "deliveryTime": "0",
                "deliveryFeeRate": "",
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
                    "maxTradingQty": "420.000",
                    "minTradingQty": "0.001",
                    "qtyStep": "0.001"
                },
                "unifiedMarginTrade": true
            }
        ],
        "nextPageCursor": ""
    },
    "retExtInfo": {},
    "time": 1667533491917
}

// option response
{
    "retCode": 0,
    "retMsg": "success",
    "result": {
        "resultTotalSize": 1,
        "cursor": "",
        "dataList": [
            {
                "category": "option",
                "symbol": "BTC-30SEP22-35000-P",
                "status": "ONLINE",
                "baseCoin": "BTC",
                "quoteCoin": "USD",
                "settleCoin": "USDC",
                "optionsType": "Put",
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
    },
    "time": 1657777124431
}
```

t(:dv_marketInstrPara)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dvinstru>/derivatives/v3/public/instruments-info</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dvinstru"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#category-category">category</a> |false |string |t(:dv3_instrument_category) |
|symbol |false |string |t(:dv3_instrument_symbol) |
|baseCoin |false |string |t(:unified_baseCoin_param) |
|limit |false |string |t(:row_comment_limit_500_1000) |
|cursor |false |string |t(:dv_cursor) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:dv_category) |
|symbol |string |t(:row_comment_symbol) |
|contractType |string |t(:dv_instrContractType) |
|status |string |t(:row_response_comment_status) |
|baseCoin |string |t(:dv_instrBaseCoin) |
|quoteCoin |string |t(:dv_instrQuoteCoin) |
|settleCoin |string |t(:dv_instrSettleCoin) |
|optionsType |string |t(:dv_OptionType) |
|launchTime |string |t(:dv_instrLaunchTime) |
|deliveryTime |string |t(:dv_instrDeliveryTime) |
|deliveryFeeRate |string |t(:deliveryFeeRate) |
|priceScale |string |t(:dv_instrPriceScale) |
|leverageFilter> minLeverage |string |t(:minLeverage) |
|leverageFilter> maxLeverage |string |t(:maxLeverage) |
|leverageFilter> leverageStep |string |t(:leverageStep) |
|priceFilter> minPrice |string |t(:minPrice) |
|priceFilter> maxPrice |string |t(:maxPrice) |
|priceFilter> tickSize |string |t(:tickSize) |
|lotSizeFilter> maxOrderQty |string |t(:dv_instrMaxOrderQty) |
|lotSizeFilter> minOrderQty |string |t(:dv_instrMinOrderQty) |
|lotSizeFilter> qtyStep |string |t(:qtyStep) |
|nextPageCursor |string |t(:dv_cursor) |


### t(:dv_markpricekline)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/public/mark-price-kline?category=future&symbol=BTCPERP&interval=D&start=1652112000000&end=1652544000000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg":"success",
    "result":{
      "symbol":"BTCPERP",
     "category":"future",
      "list":[
          "1621162800",
          "49592.43",
          "49644.91",
          "49342.37",
          "49349.42",
    ]
  }
}
```

t(:linear_query_mark_price_kline_v3)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dvmarkkline>/derivatives/v3/public/mark-price-kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dvmarkkline"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#category-category">category</a> |false |string |t(:dv3_kline_category) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|<a href="#kline-interval-interval">interval</a> |<b>true</b> |string |t(:dv_klineInterval) |
|start |<b>true</b> |integer |t(:row_comment_startTime_ms) |
|end |<b>true</b> |integer |t(:row_comment_endTime_ms) |
|limit |false |integer |t(:row_comment_limit_200) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|symbol |string |t(:row_comment_symbol) |
|category |string |t(:dv_category) |
|list |string[] |t(:row_comment_mark_kline_list) |

### t(:dv_indexpricekline)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/public/index-price-kline?category=future&symbol=BTCUSDT&interval=D&start=1652112000000&end=1652544000000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg":"success",
    "result":{
      "symbol":"BTCUSDT",
      "category":"future",
      "list":[
          "1668528000000",
          "16968.92",
          "17051.23",
          "16901.28",
          "16990.57"
    ]
  }
}
```
t(:queryindexpricekline)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dvindexkline>/derivatives/v3/public/index-price-kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dvindexkline"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#category-category">category</a> |false |string |t(:dv3_kline_category) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|<a href="#kline-interval-interval">interval</a> |<b>true</b> |string |t(:dv_klineInterval) |
|start |<b>true</b> |integer |t(:row_comment_startTime_ms) |
|end |<b>true</b> |integer |t(:row_comment_endTime_ms) |
|limit |false |integer |t(:row_comment_limit_200) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|symbol |string |t(:row_comment_symbol) |
|category |string |t(:dv_category) |
|list |string[] |t(:row_comment_mark_kline_list) |


### t(:premium_index_price_kline)
> t(:codequote_curlExample)

```console
curl GET 'https://api-testnet.bybit.com/derivatives/v3/public/premium-index-price-kline?symbol=BTCPERP&interval=D&start=1668441600000&end=1668528000000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "symbol": "BTCPERP",
        "category": "",
        "list": [
            [
                "1668470400000",
                "0.001955",
                "0.002014",
                "0.001650",
                "0.002014"
            ]
        ]
    },
    "retExtInfo": {},
    "time": 1668582411036
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dvpreinprk>/derivatives/v3/public/premium-index-price-kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dvpreinprk"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#category-category">category</a> |false |string |t(:dv3_kline_category) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|<a href="#kline-interval-interval">interval</a> |<b>true</b> |string |t(:dv_klineInterval) |
|start |<b>true</b> |integer |t(:row_comment_startTime_ms) |
|end |<b>true</b> |integer |t(:row_comment_endTime_ms) |
|limit |false |integer |t(:row_comment_limit_200) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|symbol |string |t(:row_comment_symbol) |
|category |string |t(:dv_category) |
|list |string[] |t(:row_comment_mark_kline_list) |


### t(:dv_historyFundingRateHead)
> t(:codequote_curlExample)

```console
curl GET 'https://api-testnet.bybit.com/derivatives/v3/public/funding/history-funding-rate?category=future&symbol=BTCUSDT&startTime=1652112000000&endTime=1652198400000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "category": "future",
        "list": [
            {
                "symbol": "BTCUSDT",
                "fundingRate": "0.0001",
                "fundingRateTimestamp": "1657728000000"
            },
            {
                "symbol": "BTCUSDT",
                "fundingRate": "0.0001",
                "fundingRateTimestamp": "1657699200000"
            }
        ]
    },
    "time": 1657782323371
}
```
t(:market_para_fundingRate)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dvhistfundrate>/derivatives/v3/public/funding/history-funding-rate</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dvhistfundrate"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#category-category">category</a> |false |string |t(:dv3_kline_category) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|startTime |false |integer |t(:row_comment_startTime_ms) |
|endTime |false |integer |t(:row_comment_endTime_ms) |
|limit |false |integer |t(:row_comment_limit_200) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:dv_category) |
|list |array |Object |
|> symbol |string |t(:row_comment_symbol) |
|> fundingRate |string |t(:row_comment_funding_rate) |
|> fundingRateTimestamp |string |t(:row_comment_funding_rate_timestamp) |


### t(:dv_riskLimitHead)
> t(:codequote_curlExample)

```console
curl GET 'https://api-testnet.bybit.com/derivatives/v3/public/risk-limit/list?category=future&symbol=BTCUSDT'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "category": "future",
        "list": [
            {
                "id": 1,
                "symbol": "BTCUSDT",
                "limit": "2000000",
                "maintainMargin": "0.005",
                "initialMargin": "0.01",
                "section": [
                    "1",
                    "3",
                    "5",
                    "10",
                    "25",
                    "50",
                    "80"
                ],
                "isLowestRisk": 1,
                "maxLeverage": "100.00"
            }
        ]
    },
    "time": 1657797260220
}
```

t(:dv_riskLimitHead)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dvrisklimit>/derivatives/v3/public/risk-limit/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dvrisklimit"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#category-category">category</a> |false |string |t(:dv3_riskLimit_category) |
|symbol |false |string |t(:row_comment_symbol) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:dv_category) |
|list |array |Object |
|> id |number |t(:row_comment_riskId)  |
|> symbol|string |t(:row_comment_symbol) |
|> limit |string |t(:risklimit) |
|> maintainMargin |string |t(:row_comment_maintain_margin) |
|> initialMargin |string |t(:dv_riskInitialMargin)  |
|> section |array |t(:row_comment_section) |
|> isLowestRisk |number |t(:row_comment_is_lowest_risk) |
|> maxLeverage |string |t(:row_comment_max_leverage) |


### t(:dv_optionDeliveryHead)
> t(:codequote_curlExample)

```console
curl GET 'https://api-testnet.bybit.com/derivatives/v3/public/delivery-price?symbol=BTC-14JUL22-18000-C&category=option'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "success",
    "result": {
        "resultTotalSize": 1,
        "cursor": "",
        "dataList": [
            {
                "category": "option",
                "symbol": "BTC-14JUL22-18000-C",
                "deliveryPrice": "19967.372502790",
                "deliveryTime": "1657785600000"
            }
        ]
    },
    "time": 1657797556994
}
```

t(:dv_market_option_para)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dvdeliveryprice>/derivatives/v3/public/delivery-price</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dvdeliveryprice"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#category-category">category</a> |false |string |t(:dv3_deliveryPrice_category) |
|symbol |false |string |t(:row_comment_symbol) |
|baseCoin |false |string |t(:unified_baseCoin_param) |
|direction |false |string |t(:row_comment_direction_v3) |
|limit|false |string |t(:row_comment_limit_50_200) |
|cursor|false |string |t(:dv_cursor) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:dv_category) |
|symbol |string |t(:row_comment_symbol) |
|deliveryPrice |string |t(:deliveryPrice) |
|deliveryTime |string |t(:deliveryTime) |
|cursor |string |t(:dv_cursor) |


### t(:dv_publictradingrecords)
> t(:codequote_curlExample)

```console
curl GET 'https://api-testnet.bybit.com/derivatives/v3/public/recent-trade?category=future&symbol=BTCUSDT&limit=1'
```

```python--pybit

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "category": "future",
        "list": [
            {
                "execId": "da66abbc-f358-5864-8d34-84ef7274d853",
                "symbol": "BTCUSDT",
                "price": "20802.50",
                "size": "0.200",
                "side": "Sell",
                "time": "1657870316630",
                "isBlockTrade": false
            }
        ]
    },
    "time": 1657870326247
}
```

t(:market_para_records)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dvrecentrades>/derivatives/v3/public/recent-trade</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dvrecentrades"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#category-category">category</a> |false |string |t(:dv3_recentTrade_category) |
|symbol |false |string |t(:row_comment_symbol) |
|baseCoin |false |string |t(:unified_baseCoin_param) |
|optionType |false |string |t(:dv_OptionType) |
|limit |false |int |t(:row_comment_limit_500_1000)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:dv_category) |
|list |array |Object |
|> execId |string |t(:dv_recentExecId)  |
|> symbol |string |t(:row_comment_symbol) |
|> price |number |t(:dv_recentPrice) |
|> size |number |t(:row_response_comment_execqty) |
|> t(:row_parameter_side) |string |t(:dv_recentSide) |
|> time |string |t(:dv_recentTime) |
|> isBlockTrade |boolean |t(:usdc_isBlockTrade) |


### t(:dv_marketopeninterest)
> t(:codequote_curlExample)

```console
curl GET 'https://api-testnet.bybit.com/derivatives/v3/public/open-interest?category=future&symbol=BTCUSDT&interval=1h&startTime=1657555200000&endTime=1657641600000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "symbol": "BTCUSDT",
        "category": "future",
        "list": [
            {
                "openInterest": "15350.60700000",
                "timestamp": "1657641600000"
            },
            {
                "openInterest": "15605.74100000",
                "timestamp": "1657638000000"
            }
        ]
    },
    "time": 1657797822839
}
```

t(:market_para_marketopeninterest)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=dvopeninterest>/derivatives/v3/public/open-interest</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#dvopeninterest"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#category-category">category</a> |false |string |t(:dv3_kline_category) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|interval |<b>true</b> |string |t(:dv_openInterInterval) |
|startTime |false |integer |t(:row_comment_startTime_ms) |
|endTime |false |integer |t(:row_comment_endTime_ms) |
|limit |false |integer |t(:row_comment_limit_50_200) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|symbol |string |t(:row_comment_symbol) |
|category |string |t(:dv_category) |
|list |array |Object |
|> openInterest |string |t(:row_comment_resp_open_interest) |
|> timestamp |string |t(:dv_openInterTimestamp) |
