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

ws_url = "wss://stream.bybit.com/realtime"

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

t(:websocket_para_endpoint_v3)

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
// Subscribing to the trade data for BTCUSDT
ws.send('{"op":"subscribe","args":["publicTrade.BTCUSDT"]}')
```

> t(:websocket_codequote_filters2)

```javascript
// Example: Subscribing to the trade data for BTCUSDT and XRPUSDT
ws.send('{"op":"subscribe","args":["publicTrade.BTCUSDT", "publicTrade.XRPUSDT"]}')
```


t(:websocket_para_filters)

`ws.send('{"op": "subscribe", "args": ["topic.filter"]}');`

t(:websocket_para_filters1)

`ws.send('{"op": "subscribe", "args": ["topic.filter", "topic.filter"]}');`

t(:websocket_para_filters3)
t(:websocket_para_filter_resp)

### t(:websocketunsubfilters)
> t(:websocket_codequote_unsubfilters)

```javascript
// Unsubscribing from the trade data for ETHUSDT
ws.send('{"op":"unsubscribe","args":["publicTrade.ETHUSDT"]}')
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
           "kline.1.BTCUSDT"
       ]
   }
}
```

t(:websocket_para_response)



## t(:publictopics)
### t(:websocketOrderBookDepth)

> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["orderbook.25.BTCUSDT","orderbook.500.BTCUSDT"]}')
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

t(:websocketOrderBook_v3)

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
ws.send('{"op": "subscribe", "args": ["publicTrade.BTCUSDT"]}')
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
ws.send('{"op": "subscribe", "args": ["tickers.BTCUSDT"]}')
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
ws.send('{"op":"subscribe","args":["kline.1.BTCUSDT"]}')
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


## t(:privatetopics_unified)
### t(:websocketposition)
> t(:codequote_subscribe)


```javascript
ws.send('{"op":"subscribe","args":["user.position.unifiedAccount"]}');
```

> t(:codequote_responseExampleFormatAll)

```javascript

{
	"id": "c2b38e12-067f-4adc-b5ae-3806112d9461",
	"topic": "user.position.unifiedAccount",
	"ts": 1649150255792,
	"data": {
		"result": [{
			"positionIdx": 0,
			"isIsolated": false,
			"riskId": "1",
			"symbol": "BTCUSDT",
			"side": "None",
			"size": "0.0000",
			"entryPrice": "0.00000000",
			"sessionAvgPrice": "0.00000000",
			"leverage": "10",
			"positionMargin": "0.00000000",
			"markPrice": "46475.00000000",
			"sessionUPL": "0.00000000",
			"sessionRPL": "",
			"positionIM": "0.00000000",
			"positionMM": "0.00000000",
			"takeProfit": "",
			"stopLoss": "",
			"trailingStop": "",
			"positionStatus": "normal",
			"positionValue": "0.00000000",
			"unrealisedPnl": "0.00000000",
			"cumRealisedPnl": "0.00000000",
			"createdTime": 1649150255603,
			"updatedTime": 1649150255666,
			"tpslMode": "Full"
		}],
		"version": 18
	},
	"type": "snapshot"
}

```


t(:websocketpositionV3)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|positionIdx |number |t(:row_comment_query_positionIdx_v3)  |
|isIsolated|bool |t(:row_comment_query_isIsolated_v3)    |
|riskId |string |t(:row_comment_riskId)  |
|symbol |string |t(:row_comment_symbol_v3)  |
|side |string |t(:row_comment_query_side_v3)  |
|size |string |t(:row_comment_query_size_v3)  |
|entryPrice |string |t(:row_comment_query_entryPrice_v3)  |
|sessionAvgPrice |string |t(:row_comment_query_sessionAvgPrice_v3)  |
|leverage |string |t(:row_comment_query_leverage_v3)  |
|positionMargin |string |t(:row_comment_query_positionMargin_v3)  |
|markPrice |string |t(:row_comment_query_markPrice_v3)  |
|sessionUPL |string |t(:row_comment_query_sessionUPL_v3)  |
|sessionRPL |string |t(:row_comment_query_sessionRPL_v3)  |
|positionIM |string |t(:row_comment_query_positionIM_v3)  |
|positionMM |string |t(:row_comment_query_positionMM_v3)  |
|takeProfit |string |t(:row_comment_query_takeProfit_v3)  |
|stopLoss |string |t(:row_comment_query_stopLoss_v3)  |
|trailingStop |string |t(:row_comment_query_trailingStop_v3)  |
|positionValue |string |t(:row_comment_query_positionValue_v3)  |
|unrealisedPnl |string |t(:row_comment_query_unrealisedPnl_v3)  |
|cumRealisedPnl |string |t(:row_comment_query_cumRealisedPnl_v3)  |
|createdTime |number |t(:row_comment_query_createdTime_v3)  |
|updatedTime |number |t(:row_comment_query_updatedTime_v3)  |
|tpslMode |string |t(:row_comment_query_tpslMode_v3)  |



### t(:websocketexecution)
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","args":["user.execution.unifiedAccount"]}');
```

> t(:codequote_responseExampleFormatAll)

```javascript

{
	"id": "1e035d63-4d82-4f5c-acfa-32412573d891",
	"topic": "user.execution.unifiedAccount",
	"ts": 1649127768339,
	"data": {
		"result": [{
			"symbol": "BTCUSDT",
			"side": "Buy",
			"orderId": "0c06343d-02df-46e8-92c7-508a008b030a",
			"execId": "b1d29ebf-3696-5668-a005-5fdf16343d15",
			"orderLinkId": "lin-sit-perp-1040",
			"execPrice": "43100.00000000",
			"orderQty": "0.0500",
			"execType": "Trade",
			"execQty": "0.0500",
			"leavesQty": "0.0000",
			"execFee": "-0.53875000",
			"execTime": 1649127768215,
			"feeRate": "-0.000250",
			"execValue": "2155.00000000",
			"lastLiquidityInd": "MAKER",
			"orderPrice": "43100.00000000",
			"orderType": "Limit",
			"stopOrderType": "UNKNOWN"
		}],
		"version": 10
	},
	"type": "snapshot"
}

```

t(:websocketexecutionV3)


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
|execTime |number |t(:row_comment_query_execTime_v3)  |



### t(:websocketOrder)
> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","args":["user.order.unifiedAccount"]}');
```


> t(:codequote_responseExampleFormatAll)

```javascript

{
	"id": "2f81572c-e0fa-4370-b080-1a1ee0e43174",
	"topic": "user.order.unifiedAccount",
	"ts": 1649150255791,
	"data": {
		"result": [{
			"orderId": "cc171fdb-d189-4ade-a098-9205e2b7a25e",
			"orderLinkId": "lin-sit-perp-1046",
			"symbol": "BTCUSDT",
			"side": "Sell",
			"orderType": "Limit",
			"price": "47000.00000000",
			"qty": "0.0500",
			"timeInForce": "GoodTillCancel",
			"orderStatus": "New",
			"stopOrderType": "UNKNOWN",
			"triggerBy": "UNKNOWN",
			"triggerPrice": "",
			"reduceOnly": false,
			"closeOnTrigger": "false",
			"createdTime": 1649150255604,
			"updatedTime": 1649150255666,
			"iv": "",
			"orderIM": "",
			"takeProfit": "",
			"stopLoss": "",
			"tpTriggerBy": "UNKNOWN",
			"slTriggerBy": "UNKNOWN",
			"basePrice": ""
		}],
		"version": 18
	},
	"type": "snapshot"
}

```

t(:websocketOrderV3)


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
|iv |string |t(:row_comment_query_iv_v3)  |
|timeInForce |string |t(:row_comment_query_timeInForce_v3)  |
|orderStatus |string |t(:row_comment_query_orderStatus_v3)  |
|triggerPrice |string |t(:row_comment_query_triggerPrice_v3)  |
|orderLinkId |string |t(:row_comment_query_orderLinkId_v3)  |
|createdTime |number |t(:row_comment_query_createdTime_v3)  |
|updatedTime |number |t(:row_comment_query_updatedTime_v3)  |
|takeProfit |string |t(:row_comment_query_takeProfit_v3)  |
|stopLoss |string |t(:row_comment_query_stopLoss_v3)  |
|tpTriggerBy |string |t(:row_comment_query_tpTriggerBy_v3)  |
|slTriggerBy |string |t(:row_comment_query_slTriggerBy_v3)  |
|basePrice |string |t(:row_comment_query_basePrice_v3)  |
|triggerBy |string |t(:row_comment_query_triggerBy_v3)  |
|reduceOnly |bool |t(:row_comment_query_reduceOnly_v3)  |
|closeOnTrigger |bool |t(:row_comment_query_closeOnTrigger_v3)  |


### t(:websocketwallet)
> t(:codequote_subscribe)

```javascript
ws.send('{"op": "subscribe", "args": ["user.wallet.unifiedAccount"]}')
```

> t(:codequote_responseExampleFormatAll)

```javascript

{
	"id": "46bd0430-1d03-48f7-a503-c6c020d07536",
	"topic": "user.wallet.unifiedAccount",
	"ts": 1649150852199,
	"data": {
		"result": {
			"accountIMRate": "0.0002",
			"accountMMRate": "0.0000",
			"totalEquity": "510444.50000000",
			"totalWalletBalance": "510444.50000000",
			"totalMarginBalance": "510444.50000000",
			"totalAvailableBalance": "510333.52491801",
			"totalPerpUPL": "0.00000000",
			"totalInitialMargin": "110.97508199",
			"totalMaintenanceMargin": "9.13733489",
			"coin": [{
				"currencyCoin": "USDC",
				"equity": "0.00000000",
				"usdValue": "0.00000000",
				"walletBalance": "0.00000000",
				"marginBalance": "510444.50000000",
				"availableBalance": "510333.52491801",
				"marginBalanceWithoutConvert": "0.00000000",
				"availableBalanceWithoutConvert": "0.00000000",
				"borrowSize": "0.00000000",
				"availableToBorrow": "200000.00000000",
				"accruedInterest": "0.00000000",
				"totalOrderIM": "0.00000000",
				"totalPositionIM": "0.00000000",
				"totalPositionMM": "0.00000000"
			}]
		},
		"version": 19
	},
	"type": "snapshot"
}

```

t(:websocketwalletV3)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|accountIMRate |string |t(:row_comment_query_accountIMRate_v3)    |
|accountMMRate |string |t(:row_comment_query_accountMMRate_v3)    |
|totalEquity |string |t(:row_comment_query_totalEquity_v3)    |
|totalWalletBalance |string |t(:row_comment_query_totalWalletBalance_v3)    |
|totalMarginBalance |string |t(:row_comment_query_totalMarginBalance_v3)    |
|totalAvailableBalance |string |t(:row_comment_query_totalAvailableBalance_v3)    |
|totalPerpUPL |string |t(:row_comment_query_totalPerpUPL_v3)    |
|totalInitialMargin |string |t(:row_comment_query_totalInitialMargin_v3)    |
|totalMaintenanceMargin |string |t(:row_comment_query_totalMaintenanceMargin_v3)    |
|Coin> coin |string |t(:row_comment_query_coin_coin_v3)    |
|Coin> equity |string |t(:row_comment_query_coin_equity_v3)    |
|Coin> usdValue |string |t(:row_comment_query_coin_usdValue_v3)    |
|Coin> walletBalance |string |t(:row_comment_query_coin_walletBalance_v3)    |
|Coin> marginBalance |string |t(:row_comment_query_coin_marginBalance_v3)    |
|Coin> availableBalance |string |t(:row_comment_query_coin_availableBalance_v3)    |
|Coin> marginBalanceWithoutConvert |string |t(:row_comment_query_coin_marginBalanceWithoutConvert_v3)    |
|Coin> availableBalanceWithoutConvert |string |t(:row_comment_query_coin_availableBalanceWithoutConvert_v3)    |
|Coin> borrowSize |string |t(:row_comment_query_coin_borrowSize_v3)    |
|Coin> availableToBorrow |string |t(:row_comment_query_coin_availableToBorrow_v3)    |
|Coin> accruedInterest |string |t(:row_comment_query_coin_accruedInterest_v3)    |
|Coin> totalOrderIM |string |t(:row_comment_query_coin_totalOrderIM_v3)    |
|Coin> totalPositionIM |string |t(:row_comment_query_coin_totalPositionIM_v3)    |
|Coin> totalPositionMM |string |t(:row_comment_query_coin_totalPositionMM_v3)    |
|Coin> unrealisedPnl |string |t(:row_comment_query_coin_unrealisedPnl_v3)    |
|Coin> cumRealisedPnl |string |t(:row_comment_query_coin_cumRealisedPnl_v3)    |

### t(:greeksOption)

> t(:codequote_subscribe)

```javascript
ws.send('{"op":"subscribe","args":["user.greeks.unifiedAccount"]}');

```

> t(:codequote_snapshot)

```javascript

{
	"id": "6fa06656-141c-4197-b4bc-ef1a89bdef88",
	"topic": "user.greeks.unifiedAccount",
	"ts": 1649241177474,
	"data": {
		"result": [{
			"coin": "BTC",
			"totalDelta": "0.0500",
			"totalGamma": "0.00001",
			"totalVega": "0.0001",
			"totalTheta": "-0.0001"
		}],
		"version": 49
	},
	"type": "snapshot"
}

```

t(:udscGeeksDescV3)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| coin |string |t(:usdcBaseCoin) |
| totalDelta |string |t(:delta) |
| totalGamma |string |t(:gamma) |
| totalVega|string |t(:vega) |
| totalTheta |string |t(:theta) |
