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
t(:linear_websocket_endpoints_aside)
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
    "success": true,
    "ret_msg": "pong",
    "conn_id": "036e5d21-804c-4447-a92d-b65a44d00700"
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
// Subscribing to the trade data for ETHUSDT
ws.send('{"op":"subscribe","args":["trade.ETHUSDT"]}')
```

> t(:websocket_codequote_filters_linear)

```javascript
// Example: Subscribing to the trade data for BTCUSD and XRPUSD
ws.send('{"op":"subscribe","args":["trade.BTCUSDT","trade.XRPUSDT"]}')
```



t(:websocket_para_filters)

`ws.send('{"op": "subscribe", "args": ["topic.filter"]}');`

t(:websocket_para_filters1)

`ws.send('{"op": "subscribe", "args": ["topic.filter", "topic.filter"]}');`

### t(:websocketunsubfilters)
> t(:websocket_codequote_unsubfilters)

```javascript
// Unsubscribing from the trade data for ETHUSDT
ws.send('{"op":"unsubscribe","args":["trade.ETHUSDT"]}')
```

t(:websocket_para_unsubfilters)

`ws.send('{"op": "unsubscribe", "args": ["topic.filter", "topic.filter"]}');`

### t(:intervals)
t(:websocket_para_intervals)

## t(:websocketresponse)
> t(:websocket_codequote_response)

```javascript
{
   "success": true,
   "ret_msg": "",
   "conn_id":"e0e10eee-4eff-4d21-881e-a0c55c25e2da"
   "request": {
       "op": "subscribe",
       "args": [
           "kline.BTCUSDT.1m"
       ]
   }
}
```

t(:websocket_para_response)

## t(:publictopics)
### t(:websocketorderbook25)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["orderBookL2_25.BTCUSDT"]}');
```

```python--pybit
from time import sleep
from pybit import usdt_perpetual
ws_linear = usdt_perpetual.WebSocket(
    test=True,
    ping_interval=30,  # the default is 30
    ping_timeout=10,  # the default is 10
    domain="bybit"  # the default is "bybit"
)
def handle_message(msg):
    print(msg)
# To subscribe to multiple symbols,
# pass a list: ["BTCUSDT", "ETHUSDT"]
ws_linear.orderbook_25_stream(
    handle_message, "XRPUSDT"
)
while True:
    sleep(1)
```

> t(:codequote_snapshot)

```javascript
{
     "topic": "orderBookL2_25.BTCUSDT",
     "type": "snapshot",
     "data": {
         "order_book":[
             {
                 "price": "2999.00",
                 "symbol": "BTCUSDT",
                 "id": 29990000,
                 "side": "Buy",
                 "size": 9
             },
             {
                 "price": "3001.00",
                 "symbol": "BTCUSDT",
                 "id": 30010000,
                 "side": "Sell",
                 "size": 10
             }
          ]
     },
     "cross_seq": 11518,
     "timestamp_e6": 1555647164875373
}
```

> t(:codequote_delta)

```javascript
{
     "topic": "orderBookL2_25.BTCUSDT",
     "type": "delta",
     "data": {
          "delete": [
             {
                   "price": "3001.00",
                   "symbol": "BTCUSDT",
                   "id": 30010000,
                   "side": "Sell"
             }
          ],
          "update": [
             {
                   "price": "2999.00",
                   "symbol": "BTCUSDT",
                   "id": 29990000,
                   "side": "Buy",
                   "size": 8
             }
          ],
          "insert": [
             {
                   "price": "2998.00",
                   "symbol": "BTCUSDT",
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
ws.send('{"op": "subscribe", "args": ["orderBook_200.100ms.BTCUSDT"]}');
```

```python--pybit
from time import sleep
from pybit import usdt_perpetual
ws_linear = usdt_perpetual.WebSocket(
    test=True,
    ping_interval=30,  # the default is 30
    ping_timeout=10,  # the default is 10
    domain="bybit"  # the default is "bybit"
)
def handle_message(msg):
    print(msg)
# To subscribe to multiple symbols,
# pass a list: ["BTCUSDT", "ETHUSDT"]
ws_linear.orderbook_200_stream(
    handle_message, "EOSUSDT"
)
while True:
    sleep(1)
```

> t(:codequote_snapshot)

```javascript
{
     "topic": "orderBook_200.100ms.BTCUSDT",
     "type": "snapshot",
     "data": {
         "order_book":[
             {
                 "price": "2999.00",
                 "symbol": "BTCUSDT",
                 "id": 29990000,
                 "side": "Buy",
                 "size": 9
             },
             {
                 "price": "3001.00",
                 "symbol": "BTCUSDT",
                 "id": 30010000,
                 "side": "Sell",
                 "size": 10
             }
          ]
     },
     "cross_seq": 11518,
     "timestamp_e6": 1555647164875373
}
```

> t(:codequote_delta)

```javascript
{
     "topic": "orderBook_200.100ms.BTCUSDT",
     "type": "delta",
     "data": {
          "delete": [
             {
                   "price": "3001.00",
                   "symbol": "BTCUSDT",
                   "id": 30010000,
                   "side": "Sell"
             }
          ],
          "update": [
             {
                   "price": "2999.00",
                   "symbol": "BTCUSDT",
                   "id": 29990000,
                   "side": "Buy",
                   "size": 8
             }
          ],
          "insert": [
             {
                   "price": "2998.00",
                   "symbol": "BTCUSDT",
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
ws.send('{"op": "subscribe", "args": ["trade.BTCUSDT"]}')
```

```python--pybit
from time import sleep
from pybit import usdt_perpetual
ws_linear = usdt_perpetual.WebSocket(
    test=True,
    ping_interval=30,  # the default is 30
    ping_timeout=10,  # the default is 10
    domain="bybit"  # the default is "bybit"
)
def handle_message(msg):
    print(msg)
# To subscribe to multiple symbols,
# pass a list: ["BTCUSDT", "ETHUSDT"]
ws_linear.trade_stream(
    handle_message, "EOSUSDT"
)
while True:
    sleep(1)
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "topic": "trade.BTCUSDT",
    "data": [
        {
            "symbol": "BTCUSDT",
            "tick_direction": "PlusTick",
            "price": 8098,
            "size": 328,
            "timestamp":"2020-03-30T02:21:06.000Z",
            "trade_time_ms":"1585534866418",
            "side":"Sell",
            "trade_id":"01e79e28-d1f4-59ac-b079-ca909606d91a"
        }
    ]
}
```

t(:websocket_para_trade)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_tick_direction) |string |t(:row_comment_position_tick_direction)  |
|t(:row_parameter_price) |number |t(:row_response_comment_price)  |
|size |number |t(:row_comment_position_size)  |
|timestamp |string |t(:row_response_comment_time)  |
|trade_time_ms |string |t(:row_response_comment_nill_time)  |
|t(:row_parameter_side) |string |t(:websocketTradeSide)  |
|trade_id |string |t(:row_response_comment_trade_id)  |


### t(:websocketinstrumentInfo)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["instrument_info.100ms.BTCUSDT"]}')
```

```python--pybit
from time import sleep
from pybit import usdt_perpetual
ws_linear = usdt_perpetual.WebSocket(
    test=True,
    ping_interval=30,  # the default is 30
    ping_timeout=10,  # the default is 10
    domain="bybit"  # the default is "bybit"
)
def handle_message(msg):
    print(msg)
# To subscribe to multiple symbols,
# pass a list: ["BTCUSDT", "ETHUSDT"]
ws_linear.instrument_info_stream(
    handle_message, "BTCUSDT"
)
while True:
    sleep(1)
```

> t(:codequote_snapshot)

```javascript
{
  "topic": "instrument_info.100ms.BTCUSDT",
  "type": "snapshot",
  "data": {
       "id": 1,
       "symbol": "BTCUSDT",
       "last_price_e4": "322955000",
       "last_price": "322955000",
       "last_tick_direction": "ZeroPlusTick",
       "prev_price_24h_e4": "331960000",
       "prev_price_24h": "331960000",
       "price_24h_pcnt_e6": "-27126",
       "high_price_24h_e4": "333120000",
       "high_price_24h": "333120000",
       "low_price_24h_e4": "315940000",
       "low_price_24h": "315940000",
       "prev_price_1h_e4": "319490000",
       "prev_price_1h": "319490000",
       "price_1h_pcnt_e6": "10845",
       "mark_price_e4": "323133000",
       "mark_price": "323133000",
       "index_price_e4": "323106800",
       "index_price": "323106800",
       "open_interest_e8": "1430451600000",
       "total_turnover_e8": "5297934997553700000",
       "turnover_24h_e8": "243143978993099700",
       "total_volume_e8": "1184936057899924",
       "volume_24h_e8": "7511238100000",
       "funding_rate_e6": "100",
       "predicted_funding_rate_e6": "-15",
       "cross_seq": "6501157651",
       "created_at": "1970-01-01T00:00:00.000Z",
       "updated_at": "2021-07-14T09:32:10.000Z",
       "next_funding_time": "2021-07-14T16:00:00Z",
       "count_down_hour": 7,
       "funding_rate_interval": 8,
       "bid1_price_e4": "322950000",
       "ask1_price_e4": "322955000"
       "bid1_price": "322950000",
       "ask1_price_e4": "322955000",
       "ask1_price": "322955000",
  },
  "cross_seq": "6501157734",
  "timestamp_e6": "1626255131908287"
}
```

> t(:codequote_delta)

```javascript
{
  "topic": "instrument_info.100ms.BTCUSDT",
  "type": "delta",
  "data": {
    "update": [
      {
        "id": 1,
        "symbol": "BTCUSDT",
        "last_price_e4": "322950000",
        "last_price": "322950000",
        "price_24h_pcnt_e6": "-27141",
        "price_1h_pcnt_e6": "10829",
        "index_price_e4": "323100000",
        "index_price": "323100000",
        "total_turnover_e8": "5297935000783200000",
        "turnover_24h_e8": "243143982222599700",
        "total_volume_e8": "1184936057999924",
        "volume_24h_e8": "7511238200000",
        "cross_seq": "6501157735",
        "created_at": "1970-01-01T00:00:00.000Z",
        "updated_at": "2021-07-14T09:32:12.000Z"
      }
    ]
  },
  "cross_seq": "6501157736",
  "timestamp_e6": "1626255132104671"
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
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)    |
|last_price_e4 |string |t(:row_comment_resp_last_price_e4)  |
|last_price |string |t(:row_comment_resp_last_price)  |
|<a href="#tick-direction-type-tick_direction">last_tick_direction</a> |string |t(:row_comment_position_tick_direction)  |
|prev_price_24h_e4 |string |t(:row_comment_resp_prev_price_24h_e4)  |
|prev_price_24h |string |t(:row_comment_resp_prev_price_24h)  |
|price_24h_pcnt_e6 |string |t(:row_comment_resp_price_24h_pcnt_e4)  |
|high_price_24h_e4 |string |t(:row_comment_resp_high_price_24h_e4)  |
|high_price_24h |string |t(:row_comment_resp_high_price_24h)  |
|low_price_24h_e4 |string |t(:row_comment_resp_low_price_24h_e4)  |
|low_price_24h |string |t(:row_comment_resp_low_price_24h)  |
|prev_price_1h_e4 |string |t(:row_comment_resp_prev_price_1h_e4)  |
|prev_price_1h |string |t(:row_comment_resp_prev_price_1h)  |
|price_1h_pcnt_e6 |string |t(:row_comment_resp_price_1h_pcnt_e6)  |
|mark_price_e4 |string |t(:row_comment_resp_mark_price_e4)  |
|mark_price |string |t(:row_comment_resp_mark_price)  |
|index_price_e4 |string |t(:row_comment_resp_index_price_e4)  |
|index_price |string |t(:row_comment_resp_index_price)  |
|open_interest_e8|string |t(:row_comment_resp_open_interest_e8). t(:row_comment_slow_update)  |
|total_turnover_e8 |string |t(:row_comment_resp_total_turnover_e8)  |
|turnover_24h_e8 |string |t(:row_comment_resp_turnover_24h_e8)  |
|total_volume_e8 |string |t(:row_comment_resp_total_volume_e8)  |
|volume_24h_e8 |string |t(:row_comment_resp_volume_24h_e8)  |
|funding_rate_e6 |string |t(:row_comment_resp_funding_rate_e6)  |
|predicted_funding_rate_e6 |string |t(:row_comment_resp_predicted_funding_rate_e6)  |
|cross_seq |string |t(:row_comment_cross_seq)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|next_funding_time |string |t(:row_comment_resp_next_funding_time)  |
|countdown_hour |number |t(:row_comment_resp_countdown_hour)  |
|funding_rate_interval |number |t(:row_comment_resp_funding_rate_interval) |
|bid1_price_e4 |string|t(:row_comment_bid1_price_e4)  |
|ask1_price_e4 |string|t(:row_comment_ask1_price_e4)  |
|bid1_price |string|t(:row_comment_bid1_price)  |
|ask1_price |string|t(:row_comment_ask1_price)  |

### t(:websocketkline)
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","args":["candle.1.BTCUSDT"]}')
```

```python--pybit
from time import sleep
from pybit import usdt_perpetual
ws_linear = usdt_perpetual.WebSocket(
    test=True,
    ping_interval=30,  # the default is 30
    ping_timeout=10,  # the default is 10
    domain="bybit"  # the default is "bybit"
)
def handle_message(msg):
    print(msg)
# To subscribe to multiple symbols,
# pass a list: ["BTCUSDT", "ETHUSDT"]
# pass an interval
ws_linear.kline_stream(
    handle_message, "DOTUSDT", "D"
)
while True:
    sleep(1)
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "topic": "candle.1.BTCUSDT",
    "data": [
        {
            "start": 1655956380,
            "end": 1655956440,
            "period": "1",
            "open": 20261,
            "close": 20257.5,
            "high": 20261,
            "low": 20256,
            "volume": "25.396",
            "turnover": "514491.9815",
            "confirm": False,
            "cross_seq": 13135807020,
            "timestamp": 1655956431377798
        }
    ],
    "timestamp_e6": 1655956431377798
}
```

t(:websocket_para_klineV2)

<aside class="notice">
t(:websocket_aside_klineV2)
</aside>


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|start|integer |t(:row_comment_startTime)    |
|end|integer |t(:row_comment_endTime)    |
|open|number |t(:row_comment_open)    |
|close|number |t(:row_comment_close)    |
|high|number |t(:row_comment_high)    |
|low|number |t(:row_comment_low)    |
|volume|string |t(:row_comment_resp_volume)    |
|turnover|string |t(:row_comment_resp_turnover)    |
|confirm|bool |t(:row_comment_confirm)    |
|cross_seq|integer |t(:row_comment_cross_seq)    |
|timestamp|integer |t(:row_comment_timestamp_e6)    |


### t(:websocketliquidation)
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","args":["liquidation.XRPUSDT"]}')
```

```python--pybit
from time import sleep
from pybit import usdt_perpetual
ws_linear = usdt_perpetual.WebSocket(
    test=True,
    ping_interval=30,  # the default is 30
    ping_timeout=10,  # the default is 10
    domain="bybit"  # the default is "bybit"
)
def handle_message(msg):
    print(msg)
# To subscribe to multiple symbols,
# pass a list: ["BTCUSDT", "ETHUSDT"]
ws_linear.liquidation_stream(
    handle_message, "DOTUSDT"
)
while True:
    sleep(1)
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "topic":"liquidation.XRPUSDT",
    "data": {
        "symbol":"XRPUSDT",
        "side":"Sell",
        "price":"3384.15",
        "qty":"0.057",
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
|t(:row_parameter_quantity)|string |t(:row_response_comment_liq_execqty)    |
|time|number |t(:row_response_comment_nill_time)    |





## t(:privatetopics)
### t(:websocketposition)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["position"]}')
```

```python--pybit
from time import sleep
from pybit import usdt_perpetual
ws_linear = usdt_perpetual.WebSocket(
    test=True,
    api_key="your api key",
    api_secret="your api secret",
    ping_interval=30,  # the default is 30
    ping_timeout=10,  # the default is 10
    domain="bybit"  # the default is "bybit"
)
def handle_message(msg):
    print(msg)
ws_linear.position_stream(
    handle_message
)
while True:
    sleep(1)
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
   "topic": "position",
   "action": "update",
   "data": [
{
            "user_id": "533285",
            "symbol": "BTCUSDT",
            "size": 0.01,
            "side": "Buy",
            "position_value": 202.195,
            "entry_price": 20219.5,
            "liq_price": 0.5,
            "bust_price": 0.5,
            "leverage": 99,
            "order_margin": 0,
            "position_margin": 1959.6383,
            "occ_closing_fee": 3e-06,
            "take_profit": 25000,
            "tp_trigger_by": "LastPrice",
            "stop_loss": 18000,
            "sl_trigger_by": "LastPrice",
            "trailing_stop": 0,
            "realised_pnl": -4.189762,
            "auto_add_margin": "0",
            "cum_realised_pnl": -13.640625,
            "position_status": "Normal",
            "position_id": "0",
            "position_seq": "92962",
            "adl_rank_indicator": "2",
            "free_qty": 0.01,
            "tp_sl_mode": "Full",
            "risk_id": "1",
            "isolated": false,
            "mode": "BothSide",
            "position_idx": "1"
        }
   ]
}
```

t(:account_para_myPosition)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|size |number |t(:row_comment_position_size)  |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|position_value |number |t(:row_comment_position_value)  |
|entry_price |number |t(:row_comment_entry_price)  |
|liq_price |number |t(:row_comment_liq_price)  |
|bust_price |number |t(:row_comment_bust_price)  |
|leverage |number |t(:resp_field_leverage)  |
|order_margin |number |t(:row_comment_order_margin)  |
|position_margin |number |t(:row_comment_position_margin)  |
|occ_closing_fee |number |t(:row_comment_occ_closing_fee)  |
|take_profit |number |t(:row_comment_take_profit)  |
|t(:row_parameter_tp_trigger_by)|string |t(:account_row_comment_tp_trigger_by) |
|stop_loss |number |t(:row_comment_stop_loss)  |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by) |
|trailing_stop |number |t(:row_comment_trailing_stop) |
|realised_pnl |number |t(:row_comment_realised_pnl)  |
|auto_add_margin |number |t(:row_comment_auto_add_margin)  |
|cum_realised_pnl |number |t(:row_comment_cum_realised_pnl)  |
|position_status |string |t(:row_comment_position_status)  |
|position_seq |string |t(:row_comment_position_seq)  |
|free_qty |number |t(:linear_resp_field_free_qty)  |
|t(:row_parameter_tp_sl_mode) |string |t(:row_comment_tp_sl_mode)  |
|risk_id |string |t(:row_comment_riskId)  |
|isolated |bool |t(:row_comment_isolated)  |
|mode |string |t(:row_comment_mode)  |
|position_idx |string |t(:row_comment_position_idx)  |


### t(:websocketexecution)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["execution"]}')
```

```python--pybit
from time import sleep
from pybit import usdt_perpetual
ws_linear = usdt_perpetual.WebSocket(
    test=True,
    api_key="your api key",
    api_secret="your api secret",
    ping_interval=30,  # the default is 30
    ping_timeout=10,  # the default is 10
    domain="bybit"  # the default is "bybit"
)
def handle_message(msg):
    print(msg)
ws_linear.execution_stream(
    handle_message
)
while True:
    sleep(1)
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "topic": "execution",
    "data": [
        {
            "symbol": "BTCUSDT",
            "side": "Sell",
            "order_id": "xxxxxxxx-xxxx-xxxx-9a8f-4a973eb5c418",
            "exec_id": "xxxxxxxx-xxxx-xxxx-8b66-c3d2fcd352f6",
            "order_link_id": "",
            "price": 11527.5,
            "order_qty": 0.001,
            "exec_type": "Trade",
            "exec_qty": 0.001,
            "exec_fee": 0.00864563,
            "leaves_qty": 0,
            "is_maker": false,
            "trade_time": "2020-08-12T21:16:18.142746Z"
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
|t(:row_parameter_price) |number |t(:row_comment_exec_price)    |
|order_qty |number |t(:row_comment_order_qty)  |
|t(:row_parameter_exec_type) |string |t(:exec_type_pnl)  |
|exec_qty |number |t(:row_comment_exec_qty)  |
|exec_fee |number |t(:row_comment_exec_fee)    |
|leaves_qty |number |t(:row_comment_leaves_qty) |
|is_maker |boolean |t(:row_comment_is_maker) |
|trade_time |string |t(:row_comment_trade_time)  |


### t(:websocketorder)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["order"]}')
```

```python--pybit
from time import sleep
from pybit import usdt_perpetual
ws_linear = usdt_perpetual.WebSocket(
    test=True,
    api_key="your api key",
    api_secret="your api secret",
    ping_interval=30,  # the default is 30
    ping_timeout=10,  # the default is 10
    domain="bybit"  # the default is "bybit"
)
def handle_message(msg):
    print(msg)
ws_linear.order_stream(
    handle_message
)
while True:
    sleep(1)
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "topic": "order",
    "action": "",
    "data": [
        {
            "order_id": "19a8cbbe-e077-42c7-bdba-505c76619ea5",
            "order_link_id": "Bactive004",
            "symbol": "BTCUSDT",
            "side": "Sell",
            "order_type": "Market",
            "price": 19185.5,
            "qty": 0.01,
            "leaves_qty": 0,
            "last_exec_price": 20196,
            "cum_exec_qty": 0.01,
            "cum_exec_value": 201.95999,
            "cum_exec_fee": 0.121176,
            "time_in_force": "ImmediateOrCancel",
            "create_type": "CreateByUser",
            "cancel_type": "UNKNOWN",
            "order_status": "Filled",
            "take_profit": 0,
            "stop_loss": 0,
            "trailing_stop": 0,
            "create_time": "2022-06-23T04:08:47.956636888Z",
            "update_time": "2022-06-23T04:08:47.960908408Z",
            "reduce_only": true,
            "close_on_trigger": false,
            "position_idx": "1"
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
|t(:row_parameter_price) |number |t(:row_comment_resp_price) |
|qty |number |t(:row_comment_exec_qty)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|last_exec_price |number |t(:row_comment_last_exec_price)  |
|cum_exec_qty |number |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |string |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |string |t(:linear_resp_field_cum_exec_fee)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce) |
|create_type |string |t(:row_comment_create_type)  |
|cancel_type |string |t(:row_comment_cancel_type)  |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus) |
|take_profit |number |t(:row_comment_take_profit) |
|stop_loss |number |t(:row_comment_stop_loss) |
|trailing_stop |number |t(:row_comment_trailing_stop) |
|create_time |string |t(:websocketorder_row_comment_timestamp)  |
|update_time |string |t(:row_comment_updated_at)  |
|reduce_only | bool | t(:row_comment_reduceOnly)|
|close_on_trigger | bool | t(:row_comment_closeOnTrigger)|
|position_idx |string |t(:row_comment_position_idx)  |

### t(:websocketstoporder)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["stop_order"]}')
```

```python--pybit
from time import sleep
from pybit import usdt_perpetual
ws_linear = usdt_perpetual.WebSocket(
    test=True,
    api_key="your api key",
    api_secret="your api secret",
    ping_interval=30,  # the default is 30
    ping_timeout=10,  # the default is 10
    domain="bybit"  # the default is "bybit"
)
def handle_message(msg):
    print(msg)
ws_linear.stop_order_stream(
    handle_message
)
while True:
    sleep(1)
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "topic": "stop_order",
    "data": [
        {
            "stop_order_id": "559bba2c-0152-4557-84f6-63dc6ab78463",
            "order_link_id": "",
            "user_id": "533285",
            "symbol": "BTCUSDT",
            "side": "Sell",
            "order_type": "Market",
            "price": 0,
            "qty": 0.01,
            "time_in_force": "ImmediateOrCancel",
            "create_type": "CreateByTakeProfit",
            "cancel_type": "UNKNOWN",
            "order_status": "Untriggered",
            "stop_order_type": "TakeProfit",
            "tp_trigger_by": "UNKNOWN",
            "trigger_price": 25000,
            "create_time": "2022-06-23T04:06:55.402188346Z",
            "update_time": "2022-06-23T04:08:47.960950878Z",
            "reduce_only": true,
            "close_on_trigger": true,
            "position_idx": "1"
        }
    ]
}
```

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|stop_order_id |string |t(:row_comment_stopOrderId) |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)  |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_order_type) |
|t(:row_parameter_price) |number |t(:row_response_comment_price)    |
|qty |number |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|create_type |string |t(:row_comment_create_type)  |
|cancel_type |string |t(:row_comment_cancel_type)  |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|t(:row_parameter_stop_order_type) |string |t(:row_comment_stopOrderType)  |
|tp_trigger_by | string |t(:row_comment_triggerBy) |
|trigger_price | number | t(:stop_order_trigger_price)|
|create_time |string |t(:websocketorder_row_comment_timestamp)  |
|update_time |string |t(:row_comment_updated_at)  |
|reduce_only |bool |t(:row_comment_reduceOnly) |
|close_on_trigger | bool |t(:row_comment_closeOnTrigger) |
|position_idx |string |t(:row_comment_position_idx)  |


### t(:websocketwallet)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["wallet"]}')
```

```python--pybit
from time import sleep
from pybit import usdt_perpetual
ws_linear = usdt_perpetual.WebSocket(
    test=True,
    api_key="your api key",
    api_secret="your api secret",
    ping_interval=30,  # the default is 30
    ping_timeout=10,  # the default is 10
    domain="bybit"  # the default is "bybit"
)
def handle_message(msg):
    print(msg)
ws_linear.wallet_stream(
    handle_message
)
while True:
    sleep(1)
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "topic": "wallet",
    "data": [
        {
            "wallet_balance":429.80713,
            "available_balance":429.67322
        }
    ]
}
```

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|wallet_balance |number |t(:row_comment_wallet_balance)  |
|available_balance |number |t(:row_comment_available_balance)  |
