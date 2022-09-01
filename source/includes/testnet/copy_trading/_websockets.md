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

ws_url = "wss://stream.bybit.com/realtime_private"

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
t(:websocket_endpoints_aside_copytrading)
</aside>

t(:linear_websocket_para_endpoint)

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
| price |string |t(:row_comment_resp_price) |
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
| price |string |t(:row_comment_resp_price) |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |number |t(:row_comment_position_size)  |


### t(:websockettrade)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["trade"]}')
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
            "trade_time_ms": 1582793344685, // trade time in millisecond
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
         "symbol": "BTCUSD",                           //instrument name
         "last_price_e4": 81165000,                    //the latest price
         "last_price": "81165000",  
         "bid1_price_e4":400025000,                    // best bid price
         "bid1_price":"400025000",
         "ask1_price_e4":475450000,                    // best ask price
         "ask1_price":"475450000",
         "last_tick_direction": "ZeroPlusTick",        //the direction of last tick:PlusTick,ZeroPlusTick,MinusTick,ZeroMinusTick
         "prev_price_24h_e4": 81585000,                //the price of prev 24h
         "prev_price_24h": "81585000",
         "price_24h_pcnt_e6": -5148,                   //the current last price percentage change from prev 24h price
         "high_price_24h_e4": 82900000,                //the highest price of prev 24h
         "high_price_24h": "82900000",
         "low_price_24h_e4": 79655000,                 //the lowest price of prev 24h
         "low_price_24h": "79655000",
         "prev_price_1h_e4": 81395000,                 //the price of prev 1h
         "prev_price_1h": "81395000",
         "price_1h_pcnt_e6": -2825,                    //the current last price percentage change from prev 1h price
         "mark_price_e4": 81178500,                    //mark price
         "mark_price": "81178500",
         "index_price_e4": 81172800,                   //index price
         "index_price": "81172800",
         "open_interest": 154418471,                   //open interest quantity - Attention, the update is not immediate - slowest update is 1 minute
         "open_value_e8": 1997561103030,               //open value quantity - Attention, the update is not immediate - the slowest update is 1 minute
         "total_turnover_e8": 2029370141961401,        //total turnover
         "turnover_24h_e8": 9072939873591,             //24h turnover
         "total_volume": 175654418740,                 //total volume
         "volume_24h": 735865248,                      //24h volume
         "funding_rate_e6": 100,                       //funding rate
         "predicted_funding_rate_e6": 100,             //predicted funding rate
         "cross_seq": 1053192577,                      //sequence
         "created_at": "2018-11-14T16:33:26Z",         
         "updated_at": "2020-01-12T18:25:16Z",         
         "next_funding_time": "2020-01-13T00:00:00Z",  //next funding time
                                                       //the rest time to settle funding fee
         "countdown_hour": 6,                           //the remaining time to settle the funding fee
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
|symbol|string |t(:row_comment_symbol)  |
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
    "topic": "klineV2.1.BTCUSD",                //topic name
    "data": [{
        "start": 1572425640,                    //start time of the candle
        "end": 1572425700,                      //end time of the candle
        "open": 9200,                           //open price
        "close": 9202.5,                        //close price
        "high": 9202.5,                         //max price
        "low": 9196,                            //min price
        "volume": 81790,                        //volume
        "turnover": 8.889247899999999,          //turnover
        "confirm": False,                       //snapshot flag
        "cross_seq": 297503466,                 
        "timestamp": 1572425676958323           //cross time
    }],
    "timestamp_e6": 1572425677047994            //server time
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
|price|string |t(:row_comment_bust_price)    |
|t(:row_parameter_quantity)|string |t(:row_response_comment_execqty)    |
|time|number |t(:row_response_comment_nill_time)    |


## t(:privatetopics)
### t(:websocketposition)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["copyTradePosition"]}')
```

```python--pybit
from pybit import WebSocket
subs = [
    "copyTradePosition"
]
ws = WebSocket(
    "wss://stream-testnet.bybit.com/realtime_private",
    subscriptions=subs,
    api_key="", api_secret=""
)
while True:
    data = ws.fetch(subs[0])
    if data:
        print(data)
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
  "topic":"copyTradePosition",
    "data":[
    {
      "symbol":"ETHUSDT",
      "positionIdx":"2",
      "positionValue":"80.05065626",
      "riskId":11,
      "leverage":"10.000000",
      "isIsolated":true,
      "side":"Sell",
      "size":"0.040000",
      "unrealisedPnl":"1.62665626",
      "liqPrice":"2191.350098",
      "bustPrice":"2201.350098",
      "entryPrice":"2001.26640650",
      "positionMargin":"8.00506666",
      "orderMargin":"0.00000000",
      "occClosingFee":"0.05283240",
      "cumRealisedPnl":"0.55284374",
      "positionStatus":"Normal",
      "positionSeq":0
    }
  ]
}
```

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|positionIdx |string |t(:copy_trade_row_comment_position_idx)  |
|positionValue |string |t(:row_comment_position_value)  |
|riskId |string |t(:row_comment_riskId)  |
|leverage |string |t(:copytrade_field_leverage)  |
|isolated |bool |t(:row_comment_isolated)  |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |string |t(:row_comment_position_size)  |
|unrealisedPnl |string |t(:unrealisedPnl)  |
|liqPrice |string |t(:row_comment_liq_price)  |
|bustPrice |string |t(:row_comment_bust_price)  |
|entryPrice |string |t(:row_comment_entry_price)  |
|positionMargin |string |t(:row_comment_position_margin)  |
|orderMargin |string |t(:row_comment_order_margin)  |
|occClosingFee |string |t(:row_comment_occ_closing_fee)  |
|cumRealisedPnl |string |t(:row_comment_cum_realised_pnl)  |
|positionStatus |string |t(:row_comment_position_status)  |
|positionSeq |number |t(:row_comment_position_seq)  |

### t(:websocketorder)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["copyTradeOrder"]}')
```

```python--pybit
from pybit import WebSocket
subs = [
    "copyTradeOrder"
]
ws = WebSocket(
    "wss://stream-testnet.bybit.com/realtime_private",
    subscriptions=subs,
    api_key="", api_secret=""
)
while True:
    data = ws.fetch(subs[0])
    if data:
        print(data)
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
  "topic":"copyTradeOrder",
    "data":[
    {
      "orderId":"6d667921-3cf4-4efd-b93f-727bd10a3b62",
      "orderLinkId":"w11a313223ddd132111",
      "symbol":"ETHUSDT",
      "orderType":"Market",
      "price":"1863.250000",
      "qty":"0.010000",
      "side":"Sell",
      "positionIdx":"2",
      "cumExecFee":"0.01175970",
      "cumExecValue":"19.59950000",
      "takeProfit": "1750"
      "stopLoss": "2000"
      "tpTriggerBy": "LastPrice"
      "slTriggerBy": "LastPrice"
      "lastExecPrice":"1959.949951",
      "cumExecQty":"0.010000",
      "createTime":1652932133873,
      "updateTime":1652932133892,
      "copyTradeOrderStatus":"OpenOrderFilled"
    }
  ]
}
```

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId |string |t(:row_comment_order_id)  |
|orderLinkId |string |t(:row_comment_orderLinkId)  |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)  |
|orderType |string |t(:row_comment_stopOrderType) |
|price |string |t(:row_comment_resp_price) |
|qty |string |t(:row_comment_exec_qty)  |
|side |string |t(:row_comment_side)  |
|positionIdx |string |t(:copy_trade_row_comment_position_idx)  |
|cumExecFee |string |t(:linear_resp_field_cum_exec_fee)  |
|cumExecValue |string |t(:linear_resp_field_cum_exec_value)  |
|takeProfit |string |t(:row_comment_take_profit) |
|stopLoss |string |t(:row_comment_stop_loss) |
|tpTriggerBy |string |t(:account_row_comment_tpTriggerBy_v3) |
|slTriggerBy |string |t(:account_row_comment_slTriggerBy_v3) |
|lastExecPrice |string |t(:row_comment_last_exec_price)  |
|cumExecQty |string |t(:linear_resp_field_cum_exec_qty)  |
|createTime |string |t(:row_comment_timestamp)  |
|updateTime |string |t(:row_comment_resp_update_time)  |
|copyTradeOrderStatus |string |t(:copytrade_field_order_status)  |

### t(:websocketexecution)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["copyTradeExecution"]}')
```

```python--pybit
from pybit import WebSocket
subs = [
    "copyTradeExecution"
]
ws = WebSocket(
    "wss://stream-testnet.bybit.com/realtime_private",
    subscriptions=subs,
    api_key="", api_secret=""
)
while True:
    data = ws.fetch(subs[0])
    if data:
        print(data)
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
  "topic":"copyTradeExecution",
    "data":[
    {
      "orderId":"6d667921-3cf4-4efd-b93f-727bd10a3b62",
      "orderLinkId":"w11a313223ddd132111",
      "symbol":"ETHUSDT",
      "side":"Sell",
      "execId":"0182b08b-a3ce-5038-a8be-5e1e9f862e90",
      "execQty":"0.010000",
      "execType":"Trade",
      "execFee":"0.01175970",
      "price":"1863.250000",
      "orderQty":"0.010000",
      "tradeTime":1652932133873
    }
  ]
}
```

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId |string |t(:row_comment_order_id)  |
|orderLinkId |string |t(:row_comment_orderLinkId)  |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)  |
|side |string |t(:row_comment_side)  |
|execId |string |t(:row_comment_exec_id) |
|execQty |string |t(:row_comment_exec_qty) |
|execType |string |t(:exec_type_pnl)  |
|execFee |string |t(:row_comment_exec_fee)  |
|price |string |t(:row_comment_exec_price)  |
|orderQty |string |t(:row_comment_order_qty)  |
|tradeTime |string |t(:row_comment_trade_time)  |

### t(:websocketwallet)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["copyTradeWallet"]}')
```

```python--pybit
from pybit import WebSocket
subs = [
    "copyTradeWallet"
]
ws = WebSocket(
    "wss://stream-testnet.bybit.com/realtime_private",
    subscriptions=subs,
    api_key="", api_secret=""
)
while True:
    data = ws.fetch(subs[0])
    if data:
        print(data)
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
  "topic":"copyTradeWallet",
    "data":{
    "walletBalance":"14009.12164704",
      "availableBalance":"13998.97749271"
  }
}
```

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|walletBalance |number |t(:row_comment_wallet_balance)  |
|availableBalance |number |t(:row_comment_available_balance)  |
