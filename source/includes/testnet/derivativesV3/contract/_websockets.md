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

ws_url = "wss://stream-testnet.bybit.com/contract/private/v3"

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

t(:websocket_para_endpoint_contract)

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
// pong response sample for usdt, usdc perp and inverse
{
    "success": true,
    "ret_msg": "pong",
    "conn_id": "1a30f215-b7d2-4542-bac8-563a79963b35",
    "req_id": "",
    "op": "ping"
}

// pong response sample for usdc option
{"args":["1661495699455"],"op":"pong"}
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
ws.send('{"op":"subscribe","args":["publicTrade.BTCUSD"],"req_id": "customised_id"}}')
```

> t(:websocket_codequote_filters2)

```javascript
// Example: Subscribing to the trade data for BTCUSD and XRPUSD
ws.send('{"op":"subscribe","args":["publicTrade.BTCUSD", "publicTrade.XRPUSD"],"req_id": "customised_id"}')
```


t(:websocket_para_filters)

`ws.send('{"op": "subscribe", "args": ["topic.filter"],"req_id": "customised_id"}');`

t(:websocket_para_filters1)

`ws.send('{"op": "subscribe", "args": ["topic.filter", "topic.filter"],"req_id": "customised_id"}');`

t(:websocket_para_filters3)
t(:websocket_para_filter_resp)

### t(:websocketunsubfilters)
> t(:websocket_codequote_unsubfilters)

```javascript
// Unsubscribing from the trade data for ETHUSD
ws.send('{"op":"unsubscribe","args":["publicTrade.ETHUSD"],"req_id": "customised_id"}')
```

t(:websocket_para_unsubfilters)

`ws.send('{"op": "unsubscribe", "args": ["topic.filter", "topic.filter"],"req_id": "customised_id"}');`

### t(:intervals)
t(:websocket_para_intervals)

## t(:websocketresponse)
> t(:websocket_codequote_response)

```javascript
{
  "success": true,
  "ret_msg": "",
  "conn_id": "fd79c21d-df3c-4439-aaab-c802bcb60e02",
  "req_id": "customize_00001",
  "op": "subscribe"
}
```

t(:websocket_para_response)



## t(:publictopics)
### t(:websocketOrderBookDepth)

> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "req_id": "10110001", "args": ["orderbook.25.BTCUSDT","orderbook.500.BTCUSDT"]}')
```
> t(:codequote_snapshot)

```javascript
{
  "topic":"orderbook.25.BTCUSDT",
    "type":"snapshot",
    "ts":1658200820646,
    "data":{
    "s":"BTCUSDT",
      "b":[
      [
        "22220.00",
        "1.300"
      ],
      [
        "22221.00",
        "1.150"
      ]
    ],
      "a":[
      [
        "22236.00",
        "18.194"
      ],
      [
        "22236.50",
        "0.602"
      ]
    ],
      "u":3566050
  }
}
```


> t(:codequote_delta)

```javascript
{
  "topic":"orderbook.25.BTCUSDT",
    "type":"delta",
    "ts":1658200820655,
    "data":{
    "s":"BTCUSDT",
      "b":[
      [
        "22224.00",
        "0.001"
      ]
    ],
      "a":[
      [
        "22247.00",
        "1.406"
      ],
      [
        "22240.50",
        "9.046"
      ],
      [
        "22236.00",
        "18.195"
      ],
      [
        "22244.50",
        "0.397"
      ]
    ],
      "u":3566051
  }
}
```

t(:websocketOrderBook_contract)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|s |string |t(:row_comment_symbol)  |
|b|array |t(:row_comment_resp_bid)    |
|a |array|t(:row_comment_resp_ask)  |
|u |number |t(:row_comment_updated_id)  |



### t(:websockettrade)

> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "req_id": "10110001", "args": ["publicTrade.BTCUSDT"]}')
```

```python--pybit

```

> t(:codequote_responseExampleFormatAll)


```javascript
{
  "topic":"publicTrade.BTCUSDT",
    "type":"snapshot",
    "ts":1658143402593,
    "data":[
    {
      "T":1658143402590,
      "s":"BTCUSDT",
      "S":"Buy",
      "v":"0.001",
      "p":"23337.00",
      "L":"PlusTick",
      "i":"83010f18-4476-55c0-84ab-ebd243e156cf"
    }
  ]
}
```

t(:websocket_para_trade_ud)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|T |number |t(:row_response_comment_timestamp)  |
|s |string |t(:row_comment_symbol)  |
|S|string |t(:websocketTradeSide)    |
|v |string |t(:row_comment_position_size)  |
|p |string |t(:row_response_comment_price)  |
|L |string |t(:row_comment_position_tick_direction)  |
|i|string |t(:row_response_comment_trade_id)  |
|ts|string |t(:row_response_comment_time)  |
|BT|bool |t(:row_response_comment_blocktrade)  |

### t(:websocketTicker_v3)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "req_id": "10110001", "args": ["tickers.BTCUSDT"]}')
```

```python--pybit

```

> t(:codequote_snapshot)

```javascript
{
  "topic":"tickers.BTCUSDT",
    "type":"snapshot",
    "data":{
    "symbol":"BTCUSDT",
      "tickDirection":"ZeroMinusTick",
      "price24hPcnt":"0.032786",
      "lastPrice":"22019.00",
      "prevPrice24h":"21320.00",
      "highPrice24h":"22522.00",
      "lowPrice24h":"20745.00",
      "prevPrice1h":"22186.50",
      "markPrice":"22010.11",
      "indexPrice":"22009.01",
      "openInterest":"44334.438",
      "turnover24h":"4609010554.786498",
      "volume24h":"213532.606",
      "fundingRate":"0.0001",
      "nextFundingTime":"2022-07-18T16:00:00Z",
      "bid1Price":"22019.00",
      "bid1Size":"41.530",
      "ask1Price":"22019.50",
      "ask1Size":"7.041",
      "basisRate":"0",
      "deliveryFeeRate":"0"
  },
  "cs":14236992078,
    "ts":1658145103785070
}
```

> t(:codequote_delta)

```javascript
{
  "topic":"tickers.BTCUSDT",
    "type":"delta",
    "data":{
    "symbol":"BTCUSDT",
      "tickDirection":"PlusTick",
      "price24hPcnt":"0.032621",
      "lastPrice":"22015.50",
      "turnover24h":"4609049418.106998",
      "volume24h":"213534.371",
      "fundingRate":"0.0001",
      "nextFundingTime":"2022-07-18T16:00:00Z",
      "bid1Price":"22019.00",
      "bid1Size":"41.530",
      "ask1Price":"22019.50",
      "ask1Size":"7.041"
  },
  "cs":14236992274,
    "ts":1658145103883091
}

```

> t(:codequote_option)

```javascript
{
    "id": "tickers.BTC-29JUL22-26000-C-335648950-1658284651212",
    "topic": "tickers.BTC-29JUL22-26000-C",
    "ts": 1658284651212,
    "data": {
        "symbol": "BTC-29JUL22-26000-C",
        "bidPrice": "360",
        "bidSize": "36.7",
        "bidIv": "0.7828",
        "askPrice": "380",
        "askSize": "0.7",
        "askIv": "0.8005",
        "lastPrice": "160",
        "highPrice24h": "0",
        "lowPrice24h": "0",
        "markPrice": "412.017195",
        "indexPrice": "23479.75",
        "markPriceIv": "0.8283",
        "underlyingPrice": "23494.15",
        "openInterest": "305.89",
        "turnover24h": "0",
        "volume24h": "0",
        "totalVolume": "2884",
        "totalTurnover": "12808823",
        "delta": "0.24076634",
        "gamma": "0.00010067",
        "vega": "11.63078846",
        "theta": "-52.22100976",
        "predictedDeliveryPrice": "0",
        "change24h": "0"
    },
    "type": "snapshot"
}

```

t(:websocket_para_ticker_v3)

<aside class="warning">
t(:websocket_aside_instrumentInfo_ud)
</aside>


<p class="fake_header">t(:futuresResponseParameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|symbol |string |t(:row_comment_symbol)  |
|tickDirection|string |t(:row_comment_position_tick_direction)  |
|price24hPcnt|string|t(:row_comment_resp_price_24h_pcnt) |
|lastPrice |string |t(:row_comment_resp_last_price)  |
|prevPrice24h |string |t(:row_comment_resp_prev_price_24h)  |
|highPrice24h |string |t(:row_comment_resp_high_price_24h)  |
|lowPrice24h |string |t(:row_comment_resp_low_price_24h)  |
|markPrice |string |t(:row_comment_resp_mark_price)  |
|indexPrice |string |t(:row_comment_resp_index_price)  |
|openInterest |string |t(:row_comment_resp_open_interest). t(:row_comment_slow_update)  |
|turnover24h |string |t(:row_comment_resp_turnover_24h)  |
|volume24h |string |t(:row_comment_resp_volume_24h)  |
|nextFundingTime |string |t(:row_comment_resp_next_funding_time_v3)  |
|fundingRate |string |t(:row_comment_resp_funding_rate_v3) |
|predicatedFundingRate |string |t(:predicatedFundingRate_v3) |
|bid1Price|string|t(:row_comment_resp_bid_price) |
|bid1Size|string|t(:row_comment_resp_bid_size) |
|ask1Price|string|t(:row_comment_resp_ask_price) |
|ask1Size|string|t(:row_comment_resp_ask_size) |
|basisRate|string|t(:basisRate_v3) |
|deliveryFeeRate|string|t(:row_comment_resp_delivery_fee_rate_v3) |
|prevPrice1h |string |t(:row_comment_resp_prev_price_1h_v3)  |
|deliveryTime |string |t(:deliveryTime_v3)  |
|predicatedDeliveryPrice |string |t(:predicatedDeliveryPrice_v3)  |

<p class="fake_header">t(:optionResponseParameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_symbol) |string |t(:usdcSymbol) |
| bidPrice |string |t(:bidPrice) |
| bidSize |string |t(:bidSize) |
| bidIv |string |t(:bidIv) |
| askPrice |string |t(:askPrice) |
| askSize |string |t(:askSize) |
| askIv |string |t(:askIv) |
| lastPrice |string |t(:usdcLastPrice) |
| highPrice24h |string |t(:highPrice24h) |
| lowPrice24h |string |t(:lowPrice24h) |
| markPrice |string |t(:usdcMarkPrice) |
| indexPrice |string |t(:usdcIndexPrice) |
| markPriceIv |string |t(:markPriceIv) |
| underlyingPrice |string |t(:underlying) |
| openInterest |string |t(:openInterest) |
| turnover24h |string |t(:turnover24h) |
| volume24h |string |t(:volume24h) |
| totalVolume |string |t(:totalVolume) |
| totalTurnOver |string |t(:totalTurnOver) |
| delta |string |t(:delta) |
| gamma |string |t(:gamma) |
| theta |string |t(:theta) |
| vega |string |t(:vega) |
| predictedDeliveryPrice |string |t(:predictedDeliveryPrice) |
| change24h |string |t(:price24Pcnt) |


### t(:websocketkline)
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","req_id": "10110001", "args":["kline.1.BTCUSDT"]}')
```

```python--pybit

```

> t(:codequote_responseExampleFormatAll)

```javascript
{
  "topic":"kline.1.BTCUSDT",
    "data":[
    {
      "start":1658150220000,
      "end":1658150279999,
      "interval":"1",
      "open":"22212",
      "close":"22214",
      "high":"22214.5",
      "low":"22212",
      "volume":"5.456",
      "turnover":"121193.36",
      "confirm":false,
      "timestamp":1658150224542
    }
  ],
    "ts":1658150224542,
    "type":"snapshot"
}
```

t(:websocket_para_kline_v3)

<aside class="notice">
t(:websocket_aside_klineV2)
</aside>

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|start|integer |t(:row_comment_startTime)    |
|end|integer |t(:row_comment_endTime)    |
|interval|string|t(:row_comment_interval) |
|open|string |t(:row_comment_open)    |
|close|string |t(:row_comment_close)    |
|high|string |t(:row_comment_high)    |
|low|string |t(:row_comment_low)    |
|volume|string |t(:row_comment_resp_volume)    |
|turnover|string |t(:row_comment_resp_turnover)    |
|confirm|bool |t(:row_comment_confirm)    |
|timestamp|integer |t(:row_comment_endTime)    |


## t(:contract_privateTopic)
### t(:websocketposition)
> t(:codequote_subscribe)


```javascript
ws.send('{"op":"subscribe","req_id": "10110001","args":["user.position.contractAccount"]}');
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "topic": "user.position.contractAccount",
    "data": [
        {
            "positionIdx": 1,
            "riskId": 716,
            "riskLimitValue": "200000",
            "symbol": "BITUSDT",
            "side": "Buy",
            "size": "50",
            "positionValue": "33.7",
            "entryPrice": "0.674",
            "tradeMode": 0,
            "autoAddMargin": 0,
            "leverage": "10",
            "positionBalance": "3.438198",
            "liqPrice": "0.001",
            "bustPrice": "0.001",
            "takeProfit": "0.000",
            "stopLoss": "0.000",
            "trailingStop": "0.000",
            "unrealisedPnl": "-0.05",
            "createdTime": "1658905548601",
            "updatedTime": "1659057535085",
            "tpSlMode": "Full"
        },
        {
            "positionIdx": 2,
            "riskId": 716,
            "riskLimitValue": "200000",
            "symbol": "BITUSDT",
            "side": "None",
            "size": "0",
            "positionValue": "0",
            "entryPrice": "0",
            "tradeMode": 0,
            "autoAddMargin": 0,
            "leverage": "10",
            "positionBalance": "0",
            "liqPrice": "0.000",
            "bustPrice": "0.000",
            "takeProfit": "0.000",
            "stopLoss": "0.000",
            "trailingStop": "0.000",
            "unrealisedPnl": "0",
            "createdTime": "1658905548601",
            "updatedTime": "1659057535085",
            "tpSlMode": "Full"
        },
        {
            "positionIdx": 1,
            "riskId": 206,
            "riskLimitValue": "200000",
            "symbol": "DOGEUSDT",
            "side": "Buy",
            "size": "200",
            "positionValue": "13.13",
            "entryPrice": "0.06565",
            "tradeMode": 0,
            "autoAddMargin": 0,
            "leverage": "10",
            "positionBalance": "1.3200902",
            "liqPrice": "0.0001",
            "bustPrice": "0.0001",
            "takeProfit": "0.0000",
            "stopLoss": "0.0000",
            "trailingStop": "0.0000",
            "unrealisedPnl": "0.71",
            "createdTime": "1658307181708",
            "updatedTime": "1659057535085",
            "tpSlMode": "Partial"
        }
    ]
}
```

t(:contract_websocketPosition)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|positionIdx |integer |t(:row_comment_query_positionIdx_v3)  |
|riskId |integer |t(:row_comment_riskId)  |
|riskLimitValue |string |t(:contract_position_riskLimitValue)  |
|symbol |string |t(:row_comment_symbol_v3)  |
|side |string |t(:row_comment_query_side_v3)  |
|size |string |t(:row_comment_query_size_v3)  |
|positionValue |string |t(:row_comment_query_positionValue_v3)  |
|entryPrice |string |t(:row_comment_query_entryPrice_v3)  |
|tradeMode |integer |t(:contract_position_tradeMode)  |
|autoAddMargin |integer |t(:contract_position_autoAddMargin)  |
|leverage |string |t(:row_comment_query_leverage_v3)  |
|positionBalance |string |t(:contract_position_positionBalance)  |
|liqPrice |string |t(:contract_position_liqPrice)  |
|bustPrice |string |t(:contract_position_bustPrice)  |
|takeProfit |string |t(:row_comment_query_takeProfit_v3)  |
|stopLoss |string |t(:row_comment_query_stopLoss_v3)  |
|trailingStop |string |t(:row_comment_query_trailingStop_v3)  |
|unrealisedPnl |string |t(:row_comment_query_unrealisedPnl_v3)  |
|createdTime |number |t(:row_comment_query_createdTime_v3)  |
|updatedTime |number |t(:row_comment_query_updatedTime_v3)  |
|tpslMode |string |t(:row_comment_query_tpslMode_v3)  |


### t(:websocketexecution)
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","req_id": "10110001","args":["user.execution.contractAccount"]}');
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "topic": "user.execution.contractAccount",
    "data": [
        {
            "symbol": "BITUSDT",
            "execFee": "0.02022",
            "execId": "beba036f-9fb4-59a7-84b7-2620e5d13e1c",
            "execPrice": "0.674",
            "execQty": "50",
            "execType": "Trade",
            "execValue": "33.7",
            "feeRate": "0.0006",
            "lastLiquidityInd": "RemovedLiquidity",
            "leavesQty": "0",
            "orderId": "ddbea432-2bd7-45dd-ab42-52d920b8136d",
            "orderLinkId": "b001",
            "orderPrice": "0.707",
            "orderQty": "50",
            "orderType": "Market",
            "stopOrderType": "UNKNOWN",
            "side": "Buy",
            "execTime": "1659057535081",
            "closedSize": "0"
        }
    ]
}
```

t(:contract_websocketExecution)


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|symbol |string |t(:row_comment_symbol_v3)   |
|execFee |string |t(:row_comment_query_execFee_v3)  |
|execId |string |t(:row_comment_query_execId_v3)  |
|execPrice |string |t(:row_comment_query_execPrice_v3)  |
|execQty |string |t(:row_comment_query_execQty_v3)  |
|execType |string |t(:row_comment_query_execType_v3)  |
|execValue |string |t(:row_comment_query_execValue_v3)  |
|feeRate |string |t(:row_comment_query_feeRate_v3)  |
|lastLiquidityInd |string |t(:row_comment_query_lastLiquidityInd_v3)  |
|leavesQty |string |t(:row_comment_query_leavesQty_v3)  |
|orderId |string |t(:row_comment_query_orderId_v3) |
|orderLinkId |string |t(:row_comment_query_orderLinkId_v3)  |
|orderPrice |string |t(:row_comment_query_price_v3)  |
|orderQty |string |t(:row_comment_query_qty_v3)  |
|orderType |string |t(:row_comment_query_orderType_v3)  |
|stopOrderType |string |t(:row_comment_query_stopOrderType_v3)  |
|side |string |t(:row_comment_query_side_v3)  |
|execTime |string |t(:row_comment_query_execTime_v3)  |
|closedSize |string |t(:closedSize)  |


### t(:websocketOrder)
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","req_id": "10110001","args":["user.order.contractAccount"]}');
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "topic": "user.order.contractAccount",
    "data": [
        {
            "symbol": "BTCUSD",
            "orderId": "ee013d82-fafc-4504-97b1-d92aca21eedd",
            "side": "Buy",
            "orderType": "Market",
            "stopOrderType": "UNKNOWN",
            "price": "21920.00",
            "qty": "200",
            "timeInForce": "ImmediateOrCancel",
            "orderStatus": "Filled",
            "triggerPrice": "0.00",
            "orderLinkId": "inv001",
            "createdTime": "1661338622771",
            "updatedTime": "1661338622775",
            "takeProfit": "0.00",
            "stopLoss": "0.00",
            "tpTriggerBy": "UNKNOWN",
            "slTriggerBy": "UNKNOWN",
            "triggerBy": "UNKNOWN",
            "reduceOnly": false,
            "closeOnTrigger": false,
            "triggerDirection": 0,
            "leavesQty": "0",
            "lastExecQty": "200",
            "lastExecPrice": "21282.00",
            "cumExecQty": "200",
            "cumExecValue": "0.00939761"
        }
    ]
}
```

t(:contract_websocketOrder)


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|symbol |string |t(:row_comment_symbol_v3)   |
|orderId |string |t(:row_comment_query_orderId_v3) |
|side |string |t(:row_comment_query_side_v3)  |
|orderType |string |t(:row_comment_query_orderType_v3)  |
|stopOrderType |string |t(:row_comment_query_stopOrderType_v3)  |
|price |string |t(:row_comment_query_price_v3)  |
|qty |string |t(:row_comment_query_qty_v3)  |
|timeInForce |string |t(:row_comment_query_timeInForce_v3)  |
|orderStatus |string |t(:row_comment_query_orderStatus_v3)  |
|triggerPrice |string |t(:row_comment_query_triggerPrice_v3)  |
|orderLinkId |string |t(:row_comment_query_orderLinkId_v3)  |
|createdTime |string |t(:row_comment_query_createdTime_v3)  |
|updatedTime |string |t(:row_comment_query_updatedTime_v3)  |
|takeProfit |string |t(:row_comment_query_takeProfit_v3)  |
|stopLoss |string |t(:row_comment_query_stopLoss_v3)  |
|t(:contract_param_executionTpTriggerBy) |string |t(:row_comment_query_tpTriggerBy_v3)  |
|t(:contract_parm_executionSlTriggerBy) |string |t(:row_comment_query_slTriggerBy_v3)  |
|basePrice |string |t(:row_comment_query_basePrice_v3)  |
|t(:contract_param_executionTriggerBy) |string |t(:row_comment_query_triggerBy_v3)  |
|reduceOnly |bool |t(:row_comment_query_reduceOnly_v3)  |
|closeOnTrigger |bool |t(:row_comment_query_closeOnTrigger_v3)  |
|leavesQty |string |t(:leavesQty)  |
|lastExecPrice |string |t(:lastExecPrice)  |
|lastExecQty |string |t(:lastExecQty)  |
|cumExecQty |string |t(:cumExecQty)  |
|cumExecValue |string |t(:cumExecValue)  |


### t(:websocketwallet)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "req_id": "10110001", "args": ["user.wallet.contractAccount"]}')
```

> t(:codequote_responseExampleFormatAll)

```javascript
{
    "topic": "user.wallet.contractAccount",
    "data": [
        {
            "coin": "USDT",
            "equity": "610.3984319",
            "walletBalance": "609.7384319",
            "positionMargin": "4.7582882",
            "availableBalance": "604.9801437",
            "orderMargin": "0",
            "unrealisedPnl": "0.66",
            "cumRealisedPnl": "-0.2615681"
        }
    ]
}
```

t(:contract_websocketWallet)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|coin |string |t(:row_comment_query_coin_coin_v3)    |
|equity |string |t(:row_comment_query_coin_equity_v3)    |
|walletBalance |string |t(:row_comment_query_coin_walletBalance_v3)    |
|positionMargin |string |t(:contract_walletPositionMargin)    |
|availableBalance |string |t(:contract_walletAvailableBalance)    |
|orderMargin |string |t(:contract_walletOrderMargin)    |
|unrealisedPnl |string |t(:row_comment_query_coin_unrealisedPnl_v3)    |
|cumRealisedPnl |string |t(:row_comment_query_coin_cumRealisedPnl_v3)    |
