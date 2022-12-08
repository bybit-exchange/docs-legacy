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

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/contract/v3/private/order/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#category-category">category</a> |false |string |t(:dv3_trade_category) |
|symbol |<b>true</b> |string |t(:row_comment_symbol)   |
|side |<b>true</b> |string |t(:row_comment_side)    |
|positionIdx |false |integer |t(:row_comment_position_idx_create_order)  |
|t(:contract_param_orderType) |<b>true</b> |string |t(:row_comment_activeOrderType)   |
|qty |<b>true</b> |string |t(:contract_comment_qty) |
|price |false |string |t(:contract_comment_price) |
|triggerDirection |false |integer |t(:contract_comment_triggerDirection) |
|triggerPrice |false |string |t(:contract_comment_triggerPrice) |
|<a href="#trigger-price-type-triggerby">triggerBy</a> |false |string |t(:contract_comment_triggerBy) |
|iv |false |string |t(:row_comment_iv_v3) |
|tpTriggerBy |false |string |t(:account_row_comment_tp_trigger_by) |
|slTriggerBy |false |string |t(:account_row_comment_sl_trigger_by) |
|t(:row_parameter_timeInForce) |<b>true</b> |string |t(:row_comment_timeInForce) |
|orderLinkId |false |string |t(:row_comment_orderLinkId_um) |
|takeProfit |false |string |t(:row_comment_takeProfit) |
|stopLoss |false |string |t(:row_comment_stopLoss) |
|reduceOnly |false |bool |t(:linear_row_comment_reduceOnly) |
|closeOnTrigger |false |bool |t(:linear_row_comment_closeOnTrigger) |
|mmp |false |bool |t(:row_comment_mmp_v3) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| orderId |string |t(:row_comment_order_id) |
|orderLinkId |string |t(:row_comment_orderLinkId)  |


### t(:contract_getOrder)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/contract/v3/private/order/list?limit=1&category=future' \
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
// future response sample
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "list": [
            {
                "symbol": "ETHPERP",
                "side": "Buy",
                "orderType": "Limit",
                "price": "1000.00",
                "qty": "0.50",
                "reduceOnly": false,
                "timeInForce": "FillOrKill",
                "orderStatus": "Deactivated",
                "leavesQty": "0.00",
                "leavesValue": "0",
                "cumExecQty": "0.00",
                "cumExecValue": "0",
                "cumExecFee": "0",
                "lastPriceOnCreated": "0.00",
                "rejectReason": "EC_NoError",
                "orderLinkId": "usdc-00005",
                "createdTime": "1669169261521",
                "updatedTime": "1669169268018",
                "orderId": "4d951f96-9ef8-4ada-aba7-d07d93d97fe5",
                "stopOrderType": "Stop",
                "takeProfit": "1300.00",
                "stopLoss": "700.00",
                "tpTriggerBy": "LastPrice",
                "slTriggerBy": "LastPrice",
                "triggerPrice": "1050.00",
                "closeOnTrigger": false,
                "triggerDirection": 2,
                "positionIdx": 0,
                "cancelType": "CancelByUser",
                "iv": "",
                "triggerBy": "MarkPrice"
            }
        ],
        "nextPageCursor": "",
        "category": "future"
    },
    "retExtInfo": {},
    "time": 1669191588649
}

// option response sample

{
    "result": {
        "nextPageCursor": "",
        "category": "option",
        "list": [
            {
                "symbol": "SOL-23NOV22-13-C",
                "orderType": "Limit",
                "orderLinkId": "option-0010",
                "orderId": "add4ce06-7d6e-4d18-baf3-8099e308402d",
                "cancelType": "CancelByUser",
                "stopOrderType": "UNKNOWN",
                "lastPriceOnCreated": "",
                "orderStatus": "Cancelled",
                "takeProfit": "",
                "cumExecValue": "0",
                "triggerDirection": "",
                "blockTradeId": "",
                "rejectReason": "",
                "price": "0.4",
                "createdTime": "1669174910041",
                "tpTriggerBy": "",
                "positionIdx": 0,
                "timeInForce": "GoodTillCancel",
                "leavesValue": "0",
                "updatedTime": "1669176681160",
                "side": "Buy",
                "triggerPrice": "",
                "cumExecFee": "0",
                "leavesQty": "20",
                "slTriggerBy": "",
                "iv": "",
                "placeType": "price",
                "closeOnTrigger": "",
                "cumExecQty": "0",
                "reduceOnly": false,
                "qty": "20",
                "stopLoss": "",
                "triggerBy": ""
            }
        ]
    },
    "retCode": 0,
    "retMsg": "Success."
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
|<a href="#category-category">category</a> |false |string |t(:dv3_trade_category) |
|orderId |false |string |t(:account_row_comment_orderId) |
|orderLinkId |false |string |t(:row_comment_orderLinkId) |
|symbol |false |string |t(:row_comment_symbol) |
|baseCoin |false |string |t(:dv3_queryOrder_baseCoin) |
|<a href="#order-status-orderstatus-stoporderstatus">orderStatus</a> |false |string |t(:orderStatus_v3) |
|<a href="#order-filter-orderfilter">orderFilter</a> |false |string |t(:row_comment_orderFilter_v3) |
|limit |false |integer |t(:row_comment_limit) |
|cursor |false |string |t(:row_comment_resp_cursor) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list |array |Object |
|> symbol |string |t(:row_comment_symbol) |
|> side |string |t(:row_comment_side) |
|> orderType |string |t(:row_comment_order_type) |
|> price |string |t(:row_comment_resp_price) |
|> qty |string |t(:contract_comment_qty) |
|> reduceOnly |boolean |t(:linear_resp_field_reduce_only) |
|> timeInForce |string |t(:row_comment_timeInForce) |
|> orderStatus |string |t(:row_comment_orderStatus) |
|> leavesQty |string |t(:row_comment_leaves_qty) |
|> leavesValue |string |t(:row_comment_leaves_value) |
|> cumExecQty |string |t(:linear_resp_field_cum_exec_qty) |
|> cumExecValue |string |t(:linear_resp_field_cum_exec_value) |
|> cumExecFee |string |t(:linear_resp_field_cum_exec_fee) |
|> lastPriceOnCreated |string |t(:row_comment_last_exec_price) |
|> rejectReason |string |t(:row_comment_query_rejectReason_v3) |
|> orderLinkId |string |t(:row_comment_orderLinkId) |
|> createdTime |string |t(:row_comment_created_at) |
|> updatedTime |string |t(:row_comment_updated_at) |
|> orderId |string |t(:account_row_comment_orderId) |
|> stopOrderType |string |t(:row_comment_stopOrderType) |
|> takeProfit |string |t(:row_comment_take_profit) |
|> stopLoss |string |t(:row_comment_stop_loss) |
|> <a href="#trigger-price-type-triggerby">tpTriggerBy</a> |string |t(:contract_comment_tpTriggerBy) |
|> <a href="#trigger-price-type-triggerby">slTriggerBy</a> |string |t(:contract_comment_slTriggerBy) |
|> triggerPrice |string |t(:contract_comment_getOrderTriggerPrice) |
|> closeOnTrigger |boolean |t(:row_response_close_on_trigger) |
|> triggerDirection |string |t(:contract_comment_triggerDirection) |
|> positionIdx |string |t(:row_comment_position_idx) |
|> cancelType |string |t(:contract_comment_cancelType) |
|> iv |string |t(:row_comment_iv_v3) |
|> <a href="#trigger-price-type-triggerby">triggerBy</a> |string |t(:contract_comment_triggerBy) |
|> blockTradeId |string |t(:blockTradeId) |
|> placeType |string |t(:optionPlaceType_comment) |
|nextPageCursor |string |t(:contract_comment_nextPageCursor) |
|category |string |dv3_orderbook_category |


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
|<a href="#category-category">category</a> |false |string |t(:dv3_trade_category) |
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
|<a href="#category-category">category</a> |false |string |t(:dv3_trade_category) |
|symbol |false |string | t(:row_comment_symbol) |
|settleCoin |false |string | t(:contract_cancelAll_settleCoin) |
|baseCoin |false |string |t(:dv3_queryOrder_baseCoin) |

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
|<a href="#category-category">category</a> |false |string |t(:dv3_trade_category) |
|orderId |false |string |t(:row_comment_orderId_replace) |
|orderLinkId |false |string |t(:row_comment_orderLinkId_replace) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|qty |false |string |t(:row_comment_pRQty) |
|price |false |string |t(:row_comment_pRPrice) |
|takeProfit |false |string |t(:row_comemnt_replace_take_profit)  |
|stopLoss |false |string |t(:row_comemnt_replace_stop_loss)  |
|tpTriggerBy |false |string |t(:account_row_comment_tp_trigger_by) |
|slTriggerBy |false |string |t(:account_row_comment_sl_trigger_by) |
|triggerBy |false |string |t(:account_row_comment_sl_trigger_by) |
|iv |false |string |t(:row_comment_iv_v3) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|order_id |string |t(:account_row_comment_orderId) |
|orderLinkId |string |t(:row_comment_orderLinkId)  |


### t(:contract_getRealtimeOrder)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/contract/v3/private/order/unfilled-orders?category=future&baseCoin=ETH' \
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

```javascript
// linear response sample
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "list": [
            {
                "symbol": "ETHPERP",
                "orderId": "72f02cc3-8d88-40d0-907f-87e758f62f28",
                "side": "Buy",
                "orderType": "Limit",
                "stopOrderType": "Stop",
                "price": "1000.00",
                "qty": "0.50",
                "timeInForce": "GoodTillCancel",
                "orderStatus": "Untriggered",
                "triggerPrice": "1050.00",
                "orderLinkId": "usdc-00006",
                "createdTime": "1669195732377",
                "updatedTime": "1669195732377",
                "takeProfit": "1300.00",
                "stopLoss": "700.00",
                "tpTriggerBy": "LastPrice",
                "slTriggerBy": "LastPrice",
                "triggerBy": "MarkPrice",
                "reduceOnly": false,
                "leavesQty": "0.50",
                "leavesValue": "500",
                "cumExecQty": "0.00",
                "cumExecValue": "0",
                "cumExecFee": "0",
                "triggerDirection": 2,
                "cancelType": "UNKNOWN",
                "lastPriceOnCreated": "",
                "iv": "",
                "closeOnTrigger": false
            }
        ],
        "nextPageCursor": "",
        "category": "future"
    },
    "retExtInfo": {},
    "time": 1669195809545
}
```

```javascript
// option response sample
{
    "result": {
        "nextPageCursor": "",
        "category": "option",
        "list": [
            {
                "symbol": "SOL-24NOV22-12-C",
                "orderType": "Limit",
                "orderLinkId": "option-0013",
                "orderId": "a1f5efd7-eb42-4d12-9fa8-d8a799d321ea",
                "lastPriceOnCreated": "",
                "stopOrderType": "UNKNOWN",
                "orderStatus": "New",
                "takeProfit": "",
                "cumExecValue": "0",
                "triggerDirection": "",
                "blockTradeId": "",
                "price": "0.4",
                "createdTime": "1669195736585",
                "tpTriggerBy": "",
                "timeInForce": "GoodTillCancel",
                "leavesValue": "",
                "updatedTime": "1669195736597",
                "side": "Buy",
                "triggerPrice": "",
                "cumExecFee": "0",
                "leavesQty": "20",
                "slTriggerBy": "",
                "iv": "0.000",
                "placeType": "price",
                "closeOnTrigger": "",
                "cumExecQty": "0",
                "reduceOnly": false,
                "qty": "20",
                "stopLoss": "",
                "triggerBy": ""
            }
        ]
    },
    "retCode": 0,
    "retMsg": "Success."
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
|<a href="#category-category">category</a> |false |string |t(:dv3_trade_category) |
|symbol |false |string |t(:contract_comment_realtimeOrderSymbol) |
|orderId |false |string | t(:misc_row_comment_orderIdNotOrderLinkId)|
|orderLinkId |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |
|settleCoin |false |string | t(:contract_comment_realtimeSettleCoin)|
|baseCoin |false |string | t(:dv3_realtimeOrder_baseCoin)|
|<a href="#order-filter-orderfilter">orderFilter</a> |false |string | t(:row_comment_orderFilter_v3)|
|limit |false |number |t(:row_comment_limit) |
|cursor |false |string |t(:row_comment_resp_cursor)   |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list |array |Object |
|> symbol |string |t(:row_comment_symbol) |
|> orderId |string |t(:account_row_comment_orderId) |
|> side |string |t(:row_comment_side) |
|> orderType |string |t(:row_comment_order_type) |
|> stopOrderType |string |t(:row_comment_stopOrderType) |
|> price |string |t(:row_comment_resp_price) |
|> qty |string |t(:contract_comment_qty) |
|> timeInForce |string |t(:row_comment_timeInForce) |
|> orderStatus |string |t(:row_comment_orderStatus) |
|> triggerPrice |string |t(:contract_comment_getOrderTriggerPrice) |
|> orderLinkId |string |t(:row_comment_orderLinkId) |
|> createdTime |string |t(:row_comment_created_at) |
|> updatedTime |string |t(:row_comment_updated_at) |
|> takeProfit |string |t(:row_comment_take_profit) |
|> stopLoss |string |t(:row_comment_stop_loss) |
|> <a href="#trigger-price-type-triggerby">tpTriggerBy</a> |string |t(:contract_comment_tpTriggerBy) |
|> <a href="#trigger-price-type-triggerby">slTriggerBy</a> |string |t(:contract_comment_slTriggerBy) |
|> <a href="#trigger-price-type-triggerby">triggerBy</a> |string |t(:contract_comment_triggerBy) |
|> reduceOnly |boolean |t(:linear_resp_field_reduce_only) |
|> leavesQty |string |t(:row_comment_leaves_qty) |
|> leavesValue |string |t(:row_comment_leaves_value) |
|> cumExecQty |string |t(:linear_resp_field_cum_exec_qty) |
|> cumExecValue |string |t(:linear_resp_field_cum_exec_value) |
|> cumExecFee |string |t(:linear_resp_field_cum_exec_fee) |
|> triggerDirection |string |t(:contract_comment_triggerDirection) |
|> cancelType |string |t(:contract_comment_cancelType) |
|> lastPriceOnCreated |string |t(:row_comment_last_exec_price) |
|> iv |string |t(:row_comment_iv_v3) |
|> closeOnTrigger |boolean |t(:row_response_close_on_trigger) |
|> placeType |string |t(:optionPlaceType_comment) |
|> blockTradeId |string |t(:blockTradeId) |
|nextPageCursor |string |t(:row_comment_query_nextPageCursor_v3)  |
|category |string |dv3_orderbook_category |


## t(:position)
### t(:dv_myposition)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/contract/v3/private/position/list?settleCoin=USDC&category=future' \
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
// future response sample
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "list": [
            {
                "positionIdx": 0,
                "riskId": "3",
                "symbol": "ETHPERP",
                "side": "Buy",
                "size": "0.2",
                "positionValue": "233.02",
                "entryPrice": "1165.1",
                "tradeMode": 0,
                "autoAddMargin": 0,
                "leverage": "12.00",
                "positionBalance": "",
                "liqPrice": "0.05",
                "bustPrice": "",
                "takeProfit": "1500",
                "stopLoss": "800",
                "trailingStop": "",
                "unrealisedPnl": "-3.05",
                "createdTime": "1669027272474",
                "updatedTime": "1669334400433",
                "tpSlMode": "UNKNOWN",
                "riskLimitValue": "800000",
                "activePrice": "",
                "markPrice": "1185.55",
                "cumRealisedPnl": "6.8814698",
                "positionMM": "4.935288",
                "positionIM": "20.14542294",
                "positionStatus": "Normal",
                "sessionAvgPrice": "1200.8"
            }
        ],
        "category": "future",
        "nextPageCursor": ""
    },
    "retExtInfo": {},
    "time": 1669347306741
}
```

t(:contract_para_position)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pList>/contract/v3/private/position/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#category-category">category</a> |false |string |t(:dv3_trade_category) |
|t(:row_parameter_symbol) |false |string |t(:contract_comment_realtimeOrderSymbol)    |
|settleCoin |false |string |t(:contract_comment_positionSettleCoin)    |
|baseCoin |false |string |t(:dv3_queryOrder_baseCoin)    |
|limit |false |number |t(:row_comment_limit) |
|cursor |false |string |t(:row_comment_resp_cursor)   |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list |array |Object |
|> positionIdx |integer |t(:row_comment_position_idx)  |
|> riskId  |integer |t(:contract_comment_riskId) |
|> t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|> t(:row_parameter_side) |string |t(:row_comment_side)  |
|> size |string |t(:row_comment_position_size)  |
|> positionValue |string |t(:row_comment_position_value)  |
|> entryPrice |string |t(:linear_resp_field_entry_price)  |
|> tradeMode |integer |t(:contract_comment_tradeMode) |
|> autoAddMargin |integer |t(:row_comment_auto_add_margin)  |
|> leverage |string |t(:resp_field_leverage)  |
|> positionBalance |string |t(:contract_comment_positionBalance)  |
|> liqPrice |string |t(:linear_resp_field_liq_price)  |
|> bustPrice |string |t(:linear_resp_field_bust_price)  |
|> takeProfit |string |t(:row_comment_take_profit)  |
|> stopLoss |string |t(:row_comment_stop_loss)  |
|> trailingStop |string |t(:row_comment_trailing_stop)  |
|> unrealisedPnl |string |t(:row_comment_unrealised_pnl)  |
|> createdTime |string |t(:row_comment_created_at)  |
|> updatedTime |string |t(:row_comment_updated_at)  |
|> <a href="#tp-sl-mode-tpslmode">tpSlMode</a> |string |t(:row_comment_tp_sl_mode)  |
|> riskLimitValue | string | t(:contract_position_riskLimitValue) |
|> activePrice | string | t(:account_row_comment_activePrice_v3) |
|> markPrice |string |t(:row_comment_query_markPrice_v3)  |
|> cumRealisedPnl |string |t(:row_comment_query_cumRealisedPnl_v3)  |
|> positionMM |string |t(:row_comment_query_positionMM_v3)  |
|> positionIM |string |t(:row_comment_query_positionIM_v3)  |
|> sessionAvgPrice |string |t(:row_comment_query_sessionAvgPrice_v3)  |
|category |string |t(:dv3_orderbook_category) |
|nextPageCursor |string |t(:row_comment_query_nextPageCursor_v3)  |

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
    "retExtInfo": null,
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
    "retExtInfo": null,
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
    "retExtInfo": null,
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
    "retExtInfo": null,
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
    "retExtInfo": null,
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
    "retExtInfo": null,
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
    "retExtInfo": null,
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
curl --location --request GET 'https://api-testnet.bybit.com/contract/v3/private/execution/list?symbol=ETHPERP&execType=Trade&limit=1&cursor=118%3A1%2C118%3A1&category=future' \
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
// future response sample
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "list": [
            {
                "symbol": "ETHPERP",
                "execFee": "0.065289",
                "execId": "c613e2c3-b7fb-53b2-9421-f97f1a400a33",
                "execPrice": "1088.15",
                "execQty": "0.1",
                "execType": "Trade",
                "execValue": "108.815",
                "feeRate": "0.0006",
                "lastLiquidityInd": "RemovedLiquidity",
                "leavesQty": "",
                "orderId": "6a70d7b4-a49a-4016-9dc9-e0ac6286a263",
                "orderLinkId": "",
                "orderPrice": "1036.5",
                "orderQty": "0.1",
                "orderType": "Market",
                "stopOrderType": "UNKNOWN",
                "side": "Sell",
                "execTime": "1669107912593",
                "closedSize": "0",
                "iv": "",
                "blockTradeId": "",
                "markPrice": "",
                "markIv": "",
                "underlyingPrice": "",
                "indexPrice": ""
            }
        ],
        "nextPageCursor": "94%3A1%2C94%3A1",
        "category": "future"
    },
    "retExtInfo": {},
    "time": 1669342862947
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
|<a href="#category-category">category</a> |false |string |t(:dv3_trade_category) |
|orderId |false |string |t(:contract_comment_orderId) |
|t(:row_parameter_symbol) |false |string |t(:contract_executionList_symbol) |
|baseCoin |false |string |t(:dv3_queryOrder_baseCoin) |
|orderLinkId |false |string |t(:orderLinkId) |
|<a href="#order-filter-orderfilter">orderFilter</a>|false |string |t(:contract_executionList_orderFilter) |
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
|list> iv |string |t(:usdcIv)  |
|list> blockTradeId |string |t(:blockTradeId)  |
|list> markPrice |string |t(:usdcMarkPrice)  |
|list> markIv |string |t(:usdcMarkPriceIv)  |
|list> underlyingPrice |string |t(:usdcUnderlyingPrice)  |
|list> indexPrice |string |t(:usdcIndexPrice)  |
|nextPageCursor |string |t(:contract_comment_nextPageCursor)  |
|category |string |t(:dv3_orderbook_category)  |


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
    "retExtInfo": null,
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
|startTime |false |number |t(:contract_comment_startTime) |
|endTime |false |number |t(:contract_comment_endTime) |
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
                "serviceCash": "0",
                "accountIM": "",
                "accountMM": ""
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
|list> accountIM |string |t(:contract_wallet_accountIM)  |
|list> accountMM |string |t(:contract_wallet_accountMM)  |


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


### t(:accountConfig)
t(:accountConfig_para)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/contract/v3/private/account/info' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: a197c0d9d19d2465b13062812bbed934938483edb4154eec946f28dd0b989692' \
--header 'X-BAPI-API-KEY: XXXXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1669357817143' \
--header 'X-BAPI-RECV-WINDOW: 5000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "Success.",
    "result": {
        "marginMode": "REGULAR_MARGIN",
        "updateTime": "1663298679000"
    }
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=accountInfo>/contract/v3/private/account/info</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#accountInfo"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|marginMode|string|t(:usdcMarginMode)|
|updateTime |string |t(:contract_accountTakerFeeRate)  |


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
|<a href="#wallet-fund-type-walletfundtype-type">walletFundType</a> |false |string |t(:row_comment_walletFundType) |
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


### t(:dv_queryTransactionLogs)
t(:contract_translog_para)

> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/contract/v3/private/account/transaction-log?category=option&baseCoin=SOL&limit=1' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 9b7bbe921c3b5c0d98696b7123d4f6fb5ca0456689bf6ef018565d5914a62221' \
--header 'X-BAPI-API-KEY: XXXXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1669348789744' \
--header 'X-BAPI-RECV-WINDOW: 5000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
// future response sample
{
    "result": {
        "nextPageCursor": "143%3A0%2C143%3A0",
        "list": [
            {
                "symbol": "ETHPERP",
                "side": "Buy",
                "funding": "-0.024016",
                "orderLinkId": "",
                "orderId": "",
                "fee": "",
                "change": "1.465984",
                "cashFlow": "1.49",
                "transactionTime": "1669334400000",
                "type": "SETTLEMENT",
                "feeRate": "0.0001",
                "size": "0.2",
                "qty": "",
                "cashBalance": "1161.9742137",
                "category": "future",
                "tradePrice": "",
                "tradeId": "",
                "info": ""
            }
        ]
    },
    "retCode": 0,
    "retMsg": "Success."
}

// option response sample
{
    "result": {
        "nextPageCursor": "131%3A2%2C131%3A2",
        "list": [
            {
                "symbol": "SOL-25NOV22-6-C",
                "side": "Buy",
                "funding": "",
                "orderLinkId": "",
                "orderId": "60995a22-9adf-441b-bbcf-4b64ed98b6d6",
                "fee": "0.04278",
                "change": "-87.04278",
                "cashFlow": "-87",
                "transactionTime": "1669266991057",
                "type": "TRADE",
                "feeRate": "0.0003",
                "size": "0",
                "qty": "10",
                "cashBalance": "1158.1461957",
                "category": "option",
                "tradePrice": "8.7",
                "tradeId": "859e4742-42ac-5a27-b643-6d14c9746b45",
                "info": ""
            }
        ]
    },
    "retCode": 0,
    "retMsg": "Success."
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=cnTranLog>/contract/v3/private/account/transaction-log</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#cnTranLog"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |false |string |t(:contract_translog_category)    |
|baseCoin |false |string |t(:usdcBaseCoinUM_transLog)   |
|t(:row_comment_query_transType_v3) |false |string |t(:row_comment_type_v3)   |
|startTime |false |number |t(:row_comment_startTime_v3)   |
|endTime |false |number |t(:row_comment_endTime_v3)   |
|direction |false |string |t(:row_comment_direction_v3)   |
|limit |false |number |t(:row_comment_limit_v3)   |
|cursor |false |string |t(:row_comment_cursor_v3)   |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|nextPageCursor |string |t(:row_comment_query_nextPageCursor_v3)  |
|list> symbol |string |t(:usdcSymbol) |
|list> t(:row_parameter_side) |string |t(:side) |
|list> funding |string |t(:usdcFunding) |
|list> orderLinkId |string |t(:orderLinkId) |
|list> orderId |string |t(:usdcOrderId) |
|list> fee |string |t(:fee) |
|list> change |string |t(:usdcChange) |
|list> cashFlow |string |t(:cashFlow) |
|list> transactionTime |string |t(:transactionTime) |
|list> type |string |t(:usdcType) |
|list> feeRate |string |t(:feeRate) |
|list> size |string |t(:uscdSize) |
|list> qty |string |t(:usdcOrderQty) |
|list> cashBalance |string |t(:cashBalance) |
|list> category |string |t(:dv3_orderbook_category) |
|list> tradePrice |string |t(:tradePrice) |
|list> tradeId |string |t(:tradeId) |
|list> info |string |t(:usdcInfo) |


### t(:setMarginMode)
t(:setMarginMode_para)

> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/contract/v3/private/account/setMarginMode' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 267202913640ad9be58193d9668aea78ffda937092608cc8f92d3d07604f790f' \
--header 'X-BAPI-API-KEY: XXXXXXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1669358755020' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "setMarginMode": "PORTFOLIO_MARGIN"
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
// success sample
{
    "retCode": 0,
    "retMsg": "Request accepted",
    "result": {
        "reasons": []
    }
}

// fail sample
{
    "retCode": 3400045,
    "retMsg": "Set margin mode failed",
    "result": {
        "reasons": [
            {
                "reasonCode": "3400002",
                "reasonMsg": "Please ensure that there are no active orders in your USDC account, including Limit, Market and Conditional orders"
            },
            {
                "reasonCode": "3400001",
                "reasonMsg": "Please ensure that there are no positions in your USDC account, including USDC perpetual and options"
            }
        ]
    }
}
```
<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=setmarginmode>/contract/v3/private/account/setMarginMode</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#setmarginmode"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|setMarginMode |<b>true</b> |string |t(:usdcMarginMode) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|reasons |array |t(:contract_setMarginMode_reasons)  |
|> reasonCode |string |t(:contract_setMarginMode_reasonCode)  |
|> reasonMsg |string |t(:contract_setMarginMode_reasonMsg)  |


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
