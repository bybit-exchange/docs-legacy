# t(:marketdata)
t(:market_para_auth)


### t(:usdcOrderBook)
> t(:codequote_curlExample)

```console

curl 'https://api-testnet.bybit.com/option/usdc/openapi/public/v1/order-book?symbol=BTC-3DEC21-62000-P'

```

```python
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "SUCCESS",
    "result": [
    {
      "price": "5000.00000000",
      "size": "2.0000",
      "side": "Buy"
    },
    {
      "price": "1.50000000",
      "size": "0.0200",
      "side": "Buy"
    },
    {
      "price": "5900.00000000",
      "size": "0.9000",
      "side": "Sell"
    }
  ]
}
```
t(:usdc_order_book_desc)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=uopvorderBook>/option/usdc/openapi/public/v1/order-book</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvorderBook"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>



<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
| t(:row_parameter_symbol) | <b>true</b>| string | t(:usdcSymbol) |


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_price) | string | t(:usdcPrice) |
| size | string | t(:usdcSize)|
| t(:row_parameter_side) | string | t(:usdcOrderBookSide)|



### t(:querySymbolInfo)

> t(:codequote_curlExample)

```console
curl 'https://api-testnet.bybit.com/option/usdc/openapi/public/v1/symbols?symbol=BTC-30SEP22-400000-C&status=ONLINE'

```

```python
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
                "symbol": "BTC-30SEP22-400000-C",
                "status": "ONLINE",
                "baseCoin": "BTC",
                "quoteCoin": "USD",
                "settleCoin": "USDC",
                "takerFee": "0.0003",
                "makerFee": "0.0003",
                "minLeverage": "",
                "maxLeverage": "",
                "leverageStep": "",
                "minOrderPrice": "5",
                "maxOrderPrice": "10000000",
                "minOrderSize": "0.01",
                "maxOrderSize": "200",
                "tickSize": "5",
                "minOrderSizeIncrement": "0.01",
                "basicDeliveryFeeRate": "0.00015",
                "deliveryTime": "1664524800000"
            }
        ]
    }
}
```
t(:usdcSymbolInfo)


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=usdcSymbols>/option/usdc/openapi/public/v1/symbols</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#usdcSymbols"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |false|string|t(:usdcSymbol)|
|status|false|string|t(:symbolStatus)|
|baseCoin|false|string|t(:usdcBaseCoin_new)|
|direction|false|string|t(:direction)|
|limit|false|string|t(:usdcLimit_max1000_default500)|
|cursor|false|string|t(:cursor)|



<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_symbol) | string | t(:usdcSymbol) |
| status | string | t(:symbolStatus) |
| baseCoin | string | t(:usdcBaseCoin) |
| quoteCoin | string | t(:usdcQuoteCoin) |
| settleCoin | string | t(:usdcSettleCoin) |
| takerFee | string | t(:usdcTakerFee) |
| makerFee | string | t(:usdcMakerFee) |
| minLeverage | string | t(:minLeverage) |
| maxLeverage | string | t(:maxLeverage) |
| leverageStep | string | t(:leverageStep) |
| minOrderPrice | string | t(:minPrice) |
| maxOrderPrice | string | t(:maxPrice) |
| minOrderSize | string | t(:minTradingQty) |
| maxOrderSize | string | t(:maxTradingQty) |
| tickSize | string | t(:tickSize) |
| minOrderSizeIncrement | string | t(:minOrderSizeIncrement) |
| basicDeliveryFeeRate | string | t(:usdcBasicDeliveryFeeRate) |
| deliveryTime | string | t(:deliveryTime) |
| cursor | string | t(:cursor) |




### t(:usdcTickerInfo)
> t(:codequote_curlExample)

```console
curl 'https://api-testnet.bybit.com/option/usdc/openapi/public/v1/tick?symbol=BTC-28JAN22-250000-C'
```

```python
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "SUCCESS",
    "result": {
    "symbol": "BTC-28JAN22-250000-C",
      "bid": "0",
      "bidIv": "0",
      "bidSize": "0",
      "ask": "0",
      "askIv": "0",
      "askSize": "0",
      "lastPrice": "0",
      "openInterest": "0",
      "indexPrice": "56171.79000000",
      "markPrice": "12.72021285",
      "markPriceIv": "1.1701",
      "change24h": "0",
      "high24h": "0",
      "low24h": "0",
      "volume24h": "0",
      "turnover24h": "0",
      "totalVolume": "0",
      "totalTurnover": "0",
      "predictedDeliveryPrice": "0",
      "underlyingPrice": "57039.61000000",
      "delta": "0.00184380",
      "gamma": "0.00000022",
      "vega": "1.35132531",
      "theta": "-1.33819821"
  }
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=usdcTick>/option/usdc/openapi/public/v1/tick</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#usdcTick"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b>|string|t(:usdcSymbol)|


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_symbol) | string | t(:usdcSymbol) |
| bid | string | t(:usdcBid) |
| bidIv | string | t(:usdcBidIv) |
| bidSize | string | t(:usdcBidSize) |
| ask | string | t(:usdcAsk) |
| askIv | string | t(:usdcAskIv) |
| askSize | string | t(:usdcAskSize) |
| lastPrice | string | t(:usdcLastPrice) |
| openInterest | string | t(:usdcOpenInterest) |
| indexPrice | string | t(:usdcIndexPrice) |
| markPrice | string | t(:usdcMarkPrice) |
| markPriceIv | string | t(:usdcMarkPriceIv) |
| change24h | string | t(:usdcChange24h) |
| high24h | string | t(:usdcHigh24h) |
| low24h | string | t(:usdcLow24h) |
| volume24h | string | t(:usdcVolume24h) |
| turnover24h | string | t(:usdcTurnover24h) |
| totalVolume | string | t(:usdcTotalVolume) |
| totalTurnover | string | t(:usdcTotalTurnover) |
| predictedDeliveryPrice | string | t(:usdcPredictedDeliveryPrice) |
| underlyingPrice | string | t(:usdcUnderlyingPrice) |
| delta | string | t(:delta) |
| gamma | string | t(:gamma) |
| vega | string | t(:vega) |
| theta | string | t(:theta) |


### t(:queryDeliveryPrice)

> t(:codequote_curlExample)

```console
curl 'https://api-testnet.bybit.com/option/usdc/openapi/public/v1/delivery-price?symbol=BTC-3NOV21-58000-C'
```

```python
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
        "symbol": "BTC-3NOV21-58000-C",
        "deliveryPrice": "63149.218777910",
        "deliveryTime": "1635926400000"
      }
    ]
  }
}
```
<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=usdcDeliveyPrice>/option/usdc/openapi/public/v1/delivery-price</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#usdcDeliveyPrice"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |false|string|t(:usdcSymbol)|
|baseCoin |false|string|t(:usdcBaseCoin_new)|
|direction|false|string|t(:direction)|
|limit|false|string|t(:usdcDeliveryLimit)|
|cursor|false|string|t(:cursor)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_symbol) | string | t(:usdcSymbol) |
| deliveryPrice | string | t(:deliveryPrice) |
| deliveryTime | string | t(:deliveryTime) |
| cursor | string | t(:cursor) |


### t(:queryLatest500Trades)

> t(:codequote_curlExample)

```console
curl 'https://api-testnet.bybit.com/option/usdc/openapi/public/v1/query-trade-latest?category=OPTION&limit=1'
```

```python
```

> t(:codequote_responseExample)

```javascript
{
    "result": {
        "resultTotalSize": 1,
        "dataList": [
            {
                "symbol": "BTC-30SEP22-22000-C",
                "underlyingPrice": "20098.8800",
                "side": "Buy",
                "markPrice": "759.5557",
                "indexPrice": "20103.2800",
                "markIv": "0.6447",
                "orderQty": "0.200",
                "orderPrice": "780.0000",
                "time": "1662010998250",
                "iv": "0.6544782237284431",
                "tradeId": "b7fd308e-09b3-5094-92e9-c9c49ca8f982",
                "isBlockTrade": false
            },
        ]
    },
    "retCode": 0,
    "retMsg": "Success."
}
```
t(:usdcLast500TradeDesc)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=usdcTradeLastest>/option/usdc/openapi/public/v1/query-trade-latest</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#usdcTradeLastest"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category|<b>true</b>|string|t(:usdcCategory)|
|t(:row_parameter_symbol) |false|string|t(:usdcSymbol)|
|baseCoin |false|string|t(:usdcBaseCoin_new)|
|optionType|false|string|t(:usdcOptionType)|
|limit|false|string|t(:usdcLimitMax500)|


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|resultTotalSize|number|t(:resultTotalSize)|
|dataList|list|t(:dataList)|

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_symbol) |string|t(:usdcSymbol)|
|underlyingPrice |string|t(:usdcUnderlyingPrice)|
|side |string|t(:usdc_side)|
|markPrice |string|t(:usdcMarkPrice)|
|indexPrice |string|t(:usdcIndexPrice)|
|markIv |string|t(:usdcMarkPriceIv)|
|orderQty|string|t(:usdcExecQty)|
|orderPrice|string|t(:usdcExecPrice)|
|time|string|t(:time)|
|iv|string|t(:usdcIv)|
|tradeId|string|t(:tradeId)|
|isBlockTrade|boolean|t(:usdc_isBlockTrade)|


### t(:queryHistoricalVolatility)

> t(:codequote_curlExample)

```console
curl 'https://api.bybit.com/option/usdc/openapi/public/v1/query-historical-volatility?baseCoin=BTC&startTime=1659283200000&endTime=1660060800000'
```

```python
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "SUCCESS",
    "result": [
        {
            "period": 7,
            "value": "0.66571152",
            "time": "1659283200000"
        },
        ....
        {
            "period": 7,
            "value": "0.45435445",
            "time": "1660060800000"
        }
    ]
}
```
t(:historicalVolatilityPara)

<aside class="notice">
t(:historicalVolatilityNotice)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=usdchisvol>/option/usdc/openapi/public/v1/query-historical-volatility</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#usdchisvol"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#base-coin-basecoin">baseCoin</a>|false|string|t(:baseCoin)|
|<a href="#period-period">period</a> |false|string|t(:usdcPeriod_2)|
|startTime |false|string|t(:row_comment_startTime_v3)|
|endTime|false|string|t(:row_comment_endTime_v3)|


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|result|list|t(:dataList)|

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|period|string|t(:usdcPeriod_2)|
|value|string|t(:usdcVolatility)|
|time|string|t(:time)|


### t(:usdcAllTickerInfo)
> t(:codequote_curlExample)

```console
curl 'https://api-testnet.bybit.com/option/usdc/openapi/public/v1/all-tickers?baseCoin=BTC'
```

```python
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "SUCCESS",
    "result": [
        {
            "symbol": "BTC-21OCT22-16000-P",
            "bid": "0",
            "bidIv": "0",
            "bidSize": "0",
            "ask": "0",
            "askIv": "0",
            "askSize": "0",
            "lastPrice": "115",
            "openInterest": "99.15",
            "indexPrice": "19171.99",
            "markPrice": "84.81206918",
            "markPriceIv": "0.8299",
            "change24h": "0.04545455",
            "high24h": "115",
            "low24h": "115",
            "volume24h": "0.01",
            "turnover24h": "191.3837",
            "totalVolume": "298",
            "totalTurnover": "5842799",
            "predictedDeliveryPrice": "0",
            "underlyingPrice": "19162.1",
            "delta": "-0.07273689",
            "gamma": "0.00005566",
            "vega": "4.14013074",
            "theta": "-19.2782722"
        }
    ]
}
```

t(:usdcAllTickerInfo_para)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=usdcAllTick>/option/usdc/openapi/public/v1/all-tickers</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#usdcAllTick"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|baseCoin |false |string|t(:usdcBaseCoin_new)|


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_symbol) | string | t(:usdcSymbol) |
| bid | string | t(:usdcBid) |
| bidIv | string | t(:usdcBidIv) |
| bidSize | string | t(:usdcBidSize) |
| ask | string | t(:usdcAsk) |
| askIv | string | t(:usdcAskIv) |
| askSize | string | t(:usdcAskSize) |
| lastPrice | string | t(:usdcLastPrice) |
| openInterest | string | t(:usdcOpenInterest) |
| indexPrice | string | t(:usdcIndexPrice) |
| markPrice | string | t(:usdcMarkPrice) |
| markPriceIv | string | t(:usdcMarkPriceIv) |
| change24h | string | t(:usdcChange24h) |
| high24h | string | t(:usdcHigh24h) |
| low24h | string | t(:usdcLow24h) |
| volume24h | string | t(:usdcVolume24h) |
| turnover24h | string | t(:usdcTurnover24h) |
| totalVolume | string | t(:usdcTotalVolume) |
| totalTurnover | string | t(:usdcTotalTurnover) |
| predictedDeliveryPrice | string | t(:usdcPredictedDeliveryPrice) |
| underlyingPrice | string | t(:usdcUnderlyingPrice) |
| delta | string | t(:delta) |
| gamma | string | t(:gamma) |
| vega | string | t(:vega) |
| theta | string | t(:theta) |
