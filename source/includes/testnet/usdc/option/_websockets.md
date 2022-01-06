# t(:websocket)


## t(:websocketauthentication)
> t(:websocket_codequote_auth_usdc)

```python
import hmac
import websocket
import threading
import time
import json

def on_message(ws, message):
    print(json.loads(message))

def on_error(ws, error):
    print('we got error')
    print(error)

def on_close(ws):
    print("### about to close please don't close ###")

def send_auth(ws):
    key = 'XXXXXXXXXXXXXXXXXXXX'
    secret = 'XXXXXXXXXXXXXXXXXXXX'
    expires = int((time.time() + 10) * 1000)
    _val = f'GET/realtime{expires}'
    print(_val)
    signature = str(hmac.new(
        bytes(secret, 'utf-8'),
        bytes(_val, 'utf-8'), digestmod='sha256'
    ).hexdigest())
    ws.send(json.dumps({"id": "signAuth_request_id", "method": "public/signAuth",
                        "params": {"sign": signature, "apiKey": key, "timestamp": expires}}))

def on_open(ws):
    print('opened')
    send_auth(ws)
    def pingPer(ws):
        while True:
            ws.send("ping")
            time.sleep(2)
    t1 = threading.Thread(target=pingPer, args=(ws,))
    t1.start()
    ws.send(json.dumps({"method": "private/subscribe", "id": "{100003}", "params": {
        "channels": ["user.option.order", "user.option.position", "user.option.tradeHistory",
                     "user.option.orderHistory"]}}))

def connWS():
    ws = websocket.WebSocketApp("wss://stream-testnet.bybit.com/trade/option/usdc/private/v1",
                                on_message=on_message,
                                on_error=on_error,
                                on_close=on_close,
                                on_open=on_open
                                )
    ws.run_forever()

if __name__ == "__main__":
    connWS()
```


t(:usdc_websocket_para_endpoint)

<aside class="warning">
t(:websocket_best_practices)
</aside>


## t(:heartbeat)
> t(:websocket_codequote_heartbeat)

```javascript
ws.send("ping");
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

## Public Topics
### OrderBook

> t(:codequote_subscribe)

```javascript
  ws.send('{"method":"public/subscribe","id":"requestId","params":{"channels":["orderbook25.BTC-12NOV21-40000-P"]}}');
```

> t(:codequote_snapshot)

```javascript

{
  "id":"orderbook100.BTC-12NOV21-40000-P-117936-1636454548726",
  "channel":"orderbook100.BTC-12NOV21-40000-P",
  "type":"SNAPSHOT",
  "serialNumber":117936,
  "publishTime":726621846,
  "creationTime":1636454548726,
  "data":{
  "timestamp":"1636444250",
    "crossSeq":"117936",
    "symbol":"BTC-12NOV21-40000-P",
    "orderBooks":[
    {
      "price":"1764.5",
      "size":"997.99",
      "side":"Sell"
    },
    {
      "price":"40000.5",
      "size":"0.01",
      "side":"Sell"
    }
  ]
}
}



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
  ws.send('{"method":"public/subscribe","id":"{1001}","params":{"channels":["recenttrades.BTC"]}}');
```


> t(:usdc_trade_codequote_snapshot)

```javascript

{
    "id":"recenttrades.BTC-118388-1636510323155",
    "channel":"recenttrades.BTC",
    "type":"SNAPSHOT",
    "serialNumber":118388,
    "publishTime":155063442,
    "creationTime":1636510323155,
    "data":{
        "coin":"BTC",
        "trades":[
            {
                "symbol":"BTC-31DEC21-36000-P",
                "execId":"787bf079-b6a5-5bc0-a76d-59dad9036e7b",
                "price":"371",
                "size":"0.01",
                "tradeTime":"1636510323144",
                "side":"Buy",
                "crossSeq":"118388"
            }
        ]
    }
}

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




### t(:latestSymbolInfo)
> t(:codequote_subscribe)

```javascript
ws.send('{"method":"public/subscribe","id":"{1001}","params":{"channels":["instrument_info.BTC-19NOV21-58000-P"]}}');
```

> t(:codequote_snapshot)

```javascript

{
    "id":"instrument_info.BTC-19NOV21-58000-P-98790-1636511446299",
    "channel":"instrument_info.BTC-19NOV21-58000-P",
    "type":"SNAPSHOT",
    "serialNumber":98790,
    "publishTime":299440840,
    "creationTime":1636511446299,
    "data":{
        "symbol":"BTC-19NOV21-58000-P",
        "bidPrice":"421",
        "askPrice":"465",
        "bidIv":"0.7785",
        "askIv":"0.8012",
        "bidSize":"17",
        "askSize":"18",
        "markPrice":"442.51157238",
        "markPriceIv":"0.7897",
        "indexPrice":"67102.13",
        "underlyingPrice":"67407.49",
        "lastPrice":"0",
        "delta":"-0.10385629",
        "gamma":"0.00002132",
        "theta":"-82.72572574",
        "vega":"19.33584131",
        "change24h":"0",
        "volume24h":"0",
        "turnover24h":"0",
        "high24h":"0",
        "low24h":"0",
        "totalVolume":"0",
        "totalTurnover":"0",
        "openInterest":"0",
        "predictedDeliveryPrice":"62330.90608575"
    }
}

```

> t(:codequote_delta)

```javascript

```

t(:usdcLastestSymbolInfo)


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



## Private Topics
### t(:userPositionsInfo)
> t(:codequote_subscribe)

```javascript

ws.send('{"method":"private/subscribe","id":"{100002}","params":{"channels":["user.option.position"]}}');

```

> t(:usdc_trade_codequote_snapshot)

```javascript
{
  "id":"12827e35-ab18-416f-b754-5fff8315459f",
    "channel":"user.option.position",
    "type":"SNAPSHOT",
    "serialNumber":1,
    "publishTime":134984932,
    "creationTime":1640835309134,
    "data":{
    "result":[
      {
        "positionIdx":0,
        "symbol":"BTC-31DEC21-24000-P",
        "positionStatus":null,
        "side":"Sell",
        "action":"OPEN",
        "positionSize":"-0.1000",
        "positionAvgPrice":"1.45000000",
        "sessionAvgPrice":"1.45000000",
        "markPrice":"0",
        "strikePrice":"",
        "exerciseDeliveryPrice":"27.96182801",
        "positionIM":"465.9957",
        "positionMM":"358.705039",
        "fees":"",
        "pnl":"0.145",
        "sessionUPL":"0.145",
        "sessionRPL":"",
        "deliveryRPL":"",
        "iv":"1.1524",
        "version":34,
        "sendTime":1640835309093,
        "positionTime":1640834421428,
        "roi":"1",
        "crossSeq":null,
        "pushActionType":0,
        "size":"-0.1000",
        "entryPrice":"1.45000000",
        "PNL":"0.145",
        "ROI":"1"
      }
    ],
      "version":8043,
      "sendTime":1640835309093
  }
}

```


t(:usdcPositionDesc)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol |string |t(:usdcSymbol) |
| side |string |t(:side) |
| positionSize |string |t(:usdcSize) |
| positionAvgPrice |string |t(:entryPrice) |
| sessionAvgPrice |string |t(:sessionAvgPrice) |
| markPrice |string |t(:markPrice) |
| sessionUPL |string |t(:sessionUpl) |
| positionIM |string |t(:im) |
| positionMM |string |t(:usdcMm) |
| PNL |string |PNL |
| ROI |string |ROI |


### t(:userFilledHistory)
> t(:codequote_subscribe)

```javascript
ws.send('{"method":"private/subscribe","id":"{100002}","params":{"channels":["user.option.tradeHistory"]}}');
```

> t(:usdc_trade_codequote_snapshot)

```javascript

{
  "id":"985cf6de-2e7e-4d18-92ff-e7a2b4fcfcc1",
  "channel":"user.option.tradeHistory",
  "type":"SNAPSHOT",
  "serialNumber":1,
  "publishTime":129276349,
  "creationTime":1640834911129,
  "data":{
  "result":[
    {
      "orderId":"4aaea02f-d62b-4951-9e12-7e2d9e37fb4c",
      "tradeId":"77fdaeef-b931-51f4-96c8-33f97c722053",
      "transId":"cross-101810-634476-1",
      "symbol":"BTC-31DEC21-18000-P",
      "side":"Sell",
      "tradePrice":"1",
      "markPrice":"0.00000000",
      "indexPrice":"46545.16000000",
      "underlying":"46562.86000000",
      "positionAvgPrice":"1",
      "iv":"1.1980",
      "size":"0.01",
      "fees":"0.001",
      "tradeTime":1640834911093,
      "version":null,
      "sendTime":null,
      "crossSeq":null,
      "reduceOnly":false,
      "orderLinkId":"test2021122417000217",
      "execPrice":"1",
      "execQty":"0.01",
      "execFee":"0.001"
    }
  ],
    "version":33,
    "sendTime":1640834911106
}
}


```


t(:usdcFilledHistory)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| tradeTime|number |t(:tradeTime) |
| orderId |string |  |
| orderLinkId |string |t(:orderLinkId) |
| tradeId |string |t(:usdcTradeId) |
| symbol |string |t(:usdcSymbol) |
| execPrice |string |t(:excPrice) |
| execQty |string |t(:execQty) |
| execFee |string |t(:execFee) |
| execType |string |t(:execType) |

### t(:activeOrders)

> t(:codequote_subscribe)

```javascript
 ws.send('{"method":"private/subscribe","id":"{100003}","params":{"channels":["user.option.order"]}}');
```

> t(:usdc_trade_codequote_snapshot)

```javascript

{
  "id":"f013f9e9-5d6c-4d43-bed4-6858d8a9de1e",
  "channel":"user.option.order",
  "type":"SNAPSHOT",
  "serialNumber":1,
  "publishTime":470805183,
  "creationTime":1637828113470,
  "data":{
  "result":[
    {
      "orderId":"cee50e1d-c36a-46f3-b861-4012f8c2589b",
      "symbol":"BTC-26NOV21-30000-P",
      "orderStatus":"New",
      "side":"Buy",
      "orderPrice":"3383.50000000",
      "orderAllSize":"0.0100",
      "orderFilledSize":"0.0000",
      "orderRemainingSize":"0.0100",
      "orderAvgPrice":"3383.50000000",
      "orderIM":"33.97985865",
      "orderType":"Limit",
      "orderTime":1637828113432,
      "reduceOnly":0,
      "timeInForce":"GoodTillCancel",
      "fees":"0.00000000",
      "cashFlow":"",
      "orderRPL":"",
      "version":9719,
      "sendTime":9719,
      "crossSeq":null,
      "deliveryTime":1637913600000,
      "strikePrice":"30000",
      "symbolType":"P",
      "postOnly":0,
      "placeType":"price",
      "placeMode":"advanced",
      "iv":"14.8490",
      "pushActionType":0
    }
  ],
    "version":240533,
    "sendTime":1637828113452
}
}


```

t(:usdcActiveOrder)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| orderId |string |t(:usdcOrderId) |
| orderLinkId |string |t(:orderLinkId) |
| symbol |string |t(:usdcSymbol) |
| orderType|string |t(:usdcOrderType) |
| side |string |t(:side) |
| orderAllSize |string |t(:orderAllSize) |
| orderFilledSize |string |t(:orderFilledSize) |
| orderPrice |string |t(:usdcOrderPrice) |
| iv |string |t(:optionIv) |
| t(:row_parameter_timeInForce) |string |t(:row_comment_timeInForce) |
| cumExecQty |string |t(:cumExecQty) |
| cumExecFee |string |t(:cumExecFee) |
| orderIM |string |t(:im) |
| orderStatus |string |t(:orderStatus) |
| reduceOnly |number |t(:reduceOnly) |
| basePrice |string |t(:basePrice) |


### t(:userOrderHistory)
> t(:codequote_subscribe)

```javascript
 ws.send('{"method":"private/subscribe","id":"{100003}","params":{"channels":["user.option.orderHistory"]}}');
```

> t(:usdc_trade_codequote_snapshot)

```javascript
{
  "id":"7e998370-42e2-45ac-ba5e-83f0b8ea2f13",
    "channel":"user.option.orderHistory",
    "type":"SNAPSHOT",
    "serialNumber":1,
    "publishTime":512267606,
    "creationTime":1637834483512,
    "data":{
    "result":[
      {
        "orderId":"48eca7f8-6916-4473-befc-7c4ad1790783",
        "symbol":"BTC-26NOV21-30000-P",
        "orderStatus":"Filled",
        "side":"Buy",
        "orderPrice":"3383.5",
        "orderAllSize":"0.01",
        "orderFilledSize":"0.01",
        "orderRemainingSize":"0",
        "orderAvgPrice":"3383.5",
        "orderIM":"33.979505575",
        "orderType":"Limit",
        "orderTime":1637834483427,
        "reduceOnly":0,
        "timeInForce":"GoodTillCancel",
        "fees":"0.14450558",
        "cashFlow":"-33.835",
        "orderRPL":"",
        "version":9722,
        "sendTime":9722,
        "crossSeq":null,
        "deliveryTime":1637913600000,
        "strikePrice":"30000",
        "symbolType":"P",
        "postOnly":0,
        "placeType":"price",
        "placeMode":"advanced",
        "iv":"15.409",
        "pushActionType":0
      }
    ],
      "version":251355,
      "sendTime":1637834483458
  }
}

```

t(:usdcOrderDesc)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| orderId |string |t(:usdcOrderId) |
| orderLinkId |string |t(:orderLinkId) |
| symbol |string |t(:usdcSymbol) |
| orderType|string |t(:usdcOrderType) |
| side |string |t(:side) |
| orderAllSize |string |t(:orderAllSize) |
| orderFilledSize |string |t(:orderFilledSize) |
| orderPrice |string |t(:usdcOrderPrice) |
| iv |string |t(:optionIv) |
|t(:row_parameter_timeInForce) |string |t(:row_comment_timeInForce) |
| cumExecQty |string |t(:cumExecQty) |
| cumExecFee |string |t(:cumExecFee) |
| orderIM |string |t(:im) |
| orderStatus |string |t(:orderStatus) |
| reduceOnly |number |t(:reduceOnly) |



### t(:userGreeks)

> t(:codequote_subscribe)

```javascript
ws.send('{"method":"private/subscribe","id":"{100003}","params":{"channels":["user.option.greeks"]}}');

```

> t(:codequote_snapshot)

```javascript

{
    "id":"37f1e862-5eaf-4cb5-a588-b369286cd805",
    "channel":"user.option.greeks",
    "type":"SNAPSHOT",
    "serialNumber":1,
    "publishTime":136973647,
    "creationTime":1636528352136,
    "data":{
        "result":[
            {
                "coin":"BTC",
                "totalDelta":"-0.029750694800",
                "totalGamma":"0.000001592300",
                "totalVega":"1.202332081800",
                "totalTheta":"-9.525983454600",
                "version":null,
                "sendTime":null,
                "crossSeq":null
            }
        ],
        "version":63672,
        "sendTime":1636528352096
    }
}

```

t(:udscGeeksDesc)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| baseCoin |string |t(:usdcBaseCoin) |
| totalDelta |string |t(:delta) |
| totalGamma |string |t(:gamma) |
| totalVega|string |t(:vega) |
| totalTheta |string |t(:theta) |
