# t(:marketdata)
t(:market_para_auth)


### t(:getSymbols)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/public/symbols'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "list": [
            {
                "name": "BTCUSDT",
                "alias": "BTCUSDT",
                "baseCoin": "BTC",
                "quoteCoin": "USDT",
                "basePrecision": "0.000001",
                "quotePrecision": "0.00000001",
                "minTradeQty": "0.000001",
                "minTradeAmt": "10",
                "maxTradeQty": "63.01197227",
                "maxTradeAmt": "1000000",
                "minPricePrecision": "0.01",
                "category": "1",
                "showStatus": "1",
                "innovation": "0"
            },
            {
                "name": "ETHUSDT",
                "alias": "ETHUSDT",
                "baseCoin": "ETH",
                "quoteCoin": "USDT",
                "basePrecision": "0.00001",
                "quotePrecision": "0.0000001",
                "minTradeQty": "0.00224",
                "minTradeAmt": "10",
                "maxTradeQty": "100000000",
                "maxTradeAmt": "100000000",
                "minPricePrecision": "0.01",
                "category": "1",
                "showStatus": "1",
                "innovation": "0"
            }
        ]
    },
    "retExtMap": {},
    "retExtInfo": {},
    "time": 1659067662931
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=svPostOrder>/spot/v3/public/symbols</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svPostOrder"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
| t(:column_parameter) | t(:column_required) | t(:column_type) | t(:column_comments) |
|:---------------------|:--------------------|:----------------|---------------------|

<p class="fake_header">t(:responseparameters)</p>
| t(:column_parameter) | t(:column_type) | t(:column_comments)       |
|:---------------------|:----------------|---------------------------|
| name                 | string          | t(:spotSymbol)            |
| alias                | string          | t(:spot_Alias)            |
| baseCoin             | string          | t(:spotBaseCurrency)      |
| quoteCoin            | string          | t(:spotQuoteCurrency)     |
| basePrecision        | string          | t(:spotBasePrecision)     |
| quotePrecision       | string          | t(:spotQuotePrecision)    |
| minTradeQty          | string          | t(:spotMinTradeQuantity)  |
| minTradeAmt          | string          | t(:spotMinTradeAmount)    |
| minPricePrecision    | string          | t(:spotMinPricePrecision) |
| maxTradeQty          | string          | t(:spotmaxTradeQuantity)  |
| maxTradeAmt          | string          | t(:spotmaxTradeAmount)    |
| category             | string          | t(:spotCategory)          |
| innovation           | string          | t(:spotV3_comment_innovation)     |
| showStatus           | string          | t(:spotV3_comment_showStatus)     |



### t(:orderbook)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/public/quote/depth?symbol=BTCUSDT&limit=1'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
  "retMsg": "OK",
  "result": {
    "time": 1659429083820,
    "bids": [
      [
        "21170.14",
        "0.050096"
      ]
    ],
    "asks": [
      [
        "21250",
        "0.00211"
      ]
    ]
  },
  "retExtInfo": {},
  "time": 1659429083979
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=sqvDepth>/spot/v3/public/quote/depth</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvDepth"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b>|string|t(:spotSymbol)|
|limit| false | integer | t(:spot_depth_limit)


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| time | long | t(:spot_depth_time) |
| bids | array | t(:spot_depth_bids) |
| asks | array | t(:spot_depth_asks) |



### t(:mergedOrderBook)

> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/public/quote/depth/merged?symbol=BTCUSDT&scale=1&limit=1'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
  "retMsg": "OK",
  "result": {
    "time": 1659429646349,
    "bids": [
      [
        "21170.1",
        "0.049096"
      ]
    ],
    "asks": [
      [
        "21250",
        "0.00211"
      ]
    ]
  },
  "retExtInfo": {},
  "time": 1659429646652
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=sqvdMerged>/spot/v3/public/quote/depth/merged</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvdMerged"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b>|string|t(:spotSymbol)|
|scale|false|integer|t(:spotOrderBookMergedScale)|
|limit| false | integer | t(:spot_depth_limit)


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| time | long | t(:spot_depth_time) |
| bids | array | t(:spot_depth_bids) |
| asks | array | t(:spot_depth_asks) |



### t(:publictradingrecords)
> t(:codequote_curlExample)
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/public/quote/trades?symbol=BTCUSDT&limit=1'

```console

```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
  "retMsg": "OK",
  "result": {
    "list": [
      {
        "price": "21170.14",
        "time": 1659429793926,
        "qty": "0.907276",
        "isBuyerMaker": 0
      }
    ]
  },
  "retExtInfo": {},
  "time": 1659429835311
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=sqvTrades>/spot/v3/public/quote/trades</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvTrades"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b>|string|t(:spotSymbol)|
|limit| false | integer | t(:spot_trades_limit_2)


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_price) | string | t(:spot_OrderPrice) |
| time | long | t(:spot_trade_time) |
| qty | string | t(:spotQty) |
| isBuyerMaker | integer | t(:spotV3_comment_isBuyerMaker) |



### t(:querykline)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/public/quote/kline?symbol=BTCUSDT&interval=1m&limit=1'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
  "retMsg": "OK",
  "result": {
    "list": [
      {
        "t": 1659430380000,
        "s": "BTCUSDT",
        "sn": "BTCUSDT",
        "c": "21170.14",
        "h": "21170.14",
        "l": "21127.86",
        "o": "21127.86",
        "v": "0.907276"
      }
    ]
  },
  "retExtInfo": {},
  "time": 1659430400353
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=sqvKline>/spot/v3/public/quote/kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvKline"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<aside class="notice">
t(:spot_kline_latest_records)
</aside>

<aside class="notice">
t(:spotKlineTimeRemark)
</aside>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b>|string|t(:spotSymbol)|
| <a href="#kline-interval-interval">interval</a> |<b>true</b> | string | t(:spot_kline_interval)|
| limit | false | integer | t(:spot_trades_limit) |
| startTime | false | long | t(:spot_orders_start_time) |
| endTime | false | long | t(:spot_orders_end_time) |


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t| long | t(:spotV3_comment_t)|
|s| string | t(:spotSymbol)|
|sn| string | t(:spot_Alias)|
|c| string | t(:spotClose)|
|h| string | t(:spotHigh)|
|l| string | t(:spotLow)|
|o| string | t(:spotOpen)|
|v| string | t(:spotVolume)|



### t(:spot_latestsymbolinfo)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/public/quote/ticker/24hr?symbol=BTCUSDT'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
  "retMsg": "OK",
  "result": {
    "t": 1659430933736,
    "s": "BTCUSDT",
    "lp": "21127.86",
    "h": "22000",
    "l": "19779.14",
    "o": "19935.19",
    "bp": "21170.14",
    "ap": "21250",
    "v": "211.378621",
    "qv": "4460854.96730398"
  },
  "retExtInfo": {},
  "time": 1659430975794
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=sqvt24hr>/spot/v3/public/quote/ticker/24hr</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvt24hr"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<aside class="notice">
t(:spotTicker24hrRemark)
</aside>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |false|string|t(:spotSymbol)|


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t| long | t(:spot_trade_time)|
|s| string | t(:spotSymbol)|
|lp| string | t(:spot_last_price)|
|h| string | t(:spot_high_price)|
|l| string | t(:spot_low_price)|
|o| string | t(:spot_open_price)|
|bp| string | t(:spot_best_bid_price)|
|ap| string | t(:spot_best_ask_price)|
|v| string | t(:spot_volume)|
|qv| string | t(:spot_quote_volume)|



### t(:lasttradedprice)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/public/quote/ticker/price?symbol=BTCUSDT'
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
    "price": "21127.86"
  },
  "retExtInfo": {},
  "time": 1659431315936
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=sqvtPrice>/spot/v3/public/quote/ticker/price</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvtPrice"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<aside class="notice">
t(:spotTickerPriceRemark)
</aside>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |false|string|t(:spotSymbol)|


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_symbol) | string | t(:spotSymbol) |
| t(:row_parameter_price) | string | t(:spotPrice) |



### t(:bestbidask)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/public/quote/ticker/bookTicker?symbol=BTCUSDT'

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
    "bidPrice": "21170.14",
    "bidQty": "0.908276",
    "askPrice": "21250",
    "askQty": "0.009264",
    "time": 1659431461695
  },
  "retExtInfo": {},
  "time": 1659431462103
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=sqvtBook_ticker>/spot/v3/public/quote/ticker/bookTicker</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvtBook_ticker"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<aside class="notice">
t(:spotBookTickerRemark)
</aside>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |false|string|t(:spotSymbol)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_symbol) | string | t(:spotSymbol) |
| bidPrice| string | t(:spot_best_bid_price)|
| bidQty | string | t(:spotBidQuantity)|
| askPrice| string | t(:spot_best_ask_price)|
| askQty | string |t(:spotAskQuantity)|
| time | long |t(:row_response_comment_nill_time)|
