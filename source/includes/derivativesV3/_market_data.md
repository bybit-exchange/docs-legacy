# t(:marketdata)
t(:market_para_auth)

### t(:orderbook)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/public/orderBook/L2?category=linear&symbol=BTCUSDT'
```

```python--old
//TODO: change to v3
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Market.Market_orderbook(symbol="BTCUSD").result())
```

```python--pybit
//TODO: change to v3
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com")
print(session.orderbook(symbol="BTCUSD"))
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
            ],
            [
                "28807.5",
                "0.114"
            ],
            [
                "28812.5",
                "5.539"
            ],
            [
                "28817",
                "0.036"
            ],
            [
                "28818",
                "5.006"
            ],
            [
                "28823.5",
                "5.345"
            ],
            [
                "28825",
                "5.095"
            ],
            [
                "28830",
                "0.001"
            ],
            [
                "28846",
                "0.109"
            ],
            [
                "28860",
                "0.001"
            ],
            [
                "28877",
                "2"
            ],
            [
                "28884.5",
                "0.081"
            ],
            [
                "28886.5",
                "0.604"
            ],
            [
                "28889",
                "0.001"
            ],
            [
                "28890",
                "0.001"
            ],
            [
                "28899.5",
                "0.13"
            ],
            [
                "28900",
                "11.078"
            ],
            [
                "28920",
                "0.001"
            ],
            [
                "28950",
                "0.001"
            ],
            [
                "28980",
                "0.001"
            ],
            [
                "28981",
                "0.001"
            ],
            [
                "28986.5",
                "0.039"
            ],
            [
                "28996.5",
                "0.001"
            ],
            [
                "29003.5",
                "10"
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
            ],
            [
                "29023",
                "0.168"
            ],
            [
                "29023.5",
                "0.006"
            ],
            [
                "29025.5",
                "0.496"
            ],
            [
                "29035",
                "0.08"
            ],
            [
                "29038.5",
                "0.055"
            ],
            [
                "29039",
                "0.001"
            ],
            [
                "29040",
                "0.001"
            ],
            [
                "29042",
                "0.002"
            ],
            [
                "29063.5",
                "0.105"
            ],
            [
                "29065",
                "0.105"
            ],
            [
                "29066.5",
                "0.105"
            ],
            [
                "29068",
                "0.105"
            ],
            [
                "29069.5",
                "0.105"
            ],
            [
                "29070",
                "0.001"
            ],
            [
                "29071",
                "0.105"
            ],
            [
                "29072.5",
                "0.105"
            ],
            [
                "29074",
                "0.105"
            ],
            [
                "29075.5",
                "0.105"
            ],
            [
                "29077",
                "0.105"
            ],
            [
                "29077.5",
                "0.06"
            ],
            [
                "29078.5",
                "0.105"
            ],
            [
                "29080",
                "0.105"
            ],
            [
                "29081.5",
                "0.105"
            ]
        ],
        "ts": 1653638043149,
        "u": 4912426
    }
}
```

t(:market_para_orderbook_v3)

<aside class="notice">
t(:market_aside_orderbook)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpoL2>/derivatives/v3/public/orderBook/L2</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoL2"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|------ |
|t(:row_parameter_category) |<b>true</b>|string |t(:row_comment_category) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol_v3) |
|limit |false |int |t(:row_comment_limit_25_500) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|p |string |t(:row_comment_resp_price) |
|v |string |t(:row_comment_resp_volume_ob) |
|b |Arrays |t(:row_comment_resp_bids) |
|a |Arrays |t(:row_comment_resp_asks) |
|u |string |t(:row_comment_resp_updateId) |
|ts |int |t(:row_comment_resp_timestamp) |


### t(:querykline)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/public/kline?category=linear&symbol=BTCUSDT&interval=D&start=1652112000000&end=1652544000000'
```

```python--old
//TODO: change to v3
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Kline.Kline_get(symbol="BTCUSD", interval="m", **{'from':1581231260}).result())
```

```python--pybit
//TODO: change to v3
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com")
print(session.query_kline(
    symbol="BTCUSD",
    interval="m",
    from_time=1581231260
))
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
      },
      {
        "start": "1652227200000",
        "open": "30982.5",
        "high": "32365",
        "low": "27697.5",
        "close": "29081.5",
        "volume": "17464.279",
        "turnover": "529189880.3045",
        "symbol": "BTCUSDT",
        "interval": "D"
      },
      {
        "start": "1652313600000",
        "open": "29081.5",
        "high": "30409.5",
        "low": "26580",
        "close": "29015",
        "volume": "22994.569",
        "turnover": "654342701.26",
        "symbol": "BTCUSDT",
        "interval": "D"
      },
      {
        "start": "1652400000000",
        "open": "29015",
        "high": "31149.5",
        "low": "28743",
        "close": "29284.5",
        "volume": "9907.605",
        "turnover": "299870552.126",
        "symbol": "BTCUSDT",
        "interval": "D"
      },
      {
        "start": "1652486400000",
        "open": "29284.5",
        "high": "30409.5",
        "low": "28649.5",
        "close": "30115.5",
        "volume": "9975.291",
        "turnover": "292816985.039",
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
<code><span id=vpkList>/derivatives/v3/public/kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpkList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_category) |<b>true</b> |string |t(:row_comment_category_qk) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol_v3) |
|<a href="#kline-interval-interval">interval</a> |<b>true</b> |string |t(:row_comment_interval) |
|start |<b>true</b> |integer |t(:row_comment_startTime_ms) |
|end |<b>true</b> |integer |t(:row_comment_endTime_ms) |
|limit |false |integer |t(:row_comment_limit_200) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_category) |string |t(:row_comment_category) |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol_v3) |
|<a href="#kline-interval-interval">interval</a> |string |t(:row_comment_interval) |
|start |integer |t(:row_comment_resp_start_ms_v3) |
|open |string |t(:row_comment_open) |
|high |string |t(:row_comment_high) |
|low |string |t(:row_comment_low) |
|close |string |t(:row_comment_resp_close_v3) |
|volume |string |t(:row_comment_resp_volume_qk) |
|turnover |string |t(:row_comment_resp_turnover) |

### t(:latestsymbolinfo_v3)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/public/tickers?category=linear&symbol=BTCUSDT'
```

```python--old
//TODO: change to v3
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Market.Market_symbolInfo().result())
```

```python--pybit
//TODO: change to v3
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com")
print(session.latest_information_for_symbol(
    symbol="BTCUSD"
))
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

//t(:row_comment_symbol_with_option)
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

t(:market_para_symbol_v3)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpTickers>/derivatives/v3/public/tickers</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpTickers"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_category) |<b>true</b> |string |t(:row_comment_category) |
|t(:row_parameter_symbol) |false |string |t(:row_comment_symbol_v3_with_option) |



<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| askIv |string |t(:usdcAskIv) |
| deliveryTime |string |t(:deliveryTime) |
| price24hPcnt |string |t(:row_comment_resp_price_24h_pcnt) |
| nextFundingTime |string |t(:row_comment_resp_next_funding_time) |
| predictedDeliveryPrice |string |t(:row_comment_resp_predictedDeliveryPrice) |
| countdownHour |string |t(:row_comment_resp_countdown_hour) |
| indexPrice |string |t(:row_comment_resp_price_24h_pcnt) |
| prevPrice24h |string |t(:row_comment_resp_prev_price_24h) |
| openInterest |string |t(:row_comment_resp_open_interest) |
| openInterestValue |string |t(:row_comment_resp_openInterestValue) |
| underlyingPrice |string |t(:row_comment_resp_volume_24h) |
| volume24h |number |t(:row_comment_resp_mark_price) |
| symbol |string |t(:row_comment_symbol_v3) |
| vega |number |t(:vega) |
| lastPrice |string |t(:row_comment_resp_last_price) |
| totalVolume |string |t(:usdcTotalVolume) |
| bidPrice |string |t(:row_comment_resp_bid_price) |
| totalTurnover |number |t(:usdcTotalTurnover) |
| turnover24h |number |t(:usdcTurnover24h) |
| t(:row_parameter_category) |string |t(:row_comment_category) |
| askPrice |string |t(:row_comment_resp_ask_price) |
| fundingRate |string |t(:row_comment_funding_rate) |
| bidSize |string |t(:usdcBidSize) |
| bidIv |string |t(:usdcBidIv) |
| highPrice24h |string |t(:row_comment_resp_high_price_24h) |
| delta |string |t(:delta) |
| theta |string |t(:theta) |
| askSize |string |t(:usdcAskSize) |
| price1hPcnt |string |t(:row_comment_resp_price_1h_pcnt) |
| prevPrice1h |string |t(:row_comment_resp_prev_price_1h) |
| markPrice |string |t(:row_comment_resp_mark_price) |
| gamma |string |t(:gamma) |
| deliveryFeeRate |string |t(:row_comment_resp_deliveryFeeRate) |
| lowPrice24h |string |t(:row_comment_resp_low_price_24h) |
| markPrice2Iv |string |t(:usdcMarkPriceIv) |
| predictedFundingRate |string |t(:row_comment_predicted_funding_rate) |


### t(:querysymbol)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/public/instruments-info?category=linear&symbol=BTCUSDT'
```

```python--old
//TODO: change to v3
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Symbol.Symbol_get().result())
```

```python--pybit
//TODO: change to v3
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com")
print(session.query_symbol())
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

//t(:resp_field_option_list_instruinfo)
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

t(:market_para_instrumentsInfo)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpSymbols>/derivatives/v3/public/instruments-info</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpSymbols"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_category) |<b>true</b> |string |t(:row_comment_category) |
|symbol |false |string |t(:row_comment_symbol_v3) |
|t(:row_parameter_status))|false |string |t(:row_comment_status) |
|direction |false |string |t(:direction) |
|limit |false |string |t(:row_comment_limit_500_1000) |
|cursor |false |string |t(:cursor) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:row_comment_category)    |
|symbol |string |t(:row_comment_symbol_v3)    |
|contractType |string |t(:row_comment_resp_contractType)    |
|t(:row_parameter_status) |string |t(:row_comment_status)    |
|baseCoin |string |t(:row_comment_resp_baseCoin)    |
|quoteCoin |string |t(:row_comment_resp_quoteCoin)    |
|settleCoin |string |t(:row_comment_resp_settleCoin)    |
|optionsType |string |t(:row_comment_resp_optionsType)    |
|launchTime |number |t(:row_comment_resp_launchTime)    |
|deliveryTime |number |t(:deliveryFeeRate)    |
|deliveryFeeRate |number |t(:deliveryFeeRate)    |
|priceScale |number |t(:row_response_comment_price_scale)    |
|minLeverage |number |t(:row_response_comment_min_leverage)    |
|maxLeverage |number |t(:row_response_comment_public_max_leverage)    |
|leverageStep |string |t(:row_response_comment_leverage_step)    |
|minPrice |string |t(:row_response_comment_min_price)    |
|maxPrice |string |t(:row_response_comment_max_price)    |
|tickSize |string |t(:row_response_comment_tick_size)    |
|maxOrderQty |number |t(:row_comment_resp_maxOrderQty)    |
|minOrderQty |number |t(:row_comment_resp_minOrderQty)    |
|qtyStep |number |t(:row_response_comment_qty_step)    |
|imBaseValue |string |t(:row_comment_resp_imBaseValue)    |
|imIncrementValue |string |t(:row_comment_resp_imIncrementValue)    |
|mmBaseValue |string |t(:row_comment_resp_mmBaseValue)    |
|mmIncrementValue |string |t(:row_comment_resp_mmIncrementValue)    |
|riskLimitBaseValue |string |t(:row_comment_resp_riskLimitBaseValue)    |
|riskLimitIncrementValue |string |t(:row_comment_resp_riskLimitIncrementValue)    |
|positionLimitValue |string |t(:row_comment_resp_positionLimitValue)    |
|cursor |string |t(:cursor)    |


### t(:markpricekline_v3)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/public/mark-price-kline?category=linear&symbol=BTCUSDT&interval=D&start=1652112000000&end=1652544000000'
```

```python--old
// change to v3
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Kline.Kline_markPrice(symbol="BTCUSD", interval="30",limit=200, **{'from':1600544880}).result())
```

```python--pybit
// change to v3
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com")
print(session.query_mark_price_kline(
    symbol="BTCUSD",
    interval=30,
    limit=200,
    from_time=1600544880
))
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
<code><span id=plmpk>/derivatives/v3/public/mark-price-kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#plmpk"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_category) |<b>true</b> |string |t(:row_comment_category_qk) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol_v3) |
|<a href="#kline-interval-interval">interval</a> |<b>true</b> |string |t(:row_comment_interval) |
|start |<b>true</b> |integer |t(:row_comment_startTime_ms) |
|end |<b>true</b> |integer |t(:row_comment_endTime_ms) |
|limit |false |integer |t(:row_comment_limit_200) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_category) |string |t(:row_comment_category) |
| t(:row_parameter_symbol) |string |t(:row_comment_symbol_v3) |
| <a href="#kline-interval-interval">interval</a> |string |t(:row_comment_interval) |
| start |integer |t(:row_comment_resp_start_ms_v3) |
| open |string |t(:row_comment_open) |
| high |string |t(:row_comment_high) |
| low |string |t(:row_comment_low) |
| close |string |t(:row_comment_resp_close_v3) |

### t(:queryindexpricekline)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/public/index-price-kline?category=linear&symbol=BTCUSDT&interval=D&start=1652112000000&end=1652544000000'
```

```python--old
// change to v3
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Kline.Kline_indexPrice(symbol="BTCUSD", interval="1", **{'from':1615067084}).result())
```

```python--pybit
// change to v3
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com")
print(session.query_index_price_kline(
    symbol="BTCUSD",
    interval=30,
    limit=200,
    from_time=1600544880
))
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
      },
      {
        "start": "1652227200000",
        "open": "31015.33",
        "high": "32158.42",
        "low": "27799.05",
        "close": "29104.81",
        "symbol": "BTCUSDT",
        "interval": "D"
      },
      {
        "start": "1652313600000",
        "open": "29104.81",
        "high": "30220.04",
        "low": "26720.56",
        "close": "29027.8",
        "symbol": "BTCUSDT",
        "interval": "D"
      },
      {
        "start": "1652400000000",
        "open": "29027.8",
        "high": "31072.3",
        "low": "28757.68",
        "close": "29291.4",
        "symbol": "BTCUSDT",
        "interval": "D"
      },
      {
        "start": "1652486400000",
        "open": "29291.4",
        "high": "30334.75",
        "low": "28638.38",
        "close": "30088.88",
        "symbol": "BTCUSDT",
        "interval": "D"
      }
    ],
      "category": "linear"
  }
}
```
t(:inverse_query_index_price_kline)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=v2pIndexPriceKline>/derivatives/v3/public/index-price-kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#v2pIndexPriceKline"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_category) |<b>true</b> |string |t(:row_comment_category_qk) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol_v3) |
|<a href="#kline-interval-interval">interval</a> |<b>true</b> |string |t(:row_comment_interval) |
|start |<b>true</b> |integer |t(:row_comment_startTime_ms) |
|end |<b>true</b> |integer |t(:row_comment_endTime_ms) |
|limit |false |integer |t(:row_comment_limit_200) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_category) |string |t(:row_comment_category) |
| t(:row_parameter_symbol) |string |t(:row_comment_symbol_v3) |
| <a href="#kline-interval-interval">interval</a> |string |t(:row_comment_interval) |
| start |integer |t(:row_comment_resp_start_ms_v3) |
| open |string |t(:row_comment_open) |
| high |string |t(:row_comment_high) |
| low |string |t(:row_comment_low) |
| close |string |t(:row_comment_resp_close_v3) |



### t(:queryHistoryFundingRate)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/public/funding/history-funding-rate?category=linear&symbol=BTCUSDT&startTime=1652112000000&endTime=1652198400000'
```

```python--old
// change to v3
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Kline.Kline_premiumIndexPrice(symbol="BTCUSD", interval="1", **{'from':1615067084}).result())
```

```python--pybit
// change to v3
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com")
print(session.query_premium_index_kline(
    symbol="BTCUSD",
    interval=30,
    limit=200,
    from_time=1600544880
))
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
t(:market_para_histFundRate)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpPremiumIndexKline>/v2/public/premium-index-kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpPremiumIndexKline"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_category) |<b>true</b> |string |t(:row_comment_category_qk) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol_v3) |
|startTime |false |integer |t(:row_comment_startTime_ms) |
|endTime |false |integer |t(:row_comment_endTime_ms) |
|limit |false |integer |t(:row_comment_limit_200) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_category) |string |t(:row_comment_category) |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol_v3) |
|fundingRate |string |t(:row_comment_funding_rate) |
|fundingRateTimestamp |number |t(:fundingRateTimestamp) |


### t(:riskLimitList)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/public/risk-limit/list?category=linear&symbol=BTCUSDT'
```

```python--old
// change to v3
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Market.Market_openInterest(symbol="BTCUSD", limit=2, period="5min").result())
```

```python--pybit
// change to v3
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com")
print(session.open_interest(
    symbol="BTCUSD",
    limit=2,
    period="5min"
))
```

> t(:codequote_responseExample)

```javascript
// the path has to be confirmed
{
  "retCode": 4004,
    "retMsg": "route not found"
}
```

t(:market_para_riskLimitList)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpMarketOpenInterest>/derivatives/public/v3/risk-limit/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpMarketOpenInterest"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_category) |<b>true</b> |string |t(:row_comment_category_qk) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol_v3) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_category) |<b>true</b> |string |t(:row_comment_category) |
|id |number |t(:row_comment_riskId)  |
|symbol|string |t(:row_comment_symbol_v3)   |
|limit |number |t(:row_comment_risk_limit)    |
|maintainMargin |string |t(:row_comment_maintain_margin)  |
|initialMargin |string |t(:startingMargin)  |
|section |string |t(:row_comment_section)  |
|isLowestRisk |number |t(:row_comment_is_lowest_risk)    |
|createdTime |string |t(:row_comment_created_at)  |
|updatedTime |string |t(:row_comment_updated_at)  |
|maxLeverage |string |t(:row_comment_max_leverage)  |


### t(:optionDeliveryPrice)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/derivatives/v3/public/delivery-price?category=option&symbol=BTC-30SEP22-400000-C'
```

```python--old
// change to v3
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Market.Market_bigDeal(symbol="BTCUSD", limit=2).result())
```

```python--pybit
// change to v3
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com")
print(session.latest_big_deal(
    symbol="BTCUSD",
    limit=2
))
```

> t(:codequote_responseExample)

```javascript
// the path has to be confirmed
{
  "retCode": 4004,
    "retMsg": "route not found"
}
```

t(:market_para_optionDeliveryPrice)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpMarketBigDeal>/v2/public/big-deal</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpMarketBigDeal"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_category) |<b>true</b> |string |t(:row_comment_category_odp) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol_v3) |
|direction|false |string |t(:direction) |
|limit|false |string |t(:usdcDeliveryLimit) |
|cursor|false |string |t(:cursor) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_category) |<b>true</b> |string |t(:row_comment_category) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol_v3) |
|deliveryPrice |string |t(:deliveryPrice) |
|deliveryTime |number |t(:deliveryTime) |
|cursor |string |t(:cursor) |
-->
