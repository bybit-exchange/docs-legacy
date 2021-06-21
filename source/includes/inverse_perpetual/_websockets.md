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
// Unsubscribing to the trade data for ETHUSD
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

```python
from BybitWebsocket import BybitWebsocket
ws = BybitWebsocket(wsURL="wss://stream-testnet.bybit.com/realtime",
                    api_key=None, api_secret=None)
ws.subscribe_orderBookL2(symbol="BTCUSD")
while True:
    data = ws.get_data("orderBookL2_25.BTCUSD")
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

```python
from BybitWebsocket import BybitWebsocket
ws = BybitWebsocket(wsURL="wss://stream-testnet.bybit.com/realtime",
                    api_key=None, api_secret=None)
ws.subscribe_trade()
while True:
    data = ws.get_data("trade.BTCUSD")
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
|time |string |t(:row_response_comment_time)  |
|trade_time_ms |number |t(:row_response_comment_nill_time)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
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

```python
from BybitWebsocket import BybitWebsocket
ws = BybitWebsocket(wsURL="wss://stream-testnet.bybit.com/realtime",
                    api_key=None, api_secret=None)
ws.subscribe_insurance()
while True:
    data = ws.get_data("insurance.BTC")
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

```python
from BybitWebsocket import BybitWebsocket
ws = BybitWebsocket(wsURL="wss://stream-testnet.bybit.com/realtime",
                    api_key=None, api_secret=None)
ws.subscribe_instrument_info(symbol="BTCUSD")
while True:
    data = ws.get_data("instrument_info.100ms.BTCUSD")
    if data:
        print(data)
```

> t(:codequote_snapshot)

```javascript
{
    "topic":"instrument_info.100ms.BTCUSDH21",
    "type":"snapshot",
     "data": {
         "id": 1,
         "symbol": "BTCUSD",                           //instrument name
         "last_price_e4": 81165000,                    //the latest price
         "bid1_price_e4":400025000,                    // best bid price
         "ask1_price_e4":475450000,                    // best ask price
         "last_tick_direction": "ZeroPlusTick",        //the direction of last tick:PlusTick,ZeroPlusTick,MinusTick,ZeroMinusTick
         "prev_price_24h_e4": 81585000,                //the price of prev 24h
         "price_24h_pcnt_e6": -5148,                   //the current last price percentage change from prev 24h price
         "high_price_24h_e4": 82900000,                //the highest price of prev 24h
         "low_price_24h_e4": 79655000,                 //the lowest price of prev 24h
         "prev_price_1h_e4": 81395000,                 //the price of prev 1h
         "price_1h_pcnt_e6": -2825,                    //the current last price percentage change from prev 1h price
         "mark_price_e4": 81178500,                    //mark price
         "index_price_e4": 81172800,                   //index price
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
         "countdown_hour": 6                           //the remaining time to settle the funding fee
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
|last_tick_direction |string |t(:enum_tick_direction)  |
|prev_price_24h_e4 |integer |t(:row_comment_resp_prev_price_24h_e4)  |
|price_24h_pcnt_e6 |integer |t(:row_comment_resp_price_24h_pcnt_e4)  |
|high_price_24h_e4 |integer |t(:row_comment_resp_high_price_24h_e4)  |
|low_price_24h_e4 |integer |t(:row_comment_resp_low_price_24h_e4)  |
|prev_price_1h_e4 |integer |t(:row_comment_resp_prev_price_1h_e4)  |
|price_1h_pcnt_e6 |integer |t(:row_comment_resp_price_1h_pcnt_e6)  |
|mark_price_e4 |integer |t(:row_comment_resp_mark_price_e4)  |
|index_price_e4 |integer |t(:row_comment_resp_index_price_e4)  |
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


### t(:websocketklineV2)
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","args":["klineV2.1.BTCUSD"]}')
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
|volume|number |t(:row_comment_resp_volume)    |
|turnover|number |t(:row_comment_resp_turnover)    |
|confirm|bool |t(:row_comment_confirm)    |
|cross_seq|integer |t(:row_comment_cross_seq)    |
|timestamp|integer |t(:row_comment_endTime)    |



## t(:privatetopics)
### t(:websocketposition)
> t(:codequote_subscribe)


```javascript
ws.send('{"op": "subscribe", "args": ["position"]}')
```

```python
from BybitWebsocket import BybitWebsocket
ws = BybitWebsocket(wsURL="wss://stream-testnet.bybit.com/realtime",
                    api_key=api_key, api_secret=api_secret)
ws.subscribe_position()
while True:
    data = ws.get_data("position")
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
           "user_id":  1,                            // user ID
           "symbol": "BTCUSD",                       // the contract for this position
           "size": 11,                               // the current position amount
           "side": "Sell",                           // side
           "position_value": "0.00159252",           // positional value
           "entry_price": "6907.291588174717",       // entry price
           "liq_price": "7100.234",                  // liquidation price
           "bust_price": "7088.1234",                // bankruptcy price
           "leverage": "1",                           // leverage
           "order_margin":  "1",                      // order margin
           "position_margin":  "1",                   // position margin
           "available_balance":  "2",                 // available balance
           "take_profit": "0",                        // take profit price           
           "tp_trigger_by":  "LastPrice",             // take profit trigger price, eg: LastPrice, IndexPrice. Conditional order only
           "stop_loss": "0",                          // stop loss price
           "sl_trigger_by":  "",                     // stop loss trigger price, eg: LastPrice, IndexPrice. Conditional order only
           "realised_pnl":  "0.10",               // realised PNL
           "trailing_stop": "0",                  // trailing stop points
           "trailing_active": "0",                // trailing stop trigger price
           "wallet_balance":  "4.12",             // wallet balance
           "risk_id":  1,                       
           "occ_closing_fee":  "0.1",             // position closing
           "occ_funding_fee":  "0.1",             // funding fee
           "auto_add_margin": 0,                  // auto margin replenishment switch
           "cum_realised_pnl":  "0.12",           // Total realized profit and loss
           "position_status": "Normal",           // status of position (Normal: normal Liq: in the process of liquidation Adl: in the process of Auto-Deleveraging)
                        // Auto margin replenishment enabled (0: no 1: yes)
           "position_seq": 14                     // position version number
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

```python
from BybitWebsocket import BybitWebsocket
ws = BybitWebsocket(wsURL="wss://stream-testnet.bybit.com/realtime",
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
            "trade_time": "2020-01-14T14:07:23.629Z" // trade time
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
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|is_maker |bool |t(:row_comment_is_maker)  |
|trade_time |string |t(:row_comment_trade_time)  |



### t(:websocketorder)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["order"]}')
```

```python
from BybitWebsocket import BybitWebsocket
ws = BybitWebsocket(wsURL="wss://stream-testnet.bybit.com/realtime",
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
|order_link_id |string |t(:row_comment_order_link_id)  |
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
            "order_status": "Untriggered", //t(:enum_stop_order_status_link)
            "stop_order_type": "Stop",
            "trigger_by": "LastPrice",
            "trigger_price": "8584.5", //t(:stop_order_trigger_price)
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
|order_link_id |string |t(:row_comment_order_link_id)  |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol) |string |t(:enum_symbol_link)  |
|t(:row_parameter_order_type) |string |t(:enum_order_type_link)  |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|price |string |t(:row_response_comment_price)    |
|qty |number |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|create_type |string |t(:row_comment_create_type)  |
|cancel_type |string |t(:row_comment_cancel_type)  |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|stop_order_type |string |t(:row_comment_stopOrderType)  |
|trigger_by | string |t(:row_comment_triggerBy) |
|trigger_price | string | t(:stop_order_trigger_price)|
|close_on_trigger | bool | t(:row_comment_closeOnTrigger)|
|timestamp |string |t(:row_response_comment_time)  |
