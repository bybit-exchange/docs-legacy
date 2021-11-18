# t(:marketdata)
t(:market_para_auth)


### t(:usdcOrderBook)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/public/v1/order-book \
-H "Content-Type: application/json" \
-d '{"symbol": "BTC-22OCT21-45000-C"}'

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
t(:usdc_order_book_desc)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvorderBook>/{category}/usdc/openapi/public/v1/order-book</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvorderBook"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

t(:usdc_order_book_path)


<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
| symbol | <b>true</b>| string | t(:usdcSymbol) |


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| price | string | t(:usdcPrice) |
| size | string | t(:usdcSize)|
| side | string | t(:usdcOrderBookSide)|


### t(:querykline)

Perpetual only.

> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/perpetual/usdc/openapi/public/v1/kline/list' \
--header 'Content-Type: application/json' \
--data-raw '{
    "symbol": "BTCPERP",
    "period":"1",
    "limit":"1",
    "startTime":1
}'
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
POST
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



### t(:usdcTickerInfo)
t(:usdc_order_book_path)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/public/v1/tick \
-H "Content-Type: application/json" \
-D '{"symbol": "BTC-22OCT21-45000-C"}'
```

```python
```

> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"SUCCESS",
    "result":{
    "symbol":"BTC-22OCT21-45000-C",
      "bid":"9.40065408",
      "bidIv":"0.0000",
      "bidSize":"155196.7296",
      "ask":"12.03032704",
      "askIv":"0.0000",
      "askSize":"144786.7184",
      "lastPrice":"12.03032704",
      "openInterest":"56.3",
      "indexPrice":"57513.73000000",
      "markPrice":"12996.21947583",
      "markPriceIv":"1.1613",
      "change24h":"-0.99849621",
      "high24h":"8000.00000000",
      "low24h":"2.02000000",
      "volume24h":"11459759.9440",
      "turnover24h":"89748414.25099826",
      "totalVolume":"11459760",
      "totalTurnover":"89748415",
      "predictedDeliveryPrice":"57540.52549555",
      "underlyingPrice":"57708.12000000",
      "delta":"0.93742138",
      "gamma":"0.00001242",
      "vega":"10.51152247",
      "theta":"-76.37969432"
  }
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=sqvdMerged>/{category}/usdc/openapi/public/v1/tick</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvdMerged"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol | string | t(:usdcSymbol) |
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


### t(:querySymbolInfo)
t(:usdc_order_book_path)

> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/public/v1/symbols \
-H "Content-Type: application/json" \
-d '{"symbol":"BTC-26NOV21-80000-P","category":"option"}'

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
            "symbol": "BTC-26NOV21-80000-P",
            "status": "ONLINE",
            "baseCoin": "BTC",
            "quoteCoin": "USD",
            "takerFeeRate": "0.0075",
            "makerFeeRate": "0.0075",
            "minLeverage": 1,
            "maxLeverage": 100,
            "minPrice": "0.1",
            "maxPrice": "99999",
            "qtyStep": "0.1",
            "deliveryFeeRate": "0.1",
            "deliveryTime": 1632919052,
            "cursor": "{'id':111}",
        }
    ]
}
```
t(:usdcSymbolInfo)


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=sqvdMerged>/{category}/usdc/openapi/public/v1/symbols</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvdMerged"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category|<b>true</b>|string|t(:usdcCategory)|
|symbol|false|string|t(:usdcSymbol)|
|direction|false|string|t(:direction)|
|limit|false|string|t(:usdcLimit)|
|cursor|false|string|t(:cursor)|



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
| deliveryFeeRate | string | t(:deliveryFeeRate) |
| deliveryTime | number | t(:deliveryTime) |
| cursor | string | t(:cursor) |



### t(:markKLine)
Perpetual only.

> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/perpetual/usdc/openapi/public/v1/mark-price-kline \
-H "Content-Type: application/json" \
-d '{
    "symbol": "BTCPERP",
    "period":"1",
    "startTime":1,
    "limit":"1"
}'

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
POST
<code><span id=sqvdMerged>/perpetual/usdc/openapi/public/v1/mark-price-kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvdMerged"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

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
Perpetual only.
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/perpetual/usdc/openapi/public/v1/index-price-kline \
-H "Content-Type: application/json" \
-d '{
    "symbol": "BTCPERP",
    "period":"W",
    "startTime":1634378400
}'
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
POST
<code><span id=sqvdMerged>/perpetual/usdc/openapi/public/v1/index-price-kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvdMerged"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

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
Perpetual only.
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/perpetual/usdc/openapi/public/v1/premium-index-kline \
-H "Content-Type: application/json" \
-d '{
    "symbol": "BTCPERP",
    "limit": 1,
    "period":"1",
    "startTime":1
}'
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
POST
<code><span id=sqvdMerged>/perpetual/usdc/openapi/public/v1/premium-index-kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvdMerged"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

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

Perpetual only.

> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/perpetual/usdc/openapi/public/v1/open-interest \
-H "Content-Type: application/json" \
-d '{"symbol":"BTCUSD","period":"1"}'
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
            "symbol":"BTCUSD",
            "timestamp":1635648300,
            "openInterest":"1.1"
        }
    ]
}

```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=sqvdMerged>/perpetual/usdc/openapi/public/v1/open-interest</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvdMerged"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

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
Perpetual only.
> t(:codequote_curlExample)

```console

curl https://api-testnet.bybit.com/perpetual/usdc/openapi/public/v1/big-deal \
-H "Content-Type: application/json" \
-d '{"symbol":"BTCUSD"}'

```

```python
```

> t(:codequote_responseExample)

```javascript

{
    "retCode":0,
    "retMsg":"OK",
    "result":[
        {
            "symbol":"BTCUSD",
            "side":"Sell",
            "timestamp":1636690065,
            "value":"697998"
        }
    ]
}

```
<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=sqvdMerged>/perpetual/usdc/openapi/public/v1/big-deal</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvdMerged"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

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

Perpetual only.


> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/perpetual/usdc/openapi/public/v1/account-ratio \
-H "Content-Type: application/json" \
-d '{"symbol":"BTCUSD","period":"5min"}'
```

```python
```

> t(:codequote_responseExample)

```javascript
  {
  "retCode":0,
    "retMsg":"OK",
    "result":[
      {
        "symbol":"BTCUSD",
        "buyRatio":0.5831,
        "sellRatio":0.4169,
        "timestamp":1636700400
      }
  ]
}

```
<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=sqvdMerged>/perpetual/usdc/openapi/public/v1/account-ratio</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvdMerged"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

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



### t(:queryDeliveryPrice)

Option only.

> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/public/v1/delivery-price \
-H "Content-Type: application/json" \
-d '{"symbol":"BTC-22OCT21-45000-C"}'
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
            "symbol": "BTC-22OCT21-45000-C",
            "deliveryPrice": "100.01",
            "deliveryTime": 1597659000,
            "cursor": ""
        }
    ]
}
```
<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=sqvdMerged>/option/usdc/openapi/public/v1/delivery-price</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvdMerged"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|false|string|t(:usdcSymbol)|
|direction|false|string|t(:direction)|
|limit|false|string|t(:usdcDeliveryLimit)|
|cursor|false|string|t(:cursor)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol | string | t(:usdcSymbol) |
| deliveryPrice | string | t(:deliveryPrice) |
| deliveryTime | number | t(:deliveryTime) |
| cursor | string | t(:cursor) |



### t(:queryLatest500Trades)

For both Perpetual and Option

> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/public/v1/query-trade-latest \
-H "Content-Type: application/json" \
-d '{"category":"option","symbol":"BTC-19NOV21-30000-P","optionType":"PUT","limit":1}'
```

```python
```

> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"OK",
    "result":{
    "resultTotalSize":1,
      "cursor":"",
      "dataList":[
      {
        "id":"184c3c8b",
        "symbol":"BTC-19NOV21-30000-P",
        "orderPrice":"1.00",
        "orderQty":"0.020",
        "side":"Buy",
        "time":"1636704178974"
      }
    ]
  }
}
```
<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=sqvdMerged>/option/usdc/openapi/public/v1/query-trade-latest</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvdMerged"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category|<b>true</b>|string|t(:category)|
|symbol|false|string|t(:usdcSymbol)|
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
|symbol|string|t(:usdcSymbol)|
|orderPrice|string|t(:usdcOrderPrice)|
|orderQty|string|t(:usdcOrderQty)|
|side|string|t(:side)|
|time|number|t(:time)|

