# t(:unified_margin_account_data)
t(:unified_margin_account_para)

## t(:order)
### t(:placeOrderV3)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/derivatives/unified/v3/private/order/create \
{
  }

```

```python--old

```

```python--pybit

```


> t(:codequote_responseExample)

```javascript

```

t(:account_para_placeActive_v3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/unified/v3/private/order/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|t(:row_parameter_side) |<b>true</b> |string |t(:row_comment_side_v3)    |
|positionIdx |false |string |t(:row_comment_positionIdx_v3)   |
|<a href="#order-type-order_type">orderType</a> |<b>true</b> |string |t(:row_comment_orderType_v3)   |
|t(:row_parameter_quantity) |<b>true</b> |string |t(:row_comment_qty_v3) |
|t(:row_parameter_price) |false |string |t(:row_comment_resp_price) |
|triggerSide |false |number |t(:row_comment_triggerSide) |
|triggerPrice |false |string |t(:row_comment_triggerPrice) |
|<a href="#trigger-price-type-trigger_by">triggerBy</a> |false |string |t(:row_comment_triggerBy_v3) |
|iv |false |string |t(:row_comment_iv_v3) |
|<a href="#time-in-force-time_in_force">timeInForce</a> |<b>true</b> |string |t(:row_comment_timeInForce_v3) |
|orderLinkId |false |string |t(:row_comment_orderLinkId_v3) |
|takeProfit |false |number |t(:row_comment_takeProfit_v3) |
|stopLoss |false |number |t(:row_comment_stopLoss_v3) |
|tpTriggerBy |false |string |t(:account_row_comment_tp_trigger_by_v3) |
|slTriggerBy |false |string |t(:account_row_comment_sl_trigger_by_v3) |
|reduceOnly |false |bool |t(:row_comment_reduceOnly_v3) |
|closeOnTrigger |false |bool |t(:row_comment_closeOnTrigger_v3) |
|mmp |false |bool |t(:row_comment_mmp_v3) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments) |
|:----- |:-----|----- |
|category |string |t(:row_comment_category_v3) |
|orderId |string |t(:row_comment_order_id) |
|orderLinkId |string |t(:row_comment_orderLinkId_response_v3) |

### t(:replaceOrderV3)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/private/order/replace \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","order_id":"","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Order.Order_replace(symbol="BTCUSD", order_id="").result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.replace_active_order(
    symbol="BTCUSD",
    order_id="efa44157-c355-4a98-b6d6-1d846a936b93"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": {
        "order_id": "efa44157-c355-4a98-b6d6-1d846a936b93"
    },
    "time_now": "1539778407.210858",
    "rate_limit_status": 99,
    "rate_limit_reset_ms": 1580885703683,
    "rate_limit": 100             
}
```

t(:account_para_replaceActive_v3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoReplace>/unified/v3/private/order/replace</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoReplace"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|orderId |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|orderLinkId |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |
|orderFilter |false |string |t(:row_comment_orderFilter_v3)   |
|iv |false |string |t(:row_comment_iv_v3) |
|triggerPrice |false |string |t(:row_comment_triggerPrice_replace_v3) |
|t(:row_parameter_quantity) |false |string |t(:row_comment_qty_replace_v3) |
|t(:row_parameter_price) |false |string |t(:row_comment_price_replace_v3) |
|takeProfit |false |number |t(:row_comment_takeProfit_replace_v3) |
|stopLoss |false |number |t(:row_comment_stopLoss_replace_v3) |
|tpTriggerBy |false |string |t(:account_row_comment_tp_trigger_by_v3) |
|slTriggerBy |false |string |t(:account_row_comment_sl_trigger_by_v3) |
|<a href="#trigger-price-type-trigger_by">triggerBy</a> |false |string |t(:row_comment_triggerBy_v3) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:row_comment_category_v3) |
|orderId |string |t(:row_comment_order_id) |
|orderLinkId |string |t(:row_comment_orderLinkId_response_v3) |


### t(:cancelOrderV3)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/private/order/cancel \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","order_id":"","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Order.Order_cancel(symbol="BTCUSD", order_id="").result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.cancel_active_order(
    symbol="BTCUSD",
    order_id="3bd1844f-f3c0-4e10-8c25-10fea03763f6"
))
```


> t(:codequote_responseExample)

```javascript

```

t(:account_para_cancelActive_v3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCancel>/unified/v3/private/order/cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|orderId |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|orderLinkId |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |
|orderFilter |false |string |t(:row_comment_orderFilter_v3)   |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:row_comment_category_v3) |
|orderId |string |t(:row_comment_order_id) |
|orderLinkId |string |t(:row_comment_orderLinkId_response_v3) |


### t(:queryOrderRealtimeV3)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/order?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}order_id={order_id}&sign={sign}"
```

```python--old

```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

```
t(:account_para_queryActive_v3)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpOrder>/unified/v3/private/order/unfilled-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|orderId |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|orderLinkId |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |
|orderFilter |false |string |t(:row_comment_orderFilter_v3)   |
|direction |false |string |t(:row_comment_direction_v3)   |
|limit |false |number |t(:row_comment_limit_v3)   |
|cursor |false |string |t(:row_comment_cursor_v3)   |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:row_comment_category_v3)    |
|list> symbol |string |t(:row_comment_symbol_v3)   |
|list> orderId |string |t(:row_comment_query_orderId_v3) |
|list> side |string |t(:row_comment_query_side_v3)  |
|list> orderType |string |t(:row_comment_query_orderType_v3)  |
|list> stopOrderType |string |t(:row_comment_query_stopOrderType_v3)  |
|list> price |string |t(:row_comment_query_price_v3)  |
|list> qty |string |t(:row_comment_query_qty_v3)  |
|list> iv |string |t(:row_comment_query_iv_v3)  |
|list > orderIM |string |t(:row_comment_query_orderIM_v3)  |
|list > timeInForce |string |t(:row_comment_query_timeInForce_v3)  |
|list > orderStatus |string |t(:row_comment_query_orderStatus_v3)  |
|list > triggerPrice |string |t(:row_comment_query_triggerPrice_v3)  |
|list > orderLinkId |string |t(:row_comment_query_orderLinkId_v3)  |
|list > createdTime |number |t(:row_comment_query_createdTime_v3)  |
|list > updatedTime |number |t(:row_comment_query_updatedTime_v3)  |
|list > takeProfit |string |t(:row_comment_query_takeProfit_v3)  |
|list > stopLoss |string |t(:row_comment_query_stopLoss_v3)  |
|list > tpTriggerBy |string |t(:row_comment_query_tpTriggerBy_v3)  |
|list > slTriggerBy |string |t(:row_comment_query_slTriggerBy_v3)  |
|list > basePrice |string |t(:row_comment_query_basePrice_v3)  |
|list > triggerBy |string |t(:row_comment_query_triggerBy_v3)  |
|list > reduceOnly |bool |t(:row_comment_query_reduceOnly_v3)  |
|list > closeOnTrigger |bool |t(:row_comment_query_closeOnTrigger_v3)  |
|nextPageCursor |string |t(:row_comment_query_nextPageCursor_v3)  |


### t(:getOrderV3)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/unified/v3/private/order/list?category=linear&symbol=XRPUSDT&api_key={{bybit-api-key}}&timestamp={{timestamp}}&sign={{signature}}"
```

```python--old
// change to v3
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Order.Order_getOrders(symbol="BTCUSD",order_status="New").result())
```

```python--pybit
// change to v3
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.get_active_order(
    symbol="BTCUSD",
    order_status="New"
))
```

> t(:codequote_responseExample)

```javascript
{
  "ret_code": 10017,
    "ret_msg": "path not fund, please check request path and method",
    "ext_code": "",
    "result": null,
    "ext_info": null,
    "time_now": "1654160527.252875"
}
```

t(:account_para_getActive_v3)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpoList>/unified/v3/private/order/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|orderId |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|orderLinkId |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |
|orderStatus |false |string |t(:row_comment_orderStatus_v3)   |
|orderFilter |false |string |t(:row_comment_orderFilter_v3)   |
|direction |false |string |t(:row_comment_direction_v3)   |
|limit |false |number |t(:row_comment_limit_v3)   |
|cursor |false |string |t(:row_comment_cursor_v3)   |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:row_comment_category_v3)    |
|list> symbol |string |t(:row_comment_symbol_v3)   |
|list> side |string |t(:row_comment_query_side_v3)  |
|list> orderType |string |t(:row_comment_query_orderType_v3)  |
|list> price |string |t(:row_comment_query_price_v3)  |
|list> qty |string |t(:row_comment_query_qty_v3)  |
|list> iv |string |t(:row_comment_query_iv_v3)  |
|list > orderIM |string |t(:row_comment_query_orderIM_v3)  |
|list > reduceOnly |bool |t(:row_comment_query_reduceOnly_v3)  |
|list > timeInForce |string |t(:row_comment_query_timeInForce_v3)  |
|list > orderStatus |string |t(:row_comment_query_orderStatus_v3)  |
|list > leavesQty |string |t(:row_comment_query_leavesQty_v3)  |
|list > leavesValue |string |t(:row_comment_query_leavesValue_v3)  |
|list > cumExecQty |string |t(:row_comment_query_cumExecQty_v3)  |
|list > cumExecValue |string |t(:row_comment_query_cumExecValue_v3)  |
|list > cumExecFee |string |t(:row_comment_query_cumExecFee_v3)  |
|list > basePrice |string |t(:row_comment_query_basePrice_v3)  |
|list > rejectReason |string |t(:row_comment_query_rejectReason_v3)  |
|list > orderLinkId |string |t(:row_comment_query_orderLinkId_v3)  |
|list > createdTime |number |t(:row_comment_query_createdTime_v3)  |
|list > updatedTime |number |t(:row_comment_query_updatedTime_v3)  |
|list> orderId |string |t(:row_comment_query_orderId_v3) |
|list> stopOrderType |string |t(:row_comment_query_stopOrderType_v3)  |
|list > takeProfit |string |t(:row_comment_query_takeProfit_v3)  |
|list > stopLoss |string |t(:row_comment_query_stopLoss_v3)  |
|list > triggerPrice |string |t(:row_comment_query_triggerPrice_v3)  |
|list > tpTriggerBy |string |t(:row_comment_query_tpTriggerBy_v3)  |
|list > slTriggerBy |string |t(:row_comment_query_slTriggerBy_v3)  |
|list > closeOnTrigger |bool |t(:row_comment_query_closeOnTrigger_v3)  |
|nextPageCursor |string |t(:row_comment_query_nextPageCursor_v3)  |

### t(:batchPlaceOrder)

t(:usdcBatchOrdersDesc)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/batch-place-orders \
-H "Content-Type: application/json" \
-D '{"orderRequest":[{"symbol":"BTC-26NOV21-58000-P","orderType":"Limit","side":"Buy","orderQty":"1","orderPrice":"1","timeInForce":"GoodTillCancel"}]}'


```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": [
        {
            "orderId": "fa6cd740-56ed-477d-9385-90ccbfee49ca",
            "orderLinkId": "AAAAA4112",
            "symbol": "BTC-13MAY22-40000-C",
            "orderType": "Limit",
            "side": "Buy",
            "orderQty": "0.01",
            "orderPrice": "5",
            "extMap": {},
            "errorCode": 0,
            "errorDesc": ""
        }
    ],
    "retExtMap": {}
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvBatchPlace>/option/usdc/openapi/private/v1/batch-place-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvBatchPlace"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|orderRequest|<b>true</b>|list|t(:usdcList)|

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b>|string|t(:usdcSymbol)|
|orderType|<b>true</b>|string|t(:usdcOptionOrderType)|
|t(:row_parameter_side) |<b>true</b>|string|t(:side)|
|orderPrice|false|string|t(:usdcOptionPlaceOrderPrice)|
|orderQty|<b>true</b>|string|t(:usdcOrderQty)|
|iv|false|string|t(:optionIv_order)|
|t(:row_parameter_timeInForce)|false|string|t(:row_comment_timeInForce)|
|orderLinkId|<b>true</b>|string|t(:orderLinkId)|
|reduceOnly|false|bool|t(:reduceOnly)|
|mmp|false|string|t(:mmp)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)
|t(:row_parameter_symbol) |string|t(:usdcSymbol)|
|orderPrice|string|t(:usdcOrderPrice)|
|orderQty|string|t(:usdcOrderQty)|
|orderType|string|t(:uscdOrderType)|
|t(:row_parameter_side) |string|t(:side)|
|extMap |map|t(:usdcExtMap)|
|errorCode |string|t(:usdcErrorCode)|
|errorDesc |string|t(:usdcErrorDesc)|

### t(:batchReplaceOrders)

t(:usdcBatchOrdersDesc)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/batch-replace-orders \
-H "Content-Type: application/json" \
-D '{"replaceOrderRequest":[{"symbol":"BTC-26NOV21-58000-P","orderId":"be6c87be-da18-4876-9a64-6b7ccc859071","orderQty":"1","orderPrice":"1"}]}'


```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": [
        {
            "outRequestId": "",
            "symbol": "BTC-13MAY22-40000-C",
            "orderId": "8c65df91-91fc-461d-9b14-786379ef138c",
            "extMap": {},
            "errorCode": 0,
            "errorDesc": "",
            "orderLinkId": "AAAAA41133"
        }
    ],
    "retExtMap": {}
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvBatchReplace>/option/usdc/openapi/private/v1/batch-replace-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvBatchReplace"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|replaceOrderRequest|<b>true</b>|list|t(:usdcList)|


|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b>|string|t(:usdcSymbol)|
|orderId|false|string|t(:usdcOrderLinkId)|
|orderLinkId|false|string|t(:usdcOrderLinkId)|
|orderPrice|false|string|t(:usdcOrderPrice)|
|orderQty|false|string|t(:usdcOrderQty)|
|iv|false|string|t(:optionIv)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|outRequestId|string|t(:outRequestId)|
|symbol|string|t(:usdcSymbol)|
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)|
|extMap |map|t(:usdcExtMap)|
|errorCode |string|t(:usdcErrorCode)|
|errorDesc |string|t(:usdcErrorDesc)|

### t(:batchCancelOrders)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/batch-cancel-orders \
-H "Content-Type: application/json" \
-D '{"cancelRequest":[{"symbol":"BTC-26NOV21-58000-P","orderId":"1a69653f-c3c7-40b4-a492-17316a2086a2"}]}'


```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "retExtMap": {},
    "result": [
        {
            "outRequestId": "",
            "symbol": "BTC-13MAY22-40000-C",
            "orderId": "720b97b4-8e7c-44c9-8417-1160ed82f990",
            "orderLinkId": "AAAAA41134",
            "errorCode": 0,
            "errorDesc": ""
        }
    ]
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvBatchCancel>/option/usdc/openapi/private/v1/batch-cancel-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvBatchCancel"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|cancelRequest|<b>true</b>|list|t(:usdcList)|

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b>|string|t(:usdcSymbol)|
|orderId|false|string|t(:usdcOrderLinkId)|
|orderLinkId|false|string|t(:usdcOrderLinkId)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|outRequestId|string|t(:outRequestId)|
|symbol|string|t(:usdcSymbol)|
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)|
|errorCode |string|t(:usdcErrorCode)|
|errorDesc |string|t(:usdcErrorDesc)|


### t(:cancelAllOrders)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/private/order/cancelAll \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Order.Order_cancelAll(symbol="BTCUSD").result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.cancel_all_active_orders(
    symbol="BTCUSD"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,      
    "ret_msg": "OK",    
    "ext_code": "",     
    "ext_info": "",
    "result": [
        {
            "clOrdID": "89a38056-80f1-45b2-89d3-4d8e3a203a79",  
            "user_id": 1,                                  
            "symbol": "BTCUSD",                                
            "side": "Buy",                                      
            "order_type": "Limit",                              
            "price": "7693.5",                                  
            "qty": 1,                                           
            "time_in_force": "GoodTillCancel",                  
            "create_type": "CreateByUser",                     
            "cancel_type": "CancelByUser",                      
            "order_status": "",                                 
            "leaves_qty": 1,                                    
            "leaves_value": "0",                                
            "created_at": "2019-11-30T10:38:53.564428Z",        
            "updated_at": "2019-11-30T10:38:59.102589Z",        
            "cross_status": "PendingCancel",
            "cross_seq": 387734027                              
        }
    ],
    "time_now": "1575110339.105675",
    "rate_limit_status": 98,
    "rate_limit_reset_ms": 1580885703683,
    "rate_limit": 100
}
```

t(:account_para_cancelAllActive)

<aside class="notice">
t(:account_aside_cancelAllActive)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCancelAll>/v2/private/order/cancelAll</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancelAll"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string | t(:row_comment_symbol) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|clOrdID |string |t(:row_comment_clOrdID)  |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_order_type)  |
|t(:row_parameter_price) |number |t(:row_comment_resp_price)  |
|qty |number |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce) |
|create_type |string |t(:row_comment_create_type)  |
|cancel_type |string |t(:row_comment_cancel_type)  |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|leaves_value |number |t(:row_comment_leaves_value)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|cross_status |string |t(:row_comment_cross_status)  |
|cross_seq |number |t(:row_comment_cross_seq)  |


## t(:position)
### t(:mypositionV3)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/position/list?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}&sign={sign}"
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Positions.Positions_myPosition(symbol="BTCUSD").result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.my_position(
    symbol="BTCUSD"
))
```

> t(:codequote_responseExample)

```javascript

```

t(:account_para_myPosition_v3)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pList>/unified/v3/private/position/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |false |string |t(:row_comment_symbol_v3)   |
|direction |false |string |t(:row_comment_direction_v3)   |
|limit |false |number |t(:row_comment_limit_v3)   |
|cursor |false |string |t(:row_comment_cursor_v3)   |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:row_comment_category_v3)    |
|list> positionIdx |string |t(:row_comment_query_positionIdx_v3)   |
|list> isIsolated |bool |t(:row_comment_query_isIsolated_v3)   |
|list> riskId |bool |t(:row_comment_query_riskId_v3)   |
|list> symbol |string |t(:row_comment_symbol_v3)   |
|list> side |string |t(:row_comment_query_side_v3)  |
|list> size |string |t(:row_comment_query_size_v3)  |
|list> entryPrice |string |t(:row_comment_query_entryPrice_v3)  |
|list> sessionAvgPrice |string |t(:row_comment_query_sessionAvgPrice_v3)  |
|list> leverage |string |t(:row_comment_query_leverage_v3)  |
|list> markPrice |string |t(:row_comment_query_markPrice_v3)  |
|list> sessionUPL |string |t(:row_comment_query_sessionUPL_v3)  |
|list> sessionRPL |string |t(:row_comment_query_sessionRPL_v3)  |
|list> positionIM |string |t(:row_comment_query_positionIM_v3)  |
|list> positionMM |string |t(:row_comment_query_positionMM_v3)  |
|list > takeProfit |string |t(:row_comment_query_takeProfit_v3)  |
|list > stopLoss |string |t(:row_comment_query_stopLoss_v3)  |
|list > trailingStop |string |t(:row_comment_query_trailingStop_v3)  |
|list > positionStatus |string |t(:row_comment_query_positionStatus_v3)  |
|list > positionValue |string |t(:row_comment_query_positionValue_v3)  |
|list > unrealisedPnl |string |t(:row_comment_query_unrealisedPnl_v3)  |
|list > cumRealisedPnl |string |t(:row_comment_query_cumRealisedPnl_v3)  |
|list > createdTime |number |t(:row_comment_query_createdTime_v3)  |
|list > updatedTime |number |t(:row_comment_query_updatedTime_v3)  |
|list > tpslMode |string |t(:row_comment_query_tpslMode_v3)  |
|nextPageCursor |string |t(:row_comment_query_nextPageCursor_v3)  |


### t(:setleverageV3)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/private/position/leverage/save \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","leverage":14,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Positions.Positions_saveLeverage(symbol="BTCUSD", leverage="14").result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.set_leverage(
    symbol="BTCUSD",
    leverage=2
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": 2,
    "ext_info": null,
    "time_now": "1577477968.175013",
    "rate_limit_status": 74,
    "rate_limit_reset_ms": 1577477968183,
    "rate_limit": 75
}
```

t(:linear_account_para_setLeverage_v3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=ulSaveNew>/unified/v3/private/position/leverage/save</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ulSaveNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|buyLeverage |<b>true</b> |number |t(:row_comment_buyLeverage_v3)    |
|sellLeverage |<b>true</b> |number |t(:row_comment_sellLeverage_v3)   |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|leverage |number |t(:row_comment_query_set_leverage_v3)  |

### t(:switchmodeV3)

> t(:codequote_curlExample)

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.full_partial_position_tp_sl_switch(
    symbol="BTCUSD",
    tp_sl_mode="Partial"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "tp_sl_mode": "Partial"
    },
    "time_now": "1598266294.610276",
    "rate_limit_status": 72,
    "rate_limit_reset_ms": 1598266294607,
    "rate_limit": 75
}
```

t(:linear_private_switchmode_v3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vptSwitchMode>/unified/v3/private/position/tpsl/switch-mode</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vptSwitchMode"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|tpSlMode |<b>true</b> |number |t(:row_comment_tpSlMode_v3)    |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|tpSlMode |string |t(:row_comment_query_tpslMode_v3)  |


### t(:setrisklimitV3)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/private/position/risk-limit \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","risk_id":2,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.set_risk_limit(
    symbol="BTCUSD",
    risk_id=2
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "risk_id": 2
    },
    "time_now": "1620283810.393787",
    "token": null
}
```

t(:linear_private_setrisklimit_v3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oawrlList>/unified/v3/private/position/set-risk-limit</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawrlList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|riskId |<b>true</b> |number |t(:row_comment_riskId_v3)  |
|positionIdx |<b>true</b> |number |t(:row_comment_positionIdx_v3)  |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:row_comment_category_v3)    |
|riskId |number |t(:row_comment_riskId_v3)  |

### t(:tradingstopV3)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/private/position/trading-stop \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","stop_loss":7000,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Positions.Positions_tradingStop(symbol="BTCUSD",stop_loss="7000").result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.set_trading_stop(
    symbol="BTCUSD",
    stop_loss=7000
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": {
        "id": 27913,
        "user_id": 1,
        "symbol": "BTCUSD",
        "side": "Buy",
        "size": 5,
        "position_value": 0.0006947,
        "entry_price": 7197.35137469,
        "risk_id": 1,
        "auto_add_margin": 0,
        "leverage": 6.95,
        "position_margin": 9.996e-05,
        "liq_price": 6320,
        "bust_price": 6292.5,
        "occ_closing_fee": 6e-07,
        "occ_funding_fee": 0,
        "take_profit": 0,
        "stop_loss": 7000,
        "trailing_stop": 0,
        "position_status": "Normal",
        "deleverage_indicator": 5,
        "oc_calc_data": "{\"blq\":2,\"blv\":\"0.0002941\",\"slq\":0,\"bmp\":6800.408,\"smp\":0,\"fq\":-5,\"fc\":-0.00004279,\"bv2c\":0.14549282,\"sv2c\":0.14527699}",
        "order_margin": 4.279e-05,
        "wallet_balance": 0.03000227,
        "realised_pnl": -1.26e-06,
        "cum_realised_pnl": -1.306e-05,
        "cum_commission": 0,
        "cross_seq": 444081383,
        "position_seq": 287176872,
        "created_at": "2019-10-19T17:04:55.000Z",
        "updated_at": "2019-12-27T21:17:27.000Z",
        "ext_fields": {
            "trailing_active":"9000",
            "sl_trigger_by": "LastPrice",
            "v": 221,
            "mm": 0
        }
    },
    "ext_info": null,
    "time_now": "1577481447.436689",
    "rate_limit_status": 73,
    "rate_limit_reset_ms": 1577481447443,
    "rate_limit": 75
}
```

t(:account_para_tradingStop_v3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oapTradingStopNew>/unified/v3/private/position/trading-stop</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oapTradingStopNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|takeProfit |false |string |t(:account_row_comment_takeProfit_v3) |
|stopLoss |false |string |t(:account_row_comment_stopLoss_v3) |
|trailingStop |false |string |t(:account_row_comment_trailingStop_v3) |
|tpTriggerBy |false |string |t(:account_row_comment_tpTriggerBy_v3) |
|slTriggerBy |false |string |t(:account_row_comment_slTriggerBy_v3) |
|activePrice |false |string |t(:account_row_comment_activePrice_v3) |
|slSize |false |string |t(:account_row_comment_slSize_v3) |
|tpSize |false |string |t(:account_row_comment_tpSize_v3) |
|positionIdx |false |string |t(:row_comment_positionIdx_v3) |


### t(:userTradeRecords7DayV3)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/execution/list?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}&sign={sign}"
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Execution.Execution_getTrades(symbol="BTCUSD").result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.user_trade_records(
    symbol="BTCUSD"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "order_id": "t(:comment_abandoned)",
        "trade_list": [
            {
                "closed_size": 0,
                "cross_seq": 277136382,
                "exec_fee": "0.0000001",
                "exec_id": "256e5ef8-abfe-5772-971b-f944e15e0d68",
                "exec_price": "8178.5",
                "exec_qty": 1,
                "exec_time": "1571676941.70682",
                "exec_type": "Trade",
                "exec_value": "0.00012227",
                "fee_rate": "0.00075",
                "last_liquidity_ind": "RemovedLiquidity",
                "leaves_qty": 0,
                "nth_fill": 2,
                "order_id": "7ad50cb1-9ad0-4f74-804b-d82a516e1029",
                "order_link_id": "",
                "order_price": "8178",
                "order_qty": 1,
                "order_type": "Market",
                "side": "Buy",
                "symbol": "BTCUSD",
                "user_id": 1,
                "trade_time_ms": 1577480599000
            }
        ]
    },
    "time_now": "1577483699.281488",
    "rate_limit_status": 118,
    "rate_limit_reset_ms": 1577483699244737,
    "rate_limit": 120
}
```

t(:wallet_para_tradeRecords_v3)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpeList>/unified/v3/private/execution/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpeList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|orderId |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|orderLinkId |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |
|orderFilter |false |string |t(:row_comment_orderFilter_v3)   |
|startTime |false |number |t(:row_comment_startTime_v3)   |
|endTime |false |number |t(:row_comment_endTime_v3)   |
|direction |false |string |t(:row_comment_direction_v3)   |
|limit |false |number |t(:row_comment_limit_v3)   |
|cursor |false |string |t(:row_comment_cursor_v3)   |
|execType |false |string |t(:row_comment_execType_v3)   |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:row_comment_category_v3)    |
|list> symbol |string |t(:row_comment_symbol_v3)   |
|list> execFee |string |t(:row_comment_query_execFee_v3)  |
|list> execId |string |t(:row_comment_query_execId_v3)  |
|list> execPrice |string |t(:row_comment_query_execPrice_v3)  |
|list> execQty |string |t(:row_comment_query_execQty_v3)  |
|list> execType |string |t(:row_comment_query_execType_v3)  |
|list> execValue |string |t(:row_comment_query_execValue_v3)  |
|list> feeRate |string |t(:row_comment_query_feeRate_v3)  |
|list> lastLiquidityInd |string |t(:row_comment_query_lastLiquidityInd_v3)  |
|list > leavesQty |string |t(:row_comment_query_leavesQty_v3)  |
|list> orderId |string |t(:misc_row_comment_query_orderId_v3) |
|list > orderLinkId |string |t(:row_comment_query_orderLinkId_v3)  |
|list> orderPrice |string |t(:row_comment_query_price_v3)  |
|list> orderQty |string |t(:row_comment_query_qty_v3)  |
|list> orderType |string |t(:row_comment_query_orderType_v3)  |
|list> stopOrderType |string |t(:row_comment_query_stopOrderType_v3)  |
|list> side |string |t(:row_comment_query_side_v3)  |
|list> execTime |number |t(:row_comment_query_execTime_v3)  |
|nextPageCursor |string |t(:row_comment_query_nextPageCursor_v3)  |

### t(:queryOptionDeliveryLogV3)

> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/query-delivery-list \
-H "Content-Type: application/json" \
-d '{"symbol":"BTC-22OCT21-45000-C"}'
```

```python

```


> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"OK",
    "result":{
    "resultTotalSize":1,
      "cursor":"ccc62b1a-e1a0-42b6-86b5-3570e22cfbdf%3A1634284800789%2Cb09397d8-4da1-4d32-b70f-c59efd381f66%3A1634284800769",
      "dataList":[
      {
        "deliveryTime":"1634284800789",
        "symbol":"BTC-15OCT21-30000-P",
        "side":"Buy",
        "position":"0.00",
        "deliveryPrice":"59307.0",
        "strike":"30000",
        "fee":"0.0000",
        "deliveryRpl":"0.0000"
      }
    ]
  }
}
```

t(:wallet_para_delivery_record_v3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvQueryDelivery>/unified/v3/private/delivery-record</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvQueryDelivery"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |false |string |t(:row_comment_symbol_v3)   |
|expDate |false |string |t(:row_comment_expDate_v3)   |
|direction |false |string |t(:row_comment_direction_v3)   |
|limit |false |number |t(:row_comment_limit_v3)   |
|cursor |false |string |t(:row_comment_cursor_v3)   |


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:row_comment_category_v3)    |
|list> deliveryTime |number |t(:row_comment_deliveryTime_v3)   |
|list> symbol |string |t(:row_comment_symbol_v3)   |
|list> side |string |t(:row_comment_query_side_v3)  |
|list> position |string |t(:row_comment_query_position_v3)  |
|list> deliveryPrice |string |t(:row_comment_query_deliveryPrice_v3)  |
|list> strike |string |t(:row_comment_query_strike_v3)  |
|list> fee |string |t(:row_comment_query_fee_v3)  |
|list> deliveryRpl |string |t(:row_comment_query_deliveryRpl_v3)  |
|nextPageCursor |string |t(:row_comment_query_nextPageCursor_v3)  |


### t(:querySettleLogsV3)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/session-settlement \
-H "Content-Type: application/json" \
-d '{"symbol":"BTCPERP"}'

```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "Success.",
    "result": {
        "resultTotalSize": 20,
        "cursor": "4327:0,4286:0",
        "dataList": [
            {
                "time": "1650240000000",
                "symbol": "BTCPERP",
                "side": "Buy",
                "size": "0.001",
                "sessionAvgPrice": "39685.53",
                "markPrice": "39686.28",
                "sessionRpl": "-0.7730"
            }
        ]
    }
}
```

t(:wallet_para_settlement_record_v3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=upovSession>/unified/v3/private/settlement-record</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#upovSession"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|expDate |false |string |t(:row_comment_expDate_v3)   |
|direction |false |string |t(:row_comment_direction_v3)   |
|limit |false |number |t(:row_comment_limit_v3)   |
|cursor |false |string |t(:row_comment_cursor_v3)   |


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:row_comment_category_v3)    |
|list> symbol |string |t(:row_comment_symbol_v3)   |
|list> side |string |t(:row_comment_query_side_v3)  |
|list> size |string |t(:row_comment_query_size_v3)  |
|list> sessionAvgPrice |string |t(:row_comment_query_sessionAvgPrice_v3)  |
|list> markPrice |string |t(:row_comment_query_markPrice_v3)  |
|list> sessionRpl |string |t(:row_comment_query_sessionRpl_v3)  |
|nextPageCursor |string |t(:row_comment_query_nextPageCursor_v3)  |

## t(:account)
t(:wallet_para)


### t(:balanceV3)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/wallet/balance?api_key={api_key}&coin=BTC&timestamp={timestamp}&sign={sign}"
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Wallet.Wallet_getBalance(coin="BTC").result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.get_wallet_balance(coin="BTC"))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "BTC": {
            "equity": 1002,
            "available_balance": 999.99987471,
            "used_margin": 0.00012529,
            "order_margin": 0.00012529,
            "position_margin": 0,
            "occ_closing_fee": 0,
            "occ_funding_fee": 0,
            "wallet_balance": 1000,
            "realised_pnl": 0,
            "unrealised_pnl": 2,
            "cum_realised_pnl": 0,
            "given_cash": 0,
            "service_cash": 0
        }
    },
    "time_now": "1578284274.816029",
    "rate_limit_status": 98,
    "rate_limit_reset_ms": 1580885703683,
    "rate_limit": 100
}
```

t(:wallet_para_walletBalance_v3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpwBalance>/unified/v3/private/account/wallet/balance</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpwBalance"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|coin |false |string |t(:row_comment_coin_v3)    |


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


### t(:upgradeUnifiedAccountV3)
t(:wallet_para_upgradeUnifiedMarginAccount_v3)


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpeOrder>/unified/v3/private/account/upgrade-unified-account</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpeOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|result |string |t(:row_comment_query_result_v3) |
|msg |string |t(:row_comment_query_msg_v3)  |

<p class="fake_header">t(:resonoferror)</p>
|t(:column_parameter)|t(:column_comments)|
|:----- |:-----|----- |
|There is USDC being transferred |t(:row_comment_query_ThereisUSDCbeingtransferred_v3) |
|There is USDT being transferred |t(:row_comment_query_ThereisUSDTbeingtransferred_v3) |
|There are USDC perpetual position holdings |t(:row_comment_query_ThereareUSDCperpetualpositionholdings_v3) |
|There are USDC options position holdings |t(:row_comment_query_ThereareUSDCoptionspositionholdings_v3) |
|There are USDT perpetual position holdings |t(:row_comment_query_ThereareUSDTperpetualpositionholdings_v3) |
|There are USDC perpetual orders |t(:row_comment_query_ThereareUSDCperpetualorders_v3) |
|There are USDC option orders |t(:row_comment_query_ThereareUSDCoptionorders_v3) |
|There are USDT perpetual orders |t(:row_comment_query_ThereareUSDTperpetualorders_v3) |

### t(:queryTransactionLogsV3)
t(:wallet_para_tradingHistory_v3)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpwBalance>/unified/v3/private/account/transaction-log</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpwBalance"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|currency |<b>true</b> |string |t(:row_comment_currency_v3)   |
|baseCoin |false |string |t(:row_comment_baseCoin_v3)   |
|type |false |string |t(:row_comment_type_v3)   |
|startTime |false |number |t(:row_comment_startTime_v3)   |
|endTime |false |string |t(:row_comment_endTime_v3)   |
|direction |false |string |t(:row_comment_direction_v3)   |
|limit |false |number |t(:row_comment_limit_v3)   |
|cursor |false |string |t(:row_comment_cursor_v3)   |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|category |string |t(:row_comment_category_v3)    |
|currency |string |t(:row_comment_query_currency_v3)    |
|list> transactionTime |string |t(:row_comment_query_transactionTime_v3)   |
|list> type |string |t(:row_comment_query_type_v3)  |
|list> symbol |string |t(:row_comment_query_symbol_v3)  |
|list> side |string |t(:row_comment_query_side_v3)  |
|list> qty |string |t(:row_comment_query_qty_v3)  |
|list> size |string |t(:row_comment_query_size_v3)  |
|list> tradePrice |string |t(:row_comment_query_tradePrice_v3)  |
|list> funding |string |t(:row_comment_query_funding_v3)  |
|list> fee |string |t(:row_comment_query_fee_v3)  |
|list> cashFlow |string |t(:row_comment_query_cashFlow_v3)  |
|list> change |string |t(:row_comment_query_change_v3)  |
|list> cashBalance |string |t(:row_comment_query_cashBalance_v3)  |
|list> feeRate |string |t(:row_comment_query_feeRate_v3)  |
|list> tradeId |string |t(:row_comment_query_tradeId_v3)  |
|list> orderId |string |t(:row_comment_query_orderId_v3)  |
|list> orderLinkId |string |t(:row_comment_query_orderLinkId_v3)  |
|nextPageCursor |string |t(:row_comment_query_nextPageCursor_v3)  |



### t(:transferV3)
t(:wallet_para_transfers_v3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpwBalance>/asset/v1/private/transfer</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpwBalance"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|transfer_id |<b>true</b> |string |t(:row_comment_transfer_id_v3)    |
|amount |<b>true</b> |string |t(:row_comment_amount_v3)    |
|coin |<b>true</b> |string |t(:row_comment_coin_v3)   |
|from_account_type |<b>true</b> |string |t(:row_comment_from_account_type_v3)   |
|to_account_type |<b>true</b> |string |t(:row_comment_to_account_type_v3)   |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transfer_id |string |t(:row_comment_query_transfer_id_v3)    |


### t(:queryExchangeRecords)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/exchange-order/list?api_key={api_key}&timestamp={timestamp}&sign={sign}"
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.asset_exchange_records())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": [
        {
            "id": 31,
            "exchange_rate": 40.57202774,
            "from_coin": "BTC",
            "to_coin": "ETH",
            "to_amount": 4.05720277,
            "from_fee": 0.0005,
            "from_amount": 0.1,
            "created_at": "2020-06-15 03:32:52"
        },
        {
            "id": 30,
            "exchange_rate": 39.92359901,
            "from_coin": "BTC",
            "to_coin": "ETH",
            "to_amount": 39.923599,
            "from_fee": 0.0005,
            "from_amount": 1,
            "created_at": "2020-06-12 08:27:51"
        }
    ],
    "time_now": "1592554785.486414",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1592554785484,
    "rate_limit": 120
}

```

t(:wallet_para_assetexchangerecords)


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpeOrder>/asset/v2/private/exchange/exchange-order-all</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpeOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|fromCoin |false |string |t(:row_comment_fromCoin_v3) |
|toCoin |false |string |t(:row_comment_toCoin_v3) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|totalCount |number |t(:row_comment_query_totalCount_v3) |
|list > fromCoin |string |t(:row_comment_query_fromCoin_v3)  |
|list > fromAmount |string |t(:row_comment_query_fromAmount_v3)  |
|list > toCoin |string |t(:row_comment_query_toCoin_v3)  |
|list > toAmount |string |t(:row_comment_query_toAmount_v3)  |
|list > exchangeRate |string |t(:row_comment_query_exchangeRate_v3)  |
|list > createdAt |string |t(:row_comment_query_createdAt_v3)  |
|list > exchangeTxId |string |t(:row_comment_query_exchangeTxId_v3)  |

### t(:interestBillStatement)
t(:wallet_para_interestBillStatement)

<aside class="notice">
t(:wallet_para_interestBillStatement)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpwBalance>/unified/v3/private/account/borrow-history</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpwBalance"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|currency |<b>false</b> |string |t(:row_comment_currency_v3)   |
|startTime |<b>false</b> |number |t(:row_comment_startTime_v3)   |
|endTime |<b>false</b> |string |t(:row_comment_endTime_v3)   |
|direction |<b>false</b> |string |t(:row_comment_direction_v3)   |
|limit |<b>false</b> |number |t(:row_comment_limit_v3)   |
|cursor |<b>false</b> |string |t(:row_comment_cursor_v3)   |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> currency |string |t(:row_comment_query_currency_v3)   |
|list> createdTime |number |t(:row_comment_query_createdTime_v3)  |
|list> borrowCost |string |t(:row_comment_query_borrowCost_v3)  |
|list> hourlyBorrowRate |string |t(:row_comment_query_hourlyBorrowRate_v3)  |
|list> borrowSize |string |t(:row_comment_query_borrowSize_v3)  |
|list> costExemption |string |t(:row_comment_query_costExemption_v3)  |



# 借贷利率查询
### t(:queryLoanInterest)

t(:wallet_para_queryLoanInterest)

<aside class="notice">
t(:wallet_para_queryLoanInterest)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpwBalance>/unified/v3/private/account/borrow-rate</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpwBalance"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|currency |<b>false</b> |string |t(:row_comment_currency_v3)   |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> currency |string |t(:row_comment_query_currency_v3)   |
|list> hourlyBorrowRate |string |t(:row_comment_query_hourlyBorrowRate_v3)  |
|list> maxBorrowingAmount |string |t(:row_comment_query_maxBorrowingAmount_v3)  |
|list> freeBorrowingAmount |string |t(:row_comment_query_freeBorrowingAmount_v3)  |


