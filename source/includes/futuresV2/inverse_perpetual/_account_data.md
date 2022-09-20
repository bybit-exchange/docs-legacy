# t(:accountdata)
t(:account_para)

## t(:activeorders)
### t(:placeactive)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/private/order/create \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","side":"Buy","symbol":"BTCUSD","order_type":"Market","qty":10,"time_in_force":"GoodTillCancel","timestamp":{timestamp},"sign":"{sign}"}'

```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.place_active_order(
    symbol="BTCUSD",
    side="Buy",
    order_type="Market",
    qty=1,
    time_in_force="GoodTillCancel"
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
        "user_id": 533285,
        "order_id": "a1904030-f99c-4e35-9217-111591f08493",
        "symbol": "BTCUSD",
        "side": "Buy",
        "order_type": "Limit",
        "price": 20010,
        "qty": 200,
        "time_in_force": "GoodTillCancel",
        "order_status": "Created",
        "last_exec_time": 0,
        "last_exec_price": 0,
        "leaves_qty": 200,
        "cum_exec_qty": 0,
        "cum_exec_value": 0,
        "cum_exec_fee": 0,
        "reject_reason": "EC_NoError",
        "order_link_id": "",
        "created_at": "2022-06-20T06:56:22.070Z",
        "updated_at": "2022-06-20T06:56:22.070Z",
        "take_profit": "22000.00",
        "stop_loss": "19000.00",
        "tp_trigger_by": "MarkPrice",
        "sl_trigger_by": "MarkPrice"
    },
    "time_now": "1655708182.071362",
    "rate_limit_status": 99,
    "rate_limit_reset_ms": 1655708182068,
    "rate_limit": 100
}
```

t(:account_para_placeActive)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/v2/private/order/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_side) |<b>true</b> |string |t(:row_comment_side)    |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)   |
|t(:row_parameter_order_type) |<b>true</b> |string |t(:row_comment_activeOrderType)   |
|t(:row_parameter_quantity) |<b>true</b> |integer |t(:row_comment_qty) |
|t(:row_parameter_price) |false |number |t(:row_comment_resp_price) |
|t(:row_parameter_time_in_force) |<b>true</b> |string |t(:row_comment_timeInForce) |
|reduce_only |false |bool |t(:row_comment_reduceOnly) |
|close_on_trigger |false |bool |t(:row_comment_closeOnTrigger)
|order_link_id |false |string |t(:row_comment_orderLinkId) |
|take_profit |false |number |t(:row_comment_takeProfit) |
|stop_loss |false |number |t(:row_comment_stopLoss) |
|t(:row_parameter_tp_trigger_by) |false |string |t(:account_row_comment_tp_trigger_by) |
|t(:row_parameter_sl_trigger_by) |false |string |t(:account_row_comment_sl_trigger_by) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| user_id |number |t(:row_comment_userID) |
| order_id |string |t(:row_comment_order_id) |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_order_type)  |
|t(:row_parameter_price) |number |t(:row_comment_resp_price)  |
|qty |number |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|last_exec_time |string |t(:row_comment_last_exec_time)  |
|last_exec_price |string |t(:row_comment_last_exec_price)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|cum_exec_qty |number |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |number |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |number |t(:linear_resp_field_cum_exec_fee)  |
|reject_reason |string |t(:row_comment_reject_reason)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|take_profit |string |t(:row_comment_take_profit)  |
|stop_loss |string |t(:row_comment_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by)  |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by)  |

### t(:getactive)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/order/list?api_key={api_key}&timestamp={timestamp}&sign={sign}&symbol=BTCUSD"
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.get_active_order(
    symbol="BTCUSD",
    order_status="New"
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
        "data": [
            {
                "user_id": 533285,
                "position_idx": 0,
                "order_status": "New",
                "symbol": "BTCUSD",
                "side": "Buy",
                "order_type": "Limit",
                "price": "20010",
                "qty": "200",
                "time_in_force": "GoodTillCancel",
                "order_link_id": "",
                "order_id": "a1904030-f99c-4e35-9217-111591f08493",
                "created_at": "2022-06-20T06:56:22.070Z",
                "updated_at": "2022-06-20T06:56:22.075Z",
                "leaves_qty": "200",
                "leaves_value": "0.009995",
                "cum_exec_qty": "0",
                "cum_exec_value": "0",
                "cum_exec_fee": "0",
                "reject_reason": "EC_NoError",
                "take_profit": "22000.0000",
                "stop_loss": "19000.0000",
                "tp_trigger_by": "MarkPrice",
                "sl_trigger_by": "MarkPrice"
            }
        ],
        "cursor": "/oIljKFOerbXfuWAmnc33qCc1649q+xLuuagMYyoYh6pV+BShVJ8ph439Xw8ywSp"
    },
    "time_now": "1655708401.042813",
    "rate_limit_status": 599,
    "rate_limit_reset_ms": 1655708401039,
    "rate_limit": 600
}
```

t(:account_para_getActive)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpoList>/v2/private/order/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|t(:row_parameter_order_status) |false |string |t(:account_row_comment_orderStatus) |
|direction |false |string |t(:row_comment_cursor_direction) |
|limit |false |integer |t(:row_comment_limit) |
|cursor |false |string |t(:row_comment_cursor) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |integer |t(:row_comment_userID) |
|position_idx |integer |t(:row_comment_position_idx) |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol) |
|t(:row_parameter_side) |string |t(:row_comment_side) |
|t(:row_parameter_order_type) |string |t(:row_comment_order_type) |
|price  |string |t(:row_comment_resp_price) |
|qty  |string |t(:row_response_comment_qty) |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|order_id |string |t(:account_row_comment_orderId) |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|leaves_qty |string |t(:row_comment_leaves_qty) |
|leaves_value |string |t(:row_comment_leaves_value) |
|cum_exec_qty |string |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |string |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |string |t(:linear_resp_field_cum_exec_fee)  |
|reject_reason |string |t(:row_comment_reject_reason)  |
|take_profit |number |t(:row_comment_take_profit)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by) |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by) |
|cursor |string |t(:row_comment_resp_cursor) |


### t(:cancelactive)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/private/order/cancel \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","order_id":"","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.cancel_active_order(
    symbol="BTCUSD",
    order_id="3bd1844f-f3c0-4e10-8c25-10fea03763f6"
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
        "user_id": 533285,
        "order_id": "bab79185-7759-48f3-a5f4-206808b6f1ec",
        "symbol": "BTCUSD",
        "side": "Buy",
        "order_type": "Limit",
        "price": 19500,
        "qty": 100,
        "time_in_force": "GoodTillCancel",
        "order_status": "New",
        "last_exec_time": 1655711524.37661,
        "last_exec_price": 0,
        "leaves_qty": 100,
        "cum_exec_qty": 0,
        "cum_exec_value": 0,
        "cum_exec_fee": 0,
        "reject_reason": "EC_NoError",
        "order_link_id": "IPBTC00001",
        "created_at": "2022-06-20T07:52:04.376Z",
        "updated_at": "2022-06-20T07:54:35.339Z",
        "take_profit": "",
        "stop_loss": "",
        "tp_trigger_by": "",
        "sl_trigger_by": ""
    },
    "time_now": "1655711675.340162",
    "rate_limit_status": 99,
    "rate_limit_reset_ms": 1655711675338,
    "rate_limit": 100
}
```

t(:account_para_cancelActive)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCancel>/v2/private/order/cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|order_id |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|order_link_id |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |number |t(:row_comment_userID)  |
|order_id |string |t(:account_row_comment_orderId) |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_order_type)  |
|t(:row_parameter_price) |number |t(:row_comment_resp_price)  |
|qty |number |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce) |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|last_exec_time |string |t(:row_comment_last_exec_time)  |
|last_exec_price |string |t(:row_comment_last_exec_price)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|cum_exec_qty |number |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |number |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |number |t(:linear_resp_field_cum_exec_fee)  |
|reject_reason |string |t(:row_comment_reject_reason)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|take_profit |number |t(:row_comment_take_profit)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by) |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by) |

### t(:cancelallactive)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/private/order/cancelAll \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.cancel_all_active_orders(
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
            "clOrdID": "89f67ac2-8f51-4463-b5c1-75d0d8aca185",
            "order_link_id": "IPBTC00003",
            "user_id": 533285,
            "symbol": "BTCUSD",
            "side": "Buy",
            "order_type": "Limit",
            "price": "17000",
            "qty": 100,
            "time_in_force": "GoodTillCancel",
            "create_type": "CreateByUser",
            "cancel_type": "CancelByUser",
            "order_status": "",
            "leaves_qty": 100,
            "leaves_value": "0",
            "created_at": "2022-06-21T02:05:30.430491295Z",
            "updated_at": "2022-06-21T04:34:46.3745089Z",
            "cross_status": "PendingCancel",
            "cross_seq": 5208583955
        }
    ],
    "time_now": "1655786086.374891",
    "rate_limit_status": 80,
    "rate_limit_reset_ms": 1655786086373,
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
|order_link_id |string |t(:orderLinkId)  |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_order_type)  |
|t(:row_parameter_price) |string |t(:row_comment_resp_price)  |
|qty |number |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce) |
|create_type |string |t(:row_comment_create_type)  |
|cancel_type |string |t(:row_comment_cancel_type)  |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|leaves_value |string |t(:row_comment_leaves_value)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|cross_status |string |t(:row_comment_cross_status)  |
|cross_seq |number |t(:row_comment_cross_seq)  |

### t(:replaceactive)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/private/order/replace \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","order_id":"","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.replace_active_order(
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

t(:account_para_replaceActive)

<aside class="notice">
t(:account_aside_replaceActive)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoReplace>/v2/private/order/replace</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoReplace"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |false |string |t(:row_comment_order_id_replace) |
|order_link_id |false |string |t(:row_comment_order_link_id_replace) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol). |
|p_r_qty |false |integer |t(:row_comment_pRQty) |
|p_r_price |false |string |t(:row_comment_pRPrice) |
|take_profit |false |number |t(:row_comemnt_replace_take_profit)  |
|stop_loss |false |number |t(:row_comemnt_replace_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |false |string |t(:account_row_comment_tp_trigger_by) |
|t(:row_parameter_sl_trigger_by) |false |string |t(:account_row_comment_sl_trigger_by) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|order_id |string |t(:account_row_comment_orderId) |

### t(:queryactive)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/order?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}order_id={order_id}&sign={sign}"
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session.query_active_order(
    symbol="BTCUSD",
    order_id="e66b101a-ef3f-4647-83b5-28e0f38dcae0"
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
        "user_id": 533285,
        "position_idx": 0,
        "symbol": "BTCUSD",
        "side": "Buy",
        "order_type": "Limit",
        "price": "20000",
        "qty": 200,
        "time_in_force": "GoodTillCancel",
        "order_status": "New",
        "ext_fields": {
            "o_req_num": 1240101436
        },
        "last_exec_time": "1655716503.5852108",
        "leaves_qty": 200,
        "leaves_value": "0.01",
        "cum_exec_qty": 0,
        "cum_exec_value": null,
        "cum_exec_fee": null,
        "reject_reason": "EC_NoError",
        "cancel_type": "UNKNOWN",
        "order_link_id": "IPBTC000002",
        "created_at": "2022-06-20T09:15:03.585128212Z",
        "updated_at": "2022-06-20T09:15:03.590398174Z",
        "order_id": "2b1d811c-8ff0-4ef0-92ed-b4ed5fd6de34",
        "take_profit": "23000.00",
        "stop_loss": "18000.00",
        "tp_trigger_by": "MarkPrice",
        "sl_trigger_by": "MarkPrice"
    },
    "time_now": "1655718311.123686",
    "rate_limit_status": 597,
    "rate_limit_reset_ms": 1655718311122,
    "rate_limit": 600
}

```
t(:account_para_queryActive)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpOrder>/v2/private/order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|order_id |false |string | t(:row_comment_order_id)|
|order_link_id |false |string |t(:row_comment_orderLinkId) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |number |t(:row_comment_userID)  |
|position_idx |integer |t(:row_comment_position_idx)  |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_order_type)  |
|t(:row_parameter_price) |string |t(:row_comment_resp_price)  |
|qty |number |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|ext_fields |map |t(:row_comment_ext_fields)  |
|last_exec_time |string |t(:row_comment_last_exec_time)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|leaves_value |number |t(:row_comment_leaves_value)  |
|cum_exec_qty |number |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |number |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |string |t(:linear_resp_field_cum_exec_fee)  |
|reject_reason |string |t(:row_comment_reject_reason)  |
|cancel_type |string |t(:row_comment_cancel_type)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|order_id |string |t(:row_comment_order_id)  |
|take_profit |number |t(:row_comment_take_profit)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by)  |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by)  |


## t(:conditionalorders)
### t(:placecond)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/private/stop-order/create \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","order_type":"Limit","side":"Buy","symbol":"BTCUSD","qty":1,"price":8100,"base_price":8300,"stop_px":8150,"time_in_force":"GoodTillCancel","order_link_id":"cus_order_id_1","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.place_conditional_order(
    symbol="BTCUSD",
    order_type="Limit",
    side="Buy",
    qty=1,
    price=54100,
    base_price=54192,
    stop_px=54150,
    time_in_force="GoodTillCancel"
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
        "user_id": 533285,
        "symbol": "BTCUSD",
        "side": "Buy",
        "order_type": "Limit",
        "price": "19000.00",
        "qty": "100",
        "time_in_force": "GoodTillCancel",
        "remark": "172.104.71.120",
        "leaves_qty": "100",
        "leaves_value": "0.00526315",
        "stop_px": "19500.00",
        "reject_reason": "EC_NoError",
        "stop_order_id": "6e6a003f-fda3-4513-b944-3f41dabd2866",
        "order_link_id": "IPCOND0001",
        "trigger_by": "MarkPrice",
        "base_price": "20000.00",
        "created_at": "2022-06-21T02:19:46.052Z",
        "updated_at": "2022-06-21T02:19:46.052Z",
        "tp_trigger_by": "LastPrice",
        "sl_trigger_by": "LastPrice",
        "take_profit": "22000.00",
        "stop_loss": "17500.00"
    },
    "time_now": "1655777986.053050",
    "rate_limit_status": 99,
    "rate_limit_reset_ms": 1655777986051,
    "rate_limit": 100
}
```

t(:account_para_placeCond)

<aside class="notice">
t(:account_aside_placeCond)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpsoCreate>/v2/private/stop-order/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpsoCreate"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_side) |<b>true</b> |string |t(:row_comment_side)    |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|t(:row_parameter_order_type) |<b>true</b> |string |t(:row_comment_stopOrderType) |
|t(:row_parameter_quantity) |<b>true</b> |string |t(:row_comment_qty) |
|t(:row_parameter_price) |false | string |t(:row_comment_stopOrderPrice) |
|base_price |<b>true</b> |string | t(:row_comment_basePrice) |
|stop_px |<b>true</b> | string | t(:row_comment_stopPx) |
|t(:row_parameter_time_in_force) |<b>true</b> |string |t(:row_comment_timeInForce) |
|t(:row_parameter_trigger_price) | false | string | t(:row_comment_triggerBy)|
|close_on_trigger |false |bool |t(:row_comment_closeOnTrigger)
|order_link_id |false |string |t(:row_comment_orderLinkId) |
|take_profit |false |number |t(:row_comment_take_profit)  |
|stop_loss |false |number |t(:row_comment_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |false |string |t(:account_row_comment_tp_trigger_by)  |
|t(:row_parameter_sl_trigger_by) |false |string |t(:account_row_comment_sl_trigger_by)  |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |integer |t(:row_comment_userID)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_orderType)  |
|t(:row_parameter_price) |string |t(:row_response_comment_price)  |
|t(:row_parameter_quantity) |string |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|remark |string |t(:row_comment_remark)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|leaves_value |number |t(:row_comment_leaves_value)  |
|stop_px |string |t(:linear_row_comment_stopPx)  |
|reject_reason |string |t(:row_comment_reject_reason)  |
|stop_order_id |string |t(:row_comment_stopOrderId) |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|t(:row_parameter_trigger_price) |string |t(:row_comment_triggerBy)  |
|base_price |string |t(:row_response_comment_basePrice)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by)  |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by)  |
|take_profit |string |t(:row_comment_take_profit)  |
|stop_loss |string |t(:row_comment_stop_loss)  |


### t(:getcond)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/stop-order/list?api_key={api_key}&timestamp={timestamp}&sign={sign}"
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.get_conditional_order(
    symbol="BTCUSD",
    stop_order_status="Untriggered"
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
        "data": [
            {
                "user_id": 533285,
                "position_idx": 0,
                "stop_order_status": "Deactivated",
                "symbol": "BTCUSD",
                "side": "Buy",
                "order_type": "Limit",
                "stop_order_type": "Stop",
                "price": "19000",
                "qty": "100",
                "time_in_force": "GoodTillCancel",
                "base_price": "20000",
                "order_link_id": "IPCOND0001",
                "created_at": "2022-06-21T02:19:46.052Z",
                "updated_at": "2022-06-21T02:37:13.05Z",
                "stop_px": "19500",
                "stop_order_id": "6e6a003f-fda3-4513-b944-3f41dabd2866",
                "trigger_by": "MarkPrice",
                "take_profit": "22000.0000",
                "stop_loss": "17500.0000",
                "tp_trigger_by": "LastPrice",
                "sl_trigger_by": "LastPrice"
            }
        ],
        "cursor": "/oIljKFOerbXfuWAmnc33spA0KcdXr8norz1Mo+W758A5ScFhXQfNDZlY39W83UV"
    },
    "time_now": "1655780730.372912",
    "rate_limit_status": 599,
    "rate_limit_reset_ms": 1655780730369,
    "rate_limit": 600
}
```

t(:account_para_getCond)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpsoList>/v2/private/stop-order/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpsoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|<a href="#order-status-order_status-stop_order_status">stop_order_status</a> |false |string |t(:account_row_comment_req_stopOrderStatus) |
|direction |false |string |t(:row_comment_cursor_direction) |
|limit |false |integer |t(:row_comment_limit) |
|cursor |false |string |t(:row_comment_cursor) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |integer |t(:row_comment_userID) |
|position_idx |integer |t(:row_comment_position_idx) |
|<a href="#order-status-order_status-stop_order_status">stop_order_status</a>|string |t(:row_comment_stopOrderStatus) |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol) |
|t(:row_parameter_side) |string |t(:row_comment_side) |
|t(:row_parameter_order_type) |string |t(:row_comment_orderType) |
|t(:row_parameter_price) |string |t(:row_response_comment_price) |
|t(:row_parameter_quantity) |string |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|t(:row_parameter_stop_order_type) |string |t(:row_comment_stopOrderType)  |
|t(:row_parameter_trigger_price) |string |t(:row_response_comment_triggerBy)  |
|base_price |string |t(:row_response_comment_basePrice)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|stop_px |string |t(:linear_row_comment_stopPx)  |
|stop_order_id |string |t(:row_comment_stopOrderId) |
|take_profit |string |t(:row_comment_take_profit)  |
|stop_loss |string |t(:row_comment_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by) |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by) |
|cursor |string |t(:row_comment_resp_cursor) |


### t(:cancelcond)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/private/stop-order/cancel \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","stop_order_id":"xxx","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.cancel_conditional_order(
    symbol="BTCUSD",
    stop_order_id="c1025629-e85b-4c26-b4f3-76e86ad9f8cb"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": {
        "stop_order_id": "c1025629-e85b-4c26-b4f3-76e86ad9f8cb"
    },
    "ext_info": null,
    "time_now": "1577452218.567120",
    "rate_limit_status": 97,
    "rate_limit_reset_ms": 1577452218573,
    "rate_limit": "100"
}
```

t(:account_para_cancelCond)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpsoCancel>/v2/private/stop-order/cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpsoCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|required|type | comments|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)|
|stop_order_id |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|order_link_id |false |string | t(:misc_row_comment_orderLinkIdNotStopOrderId)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|stop_order_id |string |t(:row_comment_stopOrderId) |

### t(:cancelallcond)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/private/stop-order/cancelAll \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.cancel_all_conditional_orders(
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
            "clOrdID": "c692f699-5e41-49a0-a87f-666ae66e47c7",
            "order_link_id": "IPCOND0002",
            "user_id": 533285,
            "symbol": "BTCUSD",
            "side": "Buy",
            "order_type": "Market",
            "price": "0",
            "qty": 100,
            "time_in_force": "ImmediateOrCancel",
            "create_type": "CreateByStopOrder",
            "cancel_type": "CancelByUser",
            "order_status": "",
            "leaves_value": "0",
            "created_at": "2022-06-21T03:32:58.42058148Z",
            "updated_at": "2022-06-21T04:34:11.689866649Z",
            "cross_status": "Deactivated",
            "cross_seq": -1,
            "stop_order_type": "Stop",
            "trigger_by": "MarkPrice",
            "base_price": "20000",
            "trail_value": "0",
            "expected_direction": "Falling"
        },
        {
            "clOrdID": "d46d5544-a2a9-4eb7-a4a2-be4855bb3873",
            "user_id": 533285,
            "symbol": "BTCUSD",
            "side": "Sell",
            "order_type": "Market",
            "price": "0",
            "qty": 400,
            "time_in_force": "ImmediateOrCancel",
            "create_type": "CreateByTakeProfit",
            "cancel_type": "CancelByUser",
            "order_status": "",
            "leaves_value": "0",
            "created_at": "2022-06-21T04:08:10.185138102Z",
            "updated_at": "2022-06-21T04:34:11.689871755Z",
            "cross_status": "Deactivated",
            "cross_seq": -1,
            "stop_order_type": "TakeProfit",
            "trigger_by": "LastPrice",
            "base_price": "20636",
            "trail_value": "0",
            "expected_direction": "Rising"
        }
    ],
    "time_now": "1655786051.690280",
    "rate_limit_status": 90,
    "rate_limit_reset_ms": 1655786051688,
    "rate_limit": 100
}
```

t(:account_para_cancelAllCond)

<aside class="notice">
t(:account_aside_cancelAllActive)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpsoCancelAll>/v2/private/stop-order/cancelAll</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpsoCancelAll"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|required|type | comments|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|clOrdID |string |t(:row_comment_clOrdID)  |
|order_link_id |string |t(:orderLinkId)  |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_orderType)  |
|t(:row_parameter_price) |string |t(:row_response_comment_price)  |
|t(:row_parameter_quantity) |number |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|create_type |string |t(:row_comment_create_type)  |
|cancel_type |string |t(:row_comment_cancel_type)  |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|leaves_value |string |t(:row_comment_leaves_value)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|cross_status |string |t(:row_comment_cross_status)  |
|cross_seq |number |t(:row_comment_cross_seq)  |
|t(:row_parameter_stop_order_type) |string |t(:row_comment_stopOrderType)  |
|t(:row_parameter_trigger_price) |string |t(:row_comment_triggerBy)  |
|base_price |string |t(:row_response_comment_basePrice)  |
|expected_direction |string |t(:row_comment_expected_direction)  |


### t(:replacecond)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/private/stop-order/replace \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","stop_order_id":"","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.replace_conditional_order(
    symbol="BTCUSD",
    stop_order_id="378a1bbc-a93a-4e75-87f4-502ea754ba36",
    p_r_trigger_price=16003
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": {
        "stop_order_id": "378a1bbc-a93a-4e75-87f4-502ea754ba36"
    },
    "ext_info": null,
    "time_now": "1577475760.604942",
    "rate_limit_status": 96,
    "rate_limit_reset_ms": 1577475760612,
    "rate_limit": "100"
}
```


t(:account_para_replaceCond)

<aside class="notice">
t(:account_aside_replaceCond)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpsoReplace>/v2/private/stop-order/replace</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpsoReplace"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|stop_order_id |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|order_link_id |false |string |t(:misc_row_comment_orderLinkIdNotStopOrderId) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol). |
|p_r_qty |false |integer |t(:row_comment_pRQty) |
|p_r_price |false |string |t(:row_comment_pRPrice) |
|p_r_trigger_price |false |string |t(:row_comemnt_pRTriggerPrice) |
|take_profit |false |number |t(:row_comemnt_replace_take_profit)  |
|stop_loss |false |number |t(:row_comemnt_replace_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |false |string |t(:account_row_comment_tp_trigger_by)  |
|t(:row_parameter_sl_trigger_by) |false |string |t(:account_row_comment_sl_trigger_by)  |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|stop_order_id |string |t(:row_comment_stopOrderId) |      


### t(:querycond)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/stop-order?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}order_id={order_id}&sign={sign}"
```
```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.query_conditional_order(
    symbol="BTCUSD",
    stop_order_id="378a1bbc-a93a-4e75-87f4-502ea754ba36"
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
            "user_id": 533285,
            "position_idx": 0,
            "symbol": "BTCUSD",
            "side": "Buy",
            "order_type": "Market",
            "price": "0",
            "qty": 100,
            "stop_px": "19500.00",
            "base_price": "20000.00",
            "time_in_force": "ImmediateOrCancel",
            "order_status": "Untriggered",
            "ext_fields": {
                "o_req_num": 1328284913
            },
            "leaves_qty": 100,
            "leaves_value": "0",
            "cum_exec_qty": 0,
            "cum_exec_value": null,
            "cum_exec_fee": null,
            "reject_reason": "EC_NoError",
            "cancel_type": "UNKNOWN",
            "order_link_id": "IPCOND0002",
            "created_at": "2022-06-21T03:32:58.42058148Z",
            "updated_at": "2022-06-21T03:32:58.42058148Z",
            "order_id": "c692f699-5e41-49a0-a87f-666ae66e47c7",
            "trigger_by": "MarkPrice",
            "take_profit": "22000.00",
            "stop_loss": "17500.00",
            "tp_trigger_by": "LastPrice",
            "sl_trigger_by": "LastPrice"
        }
    ],
    "time_now": "1655782431.042082",
    "rate_limit_status": 597,
    "rate_limit_reset_ms": 1655782431039,
    "rate_limit": 600
}
```
t(:account_para_queryConditional)

<aside class="notice">
t(:account_para_queryConditionalNote)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpStopOrder>/v2/private/stop-order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpStopOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|stop_order_id |false |string | t(:row_comment_stopOrderId)|
|order_link_id |false |string |t(:row_comment_orderLinkId) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |number |t(:row_comment_userID)  |
|position_idx |integer |t(:row_comment_position_idx)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_orderType)  |
|t(:row_parameter_price) |number |t(:row_response_comment_price)  |
|t(:row_parameter_quantity) |number |t(:row_response_comment_qty)  |
|stop_px |string |t(:linear_row_comment_stopPx)  |
|base_price |string |t(:row_response_comment_basePrice)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|ext_fields |map |t(:row_comment_ext_fields)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|leaves_value |string |t(:row_comment_leaves_value)  |
|cum_exec_qty |number |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |number |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |number |t(:linear_resp_field_cum_exec_fee)  |
|reject_reason |string |t(:row_comment_reject_reason)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|order_id |string |t(:row_comment_order_id)  |
|t(:row_parameter_trigger_price) |string |t(:row_response_comment_triggerBy)  |
|take_profit |string |t(:row_comment_take_profit)  |
|stop_loss |string |t(:row_comment_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by)  |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by)  |


## t(:position)
### t(:myposition)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/position/list?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}&sign={sign}"
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.my_position(
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
        "id": 27913,
        "user_id": 1,
        "risk_id": 1,
        "symbol": "BTCUSD",
        "side": "Buy",
        "size": 5,
        "position_value": "0.0006947",
        "entry_price": "7197.35137469",
        "is_isolated":true,
        "auto_add_margin": 0,
        "leverage": "1",
        "effective_leverage": "1",
        "position_margin": "0.0006947",
        "liq_price": "3608",
        "bust_price": "3599",
        "occ_closing_fee": "0.00000105",
        "occ_funding_fee": "0",
        "take_profit": "0",
        "stop_loss": "0",
        "trailing_stop": "0",
        "position_status": "Normal",
        "deleverage_indicator": 4,
        "oc_calc_data": "{\"blq\":2,\"blv\":\"0.0002941\",\"slq\":0,\"bmp\":6800.408,\"smp\":0,\"fq\":-5,\"fc\":-0.00029477,\"bv2c\":1.00225,\"sv2c\":1.0007575}",
        "order_margin": "0.00029477",
        "wallet_balance": "0.03000227",
        "realised_pnl": "-0.00000126",
        "unrealised_pnl": 0,
        "cum_realised_pnl": "-0.00001306",
        "cross_seq": 444081383,
        "position_seq": 287141589,
        "created_at": "2019-10-19T17:04:55Z",
        "updated_at": "2019-12-27T20:25:45.158767Z"
        "tp_sl_mode": "Partial"
    },
    "time_now": "1577480599.097287",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1580885703683,
    "rate_limit": 120
}

//t(:resp_field_position_list)
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": [
        {
            "is_valid": true,
            "data": {
                "id": 0,
                "position_idx": 0,
                "mode": 0,
                "user_id": 118921,
                "risk_id": 1,
                "symbol": "BTCUSD",
                "side": "Buy",
                "size": 10,
                "position_value": "0.00076448",
                "entry_price": "13080.78694014",
                "is_isolated": false,
                "auto_add_margin": 1,
                "leverage": "100",
                "effective_leverage": "0.01",
                "position_margin": "0.40111704",
                "liq_price": "25",
                "bust_price": "25",
                "occ_closing_fee": "0.0003",
                "occ_funding_fee": "0",
                "take_profit": "0",
                "stop_loss": "0",
                "trailing_stop": "0",
                "position_status": "Normal",
                "deleverage_indicator": 1,
                "oc_calc_data": "{\"blq\":0,\"slq\":0,\"bmp\":0,\"smp\":0,\"fq\":-10,\"bv2c\":0.0115075,\"sv2c\":0.0114925}",
                "order_margin": "0",
                "wallet_balance": "0.40141704",
                "realised_pnl": "-0.00000008",
                "unrealised_pnl": 0.00003797,
                "cum_realised_pnl": "-0.090626",
                "cross_seq": 764786721,
                "position_seq": 581513847,
                "created_at": "2020-08-10T07:04:32Z",
                "updated_at": "2020-11-02T00:00:11.943371457Z"
                "tp_sl_mode": "Partial"
            }
        },
        ...
        {
            "is_valid": true,
            "data": {
                "id": 0,
                "position_idx": 0,
                "mode": 0,
                "user_id": 118921,
                "risk_id": 35,
                "symbol": "XRPUSD",
                "side": "None",
                "size": 0,
                "position_value": "0",
                "entry_price": "0",
                "is_isolated": false,
                "auto_add_margin": 1,
                "leverage": "16.67",
                "effective_leverage": "16.67",
                "position_margin": "0",
                "liq_price": "0",
                "bust_price": "0",
                "occ_closing_fee": "0",
                "occ_funding_fee": "0",
                "take_profit": "0",
                "stop_loss": "0",
                "trailing_stop": "0",
                "position_status": "Normal",
                "deleverage_indicator": 0,
                "oc_calc_data": "{\"blq\":0,\"slq\":0,\"bmp\":0,\"smp\":0,\"bv2c\":0.06153301,\"sv2c\":0.06144302}",
                "order_margin": "0",
                "wallet_balance": "0",
                "realised_pnl": "0",
                "unrealised_pnl": 0,
                "cum_realised_pnl": "0",
                "cross_seq": -1,
                "position_seq": 352149441,
                "created_at": "2020-08-10T07:04:32Z",
                "updated_at": "2020-08-22T08:06:32Z"
                "tp_sl_mode": "Partial"
            }
        }
    ],
    "time_now": "1604302124.031104",
    "rate_limit_status": 118,
    "rate_limit_reset_ms": 1604302124020,
    "rate_limit": 120
}
```

t(:account_para_myPosition)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pList>/v2/private/position/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |false |string |t(:row_comment_symbol)    |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |number |t(:row_comment_position_id)  |
|position_idx |integer |t(:row_comment_position_idx)  |
|mode |number |t(:row_comment_position_mode)  |
|user_id |number |t(:row_comment_userID)  |
|risk_id |number |t(:row_comment_riskId)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |number |t(:row_comment_position_size)  |
|position_value |string |t(:row_comment_position_value)  |
|entry_price |string |t(:row_comment_entry_price)  |
|is_isolated | bool | t(:row_comment_isolated) |
|auto_add_margin |number |t(:row_comment_auto_add_margin)  |
|leverage |string |t(:resp_field_leverage)  |
|effective_leverage |string |t(:row_comment_effective_leverage)  |
|position_margin |string |t(:row_comment_position_margin)  |
|liq_price |string |t(:row_comment_liq_price)  |
|bust_price |string |t(:row_comment_bust_price)  |
|occ_closing_fee |string |t(:row_comment_occ_closing_fee)  |
|occ_funding_fee |string |t(:row_comment_occ_funding_fee)  |
|take_profit |string |t(:row_comment_take_profit)  |
|stop_loss |string |t(:row_comment_stop_loss)  |
|trailing_stop |string |t(:row_comment_trailing_stop)  |
|position_status |string |t(:row_comment_position_status)  |
|deleverage_indicator |number |t(:row_comment_deleverage_indicator)  |
|oc_calc_data |string |t(:row_comment_oc_calc_data)  |
|order_margin |string |t(:row_comment_order_margin)  |
|wallet_balance |string |t(:row_comment_wallet_balance)  |
|realised_pnl |string |t(:row_comment_realised_pnl)  |
|unrealised_pnl |number |t(:row_comment_unrealised_pnl)  |
|cum_realised_pnl |string |t(:row_comment_cum_realised_pnl)  |
|cross_seq |number |t(:row_comment_cross_seq)  |
|position_seq |number |t(:row_comment_position_seq)  |
|created_at |string |t(:row_comment_created_at_position)  |
|updated_at |string |t(:row_comment_updated_at)  |
|t(:row_parameter_tp_sl_mode) |string |t(:linear_resp_tp_sl_mode)  |


### t(:changemargin)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/private/position/change-position-margin \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD",margin:"10","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.change_margin(
    symbol="BTCUSD",
    margin=0.00001
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": 0.00000997,
    "ext_info": null,
    "time_now": "1577480720.003444",
    "rate_limit_status": 74,
    "rate_limit_reset_ms": 1577480720011,
    "rate_limit": 75
}
```

t(:account_para_changeMargin)

<aside class="notice">
t(:account_aside_changeMargin)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pChangePositionMarginNew>/v2/private/position/change-position-margin</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pChangePositionMarginNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|margin |<b>true</b> |string |t(:row_comment_margin)  |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|result |number |t(:row_comment_margin_result)  |



### t(:tradingstop)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/private/position/trading-stop \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","stop_loss":7000,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.set_trading_stop(
    symbol="BTCUSD",
    stop_loss=7000
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
        "id": 0,
        "user_id": 533285,
        "symbol": "BTCUSD",
        "side": "Buy",
        "size": 400,
        "position_value": 0.019995,
        "entry_price": 20005.00125031,
        "risk_id": 1,
        "auto_add_margin": 0,
        "leverage": 2,
        "position_margin": 0.0099975,
        "liq_price": 13381.5,
        "bust_price": 13337,
        "occ_closing_fee": 0.000018,
        "occ_funding_fee": 0,
        "take_profit": 26000,
        "stop_loss": 14000,
        "trailing_stop": 0,
        "position_status": "Normal",
        "deleverage_indicator": 4,
        "oc_calc_data": "{\"blq\":100,\"blv\":\"0.00588235\",\"slq\":0,\"bmp\":17000.0085,\"smp\":0,\"fq\":-400,\"fc\":-0.00295,\"bv2c\":0.5015,\"sv2c\":0.5009}",
        "order_margin": 0.00295,
        "wallet_balance": 0.3999834,
        "realised_pnl": 0,
        "cum_realised_pnl": -0.00000526,
        "cum_commission": 0,
        "cross_seq": 5208583955,
        "position_seq": 0,
        "created_at": "2022-06-09T07:14:33.264474461Z",
        "updated_at": "2022-06-21T04:08:10.185159763Z",
        "ext_fields": {
            "trailing_active": "0",
            "sl_trigger_by": "LastPrice",
            "tp_trigger_by": "LastPrice",
            "v": 10151,
            "mm": 0
        }
    },
    "time_now": "1655784490.185727",
    "rate_limit_status": 74,
    "rate_limit_reset_ms": 1655784490182,
    "rate_limit": 75
}
```

t(:account_para_tradingStop)

<aside class="notice">
t(:account_aside_tradingStop)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oapTradingStopNew>/v2/private/position/trading-stop</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oapTradingStopNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|take_profit |false |number |t(:account_row_comment_takeProfit) |
|stop_loss |false |number |t(:account_row_comment_stopLoss) |
|trailing_stop |false |number |t(:account_row_comment_trailingStop) |
|t(:row_parameter_tp_trigger_by) | false | string | t(:account_row_comment_tp_trigger_by)
|t(:row_parameter_sl_trigger_by) | false | string | t(:account_row_comment_sl_trigger_by)
|new_trailing_active |false |number |t(:account_row_comment_trailingStop_active) |
|sl_size |false |number |t(:row_comment_sl_size) |
|tp_size |false |number |t(:row_comment_tp_size) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |number |t(:row_comment_position_id)  |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |number |t(:row_comment_position_size)  |
|position_value |number |t(:row_comment_position_value)  |
|entry_price |number |t(:row_comment_entry_price)  |
|risk_id |number |t(:row_comment_riskId)  |
|auto_add_margin |number |t(:row_comment_auto_add_margin)  |
|leverage |number |t(:resp_field_leverage)  |
|position_margin |number |t(:row_comment_position_margin)  |
|liq_price |number |t(:row_comment_liq_price)  |
|bust_price |number |t(:row_comment_bust_price)  |
|occ_closing_fee |number |t(:row_comment_occ_closing_fee)  |
|occ_funding_fee |number |t(:row_comment_occ_funding_fee)  |
|take_profit |number |t(:row_comment_take_profit)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|trailing_stop |number |t(:row_comment_trailing_stop)  |
|position_status |string |t(:row_comment_position_status)  |
|deleverage_indicator |number |t(:row_comment_deleverage_indicator)  |
|oc_calc_data |map |t(:row_comment_oc_calc_data)  |
|order_margin |number |t(:row_comment_order_margin)  |
|wallet_balance |number |t(:row_comment_wallet_balance)  |
|realised_pnl |number |t(:row_comment_realised_pnl)  |
|cum_realised_pnl |number |t(:row_comment_cum_realised_pnl)  |
|cum_commission |number |t(:row_comment_cum_commission)  |
|cross_seq |number |t(:row_comment_cross_seq)  |
|position_seq |number |t(:row_comment_position_seq)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|trailing_active |string |t(:row_comment_trailing_active)  |
|t(:row_parameter_sl_trigger_by) |string |t(:row_comment_sl_trigger_by)  |
|t(:row_parameter_tp_trigger_by) |string |t(:row_comment_tp_trigger_by)  |



### t(:setleverage)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/private/position/leverage/save \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","leverage":14,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.set_leverage(
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

t(:linear_account_para_setLeverage)

<aside class="notice">
t(:account_aside_setleverage)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=ulSaveNew>/v2/private/position/leverage/save</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ulSaveNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|leverage |<b>true</b> |number |t(:row_comment_leverage_old) |
|leverage_only |false |bool |t(:row_comment_leverage_only) |
<!--
|buy_leverage |<b>true</b> |number |t(:futures_row_comment_leverage) |
|sell_leverage |<b>true</b> |number |t(:futures_row_comment_leverage) |
-->

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|result |number |t(:row_comment_leverage_result)  |

### t(:usertraderecords)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/execution/list?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}&sign={sign}"
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.user_trade_records(
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

t(:wallet_para_tradeRecords)

<aside class="notice">
t(:wallet_aside_tradeRecords)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpeList>/v2/private/execution/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpeList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |false |string |t(:wallet_row_comment_orderId) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:misc_row_comment_symbolNotOrderId) |
|start_time |false |int |t(:row_comment_startTime_ms) |
|page |false |integer |t(:row_comment_page_max50) |
|limit |false |integer |t(:row_comment_limit_50_200) |
|<a href="#order-order">order</a> |false |string |t(:row_comment_order) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|closed_size |number |t(:row_comment_closed_size)  |
|cross_seq |number |t(:row_comment_cross_seq)  |
|exec_fee |string |t(:row_comment_exec_fee)    |
|exec_id |string |t(:row_comment_exec_id)  |
|exec_price |string |t(:row_comment_exec_price)    |
|exec_qty |number |t(:row_comment_exec_qty)  |
|exec_time |number |t(:row_comment_exec_timestamp)  |
|t(:row_parameter_exec_type) |string |t(:row_comment_exec_type) |
|exec_value |string |t(:row_comment_exec_value)  |
|fee_rate |string |t(:row_comment_fee_rate)  |
|t(:row_parameter_last_liquidity_ind) |string |t(:row_comment_last_liquidity_ind) |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|nth_fill |number |t(:row_comment_nth_fill)  |
|order_id |string |t(:row_comment_order_id)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|order_price |string |t(:row_comment_order_price)  |
|order_qty |number |t(:row_comment_order_qty)  |
|t(:row_parameter_order_type) |string |t(:row_comment_order_type) |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)  |
|trade_time_ms |number |t(:row_comment_trade_time)  |
|user_id |number |t(:row_comment_user_id)  |


### t(:closedprofitandloss)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/trade/closed-pnl/list?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}&sign={sign}"
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.closed_profit_and_loss(
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
        "current_page": 1,
        "data": [
            {
                "id": 9982,
                "user_id": 160320,
                "symbol": "BTCUSD",
                "order_id": "e976ac13-10e7-4883-a7ba-13b0e93659f1",
                "side": "Sell",
                "qty": 226,
                "order_price": 1600,
                "order_type": "Limit",
                "exec_type": "Trade",
                "closed_size": 113,
                "cum_entry_value": 0.07062500000000001,
                "avg_entry_price": 1600,
                "cum_exit_value": 0.066198,
                "avg_exit_price": 1707,
                "closed_pnl": 0.0043950000000000005,
                "fill_count": 1,
                "leverage": 100,
                "created_at": 1591155741
            }
        ]
    },
    "time_now": "1591173153.876047",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1591173153852,
    "rate_limit": 120
}
```

t(:linear_private_closed_pnl_records)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pltcList>/v2/private/trade/closed-pnl/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pltcList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|start_time |false |int |t(:row_comment_startTime) |
|end_time |false |int |t(:row_comment_endTime) |
|t(:row_parameter_exec_type) |false |string |t(:exec_type_pnl) |
|page |false |integer |t(:row_comment_page_max50) |
|limit |false |integer |t(:linear_row_comment_limit) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |number |t(:row_comment_position_id)  |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|order_id |string |t(:row_response_closedPnlOrderId) |
|t(:row_parameter_side) |string |t(:row_response_closedPnlSide)  |
|t(:row_parameter_quantity) |number |t(:row_response_comment_qty)  |
|order_price |number |t(:row_comment_order_price)  |
|t(:row_parameter_order_type) |string |t(:row_comment_orderType)  |
|t(:row_parameter_exec_type) |string |t(:row_comment_exec_type) |
|closed_size |number |t(:row_comment_closed_size)  |
|cum_entry_value |number |t(:linear_resp_field_cum_entry_value)    |
|avg_entry_price |number |t(:linear_resp_field_avg_entry_price)    |
|cum_exit_value |number |t(:linear_resp_field_cum_exit_value)    |
|avg_exit_price |number |t(:linear_resp_field_avg_exit_price)    |
|closed_pnl |number |t(:linear_resp_field_closed_pnl)    |
|fill_count |number |t(:linear_resp_field_fill_count)    |
|leverage |number |t(:resp_field_leverage)  |
|created_at |number |t(:row_comment_created_at)  |



### t(:switchmode)

> t(:codequote_curlExample)

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.full_partial_position_tp_sl_switch(
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

t(:linear_private_switchmode)

<aside class="notice">
t(:switchmode_aside)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vptSwitchMode>/v2/private/tpsl/switch-mode</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vptSwitchMode"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|t(:row_parameter_tp_sl_mode) |<b>true</b> |string |t(:linear_resp_tp_sl_mode)  |



<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_tp_sl_mode) |string |t(:linear_resp_tp_sl_mode)  |









### t(:marginswitch)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/private/position/switch-isolated \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD", "is_isolated":true,"buy_leverage":10,"sell_leverage":20, "timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.cross_isolated_margin_switch(
    symbol="BTCUSD",
    is_isolated=True,
    buy_leverage=10,
    sell_leverage=20
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": null,
    "ext_info": null,
    "time_now": "1577477968.175013",
    "rate_limit_status": 74,
    "rate_limit_reset_ms": 1577477968183,
    "rate_limit": 75
}
```

t(:futures_account_para_switchIsolated)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=ulSwitchIsolated>/v2/private/position/switch-isolated</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ulSwitchIsolated"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|is_isolated |<b>true</b> |bool |t(:futures_row_comment_switch_isolated)  |
|buy_leverage |<b>true</b> |number |t(:inverse_row_comment_leverage)  |
|sell_leverage |<b>true</b> |number |t(:inverse_row_comment_leverage)  |


### t(:queryfeerate)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/v2/private/position/fee-rate?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}&sign={sign} \
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.query_trading_fee_rate(
    symbol="BTCUSD"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result":
    {
      "user_id": "",
      "taker_fee_rate": "",
      "maker_fee_rate": "",
    },
    "ext_info": null,
    "time_now": "1577477968.175013",
    "rate_limit_status": 74,
    "rate_limit_reset_ms": 1577477968183,
    "rate_limit": 75
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=ulQueryFeeRate>/v2/private/position/fee-rate</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ulQueryFeeRate"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |number |t(:row_comment_position_user_id)  |
|taker_fee_rate |string |t(:row_comment_taker_fee_rate)    |
|maker_fee_rate |string |t(:row_comment_maker_fee_rate)    |


## t(:risklimit)
### t(:getrisklimit)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/public/risk-limit/list?symbol=BTCUSD"
```

```python--pybit
from pybit import inverse_perpetual
session_unauth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com"
)
print(session_unauth.get_risk_limit(
    symbol="BTCUSD"
))
```


> t(:codequote_responseExample)

```javascript
{
    "ret_code":0,
    "ret_msg":"OK",
    "ext_code":"",
    "ext_info":"",
    "result":[
        {
            "id":1,
            "symbol":"BTCUSD",
            "limit":1000000,
            "maintain_margin":0.005,
            "starting_margin":0.01,
            "section":[
                "1",
                "2",
                "3",
                "5",
                "10",
                "25",
                "50",
                "100"
            ],
            "is_lowest_risk":1,
            "created_at":"2021-03-17T08:20:53.000Z",
            "updated_at":"2021-03-17T08:20:53.000Z",
            "max_leverage":100
        },
        ...
        {
            "id":10,
            "symbol":"BTCUSD",
            "limit":10000000,
            "maintain_margin":0.05,
            "starting_margin":0.055,
            "section":[
                "1",
                "2",
                "3",
                "4",
                "5",
                "10",
                "15",
                "18"
            ],
            "is_lowest_risk":0,
            "created_at":"2021-03-17T08:21:12.000Z",
            "updated_at":"2021-03-17T08:21:12.000Z",
            "max_leverage":18.18
        }
    ],
    "time_now":"1616052270.701108"
}
```

t(:account_para_getRisk)

<aside class="notice">
t(:account_aside_getRisk_inverse)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oawrlList>/v2/public/risk-limit/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawrlList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>false</b> |string |t(:row_comment_symbol) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |number |t(:row_comment_riskId)  |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)  |
|limit |number |t(:row_comment_risk_limit)    |
|maintain_margin |number |t(:row_comment_maintain_margin)  |
|starting_margin |number |t(:row_comment_starting_margin_inverse)  |
|section |string |t(:row_comment_section)  |
|is_lowest_risk |number |t(:row_comment_is_lowest_risk)    |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|max_leverage |string |t(:row_comment_max_leverage)  |


### t(:setrisklimit)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/private/position/risk-limit \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","risk_id":2,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.set_risk_limit(
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

<aside class="notice">
t(:account_aside_getRisk_inverse)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oawrlList>/v2/private/position/risk-limit</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawrlList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|risk_id |<b>true</b> |integer |t(:row_comment_riskId) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|risk_id |number |t(:row_comment_riskId)  |


## t(:funding)
### t(:fundingRate)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/public/funding/prev-funding-rate?symbol=BTCUSD"
```

```python--pybit
from pybit import inverse_perpetual
session_unauth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com"
)
print(session_unauth.get_the_last_funding_rate(
    symbol="BTCUSD"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": {
        "symbol": "BTCUSD",
        "funding_rate": "0.00010000",
        "funding_rate_timestamp": 1577433600
    },
    "ext_info": null,
    "time_now": "1577445586.446797",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1577445586454,
    "rate_limit": 120
}
```

<aside class="notice">
t(:fundingRate_notice)
</aside>

t(:market_para_fundingRate)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oafPrevFundingRateNew>/v2/public/funding/prev-funding-rate</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oafPrevFundingRateNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)    |
|funding_rate |string |t(:row_comment_funding_rate)  |
|funding_rate_timestamp |number |t(:row_comment_funding_rate_timestamp)  |

### t(:mylastfundingfee)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/funding/prev-funding?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}&sign={sign}"
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.my_last_funding_fee(
    symbol="BTCUSD"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": {
        "symbol": "BTCUSD",
        "side": "Buy",
        "size": 1,
        "funding_rate": 0.0001,
        "exec_fee": 0.00000002,
        "exec_timestamp": 1575907200
    },
    "ext_info": null,
    "time_now": "1577446900.717204",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1577446900724,
    "rate_limit": 120
}
```

t(:account_para_myLastFunding)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oafPrevFundingNew>/v2/private/funding/prev-funding</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oafPrevFundingNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_funding_side)  |
|size |number |t(:row_comment_funding_position_size)  |
|funding_rate |number |t(:row_comment_funding_rate)  |
|exec_fee |number |t(:row_comment_exec_fee)  |
|exec_timestamp |number |t(:row_comment_exec_timestamp)  |


### t(:predictedfunding)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/funding/predicted-funding?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}&sign={sign}"
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.predicted_funding_rate(
    symbol="BTCUSD"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": {
        "predicted_funding_rate": 0.0001,
        "predicted_funding_fee": 0
    },
    "ext_info": null,
    "time_now": "1577447415.583259",
    "rate_limit_status": 118,
    "rate_limit_reset_ms": 1577447415590,
    "rate_limit": 120
}
```
t(:account_para_predictedFunding)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oafPredictedFundingNew>/v2/private/funding/predicted-funding</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oafPredictedFundingNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|predicted_funding_rate |number |t(:row_comment_predicted_funding_rate)    |
|predicted_funding_fee |number |t(:row_comment_predicted_funding_fee)  |

## t(:key)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/account/api-key?api_key={api_key}&timestamp={timestamp}&sign={sign}"
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.api_key_info())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": [
        {
            "api_key": "7GkMBBLTbGRfa0Nuh1",
            "type": "personal",
            "user_id": 1,
            "inviter_id": 3,
            "ips": [
                "*"
            ],
            "note": "scalping_bot",
            "permissions": [
                "Order",
                "Position"
            ],
            "created_at": "2019-10-28T13:22:39.000Z",
            "expired_at": "2020-01-28T13:22:39.000Z",
            "read_only": false,
            "vip_level":"",
            "mkt_maker_level":""
        }
    ],
    "ext_info": null,
    "time_now": "1577445138.790150",
    "rate_limit_status": 99,
    "rate_limit_reset_ms": 1577445138812,
    "rate_limit": 100
}
```

t(:account_para_key)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oaApiKeyNew>/v2/private/account/api-key</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaApiKeyNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|api_key |string |t(:row_comment_api_key)    |
|type |string |t(:row_comment_type)  |
|user_id |number |t(:row_comment_position_user_id)  |
|inviter_id |number |t(:row_comment_position_inviter_id)  |
|ips |string |t(:row_comment_position_ips)  |
|note |string |t(:row_comment_note)  |
|permissions |string |t(:row_comment_permissions)  |
|created_at |string |t(:row_comment_created_at)  |
|expired_at |string |t(:row_comment_expired_at)  |
|read_only |bool |t(:row_comment_read_only)  |
|vip_level |string |t(:row_comment_vip_level)  |
|mkt_maker_level |string |t(:row_comment_mkt_maker_level)  |

## t(:lcp)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/account/lcp?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}&sign={sign}"
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.lcp_info(
    symbol="BTCUSD"
))
```


> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": [
        "lcp_list": [
        {
            "date": "2020-04-27",
            "self_ratio": 0,
            "platform_ratio": 0,
            "score": 0.1459
        },
        {
            "date": "2020-04-26",
            "self_ratio": 0,
            "platform_ratio": 0,
            "score": 0.1459
        }
        ]
    ],
    "ext_info": null,
    "time_now": "1577445138.790150",
    "rate_limit_status": 99,
    "rate_limit_reset_ms": 1577445138812,
    "rate_limit": 100
}
```

t(:account_para_lcp)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oaApiLcp>/v2/private/account/lcp</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaApiLcp"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|date |string |t(:row_comment_lcp_date)    |
|self_ratio |number |t(:row_comment_lcp_self_ratio)  |
|platform_ratio |number |t(:row_comment_lcp_platform_ratio)  |
|score |number |t(:row_comment_lcp_score)  |
