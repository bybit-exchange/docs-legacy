# t(:websocket)
## t(:websocketauthentication)
> t(:websocket_codequote_auth)

> t(:websocket_codequote_auth1)

```javascript
var api_key = "";
var secret = "";
// A UNIX timestamp after which the request become invalid. This is to prevent replay attacks.
// unit:millisecond
var expires = time.now()+1000;

// Signature
var signature = hex(HMAC_SHA256(secret, 'GET/realtime' + expires));

// Parameters string
var param = "api_key={api_key}&expires={expires}&signature={signature}";

// Establishing connection
var ws = new WebSocket("wsurl?param");
```

> t(:websocket_codequote_auth2)

```javascript
var ws = new WebSocket("wsurl")
// Signature is the same for both methods of authentication
ws.send('{"op":"auth","args":["{api_key}","{expires}","{signature}"]}');
```


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
// Unsubscribing to the trade data for ETHUSDT
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
   "success": true, // Whether subscription is successful
   "ret_msg": "",   // Successful subscription: "", otherwise it shows error message
   "conn_id":"e0e10eee-4eff-4d21-881e-a0c55c25e2da",// current connection id
   "request": {     // Request to your subscription
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

```python
from BybitWebsocket import BybitWebsocket
ws = BybitWebsocket(wsURL="wss://stream-testnet.bybit.com/realtime_public",
                    api_key=None, api_secret=None)
ws.subscribe_orderBookL2(symbol="BTCUSDT")
while True:
    data = ws.get_data("orderBookL2_25.BTCUSDT")
    if data:
        print(data)
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
| price |string |t(:row_comment_resp_price) |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |number |t(:row_comment_position_size)  |


### t(:websocketorderbook200)

> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["orderBook_200.100ms.BTCUSDT"]}');
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
| price |string |t(:row_comment_resp_price) |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |number |t(:row_comment_position_size)  |


### t(:websockettrade)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["trade.BTCUSDT"]}')
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
|tick_direction |string |t(:row_comment_position_tick_direction)  |
|t(:row_parameter_price) |number |t(:row_response_comment_price)  |
|size |number |t(:row_comment_position_size)  |
|time |string |t(:row_response_comment_time)  |
|trade_time_ms |string |t(:row_response_comment_nill_time)  |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|trade_id |string |t(:row_response_comment_trade_id)  |


### t(:websocketinstrumentInfo)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["instrument_info.100ms.BTCUSDT"]}')
```

```python
from BybitWebsocket import BybitWebsocket
ws = BybitWebsocket(wsURL="wss://stream-testnet.bybit.com/realtime_public",
                    api_key=None, api_secret=None)
ws.subscribe_instrument_info("BTCUSDT")
while True:
    data = ws.get_data("instrument_info.100ms.BTCUSDT")
    if data:
        print(data)
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
    "last_tick_direction": "ZeroPlusTick",
    "prev_price_24h_e4": "331960000",
    "price_24h_pcnt_e6": "-27126",
    "high_price_24h_e4": "333120000",
    "low_price_24h_e4": "315940000",
    "prev_price_1h_e4": "319490000",
    "price_1h_pcnt_e6": "10845",
    "mark_price_e4": "323133000",
    "index_price_e4": "323106800",
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
    "count_down_hour": "7",
    "bid1_price_e4": "322950000",
    "ask1_price_e4": "322955000"
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
        "price_24h_pcnt_e6": "-27141",
        "price_1h_pcnt_e6": "10829",
        "index_price_e4": "323100000",
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
|symbol|string |t(:row_comment_symbol)    |
|last_price_e4 |integer |t(:row_comment_resp_last_price_e4)  |
|last_tick_direction |string |t(:enum_tick_direction)  |
|prev_price_24h_e4 |integer |t(:row_comment_resp_prev_price_24h_e4)  |
|price_24h_pcnt_e6 |integer |t(:row_comment_resp_price_24h_pcnt_e4)  |
|high_price_24h_e4 |integer |t(:row_comment_resp_high_price_24h_e4)  |
|low_price_24h_e4 |integer |t(:row_comment_resp_low_price_24h_e4)  |
|prev_price_1h_e4 |integer |t(:row_comment_resp_prev_price_1h_e4)  |
|price_1h_pcnt_e6 |integer |t(:row_comment_resp_price_1h_pcnt_e6)  |
|mark_price_e4 |integer |t(:row_comment_resp_mark_price_e4)  |
|index_price_e4 |integer |t(:row_comment_resp_index_price_e4)  |
|open_interest_e8|integer |t(:row_comment_resp_open_interest_e8). t(:row_comment_slow_update)  |
|total_turnover_e8 |integer |t(:row_comment_resp_total_turnover_e8)  |
|turnover_24h_e8 |integer |t(:row_comment_resp_turnover_24h_e8)  |
|total_volume_e8 |integer |t(:row_comment_resp_total_volume_e8)  |
|volume_24h_e8 |integer |t(:row_comment_resp_volume_24h_e8)  |
|funding_rate_e6 |integer |t(:row_comment_resp_funding_rate_e6)  |
|predicted_funding_rate_e6 |integer |t(:row_comment_resp_predicted_funding_rate_e6)  |
|cross_seq |integer |t(:row_comment_cross_seq)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|next_funding_time |string |t(:row_comment_resp_next_funding_time)  |
|countdown_hour |number |t(:row_comment_resp_countdown_hour)  |
|bid1_price_e4 |integer|t(:row_comment_bid1_price_e4)  |
|ask1_price_e4 |integer|t(:row_comment_ask1_price_e4)  |


### t(:websocketkline)
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","args":["candle.1.BTCUSDT"]}')
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "topic":"candle.1.BTCUSDT",
    "data":[
        {
            "start":1588071660,
            "end":1588071720,
            "open":7744.5,
            "close":7745,
            "high":7745,
            "low":7744,
            "volume":"33.051",
            "turnover":"255979.995",
            "confirm":true,
            "cross_seq":71947372,
            "timestamp":1588071717325846
        }
    ],
    "timestamp_e6":1588071721163975
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
|timestamp|integer |t(:row_comment_endTime)    |














## t(:privatetopics)
### t(:websocketposition)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["position"]}')
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
           "occ_closing_fee":  "0.1",
           "take_profit":  "0.1",
           "tp_trigger_by": 0,
           "stop_loss":  "0.12",
           "sl_trigger_by": "Normal",
           "realised_pnl": "Normal",
           "cum_realised_pnl": "Normal",
           "position_seq": 14
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
|position_value |string |t(:row_comment_position_value)  |
|entry_price |string |t(:row_comment_entry_price)  |
|liq_price |string |t(:row_comment_liq_price)  |
|bust_price |string |t(:row_comment_bust_price)  |
|leverage |string |t(:resp_field_leverage)  |
|order_margin |string |t(:row_comment_order_margin)  |
|position_margin |string |t(:row_comment_position_margin)  |
|occ_closing_fee |string |t(:row_comment_occ_closing_fee)  |
|take_profit |string |t(:row_comment_take_profit)  |
|t(:row_parameter_tp_trigger_by)|number |t(:account_row_comment_tp_trigger_by) |
|stop_loss |string |t(:row_comment_stop_loss)  |
|t(:row_parameter_sl_trigger_by) |string |string |t(:account_row_comment_sl_trigger_by) |
|realised_pnl |string |t(:row_comment_realised_pnl)  |
|cum_realised_pnl |string |t(:row_comment_cum_realised_pnl)  |
|position_status |string |t(:row_comment_position_status)  |
|position_seq |number |t(:row_comment_position_seq)  |


### t(:websocketexecution)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["execution"]}')
```

```python
from BybitWebsocket import BybitWebsocket
ws = BybitWebsocket(wsURL="wss://stream-testnet.bybit.com/realtime_private",
                    api_key=api_key, api_secret=api_secret)
ws.subscribe_execution()
while True:
    data = ws.get_data("execution")
    if data:
        print(data)
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

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)  |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|order_id |string |t(:row_comment_order_id)  |
|exec_id |string |t(:row_comment_exec_id)  |
|order_link_id |string |t(:row_comment_order_link_id)  |
|t(:row_parameter_price) |string |t(:row_comment_exec_price)    |
|order_qty |number |t(:row_comment_order_qty)  |
|t(:row_parameter_exec_type) |string |t(:enum_exec_type_link)  |
|exec_qty |number |t(:row_comment_exec_qty)  |
|exec_fee |string |t(:row_comment_exec_fee)    |
|trade_time |string |t(:row_comment_trade_time)  |


### t(:websocketorder)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["order"]}')
```

```python
from BybitWebsocket import BybitWebsocket
ws = BybitWebsocket(wsURL="wss://stream-testnet.bybit.com/realtime_private",
                    api_key=api_key, api_secret=api_secret)
ws.subscribe_order()
while True:
    data = ws.get_data("order")
    if data:
        print(data)
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "topic": "order",
    "action": "",
    "data": [
        {
            "order_id": "xxxxxxxx-xxxx-xxxx-9a8f-4a973eb5c418",
            "order_link_id": "",
            "symbol": "BTCUSDT",
            "side": "Buy",
            "order_type": "Limit",
            "price": 11000,
            "qty": 0.001,
            "leaves_qty": 0.001,
            "last_exec_price": 0,
            "cum_exec_qty": 0,
            "cum_exec_value": 0,
            "cum_exec_fee": 0,
            "time_in_force": "GoodTillCancel",
            "create_type": "CreateByUser",
            "cancel_type": "UNKNOWN",
            "order_status": "New",
            "take_profit": 0,
            "stop_loss": 0,
            "trailing_stop": 0,
            "reduce_only": false,
            "close_on_trigger": false,
            "create_time": "2020-08-12T21:18:40.780039678Z",
            "update_time": "2020-08-12T21:18:40.787986415Z"
        }
    ]
}
```

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|order_id |string |t(:row_comment_order_id)  |
|order_link_id |string |t(:row_comment_order_link_id)  |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)  |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_stopOrderType) |
|t(:row_parameter_price) |string |t(:row_comment_resp_price) |
|qty |number |t(:row_comment_exec_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce) |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus) |
|last_exec_price |number |t(:row_comment_last_exec_price)  |
|cum_exec_qty |number |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |string |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |string |t(:linear_resp_field_cum_exec_fee)  |
|reduce_only | bool | t(:row_comment_reduceOnly)|
|close_on_trigger | bool | t(:row_comment_closeOnTrigger)|
|create_time |string |t(:row_comment_timestamp)  |
|update_time |string |t(:row_comment_resp_update_time)  |

### t(:websocketstoporder)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["stop_order"]}')
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "topic": "stop_order",
    "data": [
        {
            "stop_order_id": "xxxxxxxx-xxxx-xxxx-98fb-335aaa6c613b",
            "order_link_id": "",
            "user_id": 1,
            "symbol": "BTCUSD",
            "side": "Buy",
            "order_type": "Limit",
            "price": "8584.5",
            "qty": 1,
            "time_in_force": "ImmediateOrCancel",
            "order_status": "Untriggered", //t(:enum_stop_order_status_link)
            "stop_order_type": "Stop",
            "trigger_by": "LastPrice",
            "trigger_price": "8584.5",
            "reduce_only": false,
            "close_on_trigger": false,
            "create_time": "2020-01-14T14:11:22.062Z",
            "update_time": "2020-01-14T14:11:22.062Z"
        }
    ]
}
```

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|stop_order_id |string |t(:row_comment_stopOrderId) |
|order_link_id |string |t(:row_comment_order_link_id)  |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol) |string |t(:enum_symbol_link)  |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:enum_order_type_link)  |
|price |string |t(:row_response_comment_price)    |
|qty |number |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|stop_order_type |string |t(:row_comment_stopOrderType)  |
|trigger_by | string |t(:row_comment_triggerBy) |
|trigger_price | string | t(:stop_order_trigger_price)|
|reduce_only | bool | t(:row_comment_reduceOnly)|
|close_on_trigger | bool | t(:row_comment_closeOnTrigger)|
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |


### t(:websocketwallet)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["wallet"]}')
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
