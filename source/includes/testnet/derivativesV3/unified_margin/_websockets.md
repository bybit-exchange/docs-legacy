# t(:websocket)
## t(:websocketauthentication)
> t(:websocket_codequote_auth)

> t(:websocket_codequote_auth1)

```python--pybit
# based on: https://github.com/bybit-exchange/pybit/blob/master/pybit/_http_manager.py

import hmac
import json
import time
import websocket

ws_url = "wss://stream.bybit.com/realtime"

api_key = ""
api_secret = ""

# Generate expires.
expires = int((time.time() + 1) * 1000)

# Generate signature.
signature = str(hmac.new(
    bytes(api_secret, "utf-8"),
    bytes(f"GET/realtime{expires}", "utf-8"), digestmod="sha256"
).hexdigest())

param = "api_key={api_key}&expires={expires}&signature={signature}".format(
    api_key=api_key,
    expires=expires,
    signature=signature
)

url = ws_url + "?" + param

ws = websocket.WebSocketApp(
    url=url,
    ...
)
```

> t(:websocket_codequote_auth2)

```python--pybit
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

<aside class="notice">
t(:websocket_endpoints_aside)
</aside>

t(:websocket_para_endpoint)

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
ws.send('{"op":"ping"}');
```

> t(:codequote_responseExample)

```javascript
{
    "success": true, // Whether ping is successful
    "ret_msg": "pong",
    "conn_id": "036e5d21-804c-4447-a92d-b65a44d00700",// current connection id
    "request": {
        "op": "ping",
        "args": null
    }
}
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

```javascript
// Subscribing to the trade data for BTCUSD
ws.send('{"op":"subscribe","args":["trade.BTCUSD"]}')
```

> t(:websocket_codequote_filters2)

```javascript
// Example: Subscribing to the trade data for BTCUSD and XRPUSD
ws.send('{"op":"subscribe","args":["trade.BTCUSD|XRPUSD"]}')
```


t(:websocket_para_filters)

`ws.send('{"op": "subscribe", "args": ["topic.filter"]}');`

t(:websocket_para_filters1)

`ws.send('{"op": "subscribe", "args": ["topic.filter", "topic.filter"]}');`

t(:websocket_para_filters3)

### t(:websocketfilters_unified)

### t(:websocketunsubfilters)
> t(:websocket_codequote_unsubfilters)

```javascript
// Unsubscribing from the trade data for ETHUSD
ws.send('{"op":"unsubscribe","args":["trade.ETHUSD"]}')
```

t(:websocket_para_unsubfilters)

`ws.send('{"op": "unsubscribe", "args": ["topic.filter", "topic.filter"]}');`

### t(:websocketunsubfilters_unified)

### t(:intervals)
t(:websocket_para_intervals)

## t(:websocketresponse)
> t(:websocket_codequote_response)

```javascript
{
   "success": true, // Whether subscription is successful
   "ret_msg": "",   // Successful subscription: "", otherwise it shows error message
   "conn_id":"e0e10eee-4eff-4d21-881e-a0c55c25e2da",// current connection id
   "request": {     // Request to your subscription
       "op": "subscribe",
       "args": [
           "kline.BTCUSD.1m"
       ]
   }
}
```

t(:websocket_para_response)



## t(:publictopics)
### t(:websocketOrderBookDepth)

> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["orderBook25.BTCUSDT",orderBook500.BTCUSDT]}')
```
> t(:codequote_snapshot)

```javascript
{
  "topic":"orderBook25.BTCUSDT",
    "type":"snapshot",
    "ts":1658200820646,
    "data":{
    "s":"BTCUSDT",
      "b":[
      [
        "22220.00",
        "1.300"
      ],
      [
        "22221.00",
        "1.150"
      ]
    ],
      "a":[
      [
        "22236.00",
        "18.194"
      ],
      [
        "22236.50",
        "0.602"
      ]
    ],
      "u":3566050
  }
}
```


> t(:codequote_delta)

```javascript
{
  "topic":"orderBook25.BTCUSDT",
    "type":"delta",
    "ts":1658200820655,
    "data":{
    "s":"BTCUSDT",
      "b":[
      [
        "22224.00",
        "0.001"
      ]
    ],
      "a":[
      [
        "22247.00",
        "1.406"
      ],
      [
        "22240.50",
        "9.046"
      ],
      [
        "22236.00",
        "18.195"
      ],
      [
        "22244.50",
        "0.397"
      ]
    ],
      "u":3566051
  }
}
```

- orderBook25.[symbol]
  - t(:market_para_orderbook)
  - [Push frequency]:20ms

<br>

- orderBook500.[symbol] <br>
  - t(:market_para_orderbook_500)
  - [Push frequency]:100ms

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|s |string |t(:row_comment_symbol)  |
|b|string array |t(:row_comment_resp_bid)    |
|a |string array|t(:row_comment_resp_ask)  |
|u |number |t(:row_comment_updated_id)  |



### t(:websockettrade)

> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["trade.BTCUSDT"]}')
```

```python--old
from BybitWebsocket import BybitWebsocket
ws = BybitWebsocket(wsURL="wss://stream-testnet.bybit.com/realtime",
                    api_key=None, api_secret=None)
ws.subscribe_trade()
while True:
    data = ws.get_data("trade.BTCUSD")
    if data:
        print(data)
```

```python--pybit
from pybit import WebSocket
subs = [
    "trade"
]
ws = WebSocket(
    "wss://stream-testnet.bybit.com/realtime",
    subscriptions=subs
)
while True:
    data = ws.fetch(subs[0])
    if data:
        print(data)
```

> t(:codequote_responseExampleFormatAll)


```javascript
{
  "topic":"trade.BTCUSDT",
    "type":"snapshot",
    "ts":1658143402593,
    "data":[
    {
      "T":1658143402590,
      "s":"BTCUSDT",
      "S":"Buy",
      "v":"0.001",
      "p":"23337.00",
      "L":"PlusTick",
      "i":"83010f18-4476-55c0-84ab-ebd243e156cf"
    }
  ]
}
```

t(:websocket_para_trade_ud)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|T |number |t(:row_response_comment_timestamp)  |
|s |string |t(:row_comment_symbol)  |
|S|string |t(:websocketTradeSide)    |
|v |string |t(:row_comment_position_size)  |
|p |string |t(:row_response_comment_price)  |
|L |string |t(:row_comment_position_tick_direction)  |
|i|string |t(:row_response_comment_trade_id)  |
|ts|string |t(:row_response_comment_time)  |
|BT|bool |t(:row_response_comment_blocktrade)  |

### t(:websocketinstrumentInfo)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["instrument_info.BTCUSDT"]}')
```

```python--old
from BybitWebsocket import BybitWebsocket
ws = BybitWebsocket(wsURL="wss://stream-testnet.bybit.com/realtime",
                    api_key=None, api_secret=None)
ws.subscribe_instrument_info(symbol="BTCUSD")
while True:
    data = ws.get_data("instrument_info.BTCUSDT")
    if data:
        print(data)
```

```python--pybit
from pybit import WebSocket
subs = [
    "instrument_info.100ms.BTCUSD"
]
ws = WebSocket(
    "wss://stream-testnet.bybit.com/realtime",
    subscriptions=subs
)
while True:
    data = ws.fetch(subs[0])
    if data:
        print(data)
```

> t(:codequote_snapshot)

```javascript
{
  "topic":"instrumentInfo.BTCUSDT",
    "type":"snapshot",
    "data":{
    "symbol":"BTCUSDT",
      "tickDirection":"ZeroMinusTick",
      "price24hPcnt":"0.032786",
      "lastPrice":"22019.00",
      "prevPrice24h":"21320.00",
      "highPrice24h":"22522.00",
      "lowPrice24h":"20745.00",
      "prevPrice1h":"22186.50",
      "markPrice":"22010.11",
      "indexPrice":"22009.01",
      "openInterest":"44334.438",
      "turnover24h":"4609010554.786498",
      "volume24h":"213532.606",
      "fundingRate":"0.0001",
      "nextFundingTime":"2022-07-18T16:00:00Z",
      "bid1Price":"22019.00",
      "bid1Size":"41.530",
      "ask1Price":"22019.50",
      "ask1Size":"7.041",
      "basisRate":"0",
      "deliveryFeeRate":"0"
  },
  "cs":14236992078,
    "ts":1658145103785070
}
```

> t(:codequote_delta)

```javascript
{
  "topic":"instrumentInfo.BTCUSDT",
    "type":"delta",
    "data":{
    "symbol":"BTCUSDT",
      "tickDirection":"PlusTick",
      "price24hPcnt":"0.032621",
      "lastPrice":"22015.50",
      "turnover24h":"4609049418.106998",
      "volume24h":"213534.371",
      "fundingRate":"0.0001",
      "nextFundingTime":"2022-07-18T16:00:00Z",
      "bid1Price":"22019.00",
      "bid1Size":"41.530",
      "ask1Price":"22019.50",
      "ask1Size":"7.041"
  },
  "cs":14236992274, 
    "ts":1658145103883091
}

```

t(:websocket_para_instrumentInfo)

<aside class="warning">
t(:websocket_aside_instrumentInfo_ud)
</aside>


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|symbol |string |t(:row_comment_symbol)  |
|tickDirection|string |t(:row_comment_position_tick_direction)  |
|price24hPcnt|string|t(:row_comment_resp_price_24h_pcnt) |
|lastPrice |string |t(:row_comment_resp_last_price)  |
|prevPrice24h |string |t(:row_comment_resp_prev_price_24h)  |
|highPrice24h |string |t(:row_comment_resp_high_price_24h)  |
|lowPrice24h |string |t(:row_comment_resp_low_price_24h)  |
|prevPrice1h |string |t(:row_comment_resp_prev_price_1h)  |
|markPrice |string |t(:row_comment_resp_mark_price)  |
|indexPrice |string |t(:row_comment_resp_index_price)  |
|openInterest |string |t(:row_comment_resp_open_interest). t(:row_comment_slow_update)  |
|turnover24h |string |t(:row_comment_resp_turnover_24h)  |
|volume_24h |string |t(:row_comment_resp_volume_24h)  |
|fundingRate |string |t(:row_comment_resp_funding_rate) |
|nextFundingTime |string |t(:row_comment_resp_next_funding_time)  |
|bid1Price|string|t(:row_comment_resp_bid_price) |
|bid1Size|string|t(:row_comment_resp_bid_size) |
|ask1Price|string|t(:row_comment_resp_ask_price) |
|ask1Size|string|t(:row_comment_resp_ask_size) |
|basisRate|string|t(:row_comment_basis_in_year) |
|deliveryFeeRate|string|t(:row_comment_resp_delivery_fee_rate) |

### t(:websocketkline)
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","args":["candle.1.BTCUSDT"]}')
```

```python--pybit
from pybit import WebSocket
subs = [
    "klineV2.1.BTCUSD"
]
ws = WebSocket(
    "wss://stream-testnet.bybit.com/realtime",
    subscriptions=subs
)
while True:
    data = ws.fetch(subs[0])
    if data:
        print(data)
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
  "topic":"candle.1.BTCUSDT",
    "data":[
    {
      "start":1658150220000,
      "end":1658150279999,
      "interval":"1",
      "open":"22212",
      "close":"22214",
      "high":"22214.5",
      "low":"22212",
      "volume":"5.456",
      "turnover":"121193.36",
      "confirm":false,
      "timestamp":1658150224542
    }
  ],
    "ts":1658150224542,
    "type":"snapshot"
}
```

t(:websocket_para_klineV2)


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|start|integer |t(:row_comment_startTime)    |
|end|integer |t(:row_comment_endTime)    |
|interval|string|t(:row_comment_interval) |
|open|string |t(:row_comment_open)    |
|close|string |t(:row_comment_close)    |
|high|string |t(:row_comment_high)    |
|low|string |t(:row_comment_low)    |
|volume|string |t(:row_comment_resp_volume)    |
|turnover|string |t(:row_comment_resp_turnover)    |
|confirm|bool |t(:row_comment_confirm)    |
|timestamp|integer |t(:row_comment_endTime)    |


## t(:privatetopics_unified)
### t(:websocketposition)
> t(:codequote_subscribe)


```javascript
ws.send('{"op": "subscribe", "args": ["position"]}')
```

```python--old
from BybitWebsocket import BybitWebsocket
ws = BybitWebsocket(wsURL="wss://stream-testnet.bybit.com/realtime",
                    api_key=api_key, api_secret=api_secret)
ws.subscribe_position()
while True:
    data = ws.get_data("position")
    if data:
        print(data)
```

```python--pybit
from pybit import WebSocket
subs = [
    "position"
]
ws = WebSocket(
    "wss://stream-testnet.bybit.com/realtime",
    api_key="", api_secret="",
    subscriptions=subs
)
while True:
    data = ws.fetch(subs[0])
    if data:
        print(data)
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
   "topic": "position",
   "action": "update",
   "data": [
       {
           "user_id":  1,
           "symbol": "BTCUSD",
           "size": 11,
           "side": "Sell",
           "position_value": "0.00159252",
           "entry_price": "6907.291588174717",
           "liq_price": "7100.234",
           "bust_price": "7088.1234",
           "leverage": "1",
           "order_margin":  "1",
           "position_margin":  "1",
           "available_balance":  "2",
           "take_profit": "0",
           "tp_trigger_by":  "LastPrice",
           "stop_loss": "0",
           "sl_trigger_by":  "",
           "realised_pnl":  "0.10",
           "trailing_stop": "0",
           "trailing_active": "0",
           "wallet_balance":  "4.12",
           "risk_id":  1,                       
           "occ_closing_fee":  "0.1",
           "occ_funding_fee":  "0.1",
           "auto_add_margin": 0,
           "cum_realised_pnl":  "0.12",
           "position_status": "Normal",
           "position_seq": 14
       }
   ]
}
```

t(:account_para_myPosition)

<aside class="notice">
t(:websocketposition_aside)
</aside>

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |number |t(:row_comment_position_size)  |
|position_value |string |t(:row_comment_position_value)  |
|entry_price |string |t(:row_comment_entry_price)  |
|liq_price |string |t(:row_comment_liq_price)  |
|bust_price |string |t(:row_comment_bust_price)  |
|leverage |string |t(:resp_field_leverage)  |
|order_margin |string |t(:row_comment_order_margin)  |
|position_margin |string |t(:row_comment_position_margin)  |
|available_balance |string |t(:row_comment_available_balance)  |
|take_profit |string |t(:row_comment_take_profit)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by) |
|stop_loss |string |t(:row_comment_stop_loss)  |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by) |
|realised_pnl |string |t(:row_comment_realised_pnl)  |
|trailing_stop |string |t(:row_comment_trailing_stop)  |
|trailing_active |string |t(:row_comment_trailing_active)  |
|wallet_balance |string |t(:row_comment_wallet_balance)  |
|risk_id |number |t(:row_comment_riskId)  |
|is_isolated | bool | t(:row_comment_isolated) |
|occ_closing_fee |string |t(:row_comment_occ_closing_fee)  |
|occ_funding_fee |string |t(:row_comment_occ_funding_fee)  |
|auto_add_margin |number |t(:row_comment_auto_add_margin)  |
|cum_realised_pnl |string |t(:row_comment_cum_realised_pnl)  |
|position_status |string |t(:row_comment_position_status)  |
|position_seq |number |t(:row_comment_position_seq)  |




### t(:websocketexecution)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["execution"]}')
```

```python--old
from BybitWebsocket import BybitWebsocket
ws = BybitWebsocket(wsURL="wss://stream-testnet.bybit.com/realtime",
                    api_key=api_key, api_secret=api_secret)
ws.subscribe_execution()
while True:
    data = ws.get_data("execution")
    if data:
        print(data)
```

```python--pybit
from pybit import WebSocket
subs = [
    "execution"
]
ws = WebSocket(
    "wss://stream-testnet.bybit.com/realtime",
    api_key="", api_secret="",
    subscriptions=subs
)
while True:
    data = ws.fetch(subs[0])
    if data:
        print(data)
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "topic": "execution",
    "data": [
        {
            "symbol": "BTCUSD",
            "side": "Buy",
            "order_id": "xxxxxxxx-xxxx-xxxx-9a8f-4a973eb5c418",
            "exec_id": "xxxxxxxx-xxxx-xxxx-8b66-c3d2fcd352f6",
            "order_link_id": "",
            "price": "8300",
            "order_qty": 1,
            "exec_type": "Trade",
            "exec_qty": 1,
            "exec_fee": "0.00000009",
            "leaves_qty": 0,
            "is_maker": false,
            "trade_time": "2020-01-14T14:07:23.629Z"
        }
    ]
}
```

t(:wallet_para_tradeRecords)

<aside class="notice">
t(:websocket_execution_aside)
</aside>

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)  |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|order_id |string |t(:row_comment_order_id)  |
|exec_id |string |t(:row_comment_exec_id)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|t(:row_parameter_price) |string |t(:row_comment_exec_price)    |
|order_qty |number |t(:row_comment_order_qty)  |
|t(:row_parameter_exec_type) |string |t(:exec_type_pnl)  |
|exec_qty |number |t(:row_comment_exec_qty)  |
|exec_fee |string |t(:row_comment_exec_fee)    |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|is_maker |bool |t(:row_comment_is_maker)  |
|trade_time |string |t(:row_comment_trade_time)  |



### t(:websocketOrder)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["order"]}')
```

```python--old
from BybitWebsocket import BybitWebsocket
ws = BybitWebsocket(wsURL="wss://stream-testnet.bybit.com/realtime",
                    api_key=api_key, api_secret=api_secret)
ws.subscribe_order()
while True:
    data = ws.get_data("order")
    if data:
        print(data)
```

```python--pybit
from pybit import WebSocket
subs = [
    "order"
]
ws = WebSocket(
    "wss://stream-testnet.bybit.com/realtime",
    api_key="", api_secret="",
    subscriptions=subs
)
while True:
    data = ws.fetch(subs[0])
    if data:
        print(data)
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "topic": "order",
    "data": [
        {
            "order_id": "xxxxxxxx-xxxx-xxxx-9a8f-4a973eb5c418",
            "order_link_id": "",
            "symbol": "BTCUSD",
            "side": "Sell",
            "order_type": "Market",
            "price": "8579.5",
            "qty": 1,
            "time_in_force": "ImmediateOrCancel",
            "create_type": "CreateByClosing",
            "cancel_type": "",
            "order_status": "Filled",
            "leaves_qty": 0,
            "cum_exec_qty": 1,
            "cum_exec_value": "0.00011655",
            "cum_exec_fee": "0.00000009",
            "timestamp": "2020-01-14T14:09:31.778Z",
            "take_profit": "0",
            "stop_loss": "0",
            "trailing_stop": "0",
            "trailing_active": "0",
            "last_exec_price": "8580",
            "reduce_only": false,
            "close_on_trigger": false
        }
    ]
}
```


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|order_id |string |t(:row_comment_order_id)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)  |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_stopOrderType) |
|t(:row_parameter_price) |string |t(:row_comment_resp_price) |
|qty |number |t(:row_comment_exec_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce) |
|create_type |string |t(:row_comment_create_type) |
|cancel_type |string |t(:row_comment_cancel_type) |
|t(:row_parameter_order_status) |string | t(:row_comment_orderStatus) |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|cum_exec_qty |number |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |string |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |string |t(:linear_resp_field_cum_exec_fee)  |
|timestamp |string |t(:websocketorder_row_comment_timestamp)  |
|take_profit |string |t(:row_comment_take_profit)  |
|stop_loss |string |t(:row_comment_stop_loss)  |
|trailing_stop |string |t(:row_comment_trailing_stop)  |
|trailing_active |string |t(:row_comment_trailing_active)  |
|last_exec_price |string |t(:row_comment_last_exec_price)  |
|reduce_only | bool | t(:row_comment_reduceOnly)|
|close_on_trigger | bool | t(:row_comment_closeOnTrigger)|


### t(:websocketwallet)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["wallet"]}')
```

```python--pybit
from pybit import WebSocket
subs = [
    "wallet"
]
ws = WebSocket(
    "wss://stream-testnet.bybit.com/realtime",
    api_key="", api_secret="",
    subscriptions=subs
)
while True:
    data = ws.fetch(subs[0])
    if data:
        print(data)
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "topic": "wallet",
    "data": [
        {
            "user_id": 738713,
            "coin": "BTC",
            "available_balance": "1.50121026",
            "wallet_balance": "1.50121261"
        }
    ]
}
```

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|wallet_balance |number |t(:row_comment_wallet_balance)  |
|available_balance |number |t(:row_comment_available_balance)  |

### t(:greeksOption)

> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","id":"{100003}","args":["user.openapi.greeks"]}');

```

> t(:codequote_snapshot)

```javascript

{
    "id":"b3666f79-abf0-45a6-9c6d-ff4d41912b57",
    "topic":"user.openapi.greeks",
    "creationTime":1646274372152,
    "data":{
        "result":[
            {
                "coin":"BTC",
                "totalDelta":"0.0006714372",
                "totalGamma":"-0.0000000654",
                "totalVega":"-0.3207237154",
                "totalTheta":"0.1142353260"
            }
        ],
        "version":3984,
        "baseLine":1
    }
}

```

t(:udscGeeksDesc)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| coin |string |t(:usdcBaseCoin) |
| totalDelta |string |t(:delta) |
| totalGamma |string |t(:gamma) |
| totalVega|string |t(:vega) |
| totalTheta |string |t(:theta) |
