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


> t(:websocket_codequote_filters3)

```javascript
// Example: Subscribing to the trade data for all symbols
ws.send('{"op": "subscribe", "args": ["trade.*"]}')
```

t(:websocket_para_filters)

`ws.send('{"op": "subscribe", "args": ["topic.filter"]}');`

t(:websocket_para_filters1)

`ws.send('{"op": "subscribe", "args": ["topic.filter", "topic.filter"]}');`

t(:websocket_para_filters2)

### t(:websocketunsubfilters)
> t(:websocket_codequote_unsubfilters)

```javascript
// Unsubscribing from the trade data for ETHUSD
ws.send('{"op":"unsubscribe","args":["trade.ETHUSD"]}')
```

t(:websocket_para_unsubfilters)

`ws.send('{"op": "unsubscribe", "args": ["topic.filter", "topic.filter"]}');`


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
### t(:websocketorderbook25)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["orderBookL2_25.BTCUSD"]}');
```

```python--old
from BybitWebsocket import BybitWebsocket
ws = BybitWebsocket(wsURL="wss://stream-testnet.bybit.com/realtime",
                    api_key=None, api_secret=None)
ws.subscribe_orderBookL2(symbol="BTCUSD")
while True:
    data = ws.get_data("orderBookL2_25.BTCUSD")
    if data:
        print(data)
```

```python--pybit
from pybit import WebSocket
subs = [
    "orderBookL2_25.BTCUSD"
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
     "topic": "orderBookL2_25.BTCUSD",
     "type": "snapshot",
     "data": [
        {
            "price": "2999.00",
            "symbol": "BTCUSD",
            "id": 29990000,
            "side": "Buy",
            "size": 9
        },
        {
            "price": "3001.00",
            "symbol": "BTCUSD",
            "id": 30010000,
            "side": "Sell",
            "size": 10
        }
     ],
     "cross_seq": 11518,
     "timestamp_e6": 1555647164875373
}
```

> t(:codequote_delta)

```javascript
{
     "topic": "orderBookL2_25.BTCUSD",
     "type": "delta",
     "data": {
          "delete": [
             {
                   "price": "3001.00",
                   "symbol": "BTCUSD",
                   "id": 30010000,
                   "side": "Sell"
             }
          ],
          "update": [
             {
                   "price": "2999.00",
                   "symbol": "BTCUSD",
                   "id": 29990000,
                   "side": "Buy",
                   "size": 8
             }
          ],
          "insert": [
             {
                   "price": "2998.00",
                   "symbol": "BTCUSD",
                   "id": 29980000,
                   "side": "Buy",
                   "size": 8
             }
          ],
          "transactTimeE6": 0
     },
     "cross_seq": 11519,
     "timestamp_e6": 1555647221331673
}
```

t(:websocket_para_orderbook251)

<aside class="notice">
t(:orderbookL2_200_link)
</aside>

t(:websocket_para_orderbook252)


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_price) |string |t(:row_comment_resp_price) |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |number |t(:row_comment_position_size)  |






### t(:websocketorderbook200)

> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["orderBook_200.100ms.BTCUSD"]}');
```

```python--pybit
from pybit import WebSocket
subs = [
    "orderBook_200.100ms.BTCUSD"
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
     "topic": "orderBook_200.100ms.BTCUSD",
     "type": "snapshot",
     "data": [
        {
            "price": "2999.00",
            "symbol": "BTCUSD",
            "id": 29990000,
            "side": "Buy",
            "size": 9
        },
        {
            "price": "3001.00",
            "symbol": "BTCUSD",
            "id": 30010000,
            "side": "Sell",
            "size": 10
        }
     ],
     "cross_seq": 11518,
     "timestamp_e6": 1555647164875373
}
```

> t(:codequote_delta)

```javascript
{
     "topic": "orderBook_200.100ms.BTCUSD",
     "type": "delta",
     "data": {
          "delete": [
             {
                   "price": "3001.00",
                   "symbol": "BTCUSD",
                   "id": 30010000,
                   "side": "Sell"
             }
          ],
          "update": [
             {
                   "price": "2999.00",
                   "symbol": "BTCUSD",
                   "id": 29990000,
                   "side": "Buy",
                   "size": 8
             }
          ],
          "insert": [
             {
                   "price": "2998.00",
                   "symbol": "BTCUSD",
                   "id": 29980000,
                   "side": "Buy",
                   "size": 8
             }
          ],
          "transactTimeE6": 0
     },
     "cross_seq": 11519,
     "timestamp_e6": 1555647221331673
}
```

t(:websocket_para_orderbook200)


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_price) |string |t(:row_comment_resp_price) |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |number |t(:row_comment_position_size)  |


### t(:websockettrade)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["trade"]}')
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
    "topic": "trade.BTCUSD",
    "data": [
        {
            "timestamp": "2020-01-12T16:59:59.000Z",
            "trade_time_ms": 1582793344685,
            "symbol": "BTCUSD",
            "side": "Sell",
            "size": 328,
            "price": 8098,
            "tick_direction": "MinusTick",
            "trade_id": "00c706e1-ba52-5bb0-98d0-bf694bdc69f7",
            "cross_seq": 1052816407
        }
    ]
}
```

t(:websocket_para_trade)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|timestamp |string |t(:row_response_comment_time)  |
|trade_time_ms |number |t(:row_response_comment_nill_time)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:websocketTradeSide)  |
|size |number |t(:row_comment_position_size)  |
|t(:row_parameter_price) |number |t(:row_response_comment_price)  |
|t(:row_parameter_tick_direction) |string |t(:row_comment_position_tick_direction)  |
|trade_id |string |t(:row_response_comment_trade_id)  |
|cross_seq |number |t(:row_comment_cross_seq)  |


### t(:websocketinsurance)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["insurance"]}')
```

```python--old
from BybitWebsocket import BybitWebsocket
ws = BybitWebsocket(wsURL="wss://stream-testnet.bybit.com/realtime",
                    api_key=None, api_secret=None)
ws.subscribe_insurance()
while True:
    data = ws.get_data("insurance.BTC")
    if data:
        print(data)
```

```python--pybit
from pybit import WebSocket
subs = [
    "insurance.BTC"
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
    "topic": "insurance.BTC",
    "data": [
        {
            "currency": "BTC",
            "timestamp": "2020-01-11T20:00:00Z",
            "wallet_balance": 98786916569
        }
    ]
}
```

t(:websocket_para_insurance)

<aside class="notice">
t(:websocket_aside_insurance)
</aside>

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|currency |string |t(:row_comment_currency)  |
|timestamp |string |t(:row_response_comment_time)  |
|wallet_balance |number |t(:row_comment_wallet_balance)  |


### t(:websocketinstrumentInfo)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["instrument_info.100ms.BTCUSD"]}')
```

```python--old
from BybitWebsocket import BybitWebsocket
ws = BybitWebsocket(wsURL="wss://stream-testnet.bybit.com/realtime",
                    api_key=None, api_secret=None)
ws.subscribe_instrument_info(symbol="BTCUSD")
while True:
    data = ws.get_data("instrument_info.100ms.BTCUSD")
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
    "topic":"instrument_info.100ms.BTCUSD",
    "type":"snapshot",
    "data": {
         "id": 1,
         "symbol": "BTCUSD",
         "last_price_e4": 81165000,
         "last_price": "81165000",  
         "bid1_price_e4":400025000,
         "bid1_price":"400025000",
         "ask1_price_e4":475450000,
         "ask1_price":"475450000",
         "last_tick_direction": "ZeroPlusTick",
         "prev_price_24h_e4": 81585000,
         "prev_price_24h": "81585000",
         "price_24h_pcnt_e6": -5148,
         "high_price_24h_e4": 82900000,
         "high_price_24h": "82900000",
         "low_price_24h_e4": 79655000,
         "low_price_24h": "79655000",
         "prev_price_1h_e4": 81395000,
         "prev_price_1h": "81395000",
         "price_1h_pcnt_e6": -2825,
         "mark_price_e4": 81178500,
         "mark_price": "81178500",
         "index_price_e4": 81172800,
         "index_price": "81172800",
         "open_interest": 154418471,
         "open_value_e8": 1997561103030,
         "total_turnover_e8": 2029370141961401,
         "turnover_24h_e8": 9072939873591,
         "total_volume": 175654418740,
         "volume_24h": 735865248,
         "funding_rate_e6": 100,
         "predicted_funding_rate_e6": 100,
         "cross_seq": 1053192577,
         "created_at": "2018-11-14T16:33:26Z",         
         "updated_at": "2020-01-12T18:25:16Z",         
         "next_funding_time": "2020-01-13T00:00:00Z",

         "countdown_hour": 6,
         "funding_rate_interval": 8
         },
    "cross_seq":9267002,
    "timestamp_e6":1615794861826248
}
```

> t(:codequote_delta)

```javascript
{
    "topic": "instrument_info.100ms.BTCUSD",
    "type": "delta",
    "data": {
        "delete": [],
        "update": [
            {
                "id": 1,
                "symbol": "BTCUSD",
                "prev_price_24h_e4": 81565000,
                "prev_price_24h": "81565000",
                "price_24h_pcnt_e6": -4904,
                "open_value_e8": 2000479681106,
                "total_turnover_e8": 2029370495672976,
                "turnover_24h_e8": 9066215468687,
                "volume_24h": 735316391,
                "cross_seq": 1053192657,
                "created_at": "2018-11-14T16:33:26Z",
                "updated_at": "2020-01-12T18:25:25Z"
            }
        ],
        "insert": []
    },
    "cross_seq": 1053192657,
    "timestamp_e6": 1578853525691123
}
```

t(:websocket_para_instrumentInfo)

<aside class="warning">
t(:websocket_aside_instrumentInfo1)
</aside>

<aside class="notice">
t(:websocket_aside_instrumentInfo2)
</aside>

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)  |
|last_price_e4 |integer |t(:row_comment_resp_last_price_e4)  |
|t(:row_parameter_tick_direction) |string |t(:row_comment_position_tick_direction)  |
|prev_price_24h_e4 |integer |t(:row_comment_resp_prev_price_24h_e4)  |
|price_24h_pcnt_e6 |integer |t(:row_comment_resp_price_24h_pcnt_e4)  |
|high_price_24h_e4 |integer |t(:row_comment_resp_high_price_24h_e4)  |
|low_price_24h_e4 |integer |t(:row_comment_resp_low_price_24h_e4)  |
|prev_price_1h_e4 |integer |t(:row_comment_resp_prev_price_1h_e4)  |
|price_1h_pcnt_e6 |integer |t(:row_comment_resp_price_1h_pcnt_e6)  |
|mark_price_e4 |integer |t(:row_comment_resp_mark_price_e4)  |
|index_price_e4 |integer |t(:row_comment_resp_index_price_e4)  |
|last_price |integer |t(:row_comment_resp_last_price)  |
|prev_price_24h |integer |t(:row_comment_resp_prev_price_24h)  |
|high_price_24h |integer |t(:row_comment_resp_high_price_24h)  |
|low_price_24h |integer |t(:row_comment_resp_low_price_24h)  |
|prev_price_1h |integer |t(:row_comment_resp_prev_price_1h)  |
|mark_price |integer |t(:row_comment_resp_mark_price)  |
|index_price |integer |t(:row_comment_resp_index_price)  |
|open_interest |integer |t(:row_comment_resp_open_interest). t(:row_comment_slow_update)  |
|open_value_e8 |integer |t(:row_comment_resp_open_value_e8). t(:row_comment_slow_update)  |
|total_turnover_e8 |integer |t(:row_comment_resp_total_turnover_e8)  |
|turnover_24h_e8 |integer |t(:row_comment_resp_turnover_24h_e8)  |
|total_volume |integer |t(:row_comment_resp_total_volume)  |
|volume_24h |integer |t(:row_comment_resp_volume_24h)  |
|predicted_funding_rate_e6 |integer |t(:row_comment_resp_predicted_funding_rate_e6)  |
|cross_seq |integer |t(:row_comment_cross_seq)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|next_funding_time |string |t(:row_comment_resp_next_funding_time)  |
|countdown_hour |integer |t(:row_comment_resp_countdown_hour)  |
|funding_rate_interval |integer |t(:row_comment_resp_funding_rate_interval) |

### t(:websocketklineV2)
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","args":["klineV2.1.BTCUSD"]}')
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
    "topic": "klineV2.1.BTCUSD",
    "data": [{
        "start": 1572425640,
        "end": 1572425700,
        "open": 9200,
        "close": 9202.5,
        "high": 9202.5,
        "low": 9196,
        "volume": 81790,
        "turnover": 8.889247899999999,
        "confirm": False,
        "cross_seq": 297503466,                 
        "timestamp": 1572425676958323
    }],
    "timestamp_e6": 1572425677047994
}
```

t(:websocket_para_klineV2)


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|start|integer |t(:row_comment_startTime)    |
|end|integer |t(:row_comment_endTime)    |
|open|number |t(:row_comment_open)    |
|close|number |t(:row_comment_close)    |
|high|number |t(:row_comment_high)    |
|low|number |t(:row_comment_low)    |
|volume|number |t(:row_comment_resp_volume)    |
|turnover|number |t(:row_comment_resp_turnover)    |
|confirm|bool |t(:row_comment_confirm)    |
|cross_seq|integer |t(:row_comment_cross_seq)    |
|timestamp|integer |t(:row_comment_endTime)    |



### t(:websocketliquidation)
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","args":["liquidation"]}')
```

```python--pybit
from pybit import WebSocket
subs = [
    "liquidation"
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
    "topic":"liquidation.ETHUSD",
    "data": {
        "symbol":"ETHUSD",
        "side":"Sell",
        "price":"3384.15",
        "qty":"3655",
        "time":1631608881954
    }
}
```
t(:websocket_query_liqrecords)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side)|string |t(:row_response_liq_record_side)    |
|t(:row_parameter_price) |string |t(:row_comment_bust_price)    |
|t(:row_parameter_quantity)|string |t(:row_response_comment_execqty)    |
|time|number |t(:row_response_comment_nill_time)    |


## t(:privatetopics)
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



### t(:websocketorder)
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
|timestamp |string |t(:row_comment_timestamp)  |
|take_profit |string |t(:row_comment_take_profit)  |
|stop_loss |string |t(:row_comment_stop_loss)  |
|trailing_stop |string |t(:row_comment_trailing_stop)  |
|trailing_active |string |t(:row_comment_trailing_active)  |
|last_exec_price |string |t(:row_comment_last_exec_price)  |
|reduce_only | bool | t(:row_comment_reduceOnly)|
|close_on_trigger | bool | t(:row_comment_closeOnTrigger)|

### t(:websocketstoporder)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["stop_order"]}')
```

```python--pybit
from pybit import WebSocket
subs = [
    "stop_order"
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
    "topic": "stop_order",
    "data": [
        {
            "order_id": "xxxxxxxx-xxxx-xxxx-98fb-335aaa6c613b",
            "order_link_id": "",
            "user_id": 1,
            "symbol": "BTCUSD",
            "side": "Buy",
            "order_type": "Limit",
            "price": "8584.5",
            "qty": 1,
            "time_in_force": "ImmediateOrCancel",
            "create_type": "CreateByStopOrder",
            "cancel_type": "",
            "order_status": "Untriggered",
            "stop_order_type": "Stop",
            "trigger_by": "LastPrice",
            "trigger_price": "8584.5",
            "close_on_trigger": false,
            "timestamp": "2020-01-14T14:11:22.062Z"
        }
    ]
}
```

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|order_id |string |t(:row_comment_order_id)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)  |
|t(:row_parameter_order_type) |string |t(:row_comment_order_type) |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_price) |string |t(:row_response_comment_price)    |
|qty |number |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|create_type |string |t(:row_comment_create_type)  |
|cancel_type |string |t(:row_comment_cancel_type)  |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|t(:row_parameter_stop_order_type) |string |t(:row_comment_stopOrderType)  |
|trigger_by | string |t(:row_comment_triggerBy) |
|t(:row_parameter_trigger_price) | string | t(:stop_order_trigger_price)|
|close_on_trigger | bool | t(:row_comment_closeOnTrigger)|
|timestamp |string |t(:row_response_comment_time)  |


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
