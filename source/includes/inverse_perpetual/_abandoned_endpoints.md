# t(:abandonedendpoints)

### t(:a_getleverage)
> t(:codequote_curlExample)

```console
curl "https://api.bybit.com/user/leverage?api_key={api_key}&timestamp={timestamp}&sign={sign}"
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Positions.userLeverage())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": {
        "BTCUSD": {
            "leverage": 5
        },
        "EOSUSD": {
            "leverage": 1
        },
        "ETHUSD": {
            "leverage": 1
        },
        "XRPUSD": {
            "leverage": 10
        }
    },
    "ext_info": null,
    "time_now": "1577477752.346548",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1577477752355,
    "rate_limit": 120
}
```

t(:account_para_userLeverage)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=uLeverage>/user/leverage</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uLeverage"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|BTCUSD > leverage |number |t(:row_comment_BTCUSD_leverage)  |
|EOSUSD > leverage |number |t(:row_comment_EOSUSD_leverage)  |
|ETHUSD > leverage |number |t(:row_comment_ETHUSD_leverage)  |
|XRPUSD > leverage |number |t(:row_comment_XRPUSD_leverage)  |


### t(:a_getactive)
> t(:codequote_curlExample)

```console
curl "https://api.bybit.com/open-api/order/list?api_key={api_key}&timestamp={timestamp}&sign={sign}&symbol=BTCUSD"
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Order.Order_getOrders().result())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": {
        "current_page": 1,
        "last_page": 6,
        "data": [
            {
                "user_id": 1,
                "symbol": "BTCUSD",
                "side": "Sell",
                "order_type": "Market",
                "price": 7074,
                "qty": 2,
                "time_in_force": "ImmediateOrCancel",
                "order_status": "Filled",
                "ext_fields": {
                    "close_on_trigger": true,
                    "orig_order_type": "BLimit",
                    "prior_x_req_price": 5898.5,
                    "op_from": "pc",
                    "remark": "127.0.0.1",
                    "o_req_num": -34799032763,
                    "xreq_type": "x_create"
                },
                "last_exec_time": "1577448481.696421",
                "last_exec_price": 7070.5,
                "leaves_qty": 0,
                "leaves_value": 0,
                "cum_exec_qty": 2,
                "cum_exec_value": 0.00028283,
                "cum_exec_fee": 0.00002,
                "reject_reason": "NoError",
                "order_link_id": "",
                "created_at": "2019-12-27T12:08:01.000Z",
                "updated_at": "2019-12-27T12:08:01.000Z",
                "order_id": "f185806b-b801-40ff-adec-52289370ed62"
            }
        ]
    },
    "ext_info": null,
    "time_now": "1577448922.437871",
    "rate_limit_status": 98,
    "rate_limit_reset_ms": 1580885703683,
    "rate_limit": 100
}
```

t(:account_para_getActive)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oaoList>/open-api/order/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |false |string |t(:account_row_comment_orderId) |
|order_link_id |false |string |t(:row_comment_orderLinkId) |
|t(:row_parameter_symbol) |false |string |t(:row_comment_symbol). t(:default) `BTCUSD` |
|order |false |string |t(:row_comment_order)  |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:row_comment_limit) |
|t(:row_parameter_order_status) |false |string |t(:account_row_comment_orderStatus) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| user_id |number |t(:row_comment_userID) |
| symbol |string |t(:row_comment_symbol) |
| side |string |t(:row_comment_side) |
| order_type |string |t(:row_comment_order_type) |
| price  |number |t(:row_comment_resp_price) |
| qty  |number |t(:row_response_comment_qty) |
|time_in_force |string |t(:row_comment_timeInForce)  |
|order_status |string |t(:row_comment_orderStatus)  |
| ext_fields>close_on_trigger |bool |t(:row_comment_closeOnTrigger) |
| ext_fields>orig_order_type |string |t(:row_comment_orig_order_type) |
| ext_fields>prior_x_req_price  |number |t(:row_comment_prior_x_req_price) |
| ext_fields>op_from |string |t(:row_comment_op_from) |
| ext_fields>remark |string |t(:row_comment_remark) |
| ext_fields>o_req_num |number |t(:row_comment_o_req_num) |
| ext_fields>xreq_type |string |t(:row_comment_xreq_type) |
| last_exec_time |string |t(:row_comment_last_exec_time) |
| last_exec_price |number |t(:row_comment_last_exec_price) |
| leaves_qty |number |t(:row_comment_leaves_qty) |
| leaves_value |number |t(:row_comment_leaves_value) |
|cum_exec_qty |number |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |number |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |number |t(:linear_resp_field_cum_exec_fee)  |
|reject_reason |string |t(:row_comment_reject_reason)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|created_at |string |t(:row_comment_created_at)  |
|order_id |string |t(:account_row_comment_orderId) |


### t(:a_getcond)
> t(:codequote_curlExample)

```console
curl "https://api.bybit.com/open-api/stop-order/list?api_key={api_key}&timestamp={timestamp}&sign={sign}"
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Conditional.Conditional_getOrders().result())
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
                "user_id": 1,
                "stop_order_status": "Untriggered",
                "symbol": "BTCUSD",
                "side": "Buy",
                "order_type": "Limit",
                "price": 8000,
                "qty": 1,
                "time_in_force": "GoodTillCancel",
                "stop_order_type": "Stop",
                "trigger_by": "LastPrice",
                "base_price": 7000,
                "order_link_id": "",
                "created_at": "2019-12-27T12:48:24.000Z",
                "updated_at": "2019-12-27T12:48:24.000Z",
                "stop_px": 7500,
                "stop_order_id": "a85cd1c0-a9a4-49d3-a1bd-bab5ebe946d5"
            },
            {
                "user_id": 1,
                "stop_order_status": "Untriggered",
                "symbol": "BTCUSD",
                "side": "Sell",
                "order_type": "Limit",
                "price": 999999,
                "qty": 1,
                "time_in_force": "PostOnly",
                "stop_order_type": "Stop",
                "trigger_by": "LastPrice",
                "base_price": 6910.5,
                "order_link_id": "",
                "created_at": "2019-12-17T12:13:20.000Z",
                "updated_at": "2019-12-17T12:13:20.000Z",
                "stop_px": 10000000000000,
                "stop_order_id": "dea89649-9492-459d-a8c4-c298b87b3d26"
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
<code><span id=oasoList>/open-api/stop-order/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oasoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|stop_order_id |false |string |t(:row_comment_stopOrderId) |
|order_link_id |false |string |t(:row_comment_orderLinkId)|
|t(:row_parameter_symbol) |false |string |t(:row_comment_symbol). Default `BTCUSD`    |
|t(:row_parameter_stop_order) |false |string |t(:row_comment_stopOrderStatus)|
|t(:row_parameter_order) |false |string |t(:row_comment_order) |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:row_comment_limit) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_stop_order)|string |t(:row_comment_stopOrderStatus)    |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_orderType)  |
|t(:row_parameter_price) |number |t(:row_response_comment_price)  |
|t(:row_parameter_quantity) |number |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|stop_order_type |string |t(:row_comment_stopOrderType)  |
|t(:row_parameter_trigger_price) |string |t(:row_comment_triggerBy)  |
|base_price |number |t(:row_response_comment_basePrice)  |
|order_link_id |string |t(:row_response_comment_orderLinkId)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|stop_px |number |t(:linear_row_comment_stopPx)  |
|stop_order_id |string |t(:row_comment_stopOrderId) |


### t(:a_placecond)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/open-api/stop-order/create \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","order_type":"Limit","side":"Buy","symbol":"BTCUSD","qty":1,"price":8100,"base_price":8300,"stop_px":8150,"time_in_force":"GoodTillCancel","order_link_id":"cus_order_id_1","timestamp":{timestamp},"sign":"{sign}"}'
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Conditional.Conditional_new(order_type="Limit",side="Buy",symbol="BTCUSD",qty=1,price=8100,base_price=8300,stop_px=8150,time_in_force="GoodTillCancel", order_link_id="cus_order_id_1").result())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": {
        "user_id": 1,
        "symbol": "BTCUSD",
        "side": "Buy",
        "order_type": "Limit",
        "price": 8000,
        "qty": 1,
        "time_in_force": "GoodTillCancel",
        "stop_order_type": "Stop",
        "trigger_by": "LastPrice",
        "base_price": 7000,
        "order_status": "Untriggered",
        "ext_fields": {
            "stop_order_type": "Stop",
            "trigger_by": "LastPrice",
            "base_price": 7000,
            "expected_direction": "Rising",
            "trigger_price": 7500,
            "op_from": "api",
            "remark": "127.0.01",
            "o_req_num": 0
        },
        "leaves_qty": 1,
        "leaves_value": 0.00013333,
        "reject_reason": null,
        "cross_seq": -1,
        "created_at": "2019-12-27T12:48:24.000Z",
        "updated_at": "2019-12-27T12:48:24.000Z",
        "stop_px": 7500,
        "stop_order_id": "a85cd1c0-a9a4-49d3-a1bd-bab5ebe946d5"
    },
    "ext_info": null,
    "time_now": "1577450904.327654",
    "rate_limit_status": 99,
    "rate_limit_reset_ms": 1577450904335,
    "rate_limit": "100"
}
```

t(:account_para_placeCond)

<aside class="notice">
t(:account_aside_placeCond)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oasoCreate>/open-api/stop-order/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oasoCreate"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_side) |<b>true</b> |string |t(:row_comment_side)    |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|t(:row_parameter_order_type) |<b>true</b> |string |t(:row_comment_stopOrderType) |
|t(:row_parameter_quantity) |<b>true</b> |integer |t(:row_comment_qty) |
|t(:row_parameter_price) |false | number |t(:row_comment_stopOrderPrice) |
|base_price |<b>true</b> |number | t(:row_comment_basePrice) |
|stop_px |<b>true</b> | number | t(:row_comment_stopPx) |
|t(:row_parameter_time_in_force) |<b>true</b> |string |t(:row_comment_timeInForce) |
|t(:row_parameter_trigger_price) | false | string | t(:row_comment_triggerBy)|
|close_on_trigger |false |bool |t(:row_comment_closeOnTrigger)
|order_link_id |false |string |t(:row_comment_orderLinkId) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_orderType)  |
|t(:row_parameter_price) |number |t(:row_response_comment_price)  |
|t(:row_parameter_quantity) |number |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|ext_fields>stop_order_type |string |t(:row_comment_stopOrderType)  |
|ext_fields>t(:row_parameter_trigger_price) |string |t(:row_comment_triggerBy)  |
|ext_fields>base_price |number |t(:row_response_comment_basePrice)  |
|ext_fields>t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|ext_fields>stop_order_type |string |t(:row_comment_stopOrderType)  |
|ext_fields>expected_direction |string |t(:row_comment_expected_direction)  |
|ext_fields>trigger_price |number |t(:stop_order_trigger_price)  |
|ext_fields>op_from |string |t(:row_comment_op_from)  |
|remark |string |t(:row_comment_remark)  |
|o_req_num |number |t(:row_comment_o_req_num)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|leaves_value |number |t(:row_comment_leaves_value)  |
|reject_reason |string |t(:row_comment_reject_reason)  |
|cross_seq |number |t(:row_comment_cross_seq)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|stop_px |number |t(:linear_row_comment_stopPx)  |
|stop_order_id |string |t(:row_comment_stopOrderId) |


### t(:a_cancelcond)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/open-api/stop-order/cancel \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","order_id":"","timestamp":{timestamp},"sign":"{sign}"}'
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Conditional.Conditional_cancel(symbol="BTCUSD", order_id="").result())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": {
        "user_id": 1,
        "stop_order_status": "Untriggered",
        "symbol": "BTCUSD",
        "side": "Buy",
        "order_type": "Limit",
        "price": 8000,
        "qty": 1,
        "time_in_force": "GoodTillCancel",
        "stop_order_type": "Stop",
        "trigger_by": "LastPrice",
        "base_price": 7000,
        "order_link_id": "",
        "created_at": "2019-12-27T13:10:18.000Z",
        "updated_at": "2019-12-27T13:10:18.000Z",
        "stop_px": 7500,
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
<code><span id=oasoCancel>/open-api/stop-order/cancel</span></code>
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
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_stop_order)|string |t(:row_comment_stopOrderStatus)    |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_orderType)  |
|t(:row_parameter_price) |number |t(:row_response_comment_price)  |
|t(:row_parameter_quantity) |number |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|stop_order_type |string |t(:row_comment_stopOrderType)  |
|t(:row_parameter_trigger_price) |string |t(:row_comment_triggerBy)  |
|base_price |number |t(:row_response_comment_basePrice)  |
|order_link_id |string |t(:row_response_comment_orderLinkId)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|stop_px |number |t(:linear_row_comment_stopPx)  |
|stop_order_id |string |t(:row_comment_stopOrderId) |



### t(:a_replacecond)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/open-api/stop-order/replace \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","stop_order_id":"","timestamp":{timestamp},"sign":"{sign}"}'
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Conditional.Conditional_replace(symbol="BTCUSD", stop_order_id="").result())
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
<code><span id=oasoReplace>/open-api/stop-order/replace</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oasoReplace"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|stop_order_id |false |string |t(:row_comment_stopOrderId) |
|order_id |false |string |t(:comment_abandoned) t(:row_comment_stopOrderId) |
|order_link_id |false |string |t(:row_comment_orderLinkId) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol). |
|p_r_qty |false |int |t(:row_comment_pRQty) |
|p_r_price |false |number |t(:row_comment_pRPrice) |
|p_r_trigger_price |false |number |t(:row_comemnt_pRTriggerPrice) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|stop_order_id |string |t(:row_comment_stopOrderId) |      

### t(:a_replaceactive)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/open-api/order/replace \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","order_id":"","timestamp":{timestamp},"sign":"{sign}"}'
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Order.Order_Replace(symbol="BTCUSD", order_id="").result())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,    //Error code,
    "ret_msg": "ok",  //Error message,
    "ext_code": "",
    "result": {
        "order_id": "efa44157-c355-4a98-b6d6-1d846a936b93"
    },
    "time_now": "1539778407.210858",    // UTC timestamp
    "rate_limit_status": 99, // The remaining number of accesses in one minute
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
<code><span id=oaoReplace>/open-api/order/replace</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaoReplace"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |false |string |t(:row_comment_orderId) |
|order_link_id |false |string |t(:row_comment_orderLinkId) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol). |
|p_r_qty |false |int |t(:row_comment_pRQty) |
|p_r_price |false |number |t(:row_comment_pRPrice) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|order_id |string |t(:account_row_comment_orderId) |



### t(:a_getrisklimit)
> t(:codequote_curlExample)

```console
curl "https://api.bybit.com/open-api/wallet/risk-limit/list?api_key={api_key}&timestamp={timestamp}&sign={sign}"
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Wallet.Wallet_getRiskLimit().result())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": [
        {
            "id": 1,
            "coin": "BTC",
            "symbol": "BTCUSD",
            "limit": 150,
            "maintain_margin": "0.50",
            "starting_margin": "1.00",
            "section": [
                "1",
                "2",
                "3",
                "5",
                "10",
                "25",
                "50",
                "100"
            ],
            "is_lowest_risk": 1,
            "created_at": "2018-09-21T11:34:11.000Z",
            "updated_at": "2018-09-21T11:34:11.000Z",
            "max_leverage": "100.00"
        },
        {
            "id": 10,
            "coin": "BTC",
            "symbol": "BTCUSD",
            "limit": 1500,
            "maintain_margin": "5.00",
            "starting_margin": "5.50",
            "section": [
                "1",
                "2",
                "3",
                "4",
                "5",
                "10",
                "15",
                "18"
            ],
            "is_lowest_risk": 0,
            "created_at": "2018-09-21T11:34:11.000Z",
            "updated_at": "2018-09-21T11:34:11.000Z",
            "max_leverage": "18.18"
        }
    ],
    "ext_info": null,
    "time_now": "1616568086.769014",
    "rate_limit_status": 599,
    "rate_limit_reset_ms": 1616568086777,
    "rate_limit": 600
}
```

t(:account_para_getRisk)

<aside class="notice">
t(:account_aside_getRisk)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oawrlList>/open-api/wallet/risk-limit/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawrlList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>false</b> |string |t(:row_comment_symbol)   |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |number |t(:row_comment_riskId)  |
|coin |string |t(:row_comment_coin_type)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)   |
|limit |number |t(:row_comment_risk_limit)    |
|maintain_margin |string |t(:row_comment_maintain_margin)  |
|starting_margin |string |t(:row_comment_starting_margin)  |
|section |string |t(:row_comment_section)  |
|is_lowest_risk |number |t(:row_comment_is_lowest_risk)    |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|max_leverage |string |t(:row_comment_max_leverage)  |


### t(:a_setrisklimit)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/open-api/wallet/risk-limit \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","risk_id":2,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Wallet.Wallet_setRiskLimit(symbol="BTCUSD", risk_id=2).result())
```

> t(:codequote_responseExample)

```javascript
{
  "ret_code": 0,
  "ret_msg": "ok",
  "ext_code": "",
  "result": {
    "position": {
      "id": 1,
      "user_id": 1,
      "symbol": "BTCUSD",
      "side": "None",
      "size": 0,
      "position_value": 0,
      "entry_price": 0,
      "risk_id": 2,
      "auto_add_margin": 0,
      "leverage": 1,
      "position_margin": 0,
      "liq_price": 0,
      "bust_price": 0,
      "occ_closing_fee": 0,
      "occ_funding_fee": 0,
      "take_profit": 0,
      "stop_loss": 0,
      "trailing_stop": 0,
      "position_status": "Normal",
      "deleverage_indicator": 0,
      "oc_calc_data": "{\"blq\":1,\"blv\":\"0.000125\",\"slq\":0,\"bmp\":8000,\"smp\":0,\"fc\":-0.00012529,\"bv2c\":1.00225,\"sv2c\":1.0007575}",
      "order_margin": 0.00012529,
      "wallet_balance": 1000,
      "realised_pnl": 0,
      "cum_realised_pnl": 0,
      "cum_commission": 0,
      "cross_seq": 4376,
      "position_seq": 13689,
      "created_at": "2019-08-13T06:51:29.000Z",
      "updated_at": "2019-12-29T03:11:08.000Z",
      "ext_fields": {
        "trailing_active": "9000",
        "v": 4
      }
    },
    "risk": {
      "id": 2,
      "coin": "BTC",
      "limit": 300,
      "maintain_margin": "1.00",
      "starting_margin": "1.50",
      "section": "[\"1\",\"2\",\"3\",\"5\",\"10\",\"25\",\"50\",\"66\"]",
      "is_lowest_risk": 0,
      "created_at": "2019-06-26T05:46:45.000Z",
      "updated_at": "2019-06-26T05:46:55.000Z"
    }
  },
  "ext_info": null,
  "time_now": "1577589068.435439",
  "rate_limit_status": 71,
  "rate_limit_reset_ms": 1577589068546,
  "rate_limit": 75
}
```

t(:account_para_setRisk)

<aside class="notice">
t(:account_aside_getRisk)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oawRiskLimit>/open-api/wallet/risk-limit</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawRiskLimit"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|risk_id |<b>true</b> |integer |t(:row_comment_riskId) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|position > id |number |t(:row_comment_position_id)  |
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
|oc_calc_data |string |t(:row_comment_oc_calc_data)  |
|order_margin |number |t(:row_comment_order_margin)  |
|wallet_balance |number |t(:row_comment_wallet_balance)  |
|realised_pnl |number |t(:row_comment_realised_pnl)  |
|cum_realised_pnl |number |t(:row_comment_cum_realised_pnl)  |
|cum_commission |number |t(:row_comment_cum_commission)  |
|cross_seq |number |t(:row_comment_cross_seq)  |
|position_seq |number |t(:row_comment_position_seq)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|ext_fields>trailing_active |string |t(:row_comment_trailing_active)  |
|risk>id |number |t(:row_comment_riskId)  |
|risk>coin |string |t(:row_comment_coin_type)  |
|risk>limit |number |t(:row_comment_risk_limit)    |
|risk>maintain_margin |string |t(:row_comment_maintain_margin)  |
|risk>starting_margin |string |t(:row_comment_starting_margin)  |
|risk>section |string |t(:row_comment_section)  |
|risk>is_lowest_risk |number |t(:row_comment_is_lowest_risk)    |
|risk>created_at |string |t(:row_comment_created_at)  |
|risk>updated_at |string |t(:row_comment_updated_at)  |
