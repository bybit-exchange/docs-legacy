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
// Subscribing to the trade data for ETHBTC
ws.send('{"op":"subscribe","args":["trade.ETHBTC"]}')
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
ws.send('{"op": "subscribe", "args": ["orderBookL2_25.BTCUSDT"]}');
```

> t(:codequote_snapshot)

```javascript
{
     "topic": "orderBookL2_25.BTCUSDT",
     "type": "snapshot",
     "data": [
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
     ],
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
     "data": [
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
     ],
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


### t(:websocketinstrumentInfo)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["instrument_info.100ms.BTCUSDT"]}')
```

> t(:codequote_snapshot)

```javascript
{
    "topic": "instrument_info.100ms.BTCUSDT",
    "type": "snapshot",
    "data": {
        "id": 1,
        "symbol": "BTCUSDT",                           //instrument name
        "last_price_e4": 81165000,                    //the latest price
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
    "cross_seq": 1053192634,
    "timestamp_e6": 1578853524091081                  //the timestamp when this information was produced
}
```

> t(:codequote_delta)

```javascript
{
    "topic": "instrument_info.100ms.BTCUSDT",
    "type": "delta",
    "data": {
        "delete": [],
        "update": [
            {
                "id": 1,
                "symbol": "BTCUSDT",
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


### t(:websocketexecution)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["execution"]}')
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
            "trade_time": "2020-01-14T14:07:23.629Z" // trade time
        }
    ]
}
```


### t(:websocketorder)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["order"]}')
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
            "order_status": "Filled",
            "last_exec_price": 0,
            "cum_exec_qty": 1,
            "cum_exec_value": "0.00011655",
            "cum_exec_fee": "0.00000009",
            "create_time": "2020-01-14T14:09:31.778Z",
            "update_time": "2020-01-14T14:09:31.778Z"
        }
    ]
}
```


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
            "create_time": "2020-01-14T14:11:22.062Z",
            "update_time": "2020-01-14T14:11:22.062Z"
        }
    ]
}
```


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