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
    api_key = 'XXXXXXXXXXXXXXX'
    secret = 'XXXXXXXXXXXXXXX'
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
        "args": ["user.openapi.perp.order", "user.openapi.perp.position", "user.openapi.perp.trade"]
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


t(:usdc_perp_websocket_para_endpoint)

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
|price |string |t(:row_comment_resp_price) |
|symbol |string |t(:usdcSymbol)    |
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
| tradeId |string |t(:tradeId) |




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

ws.send(json.dumps({"op": "subscribe", "id": "{100003}","args": ["user.openapi.perp.position"]});
```

> t(:usdc_trade_codequote_snapshot)

```javascript
{
    "id":"7b8fdb38-1cfa-40f6-8010-f2ab3eb33df4",
    "topic":"user.openapi.perp.position",
    "creationTime":1646200751865,
    "data":{
        "result":[

        ],
        "version":1,
        "baseLine":1,
        "dataType":"NEW"
    }
}
```

> t(:codequote_delta)

```javascript
{
    "id":"9cf9e9a8-2f19-4252-a2b6-1fd733a8bee2",
    "topic":"user.openapi.perp.position",
    "creationTime":1646200779801,
    "data":{
        "result":[
            {
                "symbol":"BTCPERP",
                "positionStatus":"NORMAL",
                "side":"Buy",
                "size":"0.001",
                "entryPrice":"44277",
                "sessionAvgPrice":"44277",
                "markPrice":"44285.75",
                "positionIM":"4.457586975",
                "positionMM":"0.251271975",
                "positionValue":"44.277",
                "liqPrice":"",
                "bustPrice":"",
                "occClosingFee":"",
                "unrealisedPnl":"0.0000",
                "cumRealisedPnl":"0.0000",
                "sessionUPL":"0.00875",
                "sessionRPL":"0",
                "createdAt":1646200779751,
                "updatedAt":1646200779751,
                "tpSLMode":"UNKNOWN",
                "leverage":1000,
                "trailingStop":"",
                "takeProfit":"0",
                "stopLoss":"0",
                "deleverageIndicator":0,
                "riskId":"10001"
            }
        ],
        "version":2,
        "baseLine":1,
        "dataType":"CHANGE"
    }
}
```


t(:usdc_perp_position_desc)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol |string |t(:usdcSymbol) |
| positionStatus |string |t(:usdcPositionStatus) |
| side |string |t(:side) |
| size |string |t(:usdcSize) |
| entryPrice |string |t(:entryPrice) |
| sessionAvgPrice |string |t(:perpSessionAvgPrice) |
| markPrice |string |t(:usdcMarkPrice) |
| positionIM |string |t(:im) |
| positionMM |string |t(:usdcMm) |
| positionValue |string |t(:positionValue) |
| liqPrice |string |t(:liqPrice) |
| bustPrice |string |t(:bustPrice) |
| occClosingFee |string |t(:occClosingFee) |
| unrealisedPnl |string |t(:unrealisedPnl) |
| cumRealisedPnl |string |t(:cumRealisedPnl) |
| sessionUPL |string |t(:sessionUpl) |
| createdAt |string |t(:row_comment_created_at) |
| updatedAt |string |t(:row_comment_updated_at) |
| tpSlMode |string |t(:tpSlMode) |
| leverage |string |t(:usdcLeverage) |
| trailingStop |number |t(:trailingStop) |
| takeProfit |string |t(:trakeProfit) |
| stopLoss |string |t(:stopLoss) |
| positionStatus |string |t(:positionStatus) |
| deleverageIndicator |string |t(:deleverageIndicator) |
| riskId |string |t(:riskId) |


### t(:userFilledHistory)
> t(:codequote_subscribe)

```javascript
ws.send(json.dumps({"op": "subscribe", "id": "{100003}","args": ["user.openapi.perp.trade"]}))
```

> t(:usdc_trade_codequote_snapshot)

```javascript
{
    "id":"6ffe5750-d3b6-4de8-b63a-736a59aa8278",
    "topic":"user.openapi.perp.trade",
    "creationTime":1646200779785,
    "data":{
        "result":[
            {
                "orderId":"2a44a4de-8244-4be9-b343-52bdfe135c9e",
                "orderLinkId":"",
                "tradeId":"9ae8aad2-0dae-583f-bff1-89aef6f88cd2",
                "symbol":"BTCPERP",
                "execPrice":"44277",
                "execQty":"0.001",
                "execFee":"0.03320775",
                "feeRate":"0.00075",
                "tradeTime":1646200779736,
                "lastLiquidityInd":"TAKER",
                "execValue":"44.277",
                "execType":"TRADE"
            }
        ],
        "version":1,
        "baseLine":1
    }
}
```


t(:usdc_perp_trade_history)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| orderId |string | t(:usdcOrderId) |
| orderLinkId |string |t(:orderLinkId) |
| tradeId |string |t(:tradeId)|
| symbol |string |t(:usdcSymbol) |
| execPrice |string |t(:excPrice) |
| execQty |string |t(:execQty) |
| execFee |string |t(:execFee) |
| feeRate |string |t(:feeRate) |
| tradeTime |number |t(:tradeTime) |
| lastLiquidityInd |string |t(:lastLiquidityInd) |
| execValue |string |t(:usdcExecValue)
| execType |string |t(:execType) |



### t(:usdc_perp_active_orders_snapshot)

> t(:codequote_subscribe)

```javascript
ws.send(json.dumps({"op": "subscribe", "id": "{100003}","args": ["user.openapi.perp.order"]}))
```

> t(:usdc_trade_codequote_snapshot)

```javascript
{
    "id":"c044cbae-8331-4a2e-93c9-5114ab4815cf",
    "topic":"user.openapi.perp.order",
    "creationTime":1646200751861,
    "data":{
        "result":[

        ],
        "version":1,
        "baseLine":1,
        "dataType":"NEW"
    }
}
```

> t(:codequote_delta)

```javascript
{
    "id":"aa89ef9f-e77a-4ccd-a35c-b62e2c03c8e0",
    "topic":"user.openapi.perp.order",
    "creationTime":1646200779822,
    "data":{
        "result":[
            {
                "orderId":"2a44a4de-8244-4be9-b343-52bdfe135c9e",
                "orderLinkId":"",
                "createdAt":1646200779733,
                "updatedAt":1646200779736,
                "symbol":"BTCPERP",
                "orderStatus":"Filled",
                "side":"Buy",
                "price":"44283.5",
                "qty":"0.001",
                "cumExecQty":"0.001",
                "leavesQty":"0",
                "orderIM":"0",
                "realisedPnl":"None",
                "orderType":"Limit",
                "reduceOnly":0,
                "timeInForce":"GoodTillCancel",
                "cumExecFee":"0.03320775",
                "orderPnl":"",
                "basePrice":"",
                "cumExecValue":"44.277",
                "closeOnTrigger":"false",
                "triggerBy":"UNKNOWN",
                "takeProfit":"0",
                "stopLoss":"0",
                "tpTriggerBy":"UNKNOWN",
                "slTriggerBy":"UNKNOWN",
                "triggerPrice":"0",
                "stopOrderType":"UNKNOWN",
                "cancelType":"UNKNOWN"
            }
        ],
        "version":2,
        "baseLine":1,
        "dataType":"CHANGE"
    }
}
```

t(:usdc_perp_active_order)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| orderId |string |t(:usdcOrderId) |
| orderLinkId |string |t(:orderLinkId) |
| createdAt |string |t(:row_comment_created_at) |
| updatedAt |string |t(:row_comment_updated_at) |
| symbol |string |t(:usdcSymbol) |
| orderStatus |string |t(:orderStatus) |
| side |string |t(:side) |
| price |string |t(:usdcOrderPrice) |
| qty |string |t(:orderAllSize) |
| cumExecQty |string |t(:cumExecQty) |
| leavesQty |string |t(:usdc_unfilled_order_size) |
| orderIm |string |t(:im) |
| realisedPnl |string |t(:realisedPnl) |
| orderType|string |t(:usdc_perp_order_type) |
| reduceOnly |number |t(:reduceOnly) |
| t(:row_parameter_timeInForce) |string |t(:row_comment_timeInForce) |
| cumExecFee |string |t(:cumExecFee) |
| orderPnl |string |t(:usdcOrderPnl) |
| basePrice |string |t(:basePrice) |
| cumExecValue |string |t(:cumExecValue) |
| closeOnTrigger |bool |t(:closeOnTrigger) |
| triggerBy |string |t(:triggerBy) |
| takeProfit |string |t(:takeProfit) |
| stopLoss |string |t(:stopLoss) |
| tpTriggerBy |string |t(:tptriggerby) |
| slTriggerBy |string |t(:slTriggerBy) |
| triggerPrice |string |t(:triggerPrice) |
| stopOrderType |string |t(:usdcStopOrderType) |
| cancelType |string |t(:usdcCancelType) |
