# t(:accountdata)
t(:account_para)

## t(:activeorders)
### t(:placeactive)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/private/linear/order/create \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","side":"Buy","symbol":"BTCUSD","order_type":"Market","qty":10,"time_in_force":"GoodTillCancel","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.place_active_order(
    symbol="BTCUSDT",
    side="Sell",
    order_type="Limit",
    qty=0.01,
    price=8083,
    time_in_force="GoodTillCancel",
    reduce_only=False,
    close_on_trigger=False
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
        "order_id": "a6c64aa0-c80b-4865-ae35-99be5fab3535",
        "user_id": 533285,
        "symbol": "MANAUSDT",
        "side": "Sell",
        "order_type": "Limit",
        "price": 0.8,
        "qty": 100,
        "time_in_force": "GoodTillCancel",
        "order_status": "Created",
        "last_exec_price": 0,
        "cum_exec_qty": 0,
        "cum_exec_value": 0,
        "cum_exec_fee": 0,
        "reduce_only": false,
        "close_on_trigger": false,
        "order_link_id": "Mactive001",
        "created_time": "2022-06-22T01:46:11Z",
        "updated_time": "2022-06-22T01:46:11Z",
        "take_profit": 0.65,
        "stop_loss": 0.99,
        "tp_trigger_by": "MarkPrice",
        "sl_trigger_by": "LastPrice",
        "position_idx": 2
    },
    "time_now": "1655862371.660491",
    "rate_limit_status": 99,
    "rate_limit_reset_ms": 1655862371657,
    "rate_limit": 100
}
```

t(:linear_account_para_placeActive)

<aside class="warning">
t(:account_aside_placeActive_linear_warn)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/private/linear/order/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_side) |<b>true</b> |string |t(:row_comment_side)    |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)   |
|t(:row_parameter_order_type) |<b>true</b> |string |t(:row_comment_activeOrderType)   |
|t(:row_parameter_quantity) |<b>true</b> |number |t(:linear_row_comment_qty) |
|t(:row_parameter_price) |false |number |t(:row_comment_price) |
|t(:row_parameter_time_in_force) |<b>true</b> |string |t(:row_comment_timeInForce) |
|reduce_only |<b>true</b> |bool |t(:linear_row_comment_reduceOnly) |
|close_on_trigger |<b>true</b> |bool |t(:linear_row_comment_closeOnTrigger)
|order_link_id |false |string |t(:row_comment_orderLinkId) |
|take_profit |false |number |t(:row_comment_takeProfit) |
|stop_loss |false |number |t(:row_comment_stopLoss) |
|t(:row_parameter_tp_trigger_by) |false |string |t(:account_row_comment_tp_trigger_by) |
|t(:row_parameter_sl_trigger_by) |false |string |t(:account_row_comment_sl_trigger_by) |
|position_idx |false |integer |t(:row_comment_position_idx_create_order)  |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| order_id |string |t(:row_comment_order_id) |
| user_id |number |t(:row_comment_userID) |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_order_type)  |
|t(:row_parameter_price) |number |t(:row_comment_resp_price)  |
|qty |number |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|last_exec_price |number |t(:row_comment_last_exec_price)  |
|cum_exec_qty |number |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |number |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |number |t(:linear_resp_field_cum_exec_fee)  |
|reduce_only |bool |t(:linear_resp_field_reduce_only)  |
|close_on_trigger |bool |t(:row_response_close_on_trigger)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|created_time |string |t(:row_comment_created_at)  |
|updated_time |string |t(:row_comment_updated_at)  |
|take_profit |number |t(:row_comment_take_profit)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by)  |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by)  |
|position_idx |integer |t(:row_comment_position_idx)  |

### t(:getactive)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/private/linear/order/list?api_key={api_key}&timestamp={timestamp}&sign={sign}&symbol=BTCUSDT"
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.get_active_order(
    symbol="BTCUSDT"
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
                "order_id": "a6c64aa0-c80b-4865-ae35-99be5fab3535",
                "user_id": 533285,
                "symbol": "MANAUSDT",
                "side": "Sell",
                "order_type": "Limit",
                "price": 0.8,
                "qty": 100,
                "time_in_force": "GoodTillCancel",
                "order_status": "Filled",
                "last_exec_price": 0.8315,
                "cum_exec_qty": 100,
                "cum_exec_value": 83.15,
                "cum_exec_fee": 0.04989,
                "reduce_only": false,
                "close_on_trigger": false,
                "order_link_id": "Mactive001",
                "created_time": "2022-06-22T01:46:11Z",
                "updated_time": "2022-06-22T01:46:11Z",
                "take_profit": 0.65,
                "stop_loss": 0.99,
                "tp_trigger_by": "MarkPrice",
                "sl_trigger_by": "LastPrice"
            }
        ]
    },
    "time_now": "1655862613.007213",
    "rate_limit_status": 598,
    "rate_limit_reset_ms": 1655862613003,
    "rate_limit": 600
}
```

t(:account_para_getActive)

<aside class="warning">
t(:getOrderList_warning)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oaoList>/private/linear/order/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |false |string |t(:account_row_comment_orderId) |
|order_link_id |false |string |t(:row_comment_orderLinkId) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|t(:row_parameter_order) |false |string |t(:row_comment_order)  |
|page |false |integer |t(:row_comment_page_max50) |
|limit |false |integer |t(:row_comment_limit) |
|t(:row_parameter_order_status) |false |string |t(:linear_account_row_comment_orderStatus) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|order_id |string |t(:account_row_comment_orderId) |
| user_id |number |t(:row_comment_userID) |
| t(:row_parameter_symbol) |string |t(:row_comment_symbol) |
| t(:row_parameter_side) |string |t(:row_comment_side) |
| t(:row_parameter_order_type) |string |t(:row_comment_order_type) |
| price  |number |t(:row_comment_resp_price) |
| qty  |number |t(:linear_row_comment_qty) |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|last_exec_price |number |t(:row_comment_last_exec_price)  |
|cum_exec_qty |number |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |number |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |number |t(:linear_resp_field_cum_exec_fee)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|reduce_only |bool |t(:linear_resp_field_reduce_only)  |
|close_on_trigger |bool |t(:row_response_close_on_trigger)  |
|created_time |string |t(:row_comment_created_at)  |
|updated_time |string |t(:row_comment_updated_at)  |
|take_profit |number |t(:row_comment_take_profit)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by) |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by) |

### t(:cancelactive)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/private/linear/order/cancel \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","order_id":"","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.cancel_active_order(
    symbol="BTCUSDT",
    order_id=""
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
        "order_id":"bd1844f-f3c0-4e10-8c25-10fea03763f6",
    },
    "time_now": "1575112681.814760",
    "rate_limit_status": 98,
    "rate_limit_reset_ms": 1580885703683,
    "rate_limit": 100
}
```

t(:account_para_cancelActive)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCancel>/private/linear/order/cancel</span></code>
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
|order_id |string |t(:account_row_comment_orderId) |



### t(:cancelallactive)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/private/linear/order/cancel-all \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.cancel_all_active_orders(
    symbol="BTCUSDT"
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
        "89a38056-80f1-45b2-89d3-4d8e3a203a79",  
        "89a38056-80f1-45b2-89d3-4d8e3a203a79",  
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
<code><span id=vpoCancelAll>/private/linear/order/cancel-all</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancelAll"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string | t(:row_comment_symbol) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|result |arr |t(:account_row_comment_orderId) |


### t(:replaceactive)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/private/linear/order/replace \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","order_id":"","p_r_qty":2,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.replace_active_order(
    symbol="BTCUSDT",
    order_id="",
    p_r_qty=2
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
<code><span id=oaoReplace>/private/linear/order/replace</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaoReplace"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |false |string |t(:row_comment_order_id_replace) |
|order_link_id |false |string |t(:row_comment_order_link_id_replace) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|p_r_qty |false |number |t(:row_comment_pRQty) |
|p_r_price |false |number |t(:row_comment_pRPrice) |
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
curl "https://api-testnet.bybit.com/private/linear/order/search?api_key={api_key}&symbol=BTCUSDT&timestamp={timestamp}order_id={order_id}&sign={sign}"
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.query_active_order(
    symbol="BTCUSDT",
    order_id=""
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
            "order_id": "8e7d1cd2-d7b3-4c61-87a9-a85a6e59cef8",
            "user_id": 533285,
            "symbol": "BITUSDT",
            "side": "Buy",
            "order_type": "Limit",
            "price": 0.3,
            "qty": 100,
            "time_in_force": "GoodTillCancel",
            "order_status": "New",
            "last_exec_price": 0,
            "cum_exec_qty": 0,
            "cum_exec_value": 0,
            "cum_exec_fee": 0,
            "order_link_id": "Bactive001",
            "reduce_only": false,
            "close_on_trigger": false,
            "created_time": "2022-06-22T02:11:49Z",
            "updated_time": "2022-06-22T02:11:49Z",
            "take_profit": 0.7,
            "stop_loss": 0.1,
            "tp_trigger_by": "LastPrice",
            "sl_trigger_by": "LastPrice"
        }
    ],
    "time_now": "1655863947.736147",
    "rate_limit_status": 599,
    "rate_limit_reset_ms": 1655863947734,
    "rate_limit": 600
}

//t(:resp_field_order_list)
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": [
        {
            "order_id": "6449d89e-6ef5-4f54-a065-12b2744de0ae",
            "user_id": 118921,
            "symbol": "LINKUSDT",
            "side": "Buy",
            "order_type": "Limit",
            "price": 9,
            "qty": 0.1,
            "time_in_force": "GoodTillCancel",
            "order_status": "New",
            "last_exec_price": 11874.5,
            "cum_exec_qty": 0.005,
            "cum_exec_value": 11.8745,
            "cum_exec_fee": 0.00890588,
            "order_link_id": "",
            "reduce_only": false,
            "created_time": "2020-11-27T08:25:44Z",
            "updated_time": "2020-11-27T08:25:44Z",
            "take_profit": 0,
            "stop_loss": 0,
            "tp_trigger_by": "UNKNOWN",
            "sl_trigger_by": "UNKNOWN"
        },
        ...
        {
            "order_id": "6d4dc4e0-b4e3-4fc5-a92d-3d693bdff4a5",
            "user_id": 118921,
            "symbol": "LINKUSDT",
            "side": "Buy",
            "order_type": "Limit",
            "price": 8.2,
            "qty": 9999,
            "time_in_force": "GoodTillCancel",
            "order_status": "New",
            "last_exec_price": 11888.5,
            "cum_exec_qty": 0.004,
            "cum_exec_value": 11.8745,
            "cum_exec_fee": 0.00890588,
            "order_link_id": "",
            "reduce_only": false,
            "created_time": "2020-11-23T09:19:49Z",
            "updated_time": "2020-11-23T09:20:31Z",
            "take_profit": 0,
            "stop_loss": 0,
            "tp_trigger_by": "UNKNOWN",
            "sl_trigger_by": "UNKNOWN"
        }
    ],
    "time_now": "1606465563.551193",
    "rate_limit_status": 599,
    "rate_limit_reset_ms": 1606465563547,
    "rate_limit": 600
}

```


t(:account_para_queryActive)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpOrder>/private/linear/order/search</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |false |string | t(:misc_row_comment_orderIdNotOrderLinkId)|
|order_link_id |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| order_id |string |t(:row_comment_order_id) |
| user_id |number |t(:row_comment_userID) |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_order_type)  |
|t(:row_parameter_price) |number |t(:row_comment_resp_price)  |
|qty |number |t(:linear_row_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|last_exec_price |number |t(:row_comment_last_exec_price)  |
|cum_exec_qty |number |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |number |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |number |t(:linear_resp_field_cum_exec_fee)  |
|reduce_only |bool |t(:linear_resp_field_reduce_only)  |
|close_on_trigger |bool |t(:row_response_close_on_trigger)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|created_time |string |t(:row_comment_created_at)  |
|updated_time |string |t(:row_comment_updated_at)  |
|take_profit |number |t(:row_comment_take_profit)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by) |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by) |







## t(:conditionalorders)
### t(:placecond)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/private/linear/stop-order/create \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","order_type":"Limit","side":"Buy","symbol":"BTCUSD","qty":1,"price":8100,"base_price":8300,"stop_px":8150,"time_in_force":"GoodTillCancel","trigger_by":"LastPrice",order_link_id":"cus_order_id_1","reduce_only":false,"close_on_trigger":false,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.place_conditional_order(
    symbol="BTCUSDT",
    order_type="Limit",
    side="Buy",
    qty=1,
    price=8100,
    base_price=16100,
    stop_px=8150,
    time_in_force="GoodTillCancel",
    trigger_by="LastPrice",
    order_link_id="cus_order_id_1",
    reduce_only=False,
    close_on_trigger=False
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
        "stop_order_id": "37c2f5ac-3c87-4853-a7c6-29070d4b9c4f",
        "symbol": "XRPUSDT",
        "side": "Buy",
        "order_type": "Limit",
        "price": 0.25,
        "qty": 100,
        "time_in_force": "GoodTillCancel",
        "order_status": "Untriggered",
        "trigger_price": 0.35,
        "order_link_id": "Xcond001",
        "created_time": "2022-06-22T02:20:47Z",
        "updated_time": "2022-06-22T02:20:47Z",
        "base_price": "0.3000",
        "trigger_by": "MarkPrice",
        "tp_trigger_by": "IndexPrice",
        "sl_trigger_by": "MarkPrice",
        "take_profit": 0.5,
        "stop_loss": 0.12,
        "reduce_only": false,
        "close_on_trigger": false,
        "position_idx": 1
    },
    "time_now": "1655864447.252259",
    "rate_limit_status": 99,
    "rate_limit_reset_ms": 1655864447248,
    "rate_limit": 100
}
```


t(:account_para_placeCond)

<aside class="notice">
t(:account_aside_placeCond_linear)
</aside>

<aside class="warning">
t(:account_aside_placeActive_linear_warn)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oasoCreate>/private/linear/stop-order/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oasoCreate"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_side) |<b>true</b> |string |t(:row_comment_side)    |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|t(:row_parameter_order_type) |<b>true</b> |string |t(:row_comment_stopOrderType) |
|t(:row_parameter_quantity) |<b>true</b> |number |t(:linear_row_comment_qty) |
|t(:row_parameter_price) |false | number |t(:row_comment_stopOrderPrice) |
|base_price |<b>true</b> |number | t(:linear_row_comment_basePrice) |
|stop_px |<b>true</b> | number | t(:linear_row_comment_stopPx) |
|t(:row_parameter_time_in_force) |<b>true</b> |string |t(:row_comment_timeInForce) |
|t(:row_parameter_trigger_price) | <b>true</b> | string | t(:row_comment_linear_triggerBy)|
|reduce_only |<b>true</b> |bool |t(:linear_row_comment_reduceOnly) |
|close_on_trigger |<b>true</b> |bool |t(:row_comment_closeOnTrigger)
|order_link_id |false |string |t(:row_comment_orderLinkId) |
|take_profit |false |number |t(:row_comment_takeProfit) |
|stop_loss |false |number |t(:row_comment_stopLoss) |
|t(:row_parameter_tp_trigger_by) |false |string |t(:account_row_comment_tp_trigger_by) |
|t(:row_parameter_sl_trigger_by) |false |string |t(:account_row_comment_sl_trigger_by) |
|position_idx |false |integer |t(:row_comment_position_idx_create_order)  |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|stop_order_id |string |t(:row_comment_stopOrderId) |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_orderType)  |
|t(:row_parameter_price) |number |t(:row_response_comment_price)  |
|t(:row_parameter_quantity) |number |t(:linear_row_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|trigger_price |number |t(:stop_order_trigger_price)  |
|order_link_id |string |t(:row_comment_orderLinkId) |
|created_time |string |t(:row_comment_created_at)  |
|updated_time |string |t(:row_comment_updated_at)  |
|base_price |string |t(:row_response_comment_basePrice)  |
|t(:row_parameter_trigger_price) |string |t(:row_comment_triggerBy)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by)  |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by)  |
|take_profit |number |t(:row_comment_take_profit)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|reduce_only |bool |t(:linear_resp_field_reduce_only)  |
|close_on_trigger |bool |t(:row_response_close_on_trigger)  |
|position_idx |integer |t(:row_comment_position_idx)  |

### t(:getcond)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/private/linear/stop-order/list?api_key={api_key}&timestamp={timestamp}&sign={sign}"
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.get_conditional_order(
    symbol="BTCUSDT"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": {
        "current_page": 1,
        "last_page": 1,
        "data": [
            {
                 "stop_order_id":"bd1844f-f3c0-4e10-8c25-10fea03763f6",
                 "user_id": 1,
                 "symbol": "BTCUSDT",
                 "side": "Sell",
                 "order_type": "Limit",
                 "price": 8083,
                 "qty": 10,
                 "time_in_force": "GoodTillCancel",
                 "order_status": "New",
                 "trigger_price": 8003,
                 "order_link_id": "",
                 "created_time": "2019-10-21T07:28:19.396246Z",
                 "updated_time": "2019-10-21T07:28:19.396246Z",
                 "take_profit": 0,
                 "stop_loss": 0,
                 "tp_trigger_by": "UNKNOWN",
                 "sl_trigger_by": "UNKNOWN",
                 "base_price": "16100.0000",
                 "trigger_by": "LastPrice",
            },
            {
                 "stop_order_id":"bd1844f-f3c0-4e10-8c25-10fea03763f6",
                 "user_id": 1,
                 "symbol": "BTCUSDT",
                 "side": "Sell",
                 "order_type": "Limit",
                 "price": 8083,
                 "qty": 10,
                 "time_in_force": "GoodTillCancel",
                 "order_status": "New",
                 "trigger_price": 8003,
                 "order_link_id": "",
                 "created_time": "2019-10-21T07:28:19.396246Z",
                 "updated_time": "2019-10-21T07:28:19.396246Z",
                 "take_profit": 0,
                 "stop_loss": 0,
                 "tp_trigger_by": "UNKNOWN",
                 "sl_trigger_by": "UNKNOWN",
                 "base_price": "16100.0000",
                 "trigger_by": "LastPrice",
                 "reduce_only": false,
                 "close_on_trigger": false,
            }
        ]
    },
    "ext_info": null,
    "time_now": "1577451658.755468",
    "rate_limit_status": 599,
    "rate_limit_reset_ms": 1577451658762,
    "rate_limit": 600
}
```

t(:account_para_getCond)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oasoList>/private/linear/stop-order/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oasoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|stop_order_id |false |string |t(:row_comment_stopOrderId) |
|order_link_id |false |string |t(:row_comment_orderLinkId)|
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|<a href="#order-status-order_status-stop_order_status">stop_order_status</a> |false |string |t(:row_comment_stopOrderStatus)|
|t(:row_parameter_order) |false |string |t(:row_comment_order) |
|page |false |integer |t(:row_comment_page_max50) |
|limit |false |integer |t(:row_comment_limit) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|stop_order_id |string |t(:row_comment_stopOrderId) |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_orderType)  |
|t(:row_parameter_price) |number |t(:row_response_comment_price)  |
|t(:row_parameter_quantity) |number |t(:linear_row_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|t(:row_parameter_order_status) |string |t(:row_comment_stopOrderStatus)
|trigger_price |number |t(:stop_order_trigger_price)  |
|order_link_id |string |t(:row_comment_orderLinkId) |
|created_time |string |t(:row_comment_created_at)  |
|updated_time |string |t(:row_comment_updated_at)  |
|take_profit |number |t(:row_comment_take_profit)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|t(:row_parameter_trigger_price) |string |t(:row_comment_triggerBy)  |
|base_price |string |t(:row_response_comment_basePrice)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by)  |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by)  |
|reduce_only |bool |t(:linear_resp_field_reduce_only)  |
|close_on_trigger |bool |t(:row_response_close_on_trigger)  |


### t(:cancelcond)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/private/linear/stop-order/cancel \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","stop_order_id":"","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.cancel_conditional_order(
    symbol="BTCUSDT",
    stop_order_id=""
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": {
         "stop_order_id":"bd1844f-f3c0-4e10-8c25-10fea03763f6",
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
<code><span id=oasoCancel>/private/linear/stop-order/cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oasoCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

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
curl https://api-testnet.bybit.com/private/linear/stop-order/cancel-all \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.cancel_all_conditional_orders(
    symbol="BTCUSDT"
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
        "89a38056-80f1-45b2-89d3-4d8e3a203a79",  
        "89a38056-80f1-45b2-89d3-4d8e3a203a79",
    ],
    "time_now": "1577454993.799912",
    "rate_limit_status": 90,
    "rate_limit_reset_ms": 1580885703683,
    "rate_limit": 100
}
```

t(:account_para_cancelAllCond)

<aside class="notice">
t(:account_aside_cancelAllActive)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpsoCancelAll>/private/linear/stop-order/cancel-all</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpsoCancelAll"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|required|type | comments|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)|



### t(:replacecond)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/private/linear/stop-order/replace \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","stop_order_id":"","p_r_qty":2,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.replace_conditional_order(
    symbol="BTCUSDT",
    stop_order_id="",
    p_r_qty=2
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
<code><span id=oasoReplace>/private/linear/stop-order/replace</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oasoReplace"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|stop_order_id |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|order_link_id |false |string | t(:misc_row_comment_orderLinkIdNotStopOrderId)|
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|p_r_qty |false |number |t(:row_comment_pRQty) |
|p_r_price |false |number |t(:row_comment_pRPrice) |
|p_r_trigger_price |false |number |t(:row_comemnt_pRTriggerPrice) |
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
curl "https://api-testnet.bybit.com/private/linear/stop-order/search?api_key={api_key}&symbol=BTCUSDT&timestamp={timestamp}&sign={sign}"
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.query_conditional_order(
    symbol="BTCUSDT"
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
        "stop_order_id":"bd1844f-f3c0-4e10-8c25-10fea03763f6",
        "user_id": 1,
        "symbol": "BTCUSDT",
        "side": "Sell",
        "order_type": "Limit",
        "price": 8083,
        "qty": 10,
        "time_in_force": "GoodTillCancel",
        "order_status": "New",
        "trigger_price": 8003,
        "order_link_id": "",
        "created_time": "2019-10-21T07:28:19.396246Z",
        "updated_time": "2019-10-21T07:28:19.396246Z",
        "take_profit": 0,
        "stop_loss": 0,
        "tp_trigger_by": "UNKNOWN",
        "sl_trigger_by": "UNKNOWN",
        "base_price": "16100.0000",
        "trigger_by": "LastPrice",
        "reduce_only": false,
        "close_on_trigger": false,
    },
    "time_now": "1577476584.386958",
    "rate_limit_status": 99,
    "rate_limit_reset_ms": 1580885703683,
    "rate_limit": 100
}

//t(:resp_field_order_list)
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": [
        {
            "user_id": 1301180,
            "stop_order_id": "a1dbf284-b6ee-4eaf-9fda-2d3f3fa4c501",
            "symbol": "BTCUSDT",
            "side": "Buy",
            "order_type": "Limit",
            "price": 8020,
            "qty": 0.001,
            "time_in_force": "GoodTillCancel",
            "order_status": "Untriggered",
            "trigger_price": 16000,
            "order_link_id": "",
            "created_time": "2020-11-16T09:06:17.000Z",
            "updated_time": "2020-11-16T09:06:17.000Z",
            "take_profit": 0,
            "stop_loss": 0,
            "tp_trigger_by": "UNKNOWN",
            "sl_trigger_by": "UNKNOWN",
            "trigger_by": "LastPrice"
        },
        ...
        {
            "user_id": 1301180,
            "stop_order_id": "d4g5bf862-b6ee-4eaf-9fda-2d3f3fd9g4j6",
            "symbol": "BTCUSDT",
            "side": "Sell",
            "order_type": "Limit",
            "price": 8022,
            "qty": 0.005,
            "time_in_force": "GoodTillCancel",
            "order_status": "Untriggered",
            "trigger_price": 16000,
            "order_link_id": "",
            "created_time": "2020-11-16T09:06:17.000Z",
            "updated_time": "2020-11-16T09:06:17.000Z",
            "take_profit": 0,
            "stop_loss": 0,
            "tp_trigger_by": "UNKNOWN",
            "sl_trigger_by": "UNKNOWN",
            "trigger_by": "LastPrice"
        }
    ],
    "time_now": "1606445293.547976",
    "rate_limit_status": 599,
    "rate_limit_reset_ms": 1606445293545,
    "rate_limit": 600
}
```

t(:account_para_queryConditional)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpStopOrder>/private/linear/stop-order/search</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpStopOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|stop_order_id |false |string | t(:misc_row_comment_orderIdNotOrderLinkId)|
|order_link_id |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|stop_order_id |string |t(:row_comment_stopOrderId) |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_orderType)  |
|t(:row_parameter_price) |number |t(:row_response_comment_price)  |
|t(:row_parameter_quantity) |number |t(:linear_row_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|trigger_price |number |t(:stop_order_trigger_price)  |
|base_price |string |t(:row_response_comment_basePrice)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|created_time |string |t(:row_comment_created_at)  |
|updated_time |string |t(:row_comment_updated_at)  |
|take_profit |number |t(:row_comment_take_profit)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by)  |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by)  |
|t(:row_parameter_trigger_price) |string |t(:row_comment_triggerBy)  |
|reduce_only |bool |t(:linear_resp_field_reduce_only)  |
|close_on_trigger |bool |t(:row_response_close_on_trigger)  |


## t(:position)
### t(:myposition)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/private/linear/position/list?api_key={api_key}&symbol=BTCUSDT&timestamp={timestamp}&sign={sign}"
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="XXXXXXXXXXXX",
    api_secret="XXXXXXXXXXXXXXXXXXXXXX"
)
print(session_auth.my_position(
    symbol="BTCUSDT"
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
            "symbol": "XRPUSDT",
            "side": "Buy",
            "size": 0,
            "position_value": 0,
            "entry_price": 0,
            "liq_price": 0,
            "bust_price": 0,
            "leverage": 5,
            "auto_add_margin": 0,
            "is_isolated": true,
            "position_margin": 0,
            "occ_closing_fee": 0,
            "realised_pnl": 0,
            "cum_realised_pnl": -16.35115218,
            "free_qty": 0,
            "tp_sl_mode": "Full",
            "unrealised_pnl": 0,
            "deleverage_indicator": 0,
            "risk_id": 41,
            "stop_loss": 0,
            "take_profit": 0,
            "trailing_stop": 0,
            "position_idx": 1,
            "mode": "BothSide"
        },
        {
            "user_id": 533285,
            "symbol": "XRPUSDT",
            "side": "Sell",
            "size": 50,
            "position_value": 19.58,
            "entry_price": 0.3916,
            "liq_price": 0.4529,
            "bust_price": 0.4568,
            "leverage": 6,
            "auto_add_margin": 0,
            "is_isolated": true,
            "position_margin": 3.2633354,
            "occ_closing_fee": 0.013704,
            "realised_pnl": 0,
            "cum_realised_pnl": 0.90620182,
            "free_qty": 50,
            "tp_sl_mode": "Full",
            "unrealised_pnl": 3.395,
            "deleverage_indicator": 2,
            "risk_id": 41,
            "stop_loss": 0.5,
            "take_profit": 0.28,
            "trailing_stop": 0,
            "tp_trigger_by": 1,
            "sl_trigger_by": 1,
            "position_idx": 2,
            "mode": "BothSide"
        }
    ],
    "time_now": "1655868796.293226",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1655868796290,
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
            "data": {
                "user_id": 533285,
                "symbol": "10000NFTUSDT",
                "side": "Sell",
                "size": 0,
                "position_value": 0,
                "entry_price": 0,
                "liq_price": 0,
                "bust_price": 0,
                "leverage": 10,
                "auto_add_margin": 0,
                "is_isolated": false,
                "position_margin": 0,
                "occ_closing_fee": 0,
                "realised_pnl": 0,
                "cum_realised_pnl": 0,
                "free_qty": 0,
                "tp_sl_mode": "Full",
                "unrealised_pnl": 0,
                "deleverage_indicator": 0,
                "risk_id": 1,
                "stop_loss": 0,
                "take_profit": 0,
                "trailing_stop": 0,
                "position_idx": 2,
                "mode": "BothSide"
            },
            "is_valid": true
        },
        ...
        {
            "data": {
                "user_id": 533285,
                "symbol": "10000NFTUSDT",
                "side": "Buy",
                "size": 0,
                "position_value": 0,
                "entry_price": 0,
                "liq_price": 0,
                "bust_price": 0,
                "leverage": 10,
                "auto_add_margin": 0,
                "is_isolated": false,
                "position_margin": 0,
                "occ_closing_fee": 0,
                "realised_pnl": 0,
                "cum_realised_pnl": 0,
                "free_qty": 0,
                "tp_sl_mode": "Full",
                "unrealised_pnl": 0,
                "deleverage_indicator": 0,
                "risk_id": 1,
                "stop_loss": 0,
                "take_profit": 0,
                "trailing_stop": 0,
                "position_idx": 1,
                "mode": "BothSide"
            },
            "is_valid": true
        }
    ],
    "time_now": "1604302080.356538",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1604302080353,
    "rate_limit": 120
}
```

t(:account_para_myPosition)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pList>/private/linear/position/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |false |string |t(:row_comment_symbol)    |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |number |t(:row_comment_position_size)  |
|position_value |number |t(:row_comment_position_value)  |
|entry_price |number |t(:linear_resp_field_entry_price)  |
|liq_price |number |t(:linear_resp_field_liq_price)  |
|bust_price |number |t(:linear_resp_field_bust_price)  |
|leverage |number |t(:resp_field_leverage)  |
|auto_add_margin |number |t(:row_comment_auto_add_margin)  |
|is_isolated | bool | t(:row_comment_isolated) |
|position_margin |number |t(:linear_resp_field_position_margin)  |
|occ_closing_fee |number |t(:linear_resp_field_occ_closing_fee)  |
|realised_pnl |number |t(:linear_resp_field_realised_pnl)  |
|cum_realised_pnl |number |t(:linear_resp_field_cum_realised_pnl)  |
|free_qty |number |t(:linear_resp_field_free_qty)  |
|t(:row_parameter_tp_sl_mode) |string |t(:linear_resp_tp_sl_mode)  |
|deleverage_indicator |number |t(:row_comment_deleverage_indicator)  |
|unrealised_pnl |number |t(:row_comment_unrealised_pnl)  |
|risk_id  |integer |t(:row_comment_riskId) |
|take_profit |number |t(:row_comment_take_profit)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|trailing_stop |number |t(:row_comment_trailing_stop)  |
|position_idx |integer |t(:row_comment_position_idx)  |
|mode |string |t(:linear_comment_positionmode) |

### t(:setautoaddmargin)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/private/linear/position/set-auto-add-margin \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","side":"Sell","auto_add_margin":false,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="XXXXXXXXXXX",
    api_secret="XXXXXXXXXX"
)
print(session_auth.set_auto_add_margin(
    symbol="BTCUSDT",
    side="Sell",
    auto_add_margin=False
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": null,
    "time_now": "1586780385.549188",
    "rate_limit_status": 74,
    "rate_limit_reset_ms": 1586780385547,
    "rate_limit": 75
}
```

t(:linear_account_para_setAutoAddMargin)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pSetAutoAddMargin>/private/linear/position/set-auto-add-margin</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pSetAutoAddMargin"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |<b>true</b> |string |t(:row_comment_side)    |
|auto_add_margin |<b>true</b> |bool |t(:linear_row_comment_set_auto_margin)  |
|position_idx |false |integer |t(:row_comment_position_idx)  |


### t(:marginswitch)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/private/linear/position/switch-isolated \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","is_isolated":true,"buy_leverage":1,"sell_leverage":1,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="XXXXXXX",
    api_secret="XXXXXX"
)
print(session_auth.cross_isolated_margin_switch(
    symbol="BTCUSDT",
    is_isolated=True,
    buy_leverage=1,
    sell_leverage=1
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": null,
    "time_now": "1585881597.006026",
    "rate_limit_status": 74,
    "rate_limit_reset_ms": 1585881597004,
    "rate_limit": 75
}
```

t(:linear_account_para_switchIsolated)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pSwitchIsolated>/private/linear/position/switch-isolated</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pSwitchIsolated"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|is_isolated |<b>true</b> |bool |t(:linear_row_comment_switch_isolated)  |
|buy_leverage |<b>true</b> |number |t(:linear_row_comment_leverage)  |
|sell_leverage |<b>true</b> |number |t(:linear_row_comment_leverage)  |


### t(:switchpositionmode)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/private/linear/position/switch-mode \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","mode":"MergedSingle","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="XXXXXXXXXXXX",
    api_secret="XXXXXXXXXXXXXXXXXXXXXX"
)
print(session_auth.position_mode_switch(
    symbol="BTCUSDT",
    mode="MergedSingle"
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
<code><span id=ulSwitchMode>/private/linear/position/switch-mode</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ulSwitchMode"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |false |string |t(:row_comment_symbol_with_coin)    |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:row_comment_coin_with_symbol) |
|mode |<b>true</b> |string |t(:linear_comment_positionmode) |


### t(:switchmode)

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="XXXXXXXXXXXX",
    api_secret="XXXXXXXXXXXXXXXXXXXXXX"
)
print(session_auth.full_partial_position_tp_sl_switch(
    symbol="BTCUSDT",
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
<code><span id=pltcList>/private/linear/tpsl/switch-mode</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pltcList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|t(:row_parameter_tp_sl_mode) |<b>true</b> |string |t(:linear_resp_tp_sl_mode)  |



<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_tp_sl_mode) |string |t(:linear_resp_tp_sl_mode)  |


### t(:addmargin)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","side":"Buy","margin":0.01","timestamp":{timestamp},"sign":"{sign}"}'
```
```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="XXXXXXXXXXXX",
    api_secret="XXXXXXXXXXXXXXXXXXXXXX"
)
print(session_auth.add_reduce_margin(
    symbol="BTCUSDT",
    side="Buy",
    margin=0.01
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
        "PositionListResult": {
            "user_id": 533285,
            "symbol": "XRPUSDT",
            "side": "Sell",
            "size": 50,
            "position_value": 19.58,
            "entry_price": 0.3916,
            "liq_price": 0.5267,
            "bust_price": 0.5307,
            "leverage": 10,
            "auto_add_margin": 0,
            "is_isolated": true,
            "position_margin": 6.9550018,
            "occ_closing_fee": 0.015921,
            "realised_pnl": 0,
            "cum_realised_pnl": 0.90620182,
            "free_qty": 50,
            "tp_sl_mode": "Full",
            "unrealised_pnl": 3.475,
            "deleverage_indicator": 2,
            "risk_id": 41,
            "stop_loss": 0.5,
            "take_profit": 0.28,
            "trailing_stop": 0,
            "tp_trigger_by": 1,
            "sl_trigger_by": 1,
            "position_idx": 2,
            "mode": "BothSide"
        },
        "wallet_balance": 2108.58165689,
        "available_balance": 2091.03640109
    },
    "time_now": "1655870135.180074",
    "rate_limit_status": 73,
    "rate_limit_reset_ms": 1655870135178,
    "rate_limit": 75
}
```

t(:linear_account_para_addMargin)


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pAddMargin>/private/linear/position/add-margin</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pAddMargin"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|t(:row_parameter_side) |<b>true</b> |string |t(:row_comment_side)    |
|margin |<b>true</b> |number |t(:linear_account_row_comment_margin) |
|position_idx |false |integer |t(:row_comment_position_idx)  |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |number |t(:row_comment_position_size)  |
|position_value |number |t(:linear_resp_field_position_value)  |
|entry_price |number |t(:linear_resp_field_entry_price)  |
|liq_price |number |t(:linear_resp_field_liq_price)  |
|bust_price |number |t(:linear_resp_field_bust_price)  |
|leverage |number |t(:resp_field_leverage)  |
|auto_add_margin |number |t(:row_comment_auto_add_margin)  |
|is_isolated |bool |t(:isIsolated)  |
|position_margin |number |t(:linear_resp_field_position_margin)  |
|occ_closing_fee |number |t(:linear_resp_field_occ_closing_fee)  |
|realised_pnl |number |t(:linear_resp_field_realised_pnl)  |
|cum_realised_pnl |number |t(:linear_resp_field_cum_realised_pnl)  |
|free_qty |number |t(:linear_resp_field_free_qty)  |
|t(:row_parameter_tp_sl_mode) |string |t(:linear_resp_tp_sl_mode)  |
|unrealised_pnl |number |t(:row_comment_unrealised_pnl)  |
|deleverage_indicator |number |t(:row_comment_deleverage_indicator)  |
|risk_id |number |t(:row_comment_riskId)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|take_profit |number |t(:row_comment_take_profit)  |
|trailing_stop |number |t(:row_comment_trailing_stop)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by)  |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by)  |
|position_idx |integer |t(:row_comment_position_idx)  |
|mode |string |t(:linear_comment_positionmode) |
|wallet_balance |number |t(:row_comment_wallet_balance)  |
|available_balance |number |t(:row_comment_available_balance)  |


### t(:setleverage)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/private/linear/position/set-leverage \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","buy_leverage":10,"sell_leverage":10"sign":"{sign}"}'
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="XXXXXXXXXXXX",
    api_secret="XXXXXXXXXXXXXXXXXXXXXX"
)
print(session_auth.set_leverage(
    symbol="BTCUSDT",
    buy_leverage=10,
    sell_leverage=10
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": null,
    "time_now": "1585881527.650138",
    "rate_limit_status": 74,
    "rate_limit_reset_ms": 1585881527648,
    "rate_limit": 75
}
```

t(:linear_account_para_setLeverage)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pSetLeverage>/private/linear/position/set-leverage</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pSetLeverage"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|buy_leverage |<b>true</b> |number |t(:linear_row_comment_leverage)  |
|sell_leverage |<b>true</b> |number |t(:linear_row_comment_leverage)  |


### t(:tradingstop)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/private/linear/position/trading-stop \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","side":"Buy","take_profit":10,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="XXXXXXXXXXXX",
    api_secret="XXXXXXXXXXXXXXXXXXXXXX"
)
print(session_auth.set_trading_stop(
    symbol="BTCUSDT",
    side="Buy",
    take_profit=10
))
```

> t(:codequote_responseExample)

```javascript
{
  "ret_code": 0,
  "ret_msg": "OK",
  "ext_code": "",
  "ext_info": "",
  "result": null,
  "time_now": "1586780408.193508",
  "rate_limit_status": 73,
  "rate_limit_reset_ms": 1586780408191,
  "rate_limit": 75
}
```

t(:account_para_tradingStop_linear)

<aside class="notice">
t(:account_aside_tradingStop)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pSetTpSlTs>/private/linear/position/trading-stop</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pSetTpSlTs"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|t(:row_parameter_side) |<b>true</b> |string |t(:account_row_comment_side)    |
|take_profit |false |number |t(:account_row_comment_takeProfit) |
|stop_loss |false |number |t(:account_row_comment_stopLoss) |
|trailing_stop |false |number |t(:account_row_comment_trailingStop) |
|t(:row_parameter_tp_trigger_by) | false | string | t(:account_row_comment_tp_trigger_by)
|t(:row_parameter_sl_trigger_by) | false | string | t(:account_row_comment_sl_trigger_by)
|sl_size |false |number |t(:row_comment_sl_size) |
|tp_size |false |number |t(:row_comment_tp_size) |
|position_idx |false |integer |t(:row_comment_position_idx)  |


### t(:usertraderecords)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/private/linear/trade/execution/list?api_key={api_key}&symbol=BTCUSDT&timestamp={timestamp}&sign={sign}"
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="XXXXXXXXXXXX",
    api_secret="XXXXXXXXXXXXXXXXXXXXXX"
)
print(session_auth.user_trade_records(
    symbol="BTCUSDT"
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
                    "order_id": "7369b2f4-52f1-4698-abf7-368e4ba9aefa",
                    "order_link_id": "",
                    "side": "Buy",
                    "symbol": "BTCUSDT",
                    "exec_id": "9b8216fa-98d7-55c0-b5fa-279db5727996",
                    "price": 5894
                    "order_price": 5894,
                    "order_qty": 0.001,
                    "order_type": "Limit",
                    "fee_rate": 0.00075,
                    "exec_price": 5894,
                    "exec_type": "Trade",
                    "exec_qty": 0.001,
                    "exec_fee": 0.0044205,
                    "exec_value": 5.894,
                    "leaves_qty": 0,
                    "closed_size": 0,
                    "last_liquidity_ind": "RemovedLiquidity",
                    "trade_time": 1585547384
                    "trade_time_ms": 1585547384847
                }
            ]
        },
        "time_now": "1577480599.097287",
        "rate_limit_status": 119,
        "rate_limit_reset_ms": 1580885703683,
        "rate_limit": 120
    }

}
```

t(:linear_private_trade_records)

<aside class="notice">
t(:wallet_aside_tradeRecords)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpeList>/private/linear/trade/execution/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpeList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|start_time |false |integer |t(:row_comment_startTime_ms_week) |
|end_time |false |integer |t(:row_comment_endTime_ms_week) |
|t(:row_parameter_exec_type) |false |string |t(:linear_exec_type) |
|page |false |integer |t(:row_comment_page_max50) |
|limit |false |integer |t(:linear_row_comment_limit_50_200) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|order_id |string |t(:row_comment_order_id)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)  |
|exec_id |string |t(:row_comment_exec_id)  |
|price |number |t(:row_comment_order_price)  |
|order_price |number |t(:row_comment_order_price)  |
|order_qty |number |t(:row_comment_order_qty)  |
|t(:row_parameter_order_type) |string |t(:row_comment_order_type)  |
|fee_rate |number |t(:row_comment_fee_rate)  |
|exec_price |number |t(:row_comment_exec_price)    |
|t(:row_parameter_exec_type) |string |t(:row_comment_exec_type) |
|exec_qty |number |t(:row_comment_exec_qty)  |
|exec_fee |number |t(:row_comment_exec_fee)    |
|exec_value |number |t(:row_comment_exec_value)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|closed_size |number |t(:row_comment_closed_size)  |
|t(:row_parameter_last_liquidity_ind) |string |t(:row_comment_last_liquidity_ind) |
|trade_time |number |t(:row_comment_trade_tims_sec) |
|trade_time_ms |number |t(:row_comment_trade_time_ms)  |



### t(:userhistorytraderecords)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/private/linear/trade/execution/history-list?api_key={api_key}&symbol=BTCUSDT&timestamp={timestamp}&sign={sign}"
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="XXXXXXXXXXXX",
    api_secret="XXXXXXXXXXXXXXXXXXXXXX"
)
print(session_auth.extended_user_trade_records(
    symbol="BTCUSDT"
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
        "page_token": "OVFyd2RLQ051UDhlZXNGa1RRNWEwM0FNWWZLdk9LVS95RnIzbThKa3EzUVJpc0ZiNGt2Z2NzdWxJb2h6QTZ3MHBZdmRnNlZSWFpKY0h3V1RpY0ZqcER5RlZNbGRjbGh4N2VYdXpZcUduZm9lWkFsNjFnVTJrLzdYSy9TNC9BcjhsRlRNY3NWM0x1MFdrQ05hSlFObW8yUjdpZXZyRHd3MWlvTzdmb0tWdmFwSEhqQUs0MG4wSXlsV1VZTlpWWVpla08vVGYzRWJEbVJhY2t0RmE3TDhKMCtuRnZ2ZDFuVmZQZXB6SWNGVitiZDlmSFNkazRZb1hlcXRPYzdLS040OGJVMnpER0Mzd1lFcURDTCs3SC9pRGl0UW9JZC9xSGZlNENUSW1hVHBGcUhSVlNVYzBRL3dtVVhmRXNTN2NkOHZGVGU5NThlWlRGZGp0UWxaWnhybzJmcis5UTZuYWpXTFBtVVYrQlo1VkVNPQ==",
        "data": [
            {
                "order_id": "ad263e18-ce2f-4e7c-9077-5db8d2186051",
                "order_link_id": "",
                "side": "Sell",
                "symbol": "BTCUSDT",
                "exec_id": "43514fa8-8948-5649-9854-704bae563c16",
                "price": 20284,
                "order_price": 20284,
                "order_qty": 0.32,
                "order_type": "Market",
                "fee_rate": 0.0006,
                "exec_price": 21348.5,
                "exec_type": "Trade",
                "exec_qty": 0.32,
                "exec_fee": 4.098912,
                "exec_value": 6831.52,
                "leaves_qty": 0,
                "closed_size": 0.32,
                "last_liquidity_ind": "RemovedLiquidity",
                "trade_time": 1656316742,
                "trade_time_ms": 1656316742722
            }
        ]
    },
    "time_now": "1651078431.113746",
    "rate_limit_status": 117,
    "rate_limit_reset_ms": 1651078431074,
    "rate_limit": 120
}
```

t(:linear_private_trade_records)

<aside class="notice">
t(:wallet_aside_tradeRecords)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=plteHistoryList>/private/linear/trade/execution/history-list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#plteHistoryList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|start_time |false |integer |t(:row_comment_startTime_ms_2years) |
|end_time |false |integer |t(:row_comment_endTime_ms_2years) |
|t(:row_parameter_exec_type) |false |string |t(:linear_exec_type) |
|page_token |false |string |t(:row_comment_linear_page) |
|limit |false |integer |t(:linear_row_comment_limit_100_100) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|page_token |string |t(:row_comment_linear_page) |
|data |ArrayList |
|order_id |string |t(:row_comment_order_id)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)  |
|exec_id |string |t(:row_comment_exec_id)  |
|price |number |t(:row_comment_order_price)  |
|order_price |number |t(:row_comment_order_price)  |
|order_qty |number |t(:row_comment_order_qty)  |
|t(:row_parameter_order_type) |string |t(:row_comment_order_type)  |
|fee_rate |number |t(:row_comment_fee_rate)  |
|exec_price |number |t(:row_comment_exec_price)    |
|t(:row_parameter_exec_type) |string |t(:row_comment_exec_type) |
|exec_qty |number |t(:row_comment_exec_qty)  |
|exec_fee |number |t(:row_comment_exec_fee)    |
|exec_value |number |t(:row_comment_exec_value)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|closed_size |number |t(:row_comment_closed_size)  |
|t(:row_parameter_last_liquidity_ind) |string |t(:row_comment_last_liquidity_ind) |
|trade_time |number |t(:row_comment_trade_tims_sec) |
|trade_time_ms |number |t(:row_comment_trade_time)  |



### t(:closedprofitandloss)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/private/linear/trade/closed-pnl/list?api_key={api_key}&symbol=BTCUSDT&timestamp={timestamp}&sign={sign}
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="XXXXXXXXXXXX",
    api_secret="XXXXXXXXXXXXXXXXXXXXXX"
)
print(session_auth.closed_profit_and_loss(
    symbol="BTCUSDT"
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
                 "id": 1710,
                 "user_id": 160815,
                 "symbol": "BTCUSDT",
                 "order_id": "e6a11e08-6dd0-404e-bea7-dc22b7ab0228",
                 "side": "Buy",
                 "qty": 0.5,
                 "order_price": 999999,
                 "order_type": "Market",
                 "exec_type": "Trade",
                 "closed_size": 0.5,
                 "cum_entry_value": 3000,
                 "avg_entry_price": 6000,
                 "cum_exit_value": 3000.5,
                 "avg_exit_price": 6001,
                 "closed_pnl": -5.000375,
                 "fill_count": 1,
                 "leverage": 100,
                 "created_at": 1577480599
             }
         ]
     },
     "time_now": "1577480599.097287",
     "rate_limit_status": 119,
     "rate_limit_reset_ms": 1580885703683,
     "rate_limit": 120

}
```

t(:linear_private_closed_pnl_records)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pltcList>/private/linear/trade/closed-pnl/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pltcList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|start_time |false |int |t(:row_comment_startTime) |
|end_time |false |int |t(:row_comment_endTime) |
|t(:row_parameter_exec_type) |false |string |t(:exec_type_pnl) |
|page |false |integer |t(:row_comment_page_max50)    |
|limit |false |integer |t(:linear_row_comment_limit) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |number |t(:row_comment_position_id)  |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)    |
|order_id |string |t(:row_response_closedPnlOrderId)  |
|t(:row_parameter_side) |string |t(:row_response_closedPnlSide)  |
|t(:row_parameter_quantity) |number |t(:row_comment_order_qty)  |
|order_price |number |t(:row_comment_order_price)  |
|t(:row_parameter_order_type) |string |t(:row_comment_order_type)  |
|t(:row_parameter_exec_type) |string |t(:row_comment_exec_type)  |
|closed_size |number |t(:linear_resp_field_closed_size)  |
|cum_entry_value |number |t(:linear_resp_field_cum_entry_value)    |
|avg_entry_price |number |t(:linear_resp_field_avg_entry_price)    |
|cum_exit_value |number |t(:linear_resp_field_cum_exit_value)    |
|avg_exit_price |number |t(:linear_resp_field_avg_exit_price)    |
|closed_pnl |number |t(:linear_resp_field_closed_pnl)    |
|fill_count |number |t(:linear_resp_field_fill_count)    |
|leverage |number |t(:resp_field_leverage)  |
|created_at |number |t(:row_comment_created_at)  |


## t(:risklimit)
### t(:getrisklimit)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/public/linear/risk-limit?symbol=BTCUSDT"
```


```python--pybit
from pybit import usdt_perpetual
session_unauth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com"
)
print(session_unauth.get_risk_limit(
    symbol="BTCUSDT"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "result": [
        {
            "id": 11,
            "symbol": "ETHUSDT",
            "limit": 900000,
            "maintain_margin": 0.005,
            "starting_margin": 0.01,
            "section": [
                "1",
                "3",
                "5",
                "10",
                "25",
                "50",
                "80"
            ],
            "is_lowest_risk": 1,
            "created_at": "",
            "updated_at": "",
            "max_leverage": 100
        },
        ...
        {
            "id": 36,
            "symbol": "ETHUSDT",
            "limit": 50000000,
            "maintain_margin": 0.13,
            "starting_margin": 0.2,
            "section": [
                "1",
                "2",
                "3",
                "4"
            ],
            "is_lowest_risk": 0,
            "created_at": "",
            "updated_at": "",
            "max_leverage": 5
        }
    ],
    "ext_code": "",
    "ext_info": "",
    "time_now": "1662629653.373425"
}
```

t(:account_para_getRisk)

<aside class="notice">
t(:account_aside_getRisk_linear)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oawrlList>/public/linear/risk-limit</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawrlList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |number |t(:row_comment_riskId)  |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)  |
|limit |number |t(:row_comment_risk_limit)    |
|maintain_margin |number |t(:row_comment_maintain_margin)  |
|starting_margin |number |t(:row_comment_starting_margin_linear)  |
|section |string |t(:row_comment_section)  |
|is_lowest_risk |number |t(:row_comment_is_lowest_risk)    |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|max_leverage |string |t(:row_comment_max_leverage)  |

### t(:setrisklimit)

> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/private/linear/position/set-risk \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","risk_id":2,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="XXXXXXXXXXXX",
    api_secret="XXXXXXXXXXXXXXXXXXXXXX"
)
print(session_auth.set_risk_limit(
    symbol="BTCUSDT",
    side="Buy",
    risk_id=1
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
    "time_now": "1609839125.563609",
    "rate_limit_status": 73,
    "rate_limit_reset_ms": 1609839125560,
    "rate_limit": 75
}
```
t(:account_para_setRisk)

<aside class="notice">
t(:account_aside_getRisk_linear)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=plpSetRisk>/private/linear/position/set-risk</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#plpSetRisk"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|t(:row_parameter_side) |<b>true</b> |string |t(:row_comment_side)    |
|risk_id |<b>true</b> |integer |t(:row_comment_riskId) |
|position_idx |false |integer |t(:row_comment_position_idx)  |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|risk_id |number |t(:row_comment_riskId)  |

## t(:funding)

### t(:predictedfunding)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/private/linear/funding/predicted-funding?api_key={api_key}&symbol=BTCUSDT&timestamp={timestamp}&sign={sign}"
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="XXXXXXXXXXXX",
    api_secret="XXXXXXXXXXXXXXXXXXXXXX"
)
print(session_auth.predicted_funding_rate(
    symbol="BTCUSDT"
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
        "predicted_funding_rate": -0.00375,
        "predicted_funding_fee": 0.13081256
    },
    "time_now": "1587035697.424492",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1587035697422,
    "rate_limit": 120
}
```

t(:account_para_predictedFunding)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpPredictedFunding>/private/linear/funding/predicted-funding</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpPredictedFunding"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|predicted_funding_rate |number |t(:row_comment_predicted_funding_rate)    |
|predicted_funding_fee |number |t(:row_comment_predicted_funding_fee)  |


### t(:mylastfundingfee)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/private/linear/funding/prev-funding?api_key={api_key}&symbolt=BTCUSDT&timestamp={timestamp}&sign={sign}"
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="XXXXXXXXXXXX",
    api_secret="XXXXXXXXXXXXXXXXXXXXXX"
)
print(session_auth.my_last_funding_fee(
    symbol="BTCUSDT"
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
        "symbol": "BTCUSDT",
        "side": "Buy",
        "size": 3.13,
        "funding_rate": 0.0001,
        "exec_fee": 1.868923,
        "exec_time": "2020-04-13T08:00:00.000Z"
    },
    "time_now": "1586780352.867171",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1586780352864,
    "rate_limit": 120
}
```

t(:account_para_myLastFunding)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpPreFunding>/private/linear/funding/prev-funding</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpPreFunding"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_funding_side)  |
|size |number |t(:row_comment_funding_position_size)  |
|funding_rate |number |t(:row_comment_funding_rate)  |
|exec_fee |number |t(:row_comment_exec_fee)  |
|exec_time |string |t(:row_comment_exec_timestamp)  |


## t(:key)
<a href="/docs-legacy/futuresV2/inverse#t-key">t(:shared_endpoint_desc)</a>

## t(:lcp)
<a href="/docs-legacy/futuresV2/inverse#t-lcp">t(:shared_endpoint_desc)</a>
