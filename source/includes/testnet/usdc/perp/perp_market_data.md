# t(:marketdata)
t(:market_para_auth)


### t(:usdcOrderBook)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/perpetual/usdc/openapi/public/v1/order-book?symbol=BTCPERP' \
```

```python
```

> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"SUCCESS",
    "result":[
    {
      "price":"9.40065408",
      "size":"155196.7296",
      "side":"BID"
    },
    {
      "price":"9.13032704",
      "size":"40493.4592",
      "side":"ASK"
    }
  ]
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=uopvorderBook>/perpetual/usdc/openapi/public/v1/order-book</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvorderBook"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
| symbol | <b>true</b>| string | t(:usdcSymbol) |


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| price | string | t(:usdcPrice) |
| size | string | t(:usdcSize)|
| side | string | t(:usdcPerpOrderBookSide)|



### t(:querySymbolInfo)

> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/perpetual/usdc/openapi/public/v1/symbols

```

```python
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "",
    "result": [
    {
      "symbol": "BTCPERP",
      "status": "ONLINE",
      "baseCoin": "BTC",
      "quoteCoin": "USD",
      "takerFeeRate": "0.00075",
      "makerFeeRate": "-0.00025",
      "minLeverage": "1",
      "maxLeverage": "100",
      "leverageStep": "0.01",
      "minPrice": "0.50",
      "maxPrice": "999999.00",
      "tickSize": "0.50",
      "maxTradingQty": "5.000",
      "minTradingQty": "0.001",
      "qtyStep": "0.001",
      "deliveryFeeRate": "",
      "deliveryTime": "0"
    }
  ]
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=usdcSymbols>/perpetual/usdc/openapi/public/v1/symbols</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#usdcSymbols"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|false|string|t(:usdcSymbol)|
|direction|false|string|t(:direction)|
|limit|false|string|t(:usdcLimit)|



<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol | string | t(:usdcSymbol) |
| status | string | t(:symbolStatus) |
| baseCoin | string | t(:usdcBaseCoin) |
| quoteCoin | string | t(:usdcQuoteCoin) |
| takerFeeRate | string | t(:usdcTakerFeeRate) |
| makerFeeRate | string | t(:usdcMakerFeeRate) |
| minLeverage | number | t(:minLeverage) |
| maxLeverage | number | t(:maxLeverage) |
| leverageStep | number | t(:leverageStep) |
| minPrice | string | t(:minPrice) |
| maxPrice | string | t(:maxPrice) |
| tickSize | string | t(:tickSize) |
| minTradingQty | string | t(:minTradingQty) |
| maxTradingQty | string | t(:maxTradingQty) |
| qtyStep | string | t(:qtyStep) |



### t(:usdcTickerInfo)
> t(:codequote_curlExample)

```console
curl 'https://api-testnet.bybit.com/perpetual/usdc/openapi/public/v1/tick?symbol=BTCPERP'
```

```python
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "",
    "result": {
    "symbol": "BTCPERP",
      "bid": "56685",
      "bidIv": "",
      "bidSize": "1.954",
      "ask": "56760",
      "askIv": "",
      "askSize": "114.866",
      "lastPrice": "56457.00",
      "openInterest": "1853.80",
      "indexPrice": "56928.09",
      "markPrice": "57216.42",
      "markPriceIv": "",
      "change24h": "-0.053195",
      "high24h": "59629.00",
      "low24h": "56110.50",
      "volume24h": "35.92",
      "turnover24h": "2040176.21",
      "totalVolume": "35.92",
      "totalTurnover": "2040176.21",
      "fundingRate": "0",
      "predictedFundingRate": "0",
      "nextFundingTime": "2021-11-30T16:00:00Z",
      "countdownHour": "6",
      "predictedDeliveryPrice": "",
      "underlyingPrice": "",
      "delta": "",
      "gamma": "",
      "vega": "",
      "theta": ""
  }
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=usdcTick>/perpetual/usdc/openapi/public/v1/tick</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#usdcTick"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol | string | t(:usdcSymbol) |
| bid | string | t(:usdcBid) |
| bidSize | string | t(:usdcBidSize) |
| ask | string | t(:usdcAsk) |
| askSize | string | t(:usdcAskSize) |
| lastPrice | string | t(:usdcLastPrice) |
| openInterest | string | t(:usdcOpenInterest) |
| indexPrice | string | t(:usdcIndexPrice) |
| markPrice | string | t(:usdcMarkPrice) |
| change24h | string | t(:usdcChange24h) |
| high24h | string | t(:usdcHigh24h) |
| low24h | string | t(:usdcLow24h) |
| volume24h | string | t(:usdcVolume24h) |
| turnover24h | string | t(:usdcTurnover24h) |
| totalVolume | string | t(:usdcTotalVolume) |
| totalTurnover | string | t(:usdcTotalTurnover) |
| underlyingPrice | string | t(:usdcUnderlyingPrice) |


### t(:querykline)

> t(:codequote_curlExample)

```console
curl 'https://api-testnet.bybit.com/perpetual/usdc/openapi/public/v1/kline/list?symbol=BTCPERP&period=1&limit=1&startTime=1
```

```python
```

> t(:codequote_responseExample)

```javascript

{
  "retCode":0,
  "retMsg":"",
  "result":[
  {
    "symbol":"BTCPERP",
    "volume":"0.01",
    "period":"1",
    "openTime":"1636358160",
    "open":"66001.50",
    "high":"66001.50",
    "low":"66001.50",
    "close":"66001.50",
    "turnover":"1188.02"
  }
]
}

```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=sqvdMerged>/perpetual/usdc/openapi/public/v1/kline/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvdMerged"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|period|<b>true</b>|string|t(:usdcPeriod)|
|startTime|<b>true</b>|number|t(:usdcStartTime)|
|limit| false | number | t(:usdcLimit)


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| volume | string | t(:usdcVolume) |
| symbol | string | t(:usdcSymbol) |
| open | string | t(:usdcOpen) |
| openTime | number | t(:usdcOpenTime) |
| turnover | string | t(:usdcTurnover) |
| period | string | t(:usdcPeriod) |
| low | string | t(:usdcLow) |
| high | string | t(:usdcHigh) |
| close | string | t(:usdcClose) |



### t(:markKLine)

> t(:codequote_curlExample)

```console
curl 'https://api-testnet.bybit.com/perpetual/usdc/openapi/public/v1/mark-price-kline?symbol=BTCPERP&period=1&limit=1&startTime=1'
```

```python
```

> t(:codequote_responseExample)

```javascript

{
    "retCode":0,
    "retMsg":"",
    "result":[
        {
            "symbol":"BTCPERP",
            "period":"1",
            "openTime":"1634696220",
            "open":"63884.11",
            "high":"63884.11",
            "low":"63862.49",
            "close":"63866.63"
        }
    ]
}

```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=usdcMarkPriceKline>/perpetual/usdc/openapi/public/v1/mark-price-kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#usdcMarkPriceKline"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|period|<b>true</b>|string|t(:usdcPeriod)|
|limit|false|string|t(:usdcLimit)|
|startTime|<b>true</b>|number|t(:startTime)|

  

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol | string | t(:usdcSymbol) |
| period | string | t(:usdcPeriod) |
| openTime | number | t(:openTime) |
| open | string | t(:open) |
| high | string | t(:high) |
| low | string | t(:low) |
| close | string | t(:close) |



### t(:indexKLine)
> t(:codequote_curlExample)

```console
curl 'https://api-testnet.bybit.com/perpetual/usdc/openapi/public/v1/index-price-kline?symbol=BTCPERP&period=1&limit=1&startTime=1'
```

```python
```

> t(:codequote_responseExample)

```javascript
{
    "retCode":0,
    "retMsg":"",
    "result":[
        {
            "symbol":"BTCPERP",
            "period":"W",
            "openTime":"1635120000",
            "open":"62033.96",
            "high":"62058.66",
            "low":"60005.97",
            "close":"61359.21"
        }
    ]
}

```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=uscIndexPriceKline>/perpetual/usdc/openapi/public/v1/index-price-kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uscIndexPriceKline"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|period|<b>true</b>|string|t(:usdcPeriod)|
|limit|false|string|t(:usdcLimit)|
|startTime|<b>true</b>|number|t(:startTime)|



<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol | string | t(:usdcSymbol) |
| period | string | t(:usdcPeriod) |
| openTime | number | t(:openTime) |
| open | string | t(:open) |
| high | string | t(:high) |
| low | string | t(:low) |
| close | string | t(:close) |




### t(:premiumKLine)
> t(:codequote_curlExample)

```console
curl 'https://api-testnet.bybit.com/perpetual/usdc/openapi/public/v1/premium-index-kline?symbol=BTCPERP&period=1&limit=1&startTime=1'
```

```python
```

> t(:codequote_responseExample)

```javascript

{
    "retCode":0,
    "retMsg":"",
    "result":[
        {
            "symbol":"BTCPERP",
            "period":"1",
            "openTime":"1635648300",
            "open":"0.000066",
            "high":"0.000066",
            "low":"0.000066",
            "close":"0.000066"
        }
    ]
}

```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=usdcPremiumIndexKline>/perpetual/usdc/openapi/public/v1/premium-index-kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#usdcPremiumIndexKline"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|period|<b>true</b>|string|t(:usdcPeriod)|
|limit|false|string|t(:usdcLimit)|
|startTime|<b>true</b>|number|t(:startTime)|



<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol | string | t(:usdcSymbol) |
| period | string | t(:usdcPeriod) |
| openTime | number | t(:openTime) |
| open | string | t(:open) |
| high | string | t(:high) |
| low | string | t(:low) |
| close | string | t(:close) |


### t(:queryOpenInterest)

> t(:codequote_curlExample)

```console
curl 'https://api-testnet.bybit.com/perpetual/usdc/openapi/public/v1/open-interest?symbol=BTCPERP&period=5min&limit=2'
```

```python
```

> t(:codequote_responseExample)

```javascript

{
  "retCode": 0,
  "retMsg": "",
  "result": [
  {
    "symbol": "BTCPERP",
    "timestamp": "0",
    "openInterest": "11"
  },
  {
    "symbol": "BTCPERP",
    "timestamp": "1637922300",
    "openInterest": "185380200000"
  }
]
}

```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=usdcOpenInterest>/perpetual/usdc/openapi/public/v1/open-interest</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#usdcOpenInterest"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|period|<b>true</b>|string|t(:usdcOpenInterestPeriod)|
|limit|false|string|t(:usdcOpenInterestLimit)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol | string | t(:usdcSymbol) |
| timestamp | number | t(:timestamp) |
| openInterest | string | t(:marketopeninterest) |


### t(:bigDealOrder)
> t(:codequote_curlExample)

```console

curl 'https://api-testnet.bybit.com/perpetual/usdc/openapi/public/v1/big-deal?symbol=BTCPERP&limit=2'

```

```python
```

> t(:codequote_responseExample)

```javascript

{
  "retCode": 0,
  "retMsg": "",
  "result": [
  {
    "symbol": "BTCPERP",
    "side": "Sell",
    "timestamp": "1638254956",
    "value": "1933941.70000000"
  },
  {
    "symbol": "BTCPERP",
    "side": "Sell",
    "timestamp": "1638254952",
    "value": "504610.00000000"
  }
]
}

```
<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=usdcBigDeal>/perpetual/usdc/openapi/public/v1/big-deal</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#usdcBigDeal"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|limit|false|string|t(:usdcBigDealLimit)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol | string | t(:usdcSymbol) |
| timestamp | number | t(:timestamp) |
| side | string | t(:side) |
| value | string | t(:usdcValue) |



### t(:accountRatio)


> t(:codequote_curlExample)

```console
curl 'https://api-testnet.bybit.com/perpetual/usdc/openapi/public/v1/account-ratio?symbol=BTCPERP&limit=2&period=1d'
```

```python
```

> t(:codequote_responseExample)

```javascript
 {
  "retCode": 0,
    "retMsg": "",
    "result": [
    {
      "symbol": "BTCPERP",
      "buyRatio": 0.6131,
      "sellRatio": 0.3869,
      "timestamp": "1638230400"
    },
    {
      "symbol": "BTCPERP",
      "buyRatio": 0.5902,
      "sellRatio": 0.4098,
      "timestamp": "1638144000"
    }
  ]
}

```
<p class="fake_header">t(:httprequest)</p>

GET
<code><span id=usdcAccountRatio>/perpetual/usdc/openapi/public/v1/account-ratio</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#usdcAccountRatio"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|period|<b>true</b>|string|t(:usdcAccountRatioPeriod)|
|limit|false|string|t(:usdcAccountRatioLimit)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol | string | t(:usdcSymbol) |
| buyRatio | string | t(:buyRatio) |
| sellRatio | string | t(:sellRatio) |
| timestamp | number | t(:timestamp) |



### t(:queryLatest500Trades)

> t(:codequote_curlExample)

```console
curl 'https://api-testnet.bybit.com/option/usdc/openapi/public/v1/query-trade-latest?symbol=BTCPERP&limit=2&category=PERPETUAL' \
```

```python
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "Success.",
    "result": {
    "resultTotalSize": 2,
      "cursor": "",
      "dataList": [
      {
        "id": "3caaa0ca",
        "symbol": "BTCPERP",
        "orderPrice": "58445.00",
        "orderQty": "0.010",
        "side": "Buy",
        "time": "1638275679673"
      },
      {
        "id": "10cc3064",
        "symbol": "BTCPERP",
        "orderPrice": "58477.50",
        "orderQty": "0.010",
        "side": "Buy",
        "time": "1638275670702"
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
|category|<b>true</b>|string|t(:usdcPerpCategory)|
|symbol|false|string|t(:usdcSymbol)|
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
|symbol|string|t(:usdcSymbol)|
|orderPrice|string|t(:usdcOrderPrice)|
|orderQty|string|t(:usdcOrderQty)|
|side|string|t(:side)|
|time|number|t(:time)|

