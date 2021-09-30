# t(:marketdata)
t(:market_para_auth)


### t(:usdcOrderBook)
> t(:codequote_curlExample)

```console
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
            "price": "100.01",
            "size": "1.1",
            "side": "ask"
        }
    ]
}
```
t(:usdc_order_book_desc)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=svSymbols>/usdc/openapi/public/order-book/v1/{category}</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svSymbols"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

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

> t(:codequote_curlExample)

```console
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
            "volume": "100.01",
            "symbol": "1.1",
            "open": "ask",
            "openTime": "",
            "turnover": "",
            "period": "",
            "low": "",
            "high": "",
            "close": ""
        }
    ]
}
```



<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=sqvdMerged>/usdc/openapi/public/kline/v1/{category}</span></code>
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
| volume | string | 交易量 |
| symbol | string | t(:usdcSymbol) |
| open | string | t(:usdcOpen) |
| openTime | number | t(:usdcOpenTime) |
| turnover | string | t(:usdcTurnover) |
| period | string | t(:usdcPeriod) |
| low | string | t(:usdcLow) |
| high | string | t(:usdcHigh) |
| close | string | t(:usdcClose) |



### t(:usdcTickerInfo)
> t(:codequote_curlExample)

```console
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
            "symbol": "100.01",
            "bid": "1.1",
            "bidIv": "1.1",
            "bidSize": "1.1",
            "ask": "1.1",
            "askIv": "1.1",
            "askSize": "1.1",
            "lastPrice": "1.1",
            "openInterest": "1.1",
            "indexPrice": "1.1",
            "markPrice": "1.1",
            "markPriceIv": "1.1",
            "change24h": "1.1",
            "high24h": "1.1",
            "low24h": "1.1",
            "volume24h": "1.1",
            "turnover24h": "1.1",
            "totalVolume": "1.1",
            "totalTurnover": "1.1",
            "predictedDeliveryPrice": "1.1",
            "underlyingPrice": "1.1",
            "delta": "1.1",
            "gamma": "1.1",
            "vega": "1.1",
            "theta": "1.1",
            "side": "ask"
        }
    ]
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=sqvdMerged>/usdc/usdc/openapi/public/v1/tick/{category}</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvdMerged"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

t(:usdc_tick_desc)


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


### t(:platFormOrderHistory)
> t(:codequote_curlExample)

```console
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
            "id": "100.01",
            "symbol": "BTC-26NOV21-80000-C",
            "orderPrice": "100.01",
            "orderQty": "1.1",
            "side": "Buy",
            "time": 10131231231,
        }
    ]
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=sqvdMerged>/usdc/openapi/public/v1/order-history</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvdMerged"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category|<b>true</b>|string|t(:usdcCategory)|
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|optionType|false|string|t(:usdcOptionType)|
|limit|false|string|t(:usdcLimit)|


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| id | number | t(:id) |
| symbol | string | t(:usdcSymbol) |
| orderPrice | string | t(:usdcOrderPrice) |
| orderQty | string | t(:usdcOrderQty) |
| side | string | t(:side) |
| time | number | t(:time) |


### t(:querySymbolInfo)

> t(:codequote_curlExample)

```console
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
            "symbol": "BTC-26NOV21-80000-",
            "status": "Filled",
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
<code><span id=sqvdMerged>/usdc/openapi/v1/symbols</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvdMerged"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category|<b>true</b>|string|t(:usdcCategory)|
|symbol|false|string|t(:usdcSymbol)|
|direction|false|string|t(:row_comment_direction)|
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

> t(:codequote_curlExample)

```console
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
            "symbol": "BTC-26NOV21-80000-C",
            "period": "1",
            "openTime": 1632919052000,
            "open": "100.1",
            "high": "100.1",
            "low": "100.1",
            "close": "100.1"
        }
    ]
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=sqvdMerged>/usdc/openapi/public/v1/mark-kline</span></code>
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
> t(:codequote_curlExample)

```console
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
    "symbol": "BTC-26NOV21-80000-C",
    "period": "1",
    "openTime": 1233333,
    "open": "100.1",
    "high": "100.1",
    "low": "100.1",
    "close": "100.1"
  }
]
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=sqvdMerged>/usdc/openapi/public/v1/index-kline/</span></code>
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
> t(:codequote_curlExample)

```console
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
      "symbol": "BTC-26NOV21-80000-C",
      "period": "1",
      "openTime": 1233333,
      "open": "100.1",
      "high": "100.1",
      "low": "100.1",
      "close": "100.1"
    }
  ]
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=sqvdMerged>/usdc/openapi/public/v1/premium-kline</span></code>
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

> t(:codequote_curlExample)

```console
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
            "symbol": "BTC-26NOV21-80000-C",
            "timestamp": 1232333333,
            "openInterest": "100.1"
        }
    ]
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=sqvdMerged>/usdc/openapi/public/v1/open-interest</span></code>
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
> t(:codequote_curlExample)

```console
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
            "symbol": "BTC-26NOV21-80000-C",
            "side": "Buy",
            "timestamp": 1000000001,
            "value": "100.1"
        }
    ]
}
```
<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=sqvdMerged>/usdc/openapi/public/v1/big-deal/</span></code>
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
> t(:codequote_curlExample)

```console
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
            "symbol": "100.01",
            "buyRatio": "0.6",
            "sellRatio": "0.4",
            "timestamp": 1000000001
        }
    ]
}
```
<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=sqvdMerged>/usdc/openapi/public/v1/account-ratio</span></code>
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
> t(:codequote_curlExample)

```console
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
            "symbol": "100.01",
            "deliveryPrice": "100.01",
            "deliveryTime": 1000001,
            "cursor": ""
        }
    ]
}
```
<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=sqvdMerged>/usdc/openapi/public/v1/delivery-price</span></code>
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



### t(:querySettlePrice)
> t(:codequote_curlExample)

```console
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
            "symbol": "100.01",
            "sessionAvgPrice": "1.1",
            "settlementTime": 1000000000001
        }
    ]
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=sqvdMerged>/usdc/openapi/public/v1/session-avg-price</span></code>
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
| sessionAvgPrice | string | t(:sessionAvgPrice) |
| settlementTime | number | t(:settlementTime) |

