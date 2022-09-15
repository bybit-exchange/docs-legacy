# t(:websocket)
## t(:websocketauthentication)
> t(:websocket_codequote_auth_spot)

```javascript
{
    "req_id": "10001", // optional
    "op": "auth",
    "args": [
        "api_key",
        1662350400000, //expires greater than currentTimeStamp
        "singature"
    ]
}

```

```python--pybit
# based on: https://github.com/bybit-exchange/pybit/blob/master/pybit/_http_manager.py

import hmac
import json
import time
import websocket

api_key = ""
api_secret = ""

# Generate expires.
expires = int((time.time() + 1) * 1000)

# Generate signature.
signature = str(hmac.new(
    bytes(api_secret, "utf-8"),
    bytes(f"GET/realtime{expires}", "utf-8"), digestmod="sha256"
).hexdigest())

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
t(:spot_websocket_endpoints_aside)
</aside>

t(:spot_websocket_para_endpoint_v3)

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
// req_id is a customised id, which is optional
ws.send(JSON.stringify({"req_id": "100001", "op": "ping"}));
```

> t(:codequote_responseExample)

```javascript
// with req_id
{"op":"pong","args":[1661741630642],"req_id":"100001","conn_id":"706b870c"}

// without req_id
{"op":"pong","args":[1661741654529],"conn_id":"706b870c"}
```


<aside class="warning">
t(:websocket_aside_heartbeat)
</aside>


## t(:websocketlimit)
<p>t(:websocket_spot_para_apiLimit)</P>
<p>t(:websocket_max_50_connection)</p>


## t(:subscribe)
### t(:websocketfilters)

> t(:websocket_codequote_filters1)

```javascript
// Subscribing to the trade data for BTCUSDT
{
    "req_id": "10001", // optional
    "op": "subscribe",
    "args": [
        "trade.BTCUSDT"
    ]
}
```

> t(:spot_websocket_many_symbol_desc)

```javascript
// Example: Subscribing to the trade data for BTCUSDT and ETHUSDT
{
    "req_id": "10001", // optional
    "op": "subscribe",
    "args": [
        "trade.BTCUSDT",
        "trade.ETHUSDT
    ]
}
```

t(:spot_websocket_subscribe_desc_v3)
<aside class="warning">
t(:spot_websocket_subscribe_args_warning_v3)
</aside>

### t(:websocketunfilters)

t(:spot_websocket_unsubscribe_desc_v3)

```javascript
// Example: unsubscribing to the trade data for BTCUSDT and ETHUSDT
{
    "req_id": "10002", // optional
    "op": "unsubscribe",
    "args": [
        "trade.BTCUSDT",
        "trade.ETHUSDT
    ]
}
```

```javascript
// unsubscribe response sample
{
    "op": "unsubscribe",
    "success": true,
    "req_id": "10002",
    "ret_msg": "unsubscribe",
    "conn_id": "46f097b7"
}
```

## t(:websocketresponse)
> t(:websocket_codequote_response)

```javascript
{
    "op": "subscribe",
    "success": true,
    "req_id": "10001",
    "ret_msg": "subscribe",
    "conn_id": "46f097b7"
}
```

t(:spot_websocket_para_response)

## t(:publictopics)
### t(:websocketdepth)
> t(:codequote_subscribe)

```javascript
{
    "req_id": "depth00001", //optional
    "op": "subscribe",
    "args": [
        "orderbook.40.BTCUSDT"
    ]
}
```

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "data": {
        "s": "BTCUSDT",
        "t": 1661743689733,
        "b": [
            [
                "19721.9",
                "0.784806"
            ],
            [
                "19719.37",
                "1.215194"
            ],
            [
                "19713.18",
                "0.001"
            ]
            ...
        ],
        "a": [
            [
                "19721.91",
                "0.192687"
            ],
            [
                "19727.85",
                "0.914128"
            ],
            [
                "19731.24",
                "1.008273"
            ]
            ...
        ]
    },
    "type": "delta",
    "topic": "orderbook.40.BTCUSDT",
    "ts": 1661743689735
}
```

t(:spot_websocket_orderbook_desc_v3)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:----- |----- |
| t | long | t(:spot_timestamp2) |
| s | string | t(:spot_symbol) |
| b | list | t(:spot_bid_v3) |
| a | list | t(:spot_ask_v3) |
| ts | long | t(:spot_wss_ts) |


### t(:websockettrade)
> t(:codequote_subscribe)

```javascript
{
    "req_id": "trade0001", //optional
    "op": "subscribe",
    "args": [
        "trade.BTCUSDT"
    ]
}
```

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "data": {
        "v": "2100000000001992601",
        "t": 1661742109857,
        "p": "19706.87",
        "q": "0.000158",
        "m": true
    },
    "type": "delta",
    "topic": "trade.BTCUSDT",
    "ts": 1661742109863
}
```

t(:spot_websocket_trade_desc_v3)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|v | string | t(:spot_v3_trade_v) |
|t | long | t(:spot_time) |
|p | string | t(:spot_price) |
|q | string | t(:spot_quantity) |
|m | boolean | t(:spot_side) |
| ts | long | t(:spot_wss_ts) |


### t(:websocketkline)
> t(:codequote_subscribe)

```javascript
{
    "req_id": "kline00001", //optional
    "op": "subscribe",
    "args": [
        "kline.1h.BTCUSDT"
    ]
}
```

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "data": {
        "t": 1661742000000,
        "s": "BTCUSDT",
        "c": "19685.55",
        "h": "19756.95",
        "l": "19674.61",
        "o": "19705.38",
        "v": "0.232154"
    },
    "type": "delta",
    "topic": "kline.1h.BTCUSDT",
    "ts": 1661745259605
}
```

t(:spot_websocket_kline_desc_v3)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t | long | t(:row_comment_startTime_ms) |
|s | string | t(:spot_symbol) |
|c | string | t(:spotClose) |
|h | string | t(:spotHigh) |
|l | string | t(:spotLow) |
|o | string | t(:spotOpen) |
|v | string | t(:spot_volume) |
| ts | long | t(:spot_wss_ts) |

### t(:websocketTickers)
> t(:codequote_subscribe)

```javascript
{
    "req_id": "ticker00001", //optional
    "op": "subscribe",
    "args": [
        "tickers.BTCUSDT"
    ]
}
```

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "data": {
        "t": 1661742216005,
        "s": "BTCUSDT",
        "o": "19820",
        "h": "20071.93",
        "l": "19365.85",
        "c": "19694.27",
        "v": "9997.246174",
        "qv": "197357775.97621786",
        "m": "-0.0063"
    },
    "type": "delta",
    "topic": "tickers.BTCUSDT",
    "ts": 1661742216011
}
```

t(:spot_websocket_symbol_ticker_desc_v3)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t | long | t(:spot_time) |
|s | string | t(:spot_symbol) |
|o | string | t(:spotOpen) |
|h | string | t(:spotHigh) |
|l | string | t(:spotLow) |
|c | string | t(:spotClose) |
|v | string | t(:spot_volume) |
|qv | string | t(:spot_quote_volume) |
|m | string | t(:spot_gains) |
| ts | long | t(:spot_wss_ts) |


### t(:websocektBookticker)
> t(:codequote_subscribe)

```javascript
{
    "req_id": "bookticker00001", //optional
    "op": "subscribe",
    "args": [
        "bookticker.BTCUSDT"
    ]
}
```

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "data": {
        "s": "BTCUSDT",
        "bp": "19693.04",
        "bq": "0.913957",
        "ap": "19694.27",
        "aq": "0.705447",
        "t": 1661742216108
    },
    "type": "delta",
    "topic": "bookticker.BTCUSDT",
    "ts": 1661742216109
}
```
t(:spot_websocket_ticker_desc_v3)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| s | string | t(:spot_symbol) |
| bp | string | t(:spot_buy_price) |
| bq | string | t(:spot_buy_qty) |
| ap | string | t(:spot_sell_price)|
| aq | boolean | t(:spot_sell_qty) |
| t | long | t(:spot_timestamp2) |
| ts | long | t(:spot_wss_ts) |


## t(:privatetopics)

### t(:outboundAccountInfo)

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "type": "snapshot",
    "topic": "outboundAccountInfo",
    "ts": "1662107217641",
    "data": [
        {
            "e": "outboundAccountInfo",
            "E": "1662107217640",
            "T": true,
            "W": true,
            "D": true,
            "B": [
                {
                    "a": "USDT",
                    "f": "176.81254174",
                    "l": "201.575"
                }
            ]
        }
    ]
}
```

t(:spotV3_outboundAccountInfo_desc)

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| e | string | t(:spot_event_type) |
| E | string | t(:spot_timestamp) |
| T | boolean | t(:spot_allow_trade) |
| W | boolean | t(:spot_allow_withdraw) |
| D | boolean | t(:spot_allow_deposit)|
| B | list | t(:spot_balance_change) |
| a | string | t(:spot_asset) |
| f | string | t(:spot_available_qty) |
| l | string | t(:spot_frozen_qty) |

### t(:websocketSpotOrder)

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "type": "snapshot",
    "topic": "order",
    "ts": "1662348310441",
    "data": [
        {
            "e": "order",
            "E": "1662348310441",
            "s": "BTCUSDT",
            "c": "spotx008",
            "S": "BUY",
            "o": "MARKET_OF_QUOTE",
            "f": "GTC",
            "q": "20",
            "p": "0",
            "X": "CANCELED",
            "i": "1238261807653647872",
            "M": "1238225004531834368",
            "l": "0.001007",
            "z": "0.001007",
            "L": "19842.02",
            "n": "0",
            "N": "BTC",
            "u": true,
            "w": true,
            "m": false,
            "O": "1662348310368",
            "Z": "19.98091414",
            "A": "0",
            "C": false,
            "v": "0",
            "d": "NO_LIQ",
            "t": "2100000000002220938"
        }
    ]
}
```
t(:spotV3_order_desc)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| e | string | t(:spot_event_type) |
| E | string | t(:spot_event_timestamp) |
| s | string | t(:spot_symbol) |
| c | string | t(:spot_order_client_id) |
| S | string | t(:spot_side_private) |
| <a href="#order-type-type-ordertypes">o</a> | string | t(:spotType) |
| <a href="#timeinforce-timeinforce">f</a> | string | t(:row_comment_timeInForce) |
| q | string | t(:spot_quantity) |
| p | string | t(:spot_price) |
| <a href="#order-status-status">X</a> | string | t(:spotStatus) |
| i | string | t(:spot_order_id) |
| M | string | t(:spot_match_order_id) |
| l | string | t(:spot_recent_qty) |
| z | string | t(:spot_cumulative_qty) |
| L | string | t(:spot_recent_price) |
| n | string | t(:spot_fee) |
| N | string | t(:spot_fee_symbol) |
| u | boolean | t(:spot_is_normal) |
| w | boolean | t(:spot_is_working) |
| m | boolean | t(:spot_is_limit_maker) |
| O | string | t(:spot_order_create_timestamp) |
| Z | string | t(:spot_cumulative_trade) |
| A | string | t(:spot_match_account_id) |
| C | boolean | t(:spot_is_close) |
| v | string | t(:spot_leverage) |
| d | string | t(:spot_liquidation_type) |
| t | string | t(:spotTicketId) |


### t(:websocketSpotStopOrder)

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "type": "snapshot",
    "topic": "stopOrder",
    "ts": "1662107217667",
    "data": [
        {
            "e": "stopOrder",
            "E": "1662107217667",
            "s": "BTCUSDT",
            "c": "spot01",
            "S": "BUY",
            "o": "LIMIT",
            "f": "GTC",
            "q": "0.01",
            "p": "20157.5",
            "X": "ORDER_NEW",
            "i": "1236239375040308480",
            "T": "1662107217613",
            "t": "0",
            "C": "1662107217613",
            "qp": "20157.86",
            "eo": "1236239375040308481",
            "ti": "0ef565e40fb3127b0b2951973d93d0d3",
            "si": "f79e810f69822d81"
        }
    ]
}
```
t(:spotV3_stopOrder)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| e | string | t(:spot_event_type) |
| E | string | t(:spot_event_timestamp) |
| s | string | t(:spot_symbol) |
| c | string | t(:spot_order_client_id) |
| S | string | t(:spot_side_private) |
| <a href="#order-type-type-ordertypes">o</a> | string | t(:spotType) |
| <a href="#timeinforce-timeinforce">f</a> | string | t(:row_comment_timeInForce) |
| q | string | t(:spot_quantity) |
| p | string | t(:spot_price) |
| <a href="#order-status-status">X</a> | string | t(:spot_stop_orderStatus) |
| i | string | t(:spot_order_id) |
| T | string | t(:spot_stop_orderCreateTime) |
| t | string | t(:spot_stop_orderTriggerTime) |
| C | string | t(:spot_stop_orderUpdateTime) |
| qp | string | t(:spot_stop_marketPrice) |
| eo | string | t(:spot_stop_normalOrderId) |
| ti | string | t(:spot_stop_siTi) |
| si | string | t(:spot_stop_siTi) |


### t(:ticketInfo)

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "type": "snapshot",
    "topic": "ticketInfo",
    "ts": "1662348310388",
    "data": [
        {
            "e": "ticketInfo",
            "E": "1662348310386",
            "s": "BTCUSDT",
            "q": "0.001007",
            "t": "1662348310373",
            "p": "19842.02",
            "T": "2100000000002220938",
            "o": "1238261807653647872",
            "c": "spotx008",
            "O": "1238225004531834368",
            "a": "533287",
            "A": "642908",
            "m": false,
            "S": "BUY"
        }
    ]
}
```

t(:spotV3_ticketInfo_desc)

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| e | string | t(:spot_event_type) |
| E | string | t(:spot_event_timestamp) |
| s | string | t(:spot_symbol) |
| q | string | t(:spot_quantity) |
| t | string | t(:spot_timestamp) |
| p | string | t(:spot_price) |
| T | string | t(:spot_transactId) |
| o | string | t(:spot_order_id) |
| c | string | t(:spot_order_client_id) |
| O | string | t(:spot_match_order_id) |
| a | string | t(:spot_account_id) |
| A | string | t(:spot_match_account_id) |
| m | boolean | t(:spot_ticket_info_maker) |
| S | string | t(:spot_ticket_info_side) |
