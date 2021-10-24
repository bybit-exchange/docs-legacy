# t(:websocket)


## t(:websocketauthentication)
> t(:websocket_codequote_auth_usdc)

```python
# based on: https://github.com/verata-veritatis/pybit/blob/master/pybit/__init__.py

import hmac
import json
import time
import websocket

api_key = ""
api_secret = ""

# Generate expires.
expires = int((time.time() + 1) * 1000)

# Generate signature.
signature = str(hmac.new(
    bytes(api_secret, "utf-8"),
    bytes(f"GET/realtime{expires}", "utf-8"), digestmod="sha256"
).hexdigest())

ws = websocket.WebSocketApp(
    url=url,
    ...
)

# Authenticate with API.
ws.send(
    json.dumps({
        "op": "auth",
        "args": [api_key, expires, signature]
    })
)
```


t(:usdc_websocket_para_endpoint)

<aside class="notice">
t(:websocket_aside_auth)
</aside>


t(:websocket_para_methods)

<aside class="notice">
t(:websocket_aside_signature)
</aside>

<aside class="warning">
t(:websocket_best_practices)
</aside>


## t(:heartbeat)
> t(:websocket_codequote_heartbeat)

```javascript
ws.send(JSON.stringify({"ping": 1535975085052}));
```

> t(:codequote_responseExample)

```javascript
{"pong": 1535975085152}
```


<aside class="warning">
t(:websocket_aside_heartbeat)
</aside>

t(:websocket_aside_heartbeat_option)

<!-- 连接数限制
## t(:websocketlimit)
t(:websocket_para_limit)
-->


## t(:subscribe)
### t(:websocketfilters)
> t(:websocket_codequote_filters1)

t(:usdc_websocket_subscribe_desc)

```javascript
// Subscribing to the trade data for BTCUSDT
```

### t(:websocketunfilters)

t(:usdc_websocket_unsubscribe_desc)

## t(:websocketresponse)
> t(:websocket_codequote_response)

```javascript

```

t(:spot_websocket_para_response)

## t(:publicTopic)
### orderBook

> t(:codequote_subscribe)

```javascript
```

> t(:codequote_snapshot)

```javascript

```

> t(:codequote_delta)

```javascript
```

t(:usdc_websocket_para_orderbook)


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| price |string |t(:row_comment_resp_price) |
|symbol|string |t(:usdcSymbol)    |
|side |string |t(:row_comment_side)  |
|size |number |t(:row_comment_position_size)  |




### t(:bybitTradeHistory)
> t(:codequote_subscribe)

```javascript
```

> t(:codequote_snapshot)

```javascript

```

> t(:codequote_delta)

```javascript

```

t(:usdc_current_24_total)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| tradeTime |string |t(:tradeTime) |
| symbol |string |t(:usdcSymbol) |
| side |string |t(:side) |
| size |string |t(:row_comment_position_size) |
| price |string |t(:row_comment_exec_price) |



### t(:insuranceFund)
> t(:codequote_subscribe)

```javascript
```

> t(:codequote_snapshot)

```javascript

```

> t(:codequote_delta)

```javascript

```


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| coin |string |t(:usdcCoin) |
| timestamp |string |t(:timestamp) |
| walletBalance |string |t(:walletBalance) |


### 
### t(:latestSymbolInfo)
> t(:codequote_subscribe)

```javascript
```

> t(:codequote_snapshot)

```javascript

```

> t(:codequote_delta)

```javascript

```


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol |string |t(:usdcSymbol) |
| bidPrice |string |t(:bidPrice) |
| bidIv |string |t(:bidIv) |
| bidSize |string |t(:bidSize) |
| askPrice |string |t(:askPrice) |
| askIv |string |t(:askIv) |
| askSize |string |t(:askSize) |
| lastPrice |string |t(:lastPrice) |
| openInterest |string |t(:openInterest) |
| indexPrice |string |t(:indexPrice) |
| markPrice |string |t(:markPrice) |
| markPriceIv |string |t(:markPriceIv) |
| price24Pcnt |string |t(:price24Pcnt) |
| highPrice24h |string |t(:highPrice24h) |
| lowPrice24h |string |t(:lowPrice24h) |
| volume24h |string |t(:volume24h) |
| turnover24h |string |t(:turnover24h) |
| totalVolume |string |t(:totalVolume) |
| predictedDeliveryPrice |string |t(:predictedDeliveryPrice) |
| underlying |string |t(:underlying) |
| delta |string |t(:delta) |
| gamma |string |t(:gamma) |
| vega |string |t(:vega) |
| theta |string |t(:theta) |


### KLine
> t(:codequote_subscribe)

```javascript
```

> t(:codequote_snapshot)

```javascript

```

> t(:codequote_delta)

```javascript

```


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| start |string |t(:usdcStart) |
| end |string |t(:usdcEnd) |
| open |string |t(:open) |
| close |string |t(:close) |
| high |string |t(:high) |
| low |string |t(:low) |
| volume |string |t(:usdcvolume) |
| turnover |string |t(:usdcturnover) |
| confirm |string |t(:usdcconfirm) |
| crossSeq |string |crossSeq |
| timestamp |string |t(:timestamp) |



## Private Topic
### t(:userPositionsInfo)
> t(:codequote_subscribe)

```javascript
```

> t(:codequote_snapshot)

```javascript

```

> t(:codequote_delta)

```javascript

```

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| riskId|number |t(:riskId) |
| symbol |string |t(:usdcSymbol) |
| side |string |t(:side) |
| size |string |t(:usdcSize) |
| entryPrice |string |t(:entryPrice) |
| sessionAvgPrice |string |t(:sessionAvgPrice) |
| markPrice |string |t(:markPrice) |
| positionPnl |string |t(:positionPnl) |
| roi |string |t(:roi) |
| sessionUpl |string |t(:sessionUpl) |
| im |string |t(:im) |
| mm |string |t(:usdcMm) |
| createdAt |number |t(:createdAt) |
| updatedAt |number |t(:updatedAt) |
| tpSlMode |string |t(:tpSlMode) |
| positionValue |string |t(:positionValue) |
| leverage |number |t(:leverage) |
| autoAddMargin |number |t(:usdcautoAddMargin) |
| positionMargin |string |t(:positionMargin) |
| liqPrice |string |t(:liqPrice) |
| trailingStop |number |t(:trailingStop) |
| isIsolated |number |t(:isIsolated) |
| bustPrice |string |t(:bustPrice) |
| occClosingFee |string |t(:occClosingFee) |
| occFundingFee |string |t(:occFundingFee) |
| trakeProfit |string |t(:trakeProfit) |
| stopLoss |string |t(:stopLoss) |
| positionStatus |string |t(:positionStatus) |
| deleverageIndicator |number |t(:deleverageIndicator) |
| orderMargin |string |t(:orderMargin) |
| unrealisedPnl |string |t(:unrealisedPnl) |
| cumRealisedPnl |string |t(:cumRealisedPnl) |
| cumCommission |string |t(:cumCommission) |


### t(:userFilledHistory)
> t(:codequote_subscribe)

```javascript
```

> t(:codequote_snapshot)

```javascript

```

> t(:codequote_delta)

```javascript

```

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| tradeTime|number |t(:tradeTime) |
| orderId |string |  |
| orderLinkId |string |t(:orderLinkId) |
| symbol |string |t(:usdcSymbol) |
| excPrice |string |t(:excPrice) |
| execQty |string |t(:execQty) |
| execFee |string |t(:execFee) |
| feeRate |string |t(:feeRate) |
| execType |string |t(:execType) |
| execValue |string |t(:execValue) |
| lastLiquidityInd |string |t(:lastLiquidityInd) |

### t(:userOrderHistory)

> t(:codequote_subscribe)

```javascript
```

> t(:codequote_snapshot)

```javascript
```

> t(:codequote_delta)

```javascript
```

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| orderId |string |t(:usdcOrderId) |
| orderLinkId |string |t(:orderLinkId) |
| createdAt|number |t(:createdAt) |
| updatedAt|number |t(:updatedAt) |
| symbol |string |t(:usdcSymbol) |
| orderType|string |t(:usdcOrderType) |
| side |string |t(:side) |
| orderQty |string |t(:usdcOrderQty) |
| orderPrice |string |t(:usdcOrderPrice) |
| iv |string |t(:optionIv) |
| timeInForce |string |t(:row_comment_timeInForce) |
| leavesQty |string |t(:leavesQty) |
| cumExecQty |string |t(:cumExecQty) |
| cumExecFee |string |t(:cumExecFee) |
| im |string |t(:im) |
| orderStatus |string |t(:orderStatus) |
| reduceOnly |number |t(:reduceOnly) |
| closeOnTrigger |number |t(:closeOnTrigger) |
| takeProfit |number |t(:takeProfit) |
| stopLoss |number |t(:stopLoss) |
| tpTriggerBy |number |t(:tptriggerby) |
| slTriggerBy |number |t(:slTriggerBy) |
| basePrice |number |t(:basePrice) |
| triggerPrice |number |t(:triggerPrice) |
| triggerBy |number |t(:triggerBy) |



### t(:userConditionalOrders)

> t(:codequote_subscribe)

```javascript
```

> t(:codequote_snapshot)

```javascript
```

> t(:codequote_delta)

```javascript
```

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| orderId |string |t(:usdcOrderId) |
| orderLinkId |string |t(:orderLinkId) |
| symbol |string |t(:usdcSymbol) |
| orderType|string |t(:usdcOrderType) |
| side |string |t(:side) |
| qty |string |t(:usdcQty) |
| price |string |t(:price) |
| timeInForce |string |t(:row_comment_timeInForce) |
| createType |string |t(:createType) |
| cancelType |string |t(:cancelType) |
| cumExecFee |string |t(:cumExecFee) |
| orderStatus |string |t(:orderStatus) |
| triggerBy |string |t(:triggerBy) |
| triggerPrice |string |t(:triggerPrice) |
| closeOnTrigger |string |t(:closeOnTrigger) |
| timestamp |number |t(:timestamp) |



### t(:userGreeks)

> t(:codequote_subscribe)

```javascript
```

> t(:codequote_snapshot)

```javascript
```

> t(:codequote_delta)

```javascript
```

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| baseCoin |string |t(:usdcBaseCoin) |
| delta |string |t(:delta) |
| gamma |string |t(:gamma) |
| vega|string |t(:vega) |
| theta |string |t(:theta) |

