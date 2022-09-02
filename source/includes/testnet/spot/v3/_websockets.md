# t(:websocket)
## t(:websocketauthentication)
> t(:websocket_codequote_auth_spot)

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
        "orderbook.200.BTCUSDT"
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
    "topic": "orderbook.200.BTCUSDT",
    "ts": 1661743689735
}
```

t(:spot_websocket_orderbook_desc_v3)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:----- |----- |
| t | number | t(:spot_timestamp2) |
| s | string | t(:spot_symbol) |
| b | list | t(:spot_bid_v3) |
| a | list | t(:spot_ask_v3) |


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
|t | number | t(:spot_time) |
|p | string | t(:spot_price) |
|q | string | t(:spot_quantity) |
|m | boolean | t(:spot_side) |


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
|t | number | t(:row_comment_startTime_ms) |
|s | string | t(:spot_symbol) |
|c | string | t(:spotClose) |
|h | string | t(:spotHigh) |
|l | string | t(:spotLow) |
|o | string | t(:spotOpen) |
|v | string | t(:spot_volume) |

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
|t | number | t(:spot_time) |
|s | string | t(:spot_symbol) |
|o | string | t(:spotOpen) |
|h | string | t(:spotHigh) |
|l | string | t(:spotLow) |
|c | string | t(:spotClose) |
|v | string | t(:spot_volume) |
|qv | string | t(:spot_quote_volume) |
|m | string | t(:spot_gains) |


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
| t | number | t(:spot_timestamp2) |


## t(:privatetopics)
t(:spot_private_topics_auth_sub)

### t(:outboundAccountInfo)
> t(:spot_private_topics_auth_sub)

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript
[
    {
        "e":"outboundAccountInfo",
        "E":"1629969654753",
        "T":true,
        "W":true,
        "D":true,
        "B":[
            {
                "a":"BTC",
                "f":"10000000097.1982823144",
                "l":"0"
            }
        ]
    }
]
```

t(:outboundAccountInfo_desc)

t(:spot_public_websocket_frequency_realtime)

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

### t(:executionReport)
> t(:spot_private_topics_auth_sub)

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "e": "executionReport",
    "E": "1661505745347",
    "s": "BITUSDT",
    "c": "1661505744705",
    "S": "BUY",
    "o": "MARKET_OF_QUOTE",
    "f": "GTC",
    "q": "20",
    "p": "0",
    "X": "CANCELED",
    "i": "1231193858535151104",
    "M": "1231190924099373824",
    "l": "14.16",
    "z": "14.16",
    "L": "1.4121",
    "n": "0.01416",
    "N": "BIT",
    "u": true,
    "w": true,
    "m": true,
    "O": "1661505745176",
    "Z": "19.995336",
    "A": "0",
    "C": false,
    "v": "0",
    "d": "NO_LIQ",
    "t": "2120000000001252630"
}
```
t(:executionReport_desc)

t(:spot_public_websocket_frequency_realtime)

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


### t(:stop_executionReport)
> t(:spot_private_topics_auth_sub)

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript
[
  {
      "e": "stop_executionReport",
      "E": "1660031832249",
      "s": "BTCUSDT",
      "c": "1660031262869",
      "S": "BUY",
      "o": "MARKET_OF_QUOTE",
      "f": "GTC",
      "q": "0",
      "p": "0",
      "X": "ORDER_CANCELED",
      "i": "1218825007084354304",
      "T": "1660031263181",
      "t": "0",
      "C": "1660031832223",
      "qp": "23668.86",
      "eo": "1218825007084354305",
      "ti": "4add1fe84e577026",
      "si": "bc86964648a3c395"
  }
]
```
t(:stop_executionReport_desc)

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
> t(:spot_private_topics_auth_sub)

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript
[
  {
    "e":"ticketInfo",
    "E":"1621912542359",
    "s":"BTCUSDT",
    "q":"0.001639",
    "t":"1621912542314",
    "p":"61000.0",
    "T":"899062000267837441",
    "o":"899048013515737344",
    "c":"1621910874883",
    "O":"899062000118679808",
    "a":"10043",
    "A":"10024",
    "m":true,
    "S":"BUY"
  }
]
```

t(:ticketInfo_para)

t(:spot_public_websocket_frequency_realtime)

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

