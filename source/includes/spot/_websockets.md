# t(:websocket)
## t(:websocketauthentication)
> t(:websocket_codequote_auth_spot)

```python
# based on: https://github.com/verata-veritatis/pybit/blob/master/pybit/__init__.py

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


t(:spot_websocket_para_endpoint)

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

t(:spot_websocket_subscribe_desc)

```javascript
// Subscribing to the trade data for BTCUSDT
ws.send('{"symbol":"BTCUSDT","topic":"trade","event":"sub","params":{"binary":false}}');
```

> t(:spot_websocket_many_symbol_desc)

```javascript
// Example: Subscribing to the trade data for BTCUSDT and ETHUSDT
ws.send('{"symbol":"BTCUSDT,ETHUSDT","topic":"trade","event":"sub","params":{"binary":false}}');
```


## t(:websocketresponse)
> t(:websocket_codequote_response)

```javascript
{
  "topic":"trade",
  "event":"sub",
  "symbol":"BTCUSDT",
  "params":{
    "binary":"false"
  },
  "code":"0",
  "msg":"Success"
}
```

t(:spot_websocket_para_response)

## t(:publictopics)
### t(:websockettrade)
> t(:codequote_subscribe)

```javascript
{
    "topic": "trade",
    "event": "sub",
    "symbol": "BTCUSDT",
    "params": {
        "binary": false
    }
}
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "symbol":"BTCUSDT",
    "symbolName":"BTCUSDT",
    "topic":"trade",
    "params":{
        "realtimeInterval":"24h",
        "binary":"false"
    },
    "data":[
        {
            "v":"929681067596857345",
            "t":1625562619577,
            "p":"34924.15",
            "q":"0.00027",
            "m":true
        }
    ],
    "f": true,
    "sendTime": 1626249138535,
    "shared": false
}
```

t(:spot_websocket_trade_desc_v1)

t(:spot_public_websocket_frequency_300)

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| data > v | string | t(:spot_transactId) |
| data > t | string | t(:spot_time) |
| data > p | string | t(:spot_price)|
| data > q | boolean | t(:spot_quantity) |
| data > m | boolean | t(:spot_sMessage) |
| f | boolean | t(:spot_first) |


### t(:websocketrealtimes)
> t(:codequote_subscribe)

```javascript
{
    "topic": "realtimes",
    "event": "sub",
    "symbol": "BTCUSDT",
    "params": {
        "binary": false
    }
}
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
  "symbol": "BTCUSDT",
  "symbolName": "BTCUSDT",
  "topic": "realtimes",
  "data": [{
    "t": "1565592599015",
    "s": "BTCUSDT",
    "sn": "BTCUSDT",
    "c": "12750.63",
    "h": "12800.96",
    "l": "12740.78",
    "o": "12780.23",
    "v": "73013.575",
    "qv": "15726612.498168",
    "m": "-0.0401",
    "e": 301
    }],
  "f": false,
  "sendTime": 1626252046034,
  "shared": false
}
```

t(:spot_websocket_ticker_desc_v1)

t(:spot_public_websocket_frequency_300)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| data > t | number | t(:spot_timestamp) |
| data > s | string | t(:spot_symbol) |
| data > sn | string | t(:spot_symbol) |
| data > c | string | t(:spot_close)|
| data > h | string | t(:spot_high)|
| data > l | string | t(:spot_low)|
| data > o | string | t(:spot_open)|
| data > v | string | t(:spot_volume)|
| data > qv | string | t(:spot_quote_volume)|
| data > m | string | t(:spot_gains)|
| data > e | number | t(:spotExchangeId)|
| f | boolean | t(:spot_first) |


### t(:websocketkline)
> t(:codequote_subscribe)

```javascript
{
    "topic": "kline_1m",
    "event": "sub",
    "symbol": "BTCUSDT",
    "params": {
        "binary": false
    }
}
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
  "symbol": "BTCUSDT",
  "symbolName": "BTCUSDT",
  "topic": "kline",
  "params": {
    "realtimeInterval": "24h",
    "klineType": "15m",
    "binary": "false"
  },
  "data": [{
    "t": 1565595900000,
    "s": "BTCUSDT",
    "sn": "BTCUSDT",
    "c": "11436.14",
    "h": "11437",
    "l": "11381.89",
    "o": "11381.89",
    "v": "16.3306"
  }],
  "f": true,
  "sendTime": 1626252389284,
  "shared": false
}
```

t(:spot_websocket_kline_desc_v1)

t(:spot_public_websocket_frequency_300)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t | number | t(:row_comment_resp_open_time) |
| s | string | t(:spot_symbol) |
| sn | string | t(:spot_symbol) |
| c | string | t(:spot_close)|
| h | string | t(:spot_high)|
| l | string | t(:spot_low)|
| o | string | t(:spot_open)|
| v | string | t(:spot_volume)|
| f | boolean | t(:spot_first) |

### t(:websocketdepth)
> t(:codequote_subscribe)

```javascript
{
    "topic": "depth",
    "event": "sub",
    "symbol": "BTCUSDT",
    "params": {
        "binary": false
    }
}
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
  "symbol": "BTCUSDT",
  "symbolName": "BTCUSDT",
  "topic": "depth",
  "params": {
    "realtimeInterval": "24h",
    "binary": "false"
  },
  "data": [{
    "e": 301,
    "s": "BTCUSDT",
    "t": 1565600357643,
    "v": "112801745_18",
    "b": [
      ["11371.49", "0.0014"],
      ["11371.12", "0.2"],
      ["11369.97", "0.3523"],
      ["11369.96", "0.5"],
      ["11369.95", "0.0934"],
      ["11369.94", "1.6809"],
      ["11369.6", "0.0047"],
      ["11369.17", "0.3"],
      ["11369.16", "0.2"],
      ["11369.04", "1.3203"],
    ]
    "a": [
      ["11375.41", "0.0053"],
      ["11375.42", "0.0043"],
      ["11375.48", "0.0052"],
      ["11375.58", "0.0541"],
      ["11375.7", "0.0386"],
      ["11375.71", "2"],
      ["11377", "2.0691"],
      ["11377.01", "0.0167"],
      ["11377.12", "1.5"],
      ["11377.61", "0.3"]
    ],
    "o": 0
  }],
  "f": true,
  "sendTime": 1626253839401,
  "shared": false
}
```

t(:spot_websocket_orderbook_desc_v1)

t(:spot_public_websocket_frequency_300)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:----- |----- |
| e | number | t(:spotExchangeId) |
| t | number | t(:spot_timestamp) |
| s | string | t(:spot_symbol) |
| v | string | t(:spot_version) |
| b | array | t(:spot_buys) |
| a | array | t(:spot_sells) |
| f | boolean | t(:spot_first) |
| o | number | t(:spotIgnore) |

### t(:websocketmergeddepth)
> t(:codequote_subscribe)

```javascript
{
    "topic": "mergedDepth",
    "event": "sub",
    "symbol": "BTCUSDT",
    "params": {
        "binary": false,
        "dumpScale": 1
    }
}
```


> t(:codequote_responseExampleFormatAll)

```javascript
{
  "symbol":"ETHUSDT",
  "symbolName":"ETHUSDT",
  "topic":"mergedDepth",
  "params":{"
    realtimeInterval":"24h",
    "dumpScale":"1",
    "binary":"false"
    },
  "data":[{
    "e":301,
    "s":"ETHUSDT",
    "t":1622541360174,
    "v":"10544_1",
    "b":[
          ["12001","1"],
          ["12000","0.8"],
          ["10000","1"],
          ["4988","0.5"],
          ["4987","0.8"],
          ["4986","1"],
          ["4985","0.9"],
          ["4984","1.1"],
          ["4983","1.3"],
          ["4982","0.5"],
          ["100000","0.94"]
        ],
    "a": [
          ["12001","1"],
          ["12000","0.8"],
          ["10000","1"],
          ["4988","0.5"],
          ["4987","0.8"],
          ["4986","1"],
          ["4985","0.9"],
          ["4984","1.1"],
          ["4983","1.3"],
          ["4982","0.5"],
          ["100000","0.94"]
    ],
    "o":0
    }],
    "f":false,
    "sendTime":1622541360301,
    "shared":false
}
```

t(:spot_websocket_orderbook_merge_desc_v1)

t(:spot_public_websocket_frequency_300)

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:----- |----- |
| t | number | t(:spot_timestamp) |
| s | string | t(:spot_symbol) |
| v | string | t(:spot_version) |
| b | array | t(:spot_buys) |
| a | array | t(:spot_sells) |
| f | boolean | t(:spot_first) |

### t(:websocketdiffdepth)
> t(:codequote_subscribe)

```javascript
{
    "topic": "diffDepth",
    "event": "sub",
    "symbol": "BTCUSDT",
    "params": {
        "binary": false
    }
}
```


> t(:codequote_responseExampleFormatAll)

```javascript
{
  "symbol": "BTCUSDT",
  "symbolName": "BTCUSDT",
  "topic": "diffDepth",
  "params": {
    "realtimeInterval": "24h",
    "binary": "false"
  },
  "data": [{
    "e": 301,
    "s": "BTCUSDT",
    "t": 1565600357643,
    "v": "112801745_18",
    "b": [
      ["11371.49", "0.0014"],
      ["11371.12", "0.2"],
      ["11369.97", "0.3523"],
      ["11369.96", "0.5"],
      ["11369.95", "0.0934"],
      ["11369.94", "1.6809"],
      ["11369.6", "0.0047"],
      ["11369.17", "0.3"],
      ["11369.16", "0.2"],
      ["11369.04", "1.3203"],
    "a": [
      ["11375.41", "0.0053"],
      ["11375.42", "0.0043"],
      ["11375.48", "0.0052"],
      ["11375.58", "0.0541"],
      ["11375.7", "0.0386"],
      ["11375.71", "2"],
      ["11377", "2.0691"],
      ["11377.01", "0.0167"],
      ["11377.12", "1.5"],
      ["11377.61", "0.3"]
    ],
    "o": 0
  }],
  "f": true,
  "sendTime": 1626253839401,
  "shared": false
}
```

t(:spot_websocket_orderbook_delta_desc_v1)

t(:spot_public_websocket_frequency_300)

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| e | number | t(:spotExchangeId) |
| t | number | t(:spot_timestamp) |
| s | string | t(:spot_symbol) |
| v | string | t(:spot_version) |
| b | array | t(:spot_buys) |
| a | array | t(:spot_sells) |
| f | boolean | t(:spot_first) |
| o | number | t(:spotIgnore) |

## t(:publictopics_v2)
### t(:websocketv2depth)
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

t(:spot_public_websocket_frequency_250)

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol | string | t(:spot_symbol) |
| symbolName | string | t(:spot_symbol) |
| binary | string | t(:spot_binary) |
| t | number | t(:spot_timestamp) |
| s | string | t(:spot_symbol) |
| v | string | t(:spot_version) |
| b | string | t(:spot_buy) |
| a | string | t(:spot_sell) |

### t(:websocketv2kline)
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

t(:spot_public_websocket_frequency_250)

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol | string | t(:spot_symbol) |
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

### t(:websocketv2trade)
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

t(:spot_public_websocket_frequency_250)

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol | string | t(:spot_symbol) |
| binary | string | t(:spot_binary) |
| symbolName | string | t(:spot_symbol) |
| t | number | t(:spot_timestamp) |
| p | string | t(:spot_price) |
| q | string | t(:spot_quantity)|
| m | boolean | t(:spot_side) |

### t(:websocketv2bookticker)
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

t(:spot_public_websocket_frequency_250)

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol | string | t(:spot_symbol) |
| binary | string | t(:spot_binary) |
| symbolName | string | t(:spot_symbol) |
| bidPrice | string | t(:spot_buy_price) |
| bidQty | string | t(:spot_buy_qty) |
| askPrice | string | t(:spot_sell_price)|
| askQty | boolean | t(:spot_sell_qty) |
| time | member | t(:spot_timestamp) |


### t(:websocketv2realtimes)
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

t(:spot_public_websocket_frequency_250)

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol | string | t(:spot_symbol) |
| binary | string | t(:spot_binary) |
| symbolName | string | t(:spot_symbol) |
| t | number | t(:spot_timestamp) |
| s | string | t(:spot_symbol) |
| c | string | t(:spot_close)|
| h | string | t(:spot_high)|
| l | string | t(:spot_low)|
| o | string | t(:spot_open)|
| v | string | t(:spot_volume)|
| qv | string | t(:spot_quote_volume)|
| m | string | t(:spot_gains)|


## t(:privatetopics)

t(:spot_private_topics_auth_sub)

### t(:outboundAccountInfo)
> t(:spot_private_topics_auth_sub)

> t(:codequote_responseExampleFormatAll)

```javascript
{
  "e": "outboundAccountInfo",   
  "E": 1499405658849,           
  "T": true,                   
  "W": true,                    
  "D": true,                    
  "B": [                        
    {
      "a": "LTC",               
      "f": "17366.18538083",    
      "l": "0.00000000"         
    }
  ]
}
```

t(:outboundAccountInfo_desc)

t(:spot_public_websocket_frequency_realtime)

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| e | string | t(:spot_event_type) |
| E | member | t(:spot_timestamp) |
| T | boolean | t(:spot_allow_trade) |
| W | boolean | t(:spot_allow_withdraw) |
| D | boolean | t(:spot_allow_deposit)|
| B | string | t(:spot_balance_change) |
| a | string | t(:spot_asset) |
| f | string | t(:spot_available_qty) |
| l | string | t(:spot_frozen_qty) |

### t(:executionReport)
> t(:spot_private_topics_auth_sub)

> t(:codequote_responseExampleFormatAll)

```javascript
{
  "e": "executionReport",      
  "E": 1499405658658,            
  "s": "ETHBTC",                 
  "c": 1000087761,               
  "S": "BUY",                    
  "o": "LIMIT",                  
  "f": "GTC",                    
  "q": "1.00000000",             
  "p": "0.10264410",             
  "X": "NEW",                    
  "i": 4293153,     
  "M": "0",             
  "l": "0.00000000",             
  "z": "0.00000000",             
  "L": "0.00000000",             
  "n": "0",                      
  "N": null,                     
  "u": true,                     
  "w": true,                     
  "m": false,                    
  "O": 1499405658657,            
  "Z": "0.00000000",
  "A": "0",
  "C": false,
  "v": "0"              
}
```
t(:executionReport_desc)

t(:spot_public_websocket_frequency_realtime)

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| e | string | t(:spot_event_type) |
| E | member | t(:spot_event_timestamp) |
| s | string | t(:spot_symbol) |
| c | string | t(:spot_order_client_id) |
| S | string | t(:spot_side) |
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
| m | boolean | t(:sopt_is_maker) |
| O | string | t(:spot_order_create_timestamp) |
| Z | string | t(:spot_cumulative_trade) |
| A | string | t(:spot_match_account_id) |
| C | boolean | t(:spot_is_close) |
| v | string | t(:spot_leverage) |


### t(:ticketInfo)
> t(:spot_private_topics_auth_sub)

> t(:codequote_responseExampleFormatAll)

```javascript
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
  "A":"10024"}
```

t(:ticketInfo_para)

t(:spot_public_websocket_frequency_realtime)

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| e | string | t(:spot_event_type) |
| E | member | t(:spot_event_timestamp) |
| s | string | t(:spot_symbol) |
| q | string | t(:spot_quantity) |
| t | string | t(:spot_timestamp) |
| p | string | t(:spot_price) |
| T | string | t(:spot_ticket_id) |
| o | string | t(:spot_order_id) |
| c | string | t(:spot_order_client_id) |
| O | string | t(:spot_match_order_id) |
| a | string | t(:spot_account_id) |
| A | string | t(:spot_match_account_id) |
