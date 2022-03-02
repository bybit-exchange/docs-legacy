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
    
    ws.send(
      json.dumps({
        "op": "auth",
        "args": [api_key, expires, signature]
      })
    )

def on_open(ws):
    print('opened')
    send_auth(ws)
    def pingPer(ws):
        while True:
            ws.send(
              json.dumps({
              "op": "ping",
              "args": ["946656000000"]
              })
            )
            time.sleep(25)
    t1 = threading.Thread(target=pingPer, args=(ws,))
    t1.start()
    ws.send(
      json.dumps({
        "op": "subscribe", "id": "{100003}", 
        "args": ["user.option.order", "user.option.position", 
                 "user.option.tradeHistory", "user.option.orderHistory"]
      })
    )

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
ws.send('{"op":"ping","args":["1535975085152"]}');
```

> t(:codequote_responseExample)

```javascript
{"op":"pong","args":["1535975085152"]}
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
  ws.send('{"op":"subscribe","id":"requestId","args":["orderbook25.BTC-12NOV21-40000-P"]}');
```

> t(:codequote_snapshot)

```javascript

{
  "id":"orderbook100.BTC-12NOV21-40000-P-117936-1636454548726",
  "topic":"orderbook100.BTC-12NOV21-40000-P",
  "creationTime":1636454548726,
  "data":{
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
|side |string |t(:row_comment_side)  |
|size |number |t(:row_comment_position_size)  |



### OrderBook(delta)

> t(:codequote_subscribe)

```javascript
  ws.send('{"op":"subscribe","id":"requestId","args":["delta.orderbook100.BTC-4MAR22-25000-P"]}');
```

> t(:codequote_snapshot)

```javascript

{
  "id":"delta.orderbook100.BTC-4MAR22-25000-P-65815768-1646214405074",
  "topic":"delta.orderbook100.BTC-4MAR22-25000-P",
  "creationTime":1646214405074,
  "data":{
  "version":"55",
    "dataType":"NEW",
    "orderBook":[
    {
      "price":"10",
      "size":"1.67",
      "side":"Buy"
    },
    {
      "price":"5",
      "size":"0.01",
      "side":"Buy"
    }
  ]
}
}
```


> t(:codequote_delta)

```javascript
{
  "id":"delta.orderbook100.BTC-4MAR22-25000-P-65815769-1646214587050",
    "topic":"delta.orderbook100.BTC-4MAR22-25000-P",
    "creationTime":1646214587050,
    "data":{
    "version":"56",
      "dataType":"CHANGE",
      "delete":[

    ],
      "update":[

    ],
      "insert":[
      {
        "price":"15",
        "size":"1",
        "side":"Buy"
      }
    ]
  }
}
```


t(:usdc_websocket_para_orderbook_100)

t(:usdcCommonDesc)


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| price |string |t(:row_comment_resp_price) |
|side |string |t(:row_comment_side)  |
|size |number |t(:row_comment_position_size)  |




### t(:bybitTradeHistory)
> t(:codequote_subscribe)

```javascript
  ws.send('{"op":"subscribe","id":"{1001}","args":["recenttrades.BTC"]}');
```


> t(:usdc_trade_codequote_snapshot)

```javascript

{
    "id":"recenttrades.BTC-118388-1636510323155",
    "topic":"recenttrades.BTC",
    "creationTime":1636510323155,
    "data":{
        "coin":"BTC",
        "trades":[
            {
                "symbol":"BTC-31DEC21-36000-P",
                "tradeId":"787bf079-b6a5-5bc0-a76d-59dad9036e7b",
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
| tradeId |string | t(:tradeId) |




### t(:latestSymbolInfo)
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","id":"{1001}","args":["instrument_info.BTC-19NOV21-58000-P"]}');
```

> t(:codequote_snapshot)

```javascript

{
    "id":"instrument_info.BTC-19NOV21-58000-P-98790-1636511446299",
    "topic":"instrument_info.BTC-19NOV21-58000-P",
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

ws.send('{"op":"subscribe","id":"{100002}","args":["user.openapi.option.position"]}');

```

> t(:codequote_snapshot)

```javascript
{
  "id":"85e87d06-09ed-4b05-9188-4e5a3f072c98",
    "topic":"user.openapi.option.position",
    "creationTime":1646192059408,
    "data":{
    "result":[
      {
        "symbol":"BTC-24JUN22-25000-P",
        "side":"Sell",
        "size":"-10.0000",
        "entryPrice":"5915.50000000",
        "sessionAvgPrice":"5915.50000000",
        "markPrice":"",
        "positionIM":"102764.97000000",
        "positionMM":"42404.80581340",
        "positionUPL":"",
        "sessionUPL":"50329.87108660",
        "sessionRPL":"30353.63366693",
        "createdAt":1644910387920,
        "updatedAt":1644910387920,
        "iv":"0.0000"
      }
    ],
      "version":1,
      "baseLine":3,
      "dataType":"NEW"
  }
}
```

> t(:codequote_delta)

```javascript

{
    "id":"1d055293-3836-4d56-baf2-8dec79d351f5",
    "topic":"user.openapi.option.position",
    "creationTime":1646213811719,
    "data":{
        "result":[
            {
                "symbol":"BTC-4MAR22-25000-P",
                "positionStatus":null,
                "side":"Buy",
                "size":"0.8",
                "entryPrice":"10",
                "sessionAvgPrice":"10",
                "markPrice":"0.00000364",
                "positionIM":"0",
                "positionMM":"0",
                "sessionUPL":"-7.999997088",
                "sessionRPL":"",
                "createdAt":1646213811544,
                "updatedAt":1646213811544
            }
        ],
        "version":6,
        "baseLine":2,
        "dataType":"CHANGE"
    }
}

```



t(:usdcPositionDesc)

t(:usdcCommonDesc)

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
ws.send('{"op":"subscribe","id":"{100002}","args":["user.option.tradeHistory"]}');
```

> t(:usdc_trade_codequote_snapshot)

```javascript

{
  "id":"985cf6de-2e7e-4d18-92ff-e7a2b4fcfcc1",
  "topic":"user.option.tradeHistory",
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
 ws.send('{"op":"subscribe","id":"{100003}","args":["user.openapi.option.order"]}');
```

> t(:codequote_snapshot)

```javascript

{
  "id":"d031f695-b546-49f6-8de3-8dac0f06ca14",
  "topic":"user.openapi.option.order",
  "creationTime":1646211968954,
  "data":{
  "result":[
    {
      "orderId":"5fcb8198-b22b-4116-8171-cf40539efbd7",
      "orderLinkId":"1000ss0004",
      "createdAt":1646209468927,
      "updatedAt":1646209468927,
      "symbol":"BTC-24JUN22-25000-P",
      "orderStatus":"New",
      "side":"Buy",
      "price":"100",
      "cashFlow":null,
      "realisedPnl":"",
      "qty":"1.0000",
      "cumExecQty":"0.0000",
      "leavesQty":"1.0000",
      "orderIM":"110",
      "orderType":"Limit",
      "reduceOnly":0,
      "timeInForce":"GoodTillCancel",
      "cumExecFee":"0.00000000",
      "iv":"0.5370",
      "orderPnl":"",
      "cumExecValue":"",
      "cancelType":"UNKNOWN"
    }
  ],
    "version":12,
    "baseLine":2,
    "dataType":"NEW"
}
}



```


> t(:codequote_delta)

```javascript


{
  "id":"620aeb31-b281-4736-9318-b9193c95ec33",
  "topic":"user.openapi.option.order",
  "creationTime":1646212354560,
  "data":{
  "result":[
    {
      "orderId":"41c44ec8-c8ca-40c5-b468-6fc252bfc081",
      "orderLinkId":"1000ss0005",
      "createdAt":1646212354483,
      "updatedAt":1646212354483,
      "symbol":"BTC-24JUN22-25000-P",
      "orderStatus":"New",
      "side":"Buy",
      "price":"100",
      "cashFlow":null,
      "realisedPnl":"",
      "qty":"1",
      "cumExecQty":"0",
      "leavesQty":"1",
      "orderIM":"110",
      "orderType":"Limit",
      "reduceOnly":0,
      "timeInForce":"GoodTillCancel",
      "cumExecFee":"0",
      "iv":"0.533",
      "orderPnl":"",
      "cumExecValue":"0",
      "cancelType":"UNKNOWN"
    }
  ],
    "version":13,
    "baseLine":2,
    "dataType":"CHANGE"
}
}

```


t(:usdcActiveOrder)
t(:usdcCommonDesc)

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
 ws.send('{"op":"subscribe","id":"{100003}","args":["user.option.orderHistory"]}');
```

> t(:usdc_trade_codequote_snapshot)

```javascript
{
  "id":"7e998370-42e2-45ac-ba5e-83f0b8ea2f13",
    "topic":"user.option.orderHistory",
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
ws.send('{"op":"subscribe","id":"{100003}","args":["user.option.greeks"]}');

```

> t(:codequote_snapshot)

```javascript

{
    "id":"37f1e862-5eaf-4cb5-a588-b369286cd805",
    "topic":"user.option.greeks",
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
