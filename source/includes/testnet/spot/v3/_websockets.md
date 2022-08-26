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
ws.send(JSON.stringify({"ping": 1535975085052}));
```

> t(:codequote_responseExample)

```javascript
{"pong": 1535975085152}
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
// Subscribing to the trade data for BTCUSDT
ws.send('{"symbol":"BTCUSDT","topic":"trade","event":"sub","params":{"binary":false}}');
```

> t(:spot_websocket_many_symbol_desc)

```javascript
// Example: Subscribing to the trade data for BTCUSDT and ETHUSDT
ws.send('{"symbol":"BTCUSDT,ETHUSDT","topic":"trade","event":"sub","params":{"binary":false}}');
```

t(:spot_websocket_subscribe_desc)

### t(:websocketunfilters)

t(:spot_websocket_unsubscribe_desc)

## t(:websocketresponse)
> t(:websocket_codequote_response)

```javascript

```

t(:spot_websocket_para_response)

## t(:publictopics)
### t(:websocketdepth)
> t(:codequote_subscribe)

```javascript
{
    "topic": "depth",
    "event": "sub",
    "params": {
        "symbol": "BTCUSDT",
        "binary": false
    }
}
```

```python--pybit

```

> t(:codequote_snapshot)

```javascript
{
  "topic": "depth",
  "params": {
    "symbol": "BTCUSDT",
    "binary": "false",
    "symbolName": "BTCUSDT"
  },
  "data": {
    "s": "BTCUSDT",
    "t": 1582001376853,
    "v": "13850022_2",
    "b": [
      [
        "9780.79",
        "0.01"
      ],
      [
        "9780.5",
        "0.1"
      ],
      [
        "9780.4",
        "0.517813"
      ], ...
    "a": [
      [
        "9781.21",
        "0.042842"
      ],
      [
        "9782",
        "0.3"
      ],
      [
        "9782.1",
        "0.226"
      ], ...
    ]
  }
}
```
t(:spot_websocket_orderbook_desc_v2)

t(:spot_public_websocket_frequency_100)

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| topic | string | t(:spot_topic) |
| t(:row_parameter_symbol) | string | t(:spot_symbol) |
| symbolName | string | t(:spot_symbol) |
| binary | string | t(:spot_binary) |
| t | number | t(:spot_timestamp2) |
| s | string | t(:spot_symbol) |
| v | string | t(:spot_version) |
| b | string | t(:spot_buy) |
| a | string | t(:spot_sell) |

### t(:websockettrade)
> t(:codequote_subscribe)

```javascript
{
    "topic": "trade",
    "params": {
        "symbol": "BTCUSDT",
        "binary": false
    },
    "event": "sub"
}
```

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript
{
  "topic": "trade",
  "params": {
    "symbol": "BTCUSDT",
    "binary": "false",
    "symbolName": "BTCUSDT"
  },
  "data": {
    "v": "564265886622695424",
    "t": 1582001735462,
    "p": "9787.5",
    "q": "0.195009",
    "m": true
  }
}
```

t(:spot_websocket_trade_desc_v2)

t(:spot_public_websocket_frequency_near_realtime)

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| topic | string | t(:spot_topic) |
| t(:row_parameter_symbol) | string | t(:spot_symbol) |
| binary | string | t(:spot_binary) |
| symbolName | string | t(:spot_symbol) |
| v | string | t(:spot_transactId) |
| t | number | t(:spot_time) |
| p | string | t(:spot_price) |
| q | string | t(:spot_quantity)|
| m | boolean | t(:spot_side) |

### t(:websocketkline)
> t(:codequote_subscribe)

```javascript
{
    "topic": "kline",
    "event": "sub",
    "params": {
        "symbol": "BTCUSDT",
        "klineType": "1m",
        "binary": false
    }
}
```

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript
{
  "topic": "kline",
  "params": {
    "symbol": "BTCUSDT",
    "binary": "false",
    "klineType": "1m",
    "symbolName": "BTCUSDT"
  },
  "data": {
    "t": 1582001880000,
    "s": "BTCUSDT",
    "sn": "BTCUSDT",
    "c": "9799.4",
    "h": "9801.4",
    "l": "9798.91",
    "o": "9799.4",
    "v": "15.917433"
  }
}
```
t(:spot_websocket_kline_desc_v2)

t(:spot_public_websocket_frequency_near_realtime)

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| topic | string | t(:spot_topic) |
| t(:row_parameter_symbol) | string | t(:spot_symbol) |
| binary | string | t(:spot_binary) |
| klineType | string | t(:spot_kline_type) |
| symbolName | string | t(:spot_symbol) |
| t | number | t(:row_comment_resp_open_time) |
| s | string | t(:spot_symbol) |
| sn | string | t(:spot_symbol) |
| c | string | t(:spot_close)|
| h | string | t(:spot_high)|
| l | string | t(:spot_low)|
| o | string | t(:spot_open)|
| v | string | t(:spot_volume)|


### t(:spot_websocket_tickers_v3)
> t(:codequote_subscribe)

```javascript
{
    "topic": "realtimes",
    "event": "sub",
    "params": {
        "symbol": "BTCUSDT",
        "binary": false
    }
}
```

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript
{
  "topic": "realtimes",
  "params": {
    "symbol": "BTCUSDT",
    "binary": "false",
    "symbolName": "BTCUSDT"
  },
  "data": {
    "t": 1582001616500,
    "s": "BTCUSDT",
    "o": "9736.5",
    "h": "9830.19",
    "l": "9455.71",
    "c": "9796.75",
    "v": "77211.561764",
    "qv": "740412516.91255711",
    "m": "0.0062"
  }
}
```
t(:spot_websocket_symbol_ticker_desc_v2)

t(:spot_public_websocket_frequency_near_realtime)

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| topic | string | t(:spot_topic) |
| t(:row_parameter_symbol) | string | t(:spot_symbol) |
| binary | string | t(:spot_binary) |
| symbolName | string | t(:spot_symbol) |
| t | number | t(:spot_time) |
| s | string | t(:spot_symbol) |
| c | string | t(:spot_close)|
| h | string | t(:spot_high)|
| l | string | t(:spot_low)|
| o | string | t(:spot_open)|
| v | string | t(:spot_volume)|
| qv | string | t(:spot_quote_volume)|
| m | string | t(:spot_gains)|


### t(:spot_websocekt_bookticker_v3)
> t(:codequote_subscribe)

```javascript
{
    "topic": "bookTicker",
    "event": "sub",
    "params": {
        "symbol": "BTCUSDT",
        "binary": false
    }
}
```

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript
{
  "topic": "bookTicker",
  "params": {
    "symbol": "BTCUSDT",
    "binary": "false",
    "symbolName": "BTCUSDT"
  },
  "data": {
    "symbol": "BTCUSDT",
    "bidPrice": "9797.79",
    "bidQty": "0.177976",
    "askPrice": "9799",
    "askQty": "0.65",
    "time": 1582001830346
  }
}
```
t(:spot_websocket_ticker_desc_v2)

t(:spot_public_websocket_frequency_250_delay_300)

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| topic | string | t(:spot_topic) |
| t(:row_parameter_symbol) | string | t(:spot_symbol) |
| binary | string | t(:spot_binary) |
| symbolName | string | t(:spot_symbol) |
| bidPrice | string | t(:spot_buy_price) |
| bidQty | string | t(:spot_buy_qty) |
| askPrice | string | t(:spot_sell_price)|
| askQty | boolean | t(:spot_sell_qty) |
| time | member | t(:spot_timestamp2) |


## t(:privatetopics)

t(:spot_private_topics_auth_sub)

### t(:outboundAccountInfo)
> t(:spot_private_topics_auth_sub)

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript

```

t(:outboundAccountInfo_desc)

t(:spot_public_websocket_frequency_realtime)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:executionReport)
> t(:spot_private_topics_auth_sub)

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript

```
t(:executionReport_desc)

t(:spot_public_websocket_frequency_realtime)

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:ticketInfo)
> t(:spot_private_topics_auth_sub)

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript

```

t(:ticketInfo_para)

t(:spot_public_websocket_frequency_realtime)

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
