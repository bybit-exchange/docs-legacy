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
curl 'https://api-testnet.bybit.com/option/usdc/openapi/public/v1/symbols?limit=1&status=ONLINE&status=OFFLINE'

```

```python
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "resultTotalSize": 1618,
      "cursor": "0%2C1",
      "dataList": [
      {
        "symbol": "BTC-28JAN22-250000-C",
        "status": "ONLINE",
        "baseCoin": "BTC",
        "quoteCoin": "USD",
        "settleCoin": "USDC",
        "takerFee": "0.00025",
        "makerFee": "0.00025",
        "minLeverage": "",
        "maxLeverage": "",
        "leverageStep": "",
        "minOrderPrice": "0.5",
        "maxOrderPrice": "10000000",
        "minOrderSize": "0.01",
        "maxOrderSize": "1000",
        "tickSize": "0.5",
        "minOrderSizeIncrement": "0.01",
        "basicDeliveryFeeRate": "0.00015",
        "deliveryTime": "1643356800000"
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
|direction|false|string|t(:direction)|
|limit|false|string|t(:usdcLimit)|
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
| minOrderSizeIncrement ｜ string | t(:minOrderSizeIncrement) |
| basicDeliveryFeeRate | string | t(:usdcBasicDeliveryFeeRate) |
| deliveryTime | number | t(:deliveryTime) |
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
|direction|false|string|t(:direction)|
|limit|false|string|t(:usdcDeliveryLimit)|
|cursor|false|string|t(:cursor)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_symbol) | string | t(:usdcSymbol) |
| deliveryPrice | string | t(:deliveryPrice) |
| deliveryTime | number | t(:deliveryTime) |
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
  "retCode": 0,
    "retMsg": "Success.",
    "result": {
    "resultTotalSize": 1,
      "cursor": "",
      "dataList": [
      {
        "id": "617f220d",
        "symbol": "BTC-3DEC21-80000-P",
        "orderPrice": "22775.50",
        "orderQty": "1.000",
        "time": "1638248170932"
      }
    ]
  }
}
```
<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=usdcTradeLastest>/option/usdc/openapi/public/v1/query-trade-latest</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#usdcTradeLastest"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category|<b>true</b>|string|t(:usdcCategory)|
|t(:row_parameter_symbol) |false|string|t(:usdcSymbol)|
|optionType|false|string|t(:usdcOptionType)|
|limit|false|string|t(:usdcLimitMax500)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|resultTotalSize|number|t(:resultTotalSize)|
|cursor|string|t(:cursor)|
|dataList|list|t(:dataList)|

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transactionTime|number|t(:transactionTime)|
|id|string|ID
|t(:row_parameter_symbol) |string|t(:usdcSymbol)|
|orderPrice|string|t(:usdcOrderPrice)|
|orderQty|string|t(:usdcOrderQty)|
|time|number|t(:time)|

