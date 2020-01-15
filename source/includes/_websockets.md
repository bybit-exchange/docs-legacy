# WebSocket Data
## Authentication
> Authentication methods:

> First method: Apply for authentication when establishing a connection.

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

> Second method: Apply for authentication after establishing a connection through auth request.

```javascript
var ws = new WebSocket("wsurl")
// Signature is the same for both methods of authentication
ws.send('{"op":"auth","args":["{api_key}","{expires}","{signature}"]}');
```


Base endpoints:
<ul>
<p>
  <li>Testnet:
    <span id="testnet_address">wss://stream-testnet.bybit.com/realtime</span>
    <button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#testnet_address"><img src="images/copy_to_clipboard.png" height=15 width=15></a></button>
  </li>
</p>
<p>
  <li>Mainnet:
    <span id="mainnet_address">wss://stream.bybit.com/realtime</span>
    <button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#mainnet_address"><img src="images/copy_to_clipboard.png" height=15 width=15></a></button>
  </li>
</p>
</ul>

<aside class="notice">
<b>Public</b> topics do not require authentication. The following section applies to <b>private</b> topics only.
</aside>


There are two methods of authentication, as shown in the code panel to the right.

<aside class="notice">
Example signature algorithms can be found <a href="https://github.com/bybit-exchange/bybit-official-api-docs/tree/master/en/example">here</a>.
</aside>


## How to Send the Heartbeat Packet
> How to Send

```javascript
ws.send('{"op":"ping"}');
```

> Example Response

```javascript
{
    "success": true,
    "ret_msg": "pong",
    "request": {
        "op": "ping",
        "args": null
    }
}
```


<aside class="warning">
Due to unstable networks or program errors, we strongly advise you to send the <code>ping</code> heartbeat packet to maintain websocket connections. We recommend every 30 seconds to 1 minute.
</aside>


## Rate Limits
One API key can establish 20 concurrent connections. Any additional connection after 20 connections will be rejected.


## How to Subscribe to Topics
### Understanding Websocket Filters
> How to subscribe with a filter

```javascript
// Subscribing to the trade data for ETHBTC
ws.send('{"op":"subscribe","args":["trade.ETHBTC"]}')
```

> How to subscribe with multiple filters

```javascript
// Example: Subscribing to the trade data for BTCUSD and XRPUSD
ws.send('{"op":"subscribe","args":["trade.BTCUSD|XRPUSD"]}')
```


> How to subscribe without filters

```javascript
// Example: Subscribing to the trade data for all symbols
ws.send('{"op": "subscribe", "args": ["trade.*"]}')
```

After establishing the connection, one can subscribe to a new topic by sending a JSON request. The specific formats are as follows:

`ws.send('{"op": "subscribe", "args": ["topic.filter"]}');`

The `topic` indicates the data you would like to receive whilst the `filter` parses for the specific data you desire - for example, the symbol. The `topic` is mandatory but the `filter` is optional.

To subscribe to more than one topic, simply list multiple topics out, like so:

`ws.send('{"op": "subscribe", "args": ["topic.filter", "topic.filter"]}');`

It is possible to use multiple filters for the same topic by splitting them with a pipe (`|`) - of course, these filters must all be applicable to the selected `topic`.

Finally, to subscribe to the topic without filters please use the `*` wildcard.

### Intervals
Some topics are pushed at intervals. If the `args` contain a millisecond param, such as `100ms`, this topic is pushed at intervals. Otherwise, it is pushed constantly.


## Understanding the Subscription Response
> Subscription Response

```javascript
{
   "success": true, // Whether subscription is successful
   "ret_msg": "",   // Successful subscription: "", otherwise it shows error message
   "request": {     // Request to your subscription
       "op": "subscribe",
       "args": [
           "kline.BTCUSD.1m"
       ]
   }
}
```

Every subscription will have a response.

## Public Topics
### orderBookL2_25
> How to Subscribe

```javascript
ws.send('{"op": "subscribe", "args": ["orderBookL2_25.BTCUSD"]}');
```

> Snapshot Response Example - format of the first response

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

> Delta Response Example - format of the responses following the snapshot response

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

Fetches the orderbook with a depth of 25 orders per side.

<aside class="notice">
Want a greater depth? Take a look at the <a href="#orderbookl2_200">orderBookL2_200</a> endpoint.
</aside>

After the subscription response, the first response will be the snapshot response. This shows the entire orderbook. The data is ordered by price, starting with the lowest buys and ending with the highest sells.

Following this, all responses are in the delta format, which represents updates to the orderbook relative to the last response.


### orderBookL2_200

> How to Subscribe

```javascript
ws.send('{"op": "subscribe", "args": ["orderBook_200.100ms.BTCUSD"]}');
```

> Snapshot Response Example - format of the first response

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

> Delta Response Example - format of the responses following the snapshot response

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

Fetches the orderbook with a depth of 200 orders per side.

After the subscription response, the first response will be the snapshot response. This shows the entire orderbook. The data is ordered by price, starting with the lowest buys and ending with the highest sells.

Following this, all responses are in the delta format, which represents updates to the orderbook relative to the last response.


### trade
> How to Subscribe

```javascript
ws.send('{"op": "subscribe", "args": ["trade"]}')
```

> Response Example - format of all responses

```javascript
{
    "topic": "trade.BTCUSD",
    "data": [
        {
            "timestamp": "2020-01-12T16:59:59.000Z",
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

Get real-time trading information.


### insurance
> How to Subscribe

```javascript
ws.send('{"op": "subscribe", "args": ["insurance"]}')
```

> Response Example - format of all responses

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

Get the daily insurance fund update.

<aside class="notice">
The <code>wallet_balance</code> is in Satoshis, with one Satoshi being 100 millionth (<code>100000000</code>) of one Bitcoin.
</aside>

### instrument_info
> How to Subscribe

```javascript
ws.send('{"op": "subscribe", "args": ["instrument_info.100ms.BTCUSD"]}')
```

> Snapshot Response Example - format of the first response

```javascript
{
    "topic": "instrument_info.100ms.BTCUSD",
    "type": "snapshot",
    "data": {
        "id": 1,
        "symbol": "BTCUSD",                           //instrument name
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

> Delta Response Example - format of the responses following the snapshot response

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

Get latest information for symbol.

<aside class="warning">
This topic only utilises the <code>update</code> field. Both the <code>delete</code> and <code>insert</code> fields are null. If a key is not found in the <code>update</code> field, its value has not changed.
</aside>

<aside class="notice">
Some values use scientific notation. This is indicated by that value's key, which will be appended with, for example, <code>e6</code>. If the key is <code>last_price_e4</code> and the value is <code>81585000</code>, then to find the true value we can do <code>81585000 * 10^4</code>, which equals <code>8158.5</code>.
</aside>


### klineV2
> How to Subscribe

```javascript
ws.send('{"op":"subscribe","args":["klineV2.1.BTCUSD"]}')
```

> Response Example - format of all responses

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

Currently supported intervals:

* 1 3 5 15 30
* 60 120 240 360 720
* D
* W
* M
* Y

<aside class="notice">
If <code>confirm</code> is <code>True</code>, the data is the final tick for the interval. Otherwise, it is a snapshot.
</aside>



## Private Topics
### position
> How to Subscribe

```javascript
ws.send('{"op": "subscribe", "args": ["position"]}')
```

> Response Example - format of all responses

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


### execution
> How to Subscribe

```javascript
ws.send('{"op": "subscribe", "args": ["execution"]}')
```

> Response Example - format of all responses

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


### order
> How to Subscribe

```javascript
ws.send('{"op": "subscribe", "args": ["order"]}')
```

> Response Example - format of all responses

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
            "last_exec_price": "8300"
        }
    ]
}
```


### stop_order
> How to Subscribe

```javascript
ws.send('{"op": "subscribe", "args": ["stop_order"]}')
```

> Response Example - format of all responses

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
            "timestamp": "2020-01-14T14:11:22.062Z"
        }
    ]
}
```
