# t(:unified_margin_account_data)
t(:unified_margin_account_para)

## t(:order)
### t(:placeOrderV3)
> t(:codequote_curlExample)

```console
curl 'https://api-testnet.bybit.com/unified/v3/private/order/create' \
-H "Content-Type: application/json" \
-d '{
  "api_key":"{api_key}",
  "timestamp":{timestamp},
  "sign":"{sign}",
  "category": "option",
  "symbol": "BTC-20MAR22-32000-P",
  "orderType": "Limit",
  "side": "Buy",
  "qty": "0.01",
  "price": "140",
  "timeInForce": "GoodTillCancel",
  "orderLinkId": "e80d558e-ed"
}'
```

```python--old

```

```python--pybit

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "orderId": "42c86d66331e41998d12c2440ce90c1a",
        "orderLinkId": "e80d558e-ed"
    }
}
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
curl 'https://api-testnet.bybit.com/unified/v3/private/order/replace' \
-H "Content-Type: application/json" \
-d '{
	  "api_key":"{api_key}",
    "timestamp":{timestamp},
    "sign":"{sign}",
    "category": "option",
    "symbol":"BTC-20MAR22-32000-P",
    "orderLinkId": "e80d558e-ed"
    "price":"45000",
    "qty":"0.03"
}'
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
    "retCode": 0,
    "retMsg": "OK",
    "result": {
    "orderId": "42c86d66331e41998d12c2440ce90c1a", 
    "orderLinkId": "e80d558e-ed"
  }
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
curl 'https://api-testnet.bybit.com/unified/v3/private/order/cancel' \
-H "Content-Type: application/json" \
-d '{
  "api_key":"{api_key}",
  "timestamp":{timestamp},
  "sign":"{sign}",
  "category": "option",
  "orderLinkId": "e80d558e-ed",
  "symbol": "BTC-18MAR22-25000-C"
}'
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
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "orderId": "42c86d66331e41998d12c2440ce90c1a",
        "orderLinkId": "e80d558e-ed"
    }
}
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
curl 'https://api-testnet.bybit.com/unified/v3/private/order/unfilled-orders?category=option&symbol=&orderId=&orderLinkId=&orderFilter=&cursor=&direction=&limit=10&api_key={api_key}&timestamp={timestamp}&sign={sign}'
```

```python--old

```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

{
    "retCode": 0,
    "retMsg": "Success",
    "result": {
        "nextPageCursor": "ddd0ec73-eb66-40b7-8fb3-0438dbc3f98d%3A1657714143666%2Cddd0ec73-eb66-40b7-8fb3-0438dbc3f98d%3A1657714143666",
        "category": "option",
        "list": [
            {
                "symbol": "BTC-14JUL22-17500-C",
                "orderType": "Limit",
                "updatedTime": 1657714143680,
                "side": "Buy",
                "orderLinkId": "188889689-yuanzhen-551998998898",
                "orderId": "ddd0ec73-eb66-40b7-8fb3-0438dbc3f98d",
                "orderStatus": "New",
                "iv": "0.00000000",
                "blockTradeId": "",
                "reduceOnly": false,
                "price": "1360.00000000",
                "qty": "0.0200",
                "createdTime": 1657714143666,
                "timeInForce": "GoodTillCancel",
                "orderIM": "27.31897412",
                "basePrice": ""
            }
        ]
    },
    "time": 1657714155151
}

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
|symbol |false |string |t(:row_comment_symbol_v3)   |
|orderId |false |string |t(:row_comment_query_orderId_v3) |
|orderLinkId |false |string |t(:row_comment_query_orderLinkId_v3) |
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
curl 'https://api-testnet.bybit.com/unified/v3/private/order/list?category=linear&symbol=&orderStatus=&orderId=&orderLinkId=&orderFilter=&cursor=&direction=&limit=10&timestamp={timestamp}&sign={sign}'
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
  "retCode": 0,
  "retMsg": "Success",
  "result": {
  "nextPageCursor": "7d17d359-4e38-4d3a-9a31-29791ef2dfd7%3A1657711949928%2C7d17d359-4e38-4d3a-9a31-29791ef2dfd7%3A1657711949928",
    "category": "linear",
    "list": [
    {
      "symbol": "ETHUSDT",
      "orderType": "Market",
      "orderLinkId": "",
      "orderId": "7d17d359-4e38-4d3a-9a31-29791ef2dfd7",
      "stopOrderType": "UNKNOWN",
      "orderStatus": "Filled",
      "takeProfit": "",
      "cumExecValue": "536.92500000",
      "blockTradeId": "",
      "rejectReason": "EC_NoError",
      "price": "1127.10000000",
      "createdTime": 1657711949928,
      "tpTriggerBy": "UNKNOWN",
      "timeInForce": "ImmediateOrCancel",
      "basePrice": "",
      "leavesValue": "0.00000000",
      "updatedTime": 1657711949945,
      "side": "Buy",
      "triggerPrice": "",
      "cumExecFee": "0.32215500",
      "slTriggerBy": "UNKNOWN",
      "leavesQty": "0.0000",
      "closeOnTrigger": false,
      "cumExecQty": "0.5000",
      "reduceOnly": false,
      "qty": "0.5000",
      "stopLoss": "",
      "triggerBy": "UNKNOWN",
      "orderIM": ""
    }
  ]
},
  "time": 1657713451741
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

### t(:batchPlaceOrderV3)

```console
curl 'https://api-testnet.bybit.com/unified/v3/private/order/create-batch' \
-H 'Content-Type: application/json' \
-d '{
    "api_key":"{api_key}",
    "timestamp":{timestamp},
    "sign":"{sign}",
    "category": "option",
    "list": [
        {
        "symbol": "BTC-24JUN22-45000-P",
        "orderType": "Limit",
        "side": "Buy",
        "qty": "0.01",
        "price": "140",
        "timeInForce": "GoodTillCancel",
        "orderLinkId": "5cee727a-2af8-430e-a293-42895e594d18"
        },
        {
        "symbol": "BTC-26AUG22-44000-C",
        "orderType": "Limit",
        "side": "Sell",
        "qty": "0.01",
        "price": "140",
        "timeInForce": "GoodTillCancel",
        "orderLinkId": "5cee727a-2af8-430e-a293-42895e594d18"
        }
    ]
}'
```

```python

```


> t(:codequote_responseExample)

```javascript

{
    "retCode": 0, 
    "retMsg": "OK",
    "result": {
    "list": [{
      "category": "option",
      "symbol": "BTC-24JUN22-45000-P",
      "orderId": "",
      "orderLinkId": "ac4e3b34-d64d-4b60-8188-438fbea4c552",
      "createAt": 0
      }, {
      "category": "option",
      "symbol": "BTC-26AUG22-44000-C",
      "orderId": "",
      "orderLinkId": "5cee727a-2af8-430e-a293-42895e594d18",
      "createAt": 0
      }]
    },
     "retExtInfo": {
     "list": [{
        "code": 10001,
        "msg": "BTC-24JUN22-45000-P does not exist."
      }, {
        "code": 10001,
        "msg": "Invalid order direction."
      }]
      },
     "time": 1657200736570
}

```

t(:usdcBatchOrdersDescV3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvBatchPlace>/unified/v3/private/order/create-batch</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvBatchPlace"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|list> symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|list> t(:row_parameter_side) |<b>true</b> |string |t(:row_comment_side_v3)    |
|list> positionIdx |false |string |t(:row_comment_positionIdx_v3)   |
|list> <a href="#order-type-order_type">orderType</a> |<b>true</b> |string |t(:row_comment_orderType_v3)   |
|list> t(:row_parameter_quantity) |<b>true</b> |string |t(:row_comment_qty_v3) |
|list> t(:row_parameter_price) |false |string |t(:row_comment_resp_price) |
|list> triggerSide |false |number |t(:row_comment_triggerSide) |
|list> triggerPrice |false |string |t(:row_comment_triggerPrice) |
|list> <a href="#trigger-price-type-trigger_by">triggerBy</a> |false |string |t(:row_comment_triggerBy_v3) |
|list> iv |false |string |t(:row_comment_iv_v3) |
|list> <a href="#time-in-force-time_in_force">timeInForce</a> |<b>true</b> |string |t(:row_comment_timeInForce_v3) |
|list> orderLinkId |false |string |t(:row_comment_orderLinkId_v3) |
|list> takeProfit |false |number |t(:row_comment_takeProfit_v3) |
|list> stopLoss |false |number |t(:row_comment_stopLoss_v3) |
|list> tpTriggerBy |false |string |t(:account_row_comment_tp_trigger_by_v3) |
|list> slTriggerBy |false |string |t(:account_row_comment_sl_trigger_by_v3) |
|list> reduceOnly |false |bool |t(:row_comment_reduceOnly_v3) |
|list> closeOnTrigger |false |bool |t(:row_comment_closeOnTrigger_v3) |
|list> mmp |false |bool |t(:row_comment_mmp_v3) |


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> category |string |t(:row_comment_category_v3) |
|list> symbol |string |t(:row_comment_symbol_v3) |
|list> orderId |string |t(:row_comment_query_orderId_v3) |
|list> orderLinkId |string |t(:row_comment_orderLinkId_response_v3) |
|list> createAt |number |t(:row_comment_createAt_response_v3) |


### t(:batchReplaceOrdersV3)

t(:usdcBatchReplaceOrdersDescV3)

```console
curl 'https://api-testnet.bybit.com/unified/v3/private/order/replace-batch' \
-H 'Content-Type: application/json' \
-d '{
    "api_key":"{api_key}",
    "timestamp":{timestamp},
    "sign":"{sign}",
    "category": "option",
    "list": [
        {
        "symbol": "BTC-24JUN22-45000-P",
        "qty": "0.02",
        "orderLinkId": "5cee727a-2af8-430e-a293-42895e594d18"
        },
        {
        "symbol": "BTC-26AUG22-44000-C",
        "price": "145",
        "orderLinkId": "5cee727a-2af8-430e-a293-42895e594d18"
        }
    ]
}'
```

```python

```


> t(:codequote_responseExample)

```javascript

{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
    "list": [{
      "category": "option",
      "symbol": "BTC-24JUN22-45000-P",
      "orderId": "bd5f3b34-d64d-4b60-8188-438fbea4c552",
      "orderLinkId": "ac4e3b34-d64d-4b60-8188-438fbea4c552",
      }, {
      "category": "option",
      "symbol": "BTC-26AUG22-44000-C",
      "orderId": "4ddd727a-2af8-430e-a293-42895e594d18",
      "orderLinkId": "5cee727a-2af8-430e-a293-42895e594d18",
      }]
    },
    "retExtInfo": {
      "list": [{
        "code": 0,
        "msg": "OK"
      }, {
        "code": 0,
        "msg": "OK"
      }]
    },
    "time": 1657200736570
}

```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvBatchReplace>/unified/v3/private/order/replace-batch</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvBatchReplace"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|list> symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|list> orderId |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|list> orderLinkId |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |
|list> iv |false |string |t(:row_comment_iv_v3) |
|list> t(:row_parameter_quantity) |false |string |t(:row_comment_qty_replace_v3) |
|list> t(:row_parameter_price) |false |string |t(:row_comment_price_replace_v3) |


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> category |string |t(:row_comment_category_v3) |
|list> symbol |string |t(:row_comment_symbol_v3) |
|list> orderId |string |t(:row_comment_query_orderId_v3) |
|list> orderLinkId |string |t(:row_comment_orderLinkId_response_v3) |

### t(:batchCancelOrdersV3)

t(:usdcBatchCancelOrdersDescV3)

```console
curl 'https://api-testnet.bybit.com/unified/v3/private/order/cancel-batch' \
-H 'Content-Type: application/json' \
-d '{
    "api_key":"{api_key}",
    "timestamp":{timestamp},
    "sign":"{sign}",
    "category": "option",
    "list": [
        {
        "symbol": "BTC-24JUN22-45000-P",
        "orderLinkId": "5cee727a-2af8-430e-a293-42895e594d18"
        },
        {
        "symbol": "BTC-26AUG22-44000-C",
        "orderLinkId": "5cee727a-2af8-430e-a293-42895e594d18"
        }
    ]
}'
```

```python

```


> t(:codequote_responseExample)

```javascript

{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
    "list": [{
      "category": "option",
      "symbol": "BTC-24JUN22-45000-P",
      "orderId": "bd5f3b34-d64d-4b60-8188-438fbea4c552",
      "orderLinkId": "ac4e3b34-d64d-4b60-8188-438fbea4c552",
      }, {
      "category": "option",
      "symbol": "BTC-26AUG22-44000-C",
      "orderId": "4ddd727a-2af8-430e-a293-42895e594d18",
      "orderLinkId": "5cee727a-2af8-430e-a293-42895e594d18",
      }]
     },
    "retExtInfo": {
      "list": [{
        "code": 0,
        "msg": "OK"
      }, {
        "code": 0,
        "msg": "OK"
      }]
    },
    "time": 1657200736570
}

```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvBatchCancel>/unified/v3/private/order/cancel-batch</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvBatchCancel"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|list> symbol |<b>true</b> |string |t(:row_comment_symbol_v3)   |
|list> orderId |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|list> orderLinkId |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> category |string |t(:row_comment_category_v3) |
|list> symbol |string |t(:row_comment_symbol_v3) |
|list> orderId |string |t(:row_comment_query_orderId_v3) |
|list> orderLinkId |string |t(:row_comment_orderLinkId_response_v3) |


### t(:cancelAllOrdersV3)
> t(:codequote_curlExample)

```console
curl 'https://api-testnet.bybit.com/unified/v3/private/order/cancel-all' \
-H 'Content-Type: application/json' \
-d '{
    "api_key":"{api_key}",
    "timestamp":{timestamp},
    "sign":"{sign}",
    "category": "option",
    "symbol": "BTC-24JUN22-45000-P"
}'
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
    "retCode": 0,
    "retMsg": "OK",
    "result": {
    "list": [{
      "category": "option",
      "symbol": "BTC-24JUN22-45000-P",
      "orderId": "bd5f3b34-d64d-4b60-8188-438fbea4c552",
      "orderLinkId": "ac4e3b34-d64d-4b60-8188-438fbea4c552",
      }, {
      "category": "option",
      "symbol": "BTC-24JUN22-45000-P",
      "orderId": "4ddd727a-2af8-430e-a293-42895e594d18",
      "orderLinkId": "5cee727a-2af8-430e-a293-42895e594d18",
      }]
    },
    "retExtInfo": {
      "list": [{
        "code": 0,
        "msg": "OK"
      }, {
        "code": 0,
        "msg": "OK"
      }]
    },
    "time": 1657200736570
}

```

t(:account_para_cancelAllActive_v3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCancelAll>/unified/v3/private/order/cancel-all</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancelAll"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category |<b>true</b> |string |t(:row_comment_category_v3)    |
|baseCoin |false |string |t(:row_comment_cancelAll_baseCoin_v3)   |
|settleCoin |false |string |t(:row_comment_settleCoin_v3) |
|symbol |false |string |t(:row_comment_symbol_v3) |
|orderFilter |false |string |t(:row_comment_cancelAll_orderFilter_v3) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> category |string |t(:row_comment_category_v3) |
|list> symbol |string |t(:row_comment_symbol_v3) |
|list> orderId |string |t(:row_comment_query_orderId_v3) |
|list> orderLinkId |string |t(:row_comment_orderLinkId_response_v3) |


## t(:position)
### t(:mypositionV3)
> t(:codequote_curlExample)

```console
curl 'https://api-testnet.bybit.com/unified/v3/private/position/list?category=linear&symbol=&cursor=&direction=&limit=10&timestamp={timestamp}&sign={sign}'
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

{
    "retCode": 0,
    "retMsg": "Success",
    "result": {
        "nextPageCursor": "0%3A1657711949945%2C0%3A1657711949945",
        "category": "linear",
        "list": [
            {
                "symbol": "ETHUSDT",
                "leverage": "10",
                "updatedTime": 1657711949945,
                "side": "Buy",
                "positionValue": "536.92500000",
                "takeProfit": "",
                "tpslMode": "Full",
                "riskId": 11,
                "trailingStop": "",
                "entryPrice": "1073.85000000",
                "unrealisedPnl": "",
                "markPrice": "1080.65000000",
                "size": "0.5000",
                "positionStatus": "normal",
                "stopLoss": "",
                "cumRealisedPnl": "-0.32215500",
                "positionMM": "2.97456450",
                "createdTime": 1657711949928,
                "positionIdx": 0,
                "positionIM": "53.98243950"
            }
        ]
    },
    "time": 1657713693182
}

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
curl 'https://api-testnet.bybit.com/unified/v3/private/position/set-leverage' \
-H 'Content-Type: application/json' \
-d '{
    "api_key":"{api_key}",
    "timestamp":{timestamp},
    "sign":"{sign}",
    "category": "linear",
    "symbol":"BTCUSDT",
    "buyLeverage":"5",
    "sellLeverage":"5"
}'
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
    "retCode": 0,
    "retMsg": "OK",
    "result": {},
    "time": 1657720329368
}

```

t(:linear_account_para_setLeverage_v3)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=ulSaveNew>/unified/v3/private/position/set-leverage</span></code>
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

```console
curl 'https://api-testnet.bybit.com/unified/v3/private/position/tpsl/switch-mode' \
-H 'Content-Type: application/json' \
-d '{
    "api_key":"{api_key}",
    "timestamp":{timestamp},
    "sign":"{sign}",
    "category": "linear",
    "symbol":"BCHUSDT",
    "tpSlMode":"Partial"
}'
```

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
    "retCode": 0,
    "retMsg": "OK",
    "result": {},
    "time": 1657720268433
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
curl 'https://api-testnet.bybit.com/unified/v3/private/position/set-risk-limit' \
-H 'Content-Type: application/json' \
-d '{
    "api_key":"{api_key}",
    "timestamp":{timestamp},
    "sign":"{sign}",
    "category": "linear",
    "symbol":"BTCPERP",
    "riskId":10010,
    "positionIdx":0
}'
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
    "retCode": 0,
    "retMsg": "OK",
    "result": {},
    "time": 1657720329368
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
curl 'https://api-testnet.bybit.com/unified/v3/private/position/trading-stop' \
-H 'Content-Type: application/json' \
-d '{
    "api_key":"{api_key}",
    "timestamp":{timestamp},
    "sign":"{sign}",
    "category": "linear",
    "symbol":"BTCUSDT",
    "takeProfit":"45000",
    "stopLoss":"40000",
    "tpTriggerBy":"LastPrice",
    "slTriggerBy":"LastPrice",
    "trailingStop":"",
    "activePrice":"",
    "slSize":"",
    "tpSize":"",
    "positionIdx":0
}'
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
    "retCode": 0,
    "retMsg": "OK",
    "result": {},
    "time": 1657720116299
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
|tpSize |false |string |t(:row_comment_tpSize_v3) |
|positionIdx |false |string |t(:row_comment_positionIdx_v3) |


### t(:userTradeRecords7DayV3)
> t(:codequote_curlExample)

```console

curl 'https://api-testnet.bybit.com/unified/v3/private/execution/list?category=option&orderFilter=&symbol=BTC-14JUL22-17500-C&timestamp={timestamp}&sign={sign}'
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
  "retCode": 0,
    "retMsg": "Success",
    "result": {
    "nextPageCursor": "1565%3A0%2C1565%3A0",
      "category": "option",
      "list": [
      {
        "orderType": "Limit",
        "symbol": "BTC-14JUL22-17500-C",
        "orderLinkId": "188889689-yuanzhen-558998998898",
        "side": "Buy",
        "orderId": "09c5836f-81ef-4208-a5b4-43135d3e02a2",
        "leavesQty": "0.0000",
        "execTime": 1657714122417,
        "execFee": "0.11897082",
        "feeRate": "0.000300",
        "execId": "6e492560-78b4-5d2b-b331-22921d3173c9",
        "blockTradeId": "",
        "execPrice": "2360.00000000",
        "lastLiquidityInd": "TAKER",
        "orderQty": "0.0200",
        "orderPrice": "2360.00000000",
        "execValue": "47.20000000",
        "execType": "Trade",
        "execQty": "0.0200"
      }
    ]
  },
  "time": 1657714292783
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
|list> orderId |string |t(:row_comment_query_orderId_v3) |
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
curl 'https://api-testnet.bybit.com/unified/v3/private/delivery-record?category=option&symbol=BTC-23JUN22-18500-P&expDate=&cursor=&direction=&limit=10&timestamp={timestamp}&sign={sign}'
```

```python

```


> t(:codequote_responseExample)

```javascript

{
  "retCode": 0,
    "retMsg": "Success",
    "result": {
    "nextPageCursor": "784%3A0%2C784%3A0",
      "category": "option",
      "list": [
      {
        "symbol": "BTC-23JUN22-18500-P",
        "side": "Sell",
        "deliveryTime": 1655971201376,
        "strike": "18500",
        "fee": "0.00000000",
        "position": "15.0000",
        "deliveryPrice": "20454.54294250",
        "deliveryRpl": "0.00000000"
      }
    ]
  },
  "time": 1657716373514
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
curl 'https://api-testnet.bybit.com/unified/v3/private/settlement-record?category=linear&symbol=BTCPERP&timestamp={timestamp}&sign={sign}'
```

```python

```


> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "Success",
    "result": {
    "nextPageCursor": "2248%3A0%2C2248%3A0",
      "category": "linear",
      "list": [
      {
        "symbol": "BTCPERP",
        "side": "Sell",
        "markPrice": "19691.22000000",
        "size": "-0.0100",
        "sessionRpl": "-3.80370000",
        "time": "1657699200000",
        "sessionAvgPrice": "19691.22000000"
      }
    ]
  },
  "time": 1657716316682
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
curl 'https://api-testnet.bybit.com/unified/v3/private/account/wallet/balance?coin=ETH&timestamp={timestamp}&sign={sign}'
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
    "retCode": 0,
    "retMsg": "Success",
    "result": {
      "totalEquity": "112.21267421",
      "accountIMRate": "0.6895",
      "totalMarginBalance": "80.37711012",
      "totalInitialMargin": "55.42180254",
      "totalAvailableBalance": "24.95530758",
      "accountMMRate": "0.0459",
      "totalPerpUPL": "-16.69586570",
      "totalWalletBalance": "97.07311619",
      "totalMaintenanceMargin": "3.68580537",
      "coin": [
      {
        "currencyCoin": "ETH",
        "availableToBorrow": "0.00000000",
        "borrowSize": "0.00000000",
        "bonus": "0.00000000",
        "accruedInterest": "0.00000000",
        "availableBalanceWithoutConvert": "0.00000000",
        "totalOrderIM": "",
        "equity": "0.00000000",
        "totalPositionMM": "",
        "usdValue": "0.00000000",
        "availableBalance": "0.02441165",
        "unrealisedPnl": "",
        "totalPositionIM": "",
        "marginBalanceWithoutConvert": "0.00000000",
        "walletBalance": "0.00000000",
        "cumRealisedPnl": "",
        "marginBalance": "0.07862610"
      }
    ]
  },
    "time": 1657716037033
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

> t(:codequote_curlExample)

```console
curl 'https://api-testnet.bybit.com/unified/v3/private/account/upgrade-unified-account?timestamp={timestamp}&sign={sign}'
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
  "retCode": 0,
    "retMsg": "SUCCESS",
    "result": {
    "status": "SUCCESS",
      "relieveLimitBizResponse": []
  },
  "time": 1657716101461
}
```


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
|t(:resonoferror)|t(:comments_v3)|
|:----- |:-----|----- |
|t(:row_comment_query_ThereisUSDCbeingtransferred_v3_code) |t(:row_comment_query_ThereisUSDCbeingtransferred_v3) |
|t(:row_comment_query_ThereisUSDTbeingtransferred_v3_code) |t(:row_comment_query_ThereisUSDTbeingtransferred_v3) |
|t(:row_comment_query_ThereareUSDCperpetualpositionholdings_v3_code) |t(:row_comment_query_ThereareUSDCperpetualpositionholdings_v3) |
|t(:row_comment_query_ThereareUSDCoptionspositionholdings_v3_code) |t(:row_comment_query_ThereareUSDCoptionspositionholdings_v3) |
|t(:row_comment_query_ThereareUSDTperpetualpositionholdings_v3_code) |t(:row_comment_query_ThereareUSDTperpetualpositionholdings_v3) |
|t(:row_comment_query_ThereareUSDCperpetualorders_v3_code) |t(:row_comment_query_ThereareUSDCperpetualorders_v3) |
|t(:row_comment_query_ThereareUSDCoptionorders_v3_code) |t(:row_comment_query_ThereareUSDCoptionorders_v3) |
|t(:row_comment_query_ThereareUSDTperpetualorders_v3_code) |t(:row_comment_query_ThereareUSDTperpetualorders_v3) |

### t(:queryTransactionLogsV3)
t(:wallet_para_tradingHistory_v3)

> t(:codequote_curlExample)

```console
curl 'https://api-testnet.bybit.com/unified/v3/private/account/transaction-log?category=option&type=&currency=USDC&baseCoin=&startTime=0&endTime=0&cursor=&direction=&limit=10'&timestamp={timestamp}&sign={sign}'
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "Success",
    "result": {
    "nextPageCursor": "1563%3A0%2C1563%3A0",
      "currency": "USDT",
      "category": "linear",
      "list": [
      {
        "symbol": "ETHUSDT",
        "side": "Buy",
        "funding": "",
        "orderLinkId": "",
        "orderId": "7d17d359-4e38-4d3a-9a31-29791ef2dfd7",
        "fee": "0.32215500",
        "change": "-0.32215500",
        "cashFlow": "0.00000000",
        "transactionTime": 1657711949931,
        "type": "TRADE",
        "feeRate": "0.000600",
        "size": "0.5000",
        "qty": "0.5000",
        "cashBalance": "-0.32215500",
        "tradePrice": "1073.85000000",
        "tradeId": "f306ca09-de6b-56a1-8893-71f0fecd2384"
      }
    ]
  },
  "time": 1657714367010
}
```


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
> t(:codequote_curlExample)

```console
curl 'https://api-testnet.bybit.com/asset/v1/private/transfer' \
-H 'Content-Type: application/json' \
-d '{
    "api_key":"{api_key}",
    "timestamp":{timestamp},
    "sign":"{sign}",
    "fromAccountType": "UNIFIED",
    "toAccountType": "INVESTMENT",
    "amount": "19000",
    "coin": "USDT",
    "transferId": "23af1256-1210-0113-915d-0010c5ad2332"
}'
```



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


### t(:queryExchangeRecordsV3)
> t(:codequote_curlExample)

```console

curl 'https://api-testnet.bybit.com/asset/v2/private/exchange/exchange-order-all?fromCoin=BTC&toCoin=ETH&api_key={api_key}&timestamp={timestamp}&sign={sign}'
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
    "retCode": 0,
    "retMsg": "OK",
    "totalCount" 2,
    "list": [
    {
      "exchangeTxId": "7ad50cb1-9ad0-4f74-804b-d82a516e1029",
      "exchangeRate": "40.57202774",
      "fromCoin": "BTC",
      "fromAmount": "0.1",
      "toCoin": "ETH",
      "toAmount": "4.05720277",
      "createdAt": "2020-06-15 03:32:52"
    },
    {
      "exchangeTxId": "8be60cb1-9ad0-4f74-804b-d82a516e1029",
      "exchangeRate": "39.92359901",
      "fromCoin": "BTC",
      "toCoin": "ETH",
      "toAmount": "39.923599",
      "fromAmount": "1",
      "createdAt": "2020-06-12 08:27:51"
     }
    ]
}

```

t(:wallet_para_assetexchangerecords_v3)


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

### t(:interestBillStatementV3)
> t(:codequote_curlExample)

```console
curl 'https://api-testnet.bybit.com/unified/v3/private/account/borrow-history?currency=&startTime=&endTime=&direction=&limit=2&cursor=&api_key={api_key}&timestamp={timestamp}&sign={sign}'
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
  "retCode": 0,
  "retMsg": "Success",
  "result": {
  "nextPageCursor": "540%3A0%2C539%3A0",
    "currency": null,
    "list": [
    {
      "createTime": 1657713900286,
      "costExemption": "0.00000000",
      "InterestBearingBorrowSize": "3073.3902403",
      "currency": "USDT",
      "hourlyBorrowRate": "0.000003630137",
      "borrowCost": "0.01115682"
    },
    {
      "createTime": 1657710300225,
      "costExemption": "0.00000000",
      "InterestBearingBorrowSize": "3088.3130293",
      "currency": "USDT",
      "hourlyBorrowRate": "0.000003630137",
      "borrowCost": "0.01121099"
    }
   ]
  },
  "time": 1657714596804
}

```

t(:wallet_para_interestBillStatement_v3)


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpwBalance>/unified/v3/private/account/borrow-history</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpwBalance"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|currency |<b>false</b> |string |t(:row_comment_currency_v3)   |
|startTime |<b>false</b> |number |t(:row_comment_startTime_v3)   |
|endTime |<b>false</b> |number |t(:row_comment_endTime_v3)   |
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

### t(:queryLoanInterestV3)
> t(:codequote_curlExample)

```console
curl 'https://api-testnet.bybit.com/unified/v3/private/account/borrow-rate?currency=USDC%2CUSDT&api_key={api_key}&timestamp={timestamp}&sign={sign}'
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
  "retCode": 0,
  "retMsg": "Success",
  "result": {
  "list": [
    {
      "freeBorrowingAmount": "2000.0",
      "currency": "USDT",
      "maxBorrowingAmount": "10000.0",
      "hourlyBorrowRate": "0.000003630137"
    },
    {
      "freeBorrowingAmount": "2000.0",
      "currency": "USDC",
      "maxBorrowingAmount": "10000.0",
      "hourlyBorrowRate": "0.000003630137"
    }
   ]
  },
  "time": 1657714557086
}

```


t(:wallet_para_queryLoanInterest_v3)

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


