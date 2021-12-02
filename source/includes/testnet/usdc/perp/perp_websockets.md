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


t(:usdc_perp_websocket_para_endpoint)

<aside class="warning">
t(:websocket_best_practices)
</aside>


## t(:heartbeat)
> t(:websocket_codequote_heartbeat)

> public 
 
```javascript
ws.send("{\"op\":\"ping\"}");
```

> private

```javascript
ws.send("ping");
```

> t(:codequote_responseExample)

> public

```javascript
{"success":true,"ret_msg":"pong","conn_id":"84442344-7c63-4e25-be43-7edd345ca891","request":{"op":"ping","args":null}}
```

> private 

```javascript
{"pong": 1535975085152}
```


<aside class="warning">
t(:websocket_aside_heartbeat)
</aside>


<!-- 连接数限制
## t(:websocketlimit)
t(:websocket_para_limit)
-->


## t(:subscribe)
### t(:websocketfilters)
> t(:websocket_codequote_filters1)

t(:usdc_perp_websocket_subscribe_desc)

```javascript
// Subscribing to the trade data for BTCUSDT
```

### t(:websocketunfilters)

t(:usdc_perp_websocket_unsubscribe_desc)

## t(:websocketresponse)
> t(:websocket_codequote_response)

```javascript

```

t(:spot_websocket_para_response)

## Public Topics
### OrderBook

> t(:codequote_subscribe)

```javascript
  ws.send('{"op": "subscribe", "args": ["orderBook_200.100ms.BTCPERP"]}');
```

> t(:codequote_snapshot)

```javascript

{
  "topic":"orderBookL2_25.BTCPERP",
  "type":"snapshot",
  "data":{
  "orderBook":[
    {
      "price":"56347.50",
      "symbol":"BTCPERP",
      "id":"563475000",
      "side":"Buy",
      "size":4.512
    },
    {
      "price":"56805.50",
      "symbol":"BTCPERP",
      "id":"568055000",
      "side":"Sell",
      "size":1.035
    }
  ]
},
  "crossSeq":"122458406",
  "timestampE6":"1638426051379488"
}

```

> t(:codequote_delta)

```javascript
{
    "topic":"orderBookL2_25.BTCPERP",
    "type":"delta",
    "data":{
        "delete":[
            {
                "price":"56810.00",
                "symbol":"BTCPERP",
                "id":"568100000",
                "side":"Sell"
            }
        ],
        "update":[
            {
                "price":"56758.50",
                "symbol":"BTCPERP",
                "id":"567585000",
                "side":"Buy",
                "size":2.429
            }
        ],
        "insert":[
            {
                "price":"56347.00",
                "symbol":"BTCPERP",
                "id":"563470000",
                "side":"Buy",
                "size":0.485
            }
        ]
    },
    "crossSeq":"122458433",
    "timestampE6":"1638426051822077"
}
```

t(:usdc_perp_websocket_para_orderbook)


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
  ws.send('{"op": "subscribe", "args": ["trade.BTCPERP"]}');
```


> t(:usdc_trade_codequote_snapshot)

```javascript

{
  "topic":"trade.BTCPERP",
  "data":[
  {
    "symbol":"BTCPERP",
    "tickDirection":"MinusTick",
    "price":"56689.00",
    "size":0.15,
    "timestamp":"2021-12-02T06:37:25.000Z",
    "tradeTimeMs":"1638427045643",
    "side":"Sell",
    "tradeId":"bac9d230-e553-59c4-a22e-ca2dcca1467e"
  }
]
}

```


t(:usdc_current_24_total_perp)

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
ws.send('{"op": "subscribe", "args": ["instrument_info.100ms.BTCPERP"]}');
```

> t(:codequote_snapshot)

```javascript

{
  "topic":"instrument_info.100ms.BTCPERP",
  "type":"snapshot",
  "data":{
  "id":1,
    "symbol":"BTCPERP",
    "lastPriceE4":"566055000",
    "lastPrice":"56605.50",
    "lastTickDirection":"PlusTick",
    "prevPrice24hE4":"570275000",
    "prevPrice24h":"57027.50",
    "price24hPcntE6":"-7399",
    "highPrice24hE4":"592375000",
    "highPrice24h":"59237.50",
    "lowPrice24hE4":"556675000",
    "lowPrice24h":"55667.50",
    "prevPrice1hE4":"569910000",
    "prevPrice1h":"56991.00",
    "price1hPcntE6":"-6764",
    "markPriceE4":"565270100",
    "markPrice":"56527.01",
    "indexPriceE4":"565262500",
    "indexPrice":"56526.25",
    "openInterestE8":"58513199999",
    "totalTurnoverE8":"663673580321250000",
    "turnover24hE8":"38217656797550020",
    "totalVolumeE8":"11089424900000",
    "volume24hE8":"665962700000",
    "fundingRateE6":"100",
    "predictedFundingRateE6":"100",
    "crossSeq":"122534036",
    "createdAt":"1970-01-01T00:00:00.000Z",
    "updatedAt":"2021-12-02T06:43:16.000Z",
    "nextFundingTime":"2021-12-02T08:00:00Z",
    "countDownHour":"2",
    "bid1PriceE4":"565635000",
    "bid1Price":"56563.50",
    "ask1PriceE4":"566055000",
    "ask1Price":"56605.50"
},
  "crossSeq":"122534100",
  "timestampE6":"1638427403846982"
}

```

> t(:codequote_delta)

```javascript

{
    "topic":"instrument_info.100ms.BTCPERP",
    "type":"delta",
    "data":{
        "update":[
            {
                "id":1,
                "symbol":"BTCPERP",
                "markPriceE4":"567607800",
                "markPrice":"56760.78",
                "indexPriceE4":"567615500",
                "indexPrice":"56761.55",
                "crossSeq":"122596005",
                "createdAt":"1970-01-01T00:00:00.000Z",
                "updatedAt":"2021-12-02T07:10:41.000Z"
            }
        ]
    },
    "crossSeq":"122596143",
    "timestampE6":"1638429048145806"
}

```

t(:usdc_perp_lastest_symbol_info)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|symbol|string |t(:row_comment_symbol)    |
|t(:row_parameter_tick_direction) |string |t(:row_comment_position_tick_direction)  |
|lastPrice |integer |t(:row_comment_resp_last_price)  |
|prevPrice24h |integer |t(:row_comment_resp_prev_price_24h)  |
|highPrice24h |integer |t(:row_comment_resp_high_price_24h)  |
|lowPrice24h |integer |t(:row_comment_resp_low_price_24h)  |
|prevPrice1h |integer |t(:row_comment_resp_prev_price_1h)  |
|markPrice |integer |t(:row_comment_resp_mark_price)  |
|indexPrice |integer |t(:row_comment_resp_index_price)  |
|openInterestE8|integer |t(:row_comment_resp_open_interest_e8). t(:row_comment_slow_update)  |
|totalTurnoverE8 |integer |t(:row_comment_resp_total_turnover_e8)  |
|turnover24hE8 |integer |t(:row_comment_resp_turnover_24h_e8)  |
|totalVolumeE8 |integer |t(:row_comment_resp_total_volume_e8)  |
|volume24hE8 |integer |t(:row_comment_resp_volume_24h_e8)  |
|fundingRateE6 |integer |t(:row_comment_resp_funding_rate_e6)  |
|predictedFundingRateE6 |integer |t(:row_comment_resp_predicted_funding_rate_e6)  |
|crossSeq |integer |t(:row_comment_cross_seq)  |
|createdAt |string |t(:row_comment_created_at)  |
|updatedAt |string |t(:row_comment_updated_at)  |
|nextFundingTime |string |t(:row_comment_resp_next_funding_time)  |
|countDownHour |number |t(:row_comment_resp_countdown_hour)  |
|bid1Price |integer|t(:row_comment_bid1_price)  |
|ask1Price |integer|t(:row_comment_ask1_price)  |


### KLine
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","args":["candle.1.BTCPERP"]}')

```

> t(:codequote_responseExampleFormatAll)

```javascript

{
    "topic":"candle.1.BTCPERP",
    "data":[
        {
            "start":1638429120,
            "end":1638429180,
            "period":"1",
            "open":56823.5,
            "close":56806,
            "high":56855.5,
            "low":56791,
            "volume":2.817,
            "turnover":160070.652,
            "confirm":false,
            "crossSeq":122599728,
            "timestamp":1638429160388749
        }
    ],
    "timestampE6":1638429160388752
}

```


t(:websocket_para_klineV2)

<aside class="notice">
t(:websocket_aside_klineV2)
</aside>

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



## Private Topics
### t(:userPositionsInfo)
> t(:codequote_subscribe)

```javascript

ws.send('{"method":"private/subscribe","id":"{100002}","params":{"channels":["user.perp.position"]}}');

```

> t(:usdc_trade_codequote_snapshot)

```javascript

{
  "id":"eeda6da2-ed9d-43f1-bfe8-8564017f0a63",
  "channel":"user.perp.position",
  "type":"SNAPSHOT",
  "serialNumber":1,
  "publishTime":221947838,
  "creationTime":1638429615221,
  "data":{
  "result":[
    {
      "userId":247007,
      "coin":"USDC",
      "symbolId":45,
      "positionIdx":0,
      "mode":"MergedSingle",
      "riskId":"10001",
      "leverageE2":1000,
      "positionStatus":"NORMAL",
      "adlRankIndicator":0,
      "side":"Buy",
      "size":"1.15000000",
      "value":"67979.27000000",
      "entryPrice":"59112.40860000",
      "markPrice":"56918.04",
      "unrealisedPnl":"",
      "occClosingFee":"0.00000000",
      "occFundingFee":"0.00000000",
      "liqPrice":"0.00000000",
      "bustPrice":"0.00000000",
      "bv2cE8":10142500,
      "sv2cE8":10157500,
      "cumRealisedPnl":"",
      "tpTriggerBy":"UNKNOWN",
      "slTriggerBy":"UNKNOWN",
      "takeProfit":"0.00000000",
      "stopLoss":"0.00000000",
      "trailingStop":"0.00000000",
      "activationPrice":"0.00000000",
      "tpSlMode":"UNKNOWN",
      "updatedAtE3":1638341866990,
      "tpOrderNum":0,
      "slOrderNum":0,
      "tpFreeSize":"",
      "slFreeSize":"",
      "sessionAvgPrice":"57238.06000000",
      "sessionUpl":"-368.023",
      "sessionRpl":"0",
      "positionIm":"6843.81299617575",
      "positionMm":"385.78235662575",
      "accountId":289037,
      "symbol":"BTCPERP",
      "freeCost":"-41.88852500",
      "freeQty":"-1.15000000"
    }
  ],
    "version":473374,
    "sendTime":1638429615131
}
}

```


t(:usdc_perp_position_desc)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| riskId|number |t(:riskId) |
| symbol |string |t(:usdcSymbol) |
| side |string |t(:side) |
| size |string |t(:usdcSize) |
| entryPrice |string |t(:entryPrice) |
| markPrice |string |t(:markPrice) |
| sessionUpl |string |t(:sessionUpl) |
| positionIm |string |t(:im) |
| positionMm |string |t(:usdcMm) |
| tpSlMode |string |t(:tpSlMode) |
| value |string |t(:positionValue) |
| leverageE2 |number |t(:leverage) |
| liqPrice |string |t(:liqPrice) |
| trailingStop |number |t(:trailingStop) |
| bustPrice |string |t(:bustPrice) |
| occClosingFee |string |t(:occClosingFee) |
| takeProfit |string |t(:trakeProfit) |
| stopLoss |string |t(:stopLoss) |
| positionStatus |string |t(:positionStatus) |
| deleverageIndicator |number |t(:deleverageIndicator) |
| unrealisedPnl |string |t(:unrealisedPnl) |
| cumRealisedPnl |string |t(:cumRealisedPnl) |


### t(:userFilledHistory)
> t(:codequote_subscribe)

```javascript
ws.send('{"method":"private/subscribe","id":"{100002}","params":{"channels":["user.perp.trade"]}}');
```

> t(:usdc_trade_codequote_snapshot)

```javascript

{
  "id":"03c9ef6a-a96e-452a-bace-ec760edeff32",
  "channel":"user.perp.trade",
  "type":"SNAPSHOT",
  "serialNumber":1,
  "publishTime":266836178,
  "creationTime":1638433627266,
  "data":{
  "result":[
    {
      "execValue":null,
      "symbolId":null,
      "symbol":"BTCPERP",
      "symbolName":"BTCPERP",
      "orderLinkId":null,
      "orderId":"05b0647e-d7e9-4edc-9f9c-54a3b22d3675",
      "side":"Sell",
      "orderType":"Limit",
      "reduceOnly":false,
      "price":"54294",
      "qty":"0.01",
      "leavesQty":null,
      "execTimeE3":1638433627189,
      "execType":"Trade",
      "execId":"4f45d7e5-0fd2-5812-8a3f-0aff67b08858",
      "execPrice":"57104.5",
      "execQty":"0.01",
      "feeRate":"0.00075",
      "execFee":"0.42828375",
      "version":null,
      "sendTime":null,
      "crossSeq":null,
      "maker":false
    }
  ],
    "version":9833,
    "sendTime":1638433627245
}
}

```


t(:usdc_perp_trade_history)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| execTimeE3|number |t(:tradeTime) |
| orderId |string | t(:usdcOrderId) |
| orderLinkId |string |t(:orderLinkId) |
| symbol |string |t(:usdcSymbol) |
| price |string |t(:excPrice) |
| qty |string |t(:execQty) |
| execFee |string |t(:execFee) |
| feeRate |string |t(:feeRate) |
| execType |string |t(:execType) |
| execValue |string |t(:execValue) |
| execId |string |trade Id|


### t(:activeOrders)

> t(:codequote_subscribe)

```javascript
 ws.send('{"method":"private/subscribe","id":"{100003}","params":{"channels":["user.perp.order"]}}');
```

> t(:usdc_trade_codequote_snapshot)

```javascript

{
  "id":"ba153ca0-28d2-4288-929c-7f6ca1789ace",
  "channel":"user.perp.order",
  "type":"SNAPSHOT",
  "serialNumber":1,
  "publishTime":172236766,
  "creationTime":1638435407172,
  "data":{
  "result":[
    {
      "accountId":0,
      "userId":247007,
      "symbol":"BTCPERP",
      "createType":null,
      "cancelType":"UNKNOWN",
      "orderLinkId":"",
      "tpTriggerBy":null,
      "slTriggerBy":null,
      "takeProfit":"0.00000000",
      "stopLoss":"0.00000000",
      "orderId":"c85955ab-36c9-40cd-a86d-e95f330d8ea2",
      "side":"Buy",
      "orderType":"Limit",
      "timeInForce":"GoodTillCancel",
      "reduceOnly":false,
      "stopOrderType":"UNKNOWN",
      "triggerBy":"UNKNOWN",
      "basePrice":"41300.00000000",
      "trailValue":"0.00000000",
      "triggerPrice":"0.00000000",
      "price":"41300.00000000",
      "orderAvgPrice":"0.00000000",
      "qty":"0.0100",
      "leavesQty":"0.0100",
      "cumQty":"0.0000",
      "cumValue":"0.00000000",
      "cumExecFee":"0.00000000",
      "orderStatus":"New",
      "cxlRejReason":"EC_NoError",
      "createdAtE3":1638432605741,
      "updatedAtE3":1638432605744,
      "origTriggerPrice":"",
      "origPrice":"",
      "origQty":"",
      "origOrderType":null,
      "isWorking":true,
      "type":"UNKNOWN",
      "avgPrice":"0.00000000",
      "pnl":"",
      "orderIm":"41.888525",
      "symbolId":0,
      "expectedDirection":"UNKNOWN",
      "closeOnTrigger":false
    }
  ],
    "version":487192,
    "sendTime":1638435407124
}
}


```

t(:usdc_perp_active_order)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| orderId |string |t(:usdcOrderId) |
| orderLinkId |string |t(:orderLinkId) |
| symbol |string |t(:usdcSymbol) |
| orderType|string |t(:usdc_perp_order_type) |
| side |string |t(:side) |
| qty |string |t(:orderAllSize) |
| leavesQty |string |t(:orderFilledSize) |
| price |string |t(:usdcOrderPrice) |
| t(:row_parameter_timeInForce) |string |t(:row_comment_timeInForce) |
| cumQty |string |t(:cumExecQty) |
| cumExecFee |string |t(:cumExecFee) |
| orderIm |string |t(:im) |
| orderStatus |string |t(:orderStatus) |
| reduceOnly |number |t(:reduceOnly) |
| closeOnTrigger |bool |t(:closeOnTrigger) |
| takeProfit |string |t(:takeProfit) |
| stopLoss |string |t(:stopLoss) |
| tpTriggerBy |string |t(:tptriggerby) |
| slTriggerBy |string |t(:slTriggerBy) |
| basePrice |string |t(:basePrice) |
| triggerPrice |string |t(:triggerPrice) |
| triggerBy |string |t(:triggerBy) |


### t(:userOrderHistory)
> t(:codequote_subscribe)

```javascript
 ws.send('{"method":"private/subscribe","id":"{100003}","params":{"channels":["user.perp.orderHistory"]}}');
```

> t(:usdc_trade_codequote_snapshot)

```javascript
{
  "id":"b33395cd-8279-4e35-8a88-0fb7ca250a8f",
    "channel":"user.perp.orderHistory",
    "type":"SNAPSHOT",
    "serialNumber":1,
    "publishTime":378404740,
    "creationTime":1638436244378,
    "data":{
    "result":[
      {
        "accountId":0,
        "userId":247007,
        "symbol":"BTCPERP",
        "createType":null,
        "cancelType":"UNKNOWN",
        "orderLinkId":"",
        "tpTriggerBy":null,
        "slTriggerBy":null,
        "takeProfit":"0",
        "stopLoss":"0",
        "orderId":"2fe9ed0c-f0cf-4cf2-8ac9-de28b6021fe6",
        "side":"Sell",
        "orderType":"Limit",
        "timeInForce":"GoodTillCancel",
        "reduceOnly":false,
        "stopOrderType":"UNKNOWN",
        "triggerBy":"UNKNOWN",
        "basePrice":"",
        "trailValue":"0",
        "triggerPrice":"0",
        "price":"54204.5",
        "orderAvgPrice":"57055",
        "qty":"0.01",
        "leavesQty":"0",
        "cumQty":"0.01000000",
        "cumValue":"570.55",
        "cumExecFee":"0.4279125",
        "orderStatus":"Filled",
        "cxlRejReason":"EC_NoError",
        "createdAtE3":1638436244299,
        "updatedAtE3":1638436244302,
        "origTriggerPrice":"0",
        "origPrice":"0",
        "origQty":"0",
        "origOrderType":null,
        "isWorking":true,
        "type":"Limit",
        "avgPrice":"57055",
        "pnl":"",
        "orderIm":"0",
        "symbolId":0,
        "expectedDirection":"UNKNOWN",
        "closeOnTrigger":false
      }
    ],
      "version":489367,
      "sendTime":1638436244319
  }
}
```

t(:usdc_perp_order_desc)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| orderId |string |t(:usdcOrderId) |
| orderLinkId |string |t(:orderLinkId) |
| symbol |string |t(:usdcSymbol) |
| orderType|string |t(:usdc_perp_order_type) |
| side |string |t(:side) |
| qty |string |t(:orderAllSize) |
| leavesQty |string |t(:orderFilledSize) |
| price |string |t(:usdcOrderPrice) |
| t(:row_parameter_timeInForce) |string |t(:row_comment_timeInForce) |
| cumQty |string |t(:cumExecQty) |
| cumExecFee |string |t(:cumExecFee) |
| orderIm |string |t(:im) |
| orderStatus |string |t(:orderStatus) |
| reduceOnly |number |t(:reduceOnly) |
| closeOnTrigger |bool |t(:closeOnTrigger) |
| takeProfit |string |t(:takeProfit) |
| stopLoss |string |t(:stopLoss) |
| tpTriggerBy |string |t(:tptriggerby) |
| slTriggerBy |string |t(:slTriggerBy) |
| basePrice |string |t(:basePrice) |
| triggerPrice |string |t(:triggerPrice) |
| triggerBy |string |t(:triggerBy) |

