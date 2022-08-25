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

```

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript

```

t(:spot_websocket_orderbook_desc_v1)

t(:spot_public_websocket_frequency_300_delay_650)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:----- |----- |
| t(:row_parameter_symbol) | string | t(:spot_symbol) |


### t(:websockettrade)
> t(:codequote_subscribe)

```javascript

```

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript

```

t(:spot_websocket_trade_desc_v1)

t(:spot_public_websocket_frequency_300_delay_400)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_symbol) | string | t(:spot_symbol) |


### t(:websocketkline)
> t(:codequote_subscribe)

```javascript

```

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript

```

t(:spot_websocket_kline_desc_v1)

t(:spot_public_websocket_frequency_300_delay_400)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:websocketrealtimes)
> t(:codequote_subscribe)

```javascript

```

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript

```

t(:spot_websocket_ticker_desc_v1)

t(:spot_public_websocket_frequency_300_delay_400)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:websocketBid1Ask1)
> t(:codequote_subscribe)

```javascript

```

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript

```

t(:新建一個key作為給買1賣1這個推送的描述)

t(:新建一個key作為買1賣1的頻率描述)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


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
