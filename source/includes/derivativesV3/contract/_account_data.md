# t(:accountdata)
t(:account_para)

## t(:order)
### t(:dv_placeOrder)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/contract/v3/private/order/create' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: f02a18137c25c40d64b2c474f575c01a62ba076124946d38619238e19c86a2f2' \
--header 'X-BAPI-API-KEY: XXXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1658884339826' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "symbol": "ETHUSDT",
    "side": "Sell",
    "positionIdx": 2,
    "orderType": "Limit",
    "qty": "0.5",
    "price": "1450",
    "triggerDirection": 2,
    "triggerPrice": "1500",
    "triggerBy": "MarkPrice",
    "timeInForce": "GoodTillCancel",
    "orderLinkId": "a003",
    "takeProfit": "1100",
    "stopLoss": "1700",
    "reduce_only": false,
    "closeOnTrigger": false
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode":0,
    "retMsg":"OK",
    "result":{
        "orderId":"a09a43f1-7a65-4255-8758-034103447a4e",
        "orderLinkId":""
  },
    "retExtInfo":null,
    "time":1658850321861
}
```

t(:contract_order_para)

<aside class="notice">
t(:account_aside_placeOrder_positionIdx)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/contract/v3/private/order/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol |<b>true</b> |string |t(:row_comment_symbol)   |
|side |<b>true</b> |string |t(:row_comment_side)    |
|positionIdx |false |integer |t(:row_comment_position_idx_create_order_v3)  |
|t(:contract_param_orderType) |<b>true</b> |string |t(:row_comment_activeOrderType)   |
|qty |<b>true</b> |string |t(:contract_comment_qty) |
|price |false |string |t(:contract_comment_price) |
|triggerDirection |false |integer |t(:contract_comment_triggerDirection) |
|triggerPrice |false |string |t(:contract_comment_triggerPrice) |
|<a href="#trigger-price-type-triggerby">triggerBy</a> |false |string |t(:row_comment_linear_triggerBy) |
|tpTriggerBy |false |string |t(:account_row_comment_tp_trigger_by) |
|slTriggerBy |false |string |t(:account_row_comment_sl_trigger_by) |
|t(:row_parameter_timeInForce) |<b>true</b> |string |t(:row_comment_timeInForce) |
|orderLinkId |false |string |t(:row_comment_orderLinkId) |
|takeProfit |false |string |t(:row_comment_takeProfit) |
|stopLoss |false |string |t(:row_comment_stopLoss) |
|reduceOnly |false |bool |t(:linear_row_comment_reduceOnly) |
|closeOnTrigger |false |bool |t(:linear_row_comment_closeOnTrigger)


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| orderId |string |t(:row_comment_order_id) |
|orderLinkId |string |t(:row_comment_orderLinkId)  |


### t(:contract_getOrder)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/contract/v3/private/order/list?symbol=DOGEUSDT&orderStatus=Filled' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 61df2c2de39cfce40fe334e503de4a61e26a95aebec690b9b482e4feb31cb088' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1658899014497' \
--header 'X-BAPI-RECV-WINDOW: 5000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "list": [
            {
                "symbol": "XRPUSDT",
                "side": "Buy",
                "orderType": "Market",
                "price": "0.3431",
                "qty": "65",
                "reduceOnly": true,
                "timeInForce": "ImmediateOrCancel",
                "orderStatus": "Filled",
                "leavesQty": "0",
                "leavesValue": "0",
                "cumExecQty": "65",
                "cumExecValue": "21.3265",
                "cumExecFee": "0.0127959",
                "lastPriceOnCreated": "0.0000",
                "rejectReason": "EC_NoError",
                "orderLinkId": "",
                "createdTime": "1657526321499",
                "updatedTime": "1657526321504",
                "orderId": "ac0a8134-acb3-4ee1-a2d4-41891c9c46d7",
                "stopOrderType": "UNKNOWN",
                "takeProfit": "0.0000",
                "stopLoss": "0.0000",
                "tpTriggerBy": "UNKNOWN",
                "slTriggerBy": "UNKNOWN",
                "triggerPrice": "0.0000",
                "closeOnTrigger": true,
                "triggerDirection": 0,
                "positionIdx": 2
        ],
        "nextPageCursor": "K0crQkZRL0MyQVpiN0tVSDFTS0RlMk9DemNCWHZaRHp3aFZ4Y1Yza2MyWT0="
    },
    "retExtInfo": {},
    "time": 1658899014975
}
```

t(:contract_para_getOrder)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oaoList>/contract/v3/private/order/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|orderId |false |string |t(:account_row_comment_orderId) |
|orderLinkId |false |string |t(:row_comment_orderLinkId) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|<a href="#order-status-orderstatus-stoporderstatus">orderStatus</a> |false |string |t(:orderStatus_v3) |
|orderFilter |false |string |t(:row_comment_orderFilter_v3) |
|limit |false |integer |t(:row_comment_limit) |
|cursor |false |string |t(:row_comment_resp_cursor) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> symbol |string |t(:row_comment_symbol) |
|list> side |string |t(:row_comment_side) |
|list> orderType |string |t(:row_comment_order_type) |
|list> price |string |t(:row_comment_resp_price) |
|list> qty |string |t(:contract_comment_qty) |
|list> reduceOnly |bool |t(:linear_resp_field_reduce_only)  |
|list> timeInForce |string |t(:row_comment_timeInForce)  |
|list> orderStatus |string |t(:row_comment_orderStatus)  |
|list> leavesQty |string |t(:row_comment_leaves_qty)  |
|list> leavesValue |string |t(:row_comment_leaves_value)  |
|list> cumExecQty |string |t(:linear_resp_field_cum_exec_qty)  |
|list> cumExecValue |string |t(:linear_resp_field_cum_exec_value)  |
|list> cumExecFee |string |t(:linear_resp_field_cum_exec_fee)  |
|list> lastPriceOnCreated |string |t(:row_comment_last_exec_price)  |
|list> rejectReason |string |t(:row_comment_query_rejectReason_v3) |
|list> createdTime |string |t(:row_comment_created_at)  |
|list> updatedTime |string |t(:row_comment_updated_at)  |
|list> orderLinkId |string |t(:row_comment_orderLinkId)  |
|list> orderId |string |t(:account_row_comment_orderId) |
|list> stopOrderType |string |t(:row_comment_stopOrderType) |
|list> triggerDirection |integer |t(:contract_comment_triggerDirection) |
|list> closeOnTrigger |bool |t(:row_response_close_on_trigger)  |
|list> takeProfit |string |t(:row_comment_take_profit)  |
|list> stopLoss |string |t(:row_comment_stop_loss)  |
|list> tpTriggerBy |string |t(:contract_comment_tpTriggerBy) |
|list> slTriggerBy |string |t(:contract_comment_slTriggerBy) |
|list> triggerPrice |string |t(:contract_comment_getOrderTriggerPrice) |
|list> positionIdx |integer |t(:row_comment_position_idx) |
|nextPageCursor |string |t(:contract_comment_nextPageCursor) |


### t(:contract_cancelOrder)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/contract/v3/private/order/cancel' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: c9f2c118e40040fc3a12c9400816a26e475ce2f7995248a3625d92be3454b9f1' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1658900794413' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
  "symbol": "XRPUSDT",
  "orderLinkId": null,
  "orderId": "4030430d-1dba-4134-ac77-3d81c14aaa00"
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"OK",
    "result":{
      "orderId": "4030430d-1dba-4134-ac77-3d81c14aaa00",
      "orderLinkId": ""
  },
  "retExtInfo":null,
    "time":1658850321861
}
```

t(:contract_para_cancelOrder)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCancel>/contract/v3/private/order/cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|orderId |false |string |t(:row_comment_orderId_v3_post) |
|orderLinkId |false |string |t(:row_comment_orderLinkId_v3_post) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId |string |t(:account_row_comment_orderId) |
|orderLinkId |string |t(:misc_row_comment_orderLinkIdNotOrderId) |


### t(:contract_cancelAllOrders)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/contract/v3/private/order/cancel-all' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: ee5af51734abed24925af73badbce8ef06f0dd34a3b35fcd5a829c892f565aed' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1658901358435' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
  "symbol": "XRPUSDT"
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "list": [
            {
                "orderId": "4030430d-1dba-4134-ac77-3d81c14aaa00",
                "orderLinkId": "x001"
            }
        ]
    },
    "retExtInfo": {},
    "time": 1658901359225
}
```

t(:contract_para_cancelAllOrders)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCancelAll>/contract/v3/private/order/cancel-all</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancelAll"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol |false |string | t(:row_comment_symbol) |
|settleCoin |false |string | t(:contract_cancelAll_settleCoin) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> orderId |string |t(:account_row_comment_orderId) |
|list> orderLinkId |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |


### t(:contract_replaceOrder)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/contract/v3/private/order/replace' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 78c358649d431bb30dfc35e5a3cd99128b5f23faf04c15765b3d894f2930e8f5' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1658902610018' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "symbol":"XRPUSDT",
    "orderId":"db8b74b3-72d3-4264-bf3f-52d39b41956e",
    "orderLinkId": null,
    "qty": "15",
    "price": "0.4",
    "takeProfit": "0.2",
    "stopLoss": "1.6"
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "orderId": "db8b74b3-72d3-4264-bf3f-52d39b41956e",
        "orderLinkId": "x002"
    },
    "retExtInfo": {},
    "time": 1658902610749
}
```

t(:contract_para_replaceOrder)

<aside class="notice">
t(:account_aside_replaceActive)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oaoReplace>/contract/v3/private/order/replace</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaoReplace"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|orderId |false |string |t(:row_comment_orderId_replace) |
|orderLinkId |false |string |t(:row_comment_orderLinkId_replace) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|qty |false |string |t(:row_comment_pRQty) |
|price |false |string |t(:row_comment_pRPrice) |
|takeProfit |false |string |t(:row_comemnt_replace_take_profit)  |
|stopLoss |false |string |t(:row_comemnt_replace_stop_loss)  |
|tpTriggerBy |false |string |t(:account_row_comment_tp_trigger_by) |
|slTriggerBy |false |string |t(:account_row_comment_sl_trigger_by) |
|triggerPrice |false |string |t(:row_comment_triggerPrice_replace_v3) |
|triggerBy |false |string |t(:row_comment_triggerBy_v3) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|order_id |string |t(:account_row_comment_orderId) |
|orderLinkId |string |t(:row_comment_orderLinkId)  |


### t(:contract_getRealtimeOrder)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/contract/v3/private/order/unfilled-orders?symbol=XRPUSDT' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: e3a1e4b88dfc2730c987fb3253dd3e09bc05cf68ae4d9d9d71a8235c44cb1f02' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1658902846749' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json'
```

```python--pybit

```

> t(:codequote_responseExample)

```json
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "list": [
            {
                "symbol": "XRPUSDT",
                "orderId": "db8b74b3-72d3-4264-bf3f-52d39b41956e",
                "side": "Sell",
                "orderType": "Limit",
                "stopOrderType": "Stop",
                "price": "0.4000",
                "qty": "15",
                "timeInForce": "GoodTillCancel",
                "orderStatus": "UnTriggered",
                "triggerPrice": "0.1000",
                "orderLinkId": "x002",
                "createdTime": "1658901865082",
                "updatedTime": "1658902610748",
                "takeProfit": "0.2000",
                "stopLoss": "1.6000",
                "tpTriggerBy": "UNKNOWN",
                "slTriggerBy": "UNKNOWN",
                "triggerBy": "MarkPrice",
                "reduceOnly": false,
                "leavesQty": "15",
                "leavesValue": "6",
                "cumExecQty": "0",
                "cumExecValue": "0",
                "cumExecFee": "0",
                "triggerDirection": 2
            }
        ],
        "nextPageCursor": ""
    },
    "retExtInfo": {},
    "time": 1658902847238
}
```


t(:contract_para_getRealtimeOrder)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpOrder>/contract/v3/private/order/unfilled-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol |false |string |t(:contract_comment_realtimeOrderSymbol) |
|orderId |false |string | t(:misc_row_comment_orderIdNotOrderLinkId)|
|orderLinkId |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |
|settleCoin |false |string | t(:contract_comment_positionSettleCoin)|
|<a href="#order-filter-orderfilter">orderFilter</a> |false |string | t(:row_comment_orderFilter_v3)|
|limit |false |number |t(:row_comment_limit) |
|cursor |false |string |t(:row_comment_resp_cursor)   |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> symbol |string |t(:row_comment_symbol)    |
|list> orderId |string |t(:row_comment_order_id) |
|list> side |string |t(:row_comment_side)  |
|list> orderType |string |t(:row_comment_order_type)  |
|list> triggerDirection |integer |t(:contract_comment_triggerDirection)  |
|list> price |string |t(:row_comment_resp_price)  |
|list> qty |string |t(:contract_comment_qty)  |
|list> timeInForce |string |t(:row_comment_timeInForce)  |
|list> orderStatus |string |t(:row_comment_orderStatus)  |
|list> triggerPrice |string |t(:contract_comment_triggerPrice)  |
|list> triggerBy |string |t(:row_comment_linear_triggerBy) |
|list> tpTriggerBy |string |t(:account_row_comment_tp_trigger_by) |
|list> slTriggerBy |string |t(:account_row_comment_sl_trigger_by) |
|list> orderLinkId |string |t(:row_comment_orderLinkId)  |
|list> createdTime |string |t(:row_comment_created_at)  |
|list> updatedTime |string |t(:row_comment_updated_at)  |
|list> takeProfit |string |t(:row_comment_take_profit)  |
|list> stopLoss |string |t(:row_comment_stop_loss)  |
|list> reduce_only |bool |t(:linear_resp_field_reduce_only)  |
|list> cumExecQty |string |t(:linear_resp_field_cum_exec_qty)  |
|list> cumExecValue |string |t(:linear_resp_field_cum_exec_value)  |
|list> cumExecFee |string |t(:linear_resp_field_cum_exec_fee)  |
|list> leavesQty |string |t(:row_comment_leaves_qty)  |
|list> leavesValue |string |t(:row_comment_leaves_value)  |
|nextPageCursor |string |t(:row_comment_query_nextPageCursor_v3)  |


## t(:position)
### t(:dv_myposition)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/contract/v3/private/position/list?symbol=XRPUSDT' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: b0818cb2f91264ffd712db0c8f8648041b2c5eed643200aa63e4141c7aa12500' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1658904877491' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw ''
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "list": [
            {
                "positionIdx": 0,
                "riskId": 11,
                "symbol": "ETHUSDT",
                "side": "None",
                "size": "0.00",
                "positionValue": "0",
                "entryPrice": "0",
                "tradeMode": 1,
                "autoAddMargin": 0,
                "leverage": "10",
                "positionBalance": "0",
                "liqPrice": "0.00",
                "bustPrice": "0.00",
                "takeProfit": "0.00",
                "stopLoss": "0.00",
                "trailingStop": "0.00",
                "unrealisedPnl": "0",
                "createdTime": "1659943372099",
                "updatedTime": "1669470547908",
                "tpSlMode": "Full",
                "riskLimitValue": "900000",
                "activePrice": "0.00",
                "markPrice": "1205.02",
                "cumRealisedPnl": "0.00",
                "positionMM": "",
                "positionIM": "",
                "positionStatus": "Normal",
                "sessionAvgPrice": "0.00",
                "occClosingFee": "0"
            }
        ],
        "category": "linear",
        "nextPageCursor": ""
    },
    "retExtInfo": {},
    "time": 1670836410404
}
```

t(:contract_para_position)

<aside class="notice">
t(:account_aside_queryPosition)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pList>/contract/v3/private/position/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |false |string |t(:contract_comment_realtimeOrderSymbol)    |
|settleCoin |false |string |t(:contract_comment_positionSettleCoin)    |
|limit |false |integer |t(:contract_position_limit)    |
|cursor |false |string |t(:row_comment_resp_cursor)    |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|positionIdx |integer |t(:row_comment_position_idx)  |
|riskId  |integer |t(:contract_comment_riskId) |
|riskLimitValue | string | t(:contract_position_riskLimitValue) |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |string |t(:row_comment_position_size)  |
|positionValue |string |t(:row_comment_position_value)  |
|entryPrice |string |t(:linear_resp_field_entry_price)  |
|markPrice |string |t(:row_comment_updated_at)  |
|tradeMode |integer |t(:contract_comment_tradeMode) |
|autoAddMargin |integer |t(:row_comment_auto_add_margin)  |
|leverage |string |t(:resp_field_leverage)  |
|positionBalance |string |t(:contract_comment_positionBalance)  |
|liqPrice |string |t(:linear_resp_field_liq_price)  |
|bustPrice |string |t(:linear_resp_field_bust_price)  |
|positionStatus |string |t(:row_comment_updated_at)  |
|sessionAvgPrice |string |t(:row_comment_query_sessionAvgPrice_v3)  |
|occClosingFee |string |t(:row_comment_occ_closing_fee)  |
|takeProfit |string |t(:row_comment_take_profit)  |
|stopLoss |string |t(:row_comment_stop_loss)  |
|trailingStop |string |t(:row_comment_trailing_stop)  |
|unrealisedPnl |string |t(:row_comment_unrealised_pnl)  |
|<a href="#tp-sl-mode-tpslmode">tpSLMode</a> |string |t(:row_comment_tp_sl_mode)  |
|activePrice | string | t(:account_row_comment_activePrice_v3) |
|positionIM |string |t(:row_comment_query_positionIM_v3)  |
|positionMM |string |t(:row_comment_query_positionMM_v3)  |
|cumRealisedPnl |string |t(:row_comment_query_cumRealisedPnl_v3)  |
|createdTime |string |t(:row_comment_created_at)  |
|updatedTime |string |t(:row_comment_updated_at)  |
|nextPageCursor | string | t(:contract_comment_nextPageCursor) |

### t(:setautoaddmargin)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/contract/v3/private/position/set-auto-add-margin' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 504e85b59fb0ee7c2c70d7cf2d82fc717258d67a3c3cdf631b4c4c68b43843b3' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1658908220837' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "symbol": "XRPUSDT",
    "side": "Sell",
    "autoAddMargin": 1,
    "positionIdx": 2
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {},
    "retExtInfo": {},
    "time": 1658908221642
}
```

t(:linear_account_para_setAutoAddMargin)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pSetAutoAddMargin>/contract/v3/private/position/set-auto-add-margin</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pSetAutoAddMargin"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |<b>true</b> |string |t(:row_comment_side)    |
|autoAddMargin |<b>true</b> |integer |t(:contract_comment_autoAddMargin)  |
|positionIdx |false |integer |t(:row_comment_position_idx)  |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |

### t(:dv_marginswitch)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/contract/v3/private/position/switch-isolated' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: f178bda84f8a3fa971338b7424cce2204824c0114f196650b2516962371e3902' \
--header 'X-BAPI-API-KEY: XXXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1658908531694' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "symbol":"XRPUSDT",
    "tradeMode": 1,
    "buyLeverage": "5",
    "sellLeverage": "5"
}'
```
```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {},
    "retExtInfo": {},
    "time": 1658908532580
}
```


t(:contract_para_switchIsolated)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pSwitchIsolated>/contract/v3/private/position/switch-isolated</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pSwitchIsolated"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|tradeMode |<b>true</b> |integer |t(:contract_comment_tradeMode)  |
|buyLeverage |<b>true</b> |string |t(:contract_comment_buyLeverage)  |
|sellLeverage |<b>true</b> |string |t(:contract_comment_sellLeverage)  |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |

### t(:dv_switchpositionmode)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/contract/v3/private/position/switch-mode' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: b07d38c9719187a8a9a0cee739f465edd05a1c7a30618e02a1f1dc9fc3639d97' \
--header 'X-BAPI-API-KEY: XXXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1658909270602' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "symbol":"BTCUSDT",
    "coin": null,
    "mode": 0
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {},
    "retExtInfo": {},
    "time": 1658909271272
}
```

t(:account_para_switchpositionmode_withcoin)

<table class="custom_table">
  <tr>
    <th></th><th>t(:example_h1)</th><th>coin</th><th>symbol</th>
  </tr>
  <tr>
    <td>t(:example_r1_d1)</td><td>t(:example_r1_d2)</td><td>t(:example_r1_d3)</td><td>t(:example_r1_d3)</td>
  </tr>
  <tr>
    <td>t(:example_r2_d1)</td><td colspan="3">t(:example_r2_d2)</td>
  </tr>
  <tr>
    <td>t(:example_r3_d1)</td><td>-</td><td>-</td><td>t(:example_r3_d4)</td>
  </tr>
  <tr>
    <td>t(:example_r2_d1)</td><td colspan="3">t(:example_r4_d2)</td>
  </tr>
  <tr>
    <td>t(:example_r5_d1)</td><td colspan="3">t(:example_r5_d2)</td>
  </tr>
  <tr>
    <td>t(:example_r6_d1)</td><td>-</td><td>t(:example_r6_d3)</td><td>-</td>
  </tr>
  <tr>
    <td>t(:example_r2_d1)</td><td colspan="3">t(:example_r7_d2)</td>
  </tr>
  <tr>
    <td>t(:example_r8_d1)</td><td colspan="3">t(:example_r8_d2)</td>
  </tr>
  <tr>
    <td>t(:example_r9_d1)</td><td>-</td><td>-</td><td>t(:example_r9_d3)</td>
  </tr>
  <tr>
    <td>t(:example_r2_d1)</td><td colspan="3">t(:example_r10_d1)</td>
  </tr>
  <tr>
    <td>t(:example_r11_d1)</td><td colspan="3">t(:example_r12_d1)</td>
  </tr>
</table>

t(:position_ability_para)
<table class="custom_table">
  <tr>
    <th></th><th>t(:mode_1)</th><th>t(:mode_2)</th>
  </tr>
  <tr>
    <td>t(:product_1)</td><td>t(:ability_1)</td><td>t(:ability_2)</td>
  </tr>
  <tr>
    <td>t(:product_2)</td><td>t(:ability_2)</td><td>t(:ability_2)</td>
  </tr>
  <tr>
    <td>t(:product_3)</td><td>t(:ability_2)</td><td>t(:ability_3)</td>
  </tr>
  <tr>
    <td>t(:product_4)</td><td>t(:ability_1)</td><td>t(:ability_3)</td>
  </tr>
</table>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=ulSwitchMode>/contract/v3/private/position/switch-mode</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ulSwitchMode"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |false |string |t(:row_comment_symbol_with_coin)    |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:row_comment_coin_with_symbol) |
|mode |<b>true</b> |integer |t(:contract_comment_mode) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:dv_switchmode)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/contract/v3/private/position/switch-tpsl-mode' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 018fd4ae872bdb5a90e849dc324eeab4157a047de05250bb74efb7c3434d0597' \
--header 'X-BAPI-API-KEY: XXXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1658909568597' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "symbol":"XRPUSDT",
    "tpSlMode":"Partial"
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {},
    "retExtInfo": {},
    "time": 1658909569340
}
```

t(:linear_private_switchmode)

<aside class="notice">
t(:switchmode_aside)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pltcList>/contract/v3/private/position/switch-tpsl-mode</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pltcList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|tpSlMode |<b>true</b> |string |t(:contract_comment_tpSlMode)  |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:setleverage)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/contract/v3/private/position/set-leverage' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 6d17e6aa3a7c362b05071c737dc0904bd731fea1d04e9b46ee188749d17a7ce6' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1658910157065' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "symbol":"XRPUSDT",
    "buyLeverage":"5",
    "sellLeverage":"10"
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {},
    "retExtInfo": {},
    "time": 1658910157755
}
```

t(:linear_account_para_setLeverage)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pSetLeverage>/contract/v3/private/position/set-leverage</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pSetLeverage"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|buyLeverage |<b>true</b> |string |t(:linear_row_comment_leverage)  |
|sellLeverage |<b>true</b> |string |t(:linear_row_comment_leverage)  |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |

### t(:tradingstop)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/contract/v3/private/position/trading-stop' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 4c0406d6e31e30f5c37295627abefa980c248bc25170fa7158e47d8a46425d74' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1658910815488' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "symbol": "XRPUSDT",
    "takeProfit": "0.1",
    "stopLoss": "0.7",
    "activePrice": null,
    "trailingStop": null,
    "tpTriggerBy": "LastPrice",
    "slTriggerBy": "MarkPrice",
    "slSize": null,
    "tpSize": null,
    "positionIdx": 2
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {},
    "retExtInfo": {},
    "time": 1658910815936
}
```

t(:account_para_tradingStop_linear)

<aside class="notice">
t(:account_aside_tradingStop)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pSetTpSlTs>/contract/v3/private/position/trading-stop</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pSetTpSlTs"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|takeProfit |false |string |t(:account_row_comment_takeProfit) |
|stopLoss |false |string |t(:account_row_comment_stopLoss) |
|activePrice |false |string |t(:account_row_comment_activePrice_v3) |
|trailingStop |false |string |t(:account_row_comment_trailingStop) |
|tpTriggerBy | false | string | t(:account_row_comment_tp_trigger_by)
|slTriggerBy | false | string | t(:account_row_comment_sl_trigger_by)
|slSize |false |string |t(:row_comment_sl_size) |
|tpSize |false |string |t(:row_comment_tp_size) |
|positionIdx |false |integer |t(:row_comment_position_idx)  |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:setrisklimit)

> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/contract/v3/private/position/set-risk-limit' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 82904cc14df4bb278722d4212bdb76dc7e1ec7a77e0e761d2e09b3361059a25c' \
--header 'X-BAPI-API-KEY: XXXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1658911327616' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "symbol":"XRPUSDT",
    "riskId":43,
    "positionIdx":2
}'
```

```python--pybit

```

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {},
    "retExtInfo": {},
    "time": 1658911328063
}
```

t(:account_para_setRisk)

<aside class="notice">
t(:account_aside_getRisk_linear)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=plpSetRisk>/contract/v3/private/position/set-risk-limit</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#plpSetRisk"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|riskId |<b>true</b> |integer |t(:row_comment_riskId) |
|positionIdx |false |integer |t(:row_comment_position_idx)  |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:usertraderecords)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/contract/v3/private/execution/list?symbol=XRPUSDT' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: a7358fb068bf66570e7ecf063e39a6dbd11f1d5572ba79a63d5996221d864585' \
--header 'X-BAPI-API-KEY: XXXXXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1658911518042' \
--header 'X-BAPI-RECV-WINDOW: 5000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "list": [
            {
                "symbol": "BITUSDT",
                "execFee": "0.001356",
                "execId": "499e1a2a-c664-55db-bbf0-78ad31b7b033",
                "execPrice": "0.452",
                "execQty": "5.0",
                "execType": "Trade",
                "execValue": "2.26",
                "feeRate": "0.0006",
                "lastLiquidityInd": "RemovedLiquidity",
                "leavesQty": "0.0",
                "orderId": "1d40db82-b1f6-4340-9190-650eeddd440b",
                "orderLinkId": "",
                "orderPrice": "0.430",
                "orderQty": "5.0",
                "orderType": "Market",
                "stopOrderType": "UNKNOWN",
                "side": "Sell",
                "execTime": "1657269236943",
                "closedSize": "5.0"
            },
            {
                "symbol": "BITUSDT",
                "execFee": "0.004068",
                "execId": "ed090e6a-afc0-5cb5-b51d-039592a44ec5",
                "execPrice": "0.452",
                "execQty": "15.0",
                "execType": "Trade",
                "execValue": "6.78",
                "feeRate": "0.0006",
                "lastLiquidityInd": "RemovedLiquidity",
                "leavesQty": "0.0",
                "orderId": "d34d40a1-2475-4552-9e54-347a27282ec0",
                "orderLinkId": "",
                "orderPrice": "0.429",
                "orderQty": "15.0",
                "orderType": "Market",
                "stopOrderType": "UNKNOWN",
                "side": "Sell",
                "execTime": "1657268340170",
                "closedSize": "15.0"
            }
        ],
        "nextPageCursor": ""
    },
    "retExtInfo": {},
    "time": 1658911518442
}
```

t(:linear_private_trade_records)

<aside class="notice">
t(:wallet_aside_tradeRecords)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpeList>/contract/v3/private/execution/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpeList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|orderId |false |string |t(:contract_comment_orderId) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|startTime |false |number |t(:contract_comment_startTime) |
|endTime |false |number |t(:contract_comment_endTime) |
|<a href="#exec-type-exectype">execType</a> |false |string |t(:linear_exec_type) |
|limit |false |integer |t(:linear_row_comment_limit_50_200) |
|cursor |false |string |t(:row_comment_resp_cursor)    |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> t(:row_parameter_symbol) |string |t(:row_comment_symbol)  |
|list> execFee |string |t(:row_comment_exec_fee)    |
|list> execId |string |t(:row_comment_exec_id)  |
|list> execPrice |string |t(:row_comment_exec_price)    |
|list> execQty |string |t(:row_comment_exec_qty)  |
|list> execType |string |t(:row_comment_exec_type) |
|list> execValue |string |t(:row_comment_exec_value)  |
|list> feeRate |string |t(:row_comment_fee_rate)  |
|list> <a href="#liquidity-type-lastliquidityind">lastLiquidityInd</a> |string |t(:row_comment_last_liquidity_ind) |
|list> leavesQty |string |t(:row_comment_leaves_qty)  |
|list> orderId |string |t(:row_comment_order_id)  |
|list> orderLinkId |string |t(:row_comment_orderLinkId)  |
|list> orderPrice |string |t(:row_comment_order_price)  |
|list> orderQty |string |t(:row_comment_order_qty)  |
|list> orderType |string |t(:row_comment_order_type)  |
|list> <a href="#stop-order-type-stopordertype">stopOrderType</a> |string |t(:row_comment_stopOrderType)  |
|list> t(:row_parameter_side) |string |t(:row_comment_side)  |
|list> execTime |string |t(:row_comment_query_execTime_v3)  |
|list> closedSize |string |t(:row_comment_closedSize_v3)  |
|nextPageCursor |string |t(:contract_comment_nextPageCursor)  |


### t(:dv_closedprofitandloss)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/contract/v3/private/position/closed-pnl?symbol=XRPUSDT&startTime=1658764800000&endTime=1658937600000' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: eb16a696924a92a3a47d769caf44d7373eca9ed6a644384ff6e8cd729ee9f7b1' \
--header 'X-BAPI-API-KEY: XXXXXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1658914264517' \
--header 'X-BAPI-RECV-WINDOW: 5000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "list": [
            {
                "symbol": "XRPUSDT",
                "orderId": "3834da81-2b9c-4f5b-a558-05091f26deda",
                "side": "Buy",
                "qty": "50",
                "orderPrice": "0.3541",
                "orderType": "Market",
                "execType": "Trade",
                "closedSize": "50",
                "cumEntryValue": "16.68",
                "avgEntryPrice": "0.3336",
                "cumExitValue": "16.865",
                "avgExitPrice": "0.3373",
                "closedPnl": "-0.2034435",
                "fillCount": "1",
                "leverage": "10",
                "createdAt": "1658914152212"
            }
        ],
        "nextPageCursor": "R21aYkRjQ0haRmcxeFJBanZNYm1Db01RWWdyV3YzZmdkUVNXUmtXdGpMMD0="
    },
    "retExtInfo": {},
    "time": 1658914264892
}
```

t(:linear_private_closed_pnl_records)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pltcLpnl>/contract/v3/private/position/closed-pnl</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pltcLpnl"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|startTime |false |number |t(:row_comment_startTime) |
|endTime |false |number |t(:row_comment_endTime) |
|limit |false |integer |t(:linear_row_comment_limit_50_200) |
|cursor |false |string |t(:row_comment_resp_cursor)    |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> orderId |string |t(:row_response_closedPnlOrderId)  |
|list> t(:row_parameter_symbol) |string |t(:row_comment_symbol)    |
|list> t(:row_parameter_side) |string |t(:row_response_closedPnlSide)  |
|list> t(:row_parameter_quantity) |string |t(:row_comment_order_qty)  |
|list> orderPrice |string |t(:row_comment_order_price)  |
|list> orderType |string |t(:row_comment_order_type)  |
|list> execType |string |t(:row_comment_exec_type)  |
|list> closedSize |string |t(:linear_resp_field_closed_size)  |
|list> cumEntryValue |string |t(:linear_resp_field_cum_entry_value)    |
|list> avgEntryPrice |string |t(:linear_resp_field_avg_entry_price)    |
|list> cumExitValue |string |t(:linear_resp_field_cum_exit_value)    |
|list> avgExitPrice |string |t(:linear_resp_field_avg_exit_price)    |
|list> closedPnl |string |t(:linear_resp_field_closed_pnl)    |
|list> fillCount |string |t(:linear_resp_field_fill_count)    |
|list> leverage |string |t(:resp_field_leverage)  |
|list> createdAt |string |t(:row_comment_created_at)  |
|nextPageCursor |string |t(:contract_comment_nextPageCursor)  |


## t(:contract_account)
t(:contract_accountPara)


### t(:balance)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/contract/v3/private/account/wallet/balance?coin=BTC' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: f8f516355e0c59b28d429b13b4ea6a350d02f9c96e2f9fd1be235863e8c1834c' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1658736635286' \
--header 'X-BAPI-RECV-WINDOW: 5000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "list": [
            {
                "coin": "BTC",
                "equity": "0.80319649",
                "walletBalance": "0.80319649",
                "positionMargin": "0",
                "availableBalance": "0.80319649",
                "orderMargin": "0",
                "occClosingFee": "0",
                "occFundingFee": "0",
                "unrealisedPnl": "0",
                "cumRealisedPnl": "0.00120039",
                "givenCash": "0",
                "serviceCash": "0"
            }
        ]
    },
    "retExtInfo": {},
    "time": 1658736635763
}
```

t(:wallet_para_walletBalance)

<aside class="notice">
t(:wallet_aside_walletBalance)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpwBalance>/contract/v3/private/account/wallet/balance</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpwBalance"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:contract_accountCoin) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> coin |string |t(:contract_accountCoin_resp)  |
|list> equity |string |t(:row_comment_equity)  |
|list> walletBalance |string |t(:row_comment_wallet_balance)  |
|list> positionMargin |string |t(:row_comment_position_margin)  |
|list> availableBalance |string |t(:row_comment_http_available_balance)  |
|list> orderMargin|string |t(:row_comment_order_margin)    |
|list> occClosingFee |string |t(:row_comment_occ_closing_fee)  |
|list> occFundingFee |string |t(:row_comment_occ_funding_fee)  |
|list> unrealisedPnl |string |t(:row_comment_unrealised_pnl)  |
|list> cumRealisedPnl|string |t(:row_comment_cum_realised_pnl)  |
|list> givenCash |string |t(:row_response_comment_given_cash)  |
|list> serviceCash |string |t(:row_response_comment_service_cash)  |


### t(:tradingFeeRate)
t(:contract_tradingFeeRate_para)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/contract/v3/private/account/fee-rate?symbol=ETHUSDT' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: e65aad8dd5459774ad21aaca77420947332fdbfe433bef959c6507ce2379999f' \
--header 'X-BAPI-API-KEY: XXXXXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1658739026859' \
--header 'X-BAPI-RECV-WINDOW: 5000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "list": [
            {
                "symbol": "ETHUSDT",
                "takerFeeRate": "0.0006",
                "makerFeeRate": "0.0001"
            }
        ]
    },
    "retExtInfo": {},
    "time": 1658739027301
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=tradingFeeRate>/contract/v3/private/account/fee-rate</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#tradingFeeRate"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol |false |string |t(:row_comment_symbol) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> symbol |string |t(:row_comment_symbol)  |
|list> takerFeeRate |string |t(:contract_accountTakerFeeRate)  |
|list> makerFeeRate |string |t(:contract_accountMakerFeeRate)  |


### t(:dv_walletrecords)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/contract/v3/private/account/wallet/fund-records?coin=USDT&walletFundType=AccountTransfer&limit=1' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 591a44021fff458a6dfbba517755e1105066864d94c38a0ce84619ae51cf2313' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1658737208933' \
--header 'X-BAPI-RECV-WINDOW: 5000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "list": [
            {
                "coin": "USDT",
                "type": "AccountTransfer",
                "amount": "500",
                "walletBalance": "2731.63599033",
                "execTime": "1658215763731"
            }
        ],
        "nextPageCursor": "elZpeUVCSCtFRk5pZjMrMU9reDdMdkpJS2VZdEpqczNHaExPUU5CazA0Yz0="
    },
    "retExtInfo": {},
    "time": 1658737209400
}
```

t(:wallet_para_walletRecords)

<aside class="notice">
t(:wallet_aside_walletRecords)
</aside>

<aside class="notice">
t(:wallet_aside_walletRecords1)
</aside>

<aside class="warning">
t(:wallet_aside_walletRecords2)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oawfRecordsNew>/contract/v3/private/account/wallet/fund-records</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawfRecordsNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|startTime |false |string |t(:contract_accountStatTime) |
|endTime |false |string |t(:contract_accountEndTime) |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:contract_accountCoin_resp) |
|<a href="#wallet-fund-type-wallet_fund_type-type">walletFundType</a> |false |string |t(:row_comment_walletFundType) |
|limit |false |string |t(:row_comment_limit) |
|cursor |false |string |t(:contract_accountCursor) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> coin |string |t(:row_comment_coin_type)  |
|list> type |string |t(:row_comment_fund_type)  |
|list> amount |string |t(:row_comment_fund_amount)  |
|list> wallet_balance |string |t(:row_comment_wallet_balance)  |
|list> exec_time |string |t(:row_comment_exec_timestamp)  |
|nextPageCursor |string |t(:contract_accountNextPageCursor)  |


### t(:dv_setMarginMode)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/contract/v3/private/account/setMarginMode' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: a1487d336f003c389651fc89aa88cc9b19be6e2b12eb75b70180b61b0a03fd96' \
--header 'X-BAPI-API-KEY: CYZHHQAUQVHCGTHJPX' \
--header 'X-BAPI-TIMESTAMP: 1670481748474' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "setMarginMode":"PORTFOLIO_MARGIN"
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "Request accepted",
    "result": {
        "reasons": []
    }
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=setMarginModeContractV3>/contract/v3/private/account/setMarginMode</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#setMarginModeContractV3"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|setMarginMode |<b>true</b> |string |t(:row_comment_set_margin_mode)   |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
