# t(:accountdata)
t(:account_para)

## t(:activeorders)
### t(:placeactive)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/futures/private/order/create \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","side"="Buy","symbol"="BTCUSDM21","order_type":"Market","qty":10,"time_in_force":"GoodTillCancel","timestamp":{timestamp},"sign":"{sign}"}'

```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.FuturesOrder.FuturesOrder_new(side="Buy",symbol="BTCUSDM21",order_type="Market",qty=1,time_in_force="GoodTillCancel").result())
```


> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "user_id": 1,
        "order_id": "335fd977-e5a5-4781-b6d0-c772d5bfb95b",
        "symbol": "BTCUSDM21",
        "side": "Buy",
        "order_type": "Limit",
        "price": 8800,
        "qty": 1,
        "time_in_force": "GoodTillCancel",
        "order_status": "Created",
        "last_exec_time": 0,
        "last_exec_price": 0,
        "leaves_qty": 1,
        "cum_exec_qty": 0,
        "cum_exec_value": 0,
        "cum_exec_fee": 0,
        "reject_reason": "",
        "order_link_id": "",
        "created_at": "2019-11-30T11:03:43.452Z",
        "updated_at": "2019-11-30T11:03:43.455Z"
    },
    "time_now": "1575111823.458705",
    "rate_limit_status": 98,
    "rate_limit_reset_ms": 1580885703683,
    "rate_limit": 100
}
```

t(:account_para_placeActive)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/futures/private/order/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|position_idx |<b>true</b>|integer |t(:row_comment_position_idx)  |
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
| order_id |string |t(:row_comment_orderId) |
|symbol|string |t(:row_comment_symbol)    |
|side |string |t(:row_comment_side)  |
|order_type |string |t(:row_comment_order_type)  |
|price |number |t(:row_comment_resp_price)  |
|qty |number |t(:row_response_comment_qty)  |
|time_in_force |string |t(:row_comment_timeInForce)  |
|order_status |string |t(:row_comment_orderStatus)  |
|last_exec_time |string |t(:row_comment_last_exec_time)  |
|last_exec_price |string |t(:row_comment_last_exec_price)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|cum_exec_qty |number |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |number |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |number |t(:linear_resp_field_cum_exec_fee)  |
|reject_reason |string |t(:row_comment_reject_reason)  |
|order_link_id |string |t(:row_response_comment_orderLinkId)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|take_profit |number |t(:row_comment_take_profit)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by)  |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by)  |

### t(:getactive)
> t(:codequote_curlExample)

```console
curl "https://api.bybit.com/futures/private/order/list?api_key={api_key}&timestamp={timestamp}&sign={sign}&symbol=BTCUSDM21"
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.FuturesOrder.FuturesOrder_getOrders(symbol="BTCUSDM21",order_status="New").result())
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
                "user_id": 160861,
                "position_idx": 0,
                "order_status": "Cancelled",
                "symbol": "BTCUSDM21",
                "side": "Buy",
                "order_type": "Market",
                "price": "9800",
                "qty": "16737",
                "time_in_force": "ImmediateOrCancel",
                "order_link_id": "",
                "order_id": "fead08d7-47c0-4d6a-b9e7-5c71d5df8ba1",
                "created_at": "2020-07-24T08:22:30Z",
                "updated_at": "2020-07-24T08:22:30Z",
                "leaves_qty": "0",
                "leaves_value": "0",
                "cum_exec_qty": "0",
                "cum_exec_value": "0",
                "cum_exec_fee": "0",
                "reject_reason": "EC_NoImmediateQtyToFill"
            }
        ],
        "cursor": "w01XFyyZc8lhtCLl6NgAaYBRfsN9Qtpp1f2AUy3AS4+fFDzNSlVKa0od8DKCqgAn"
    },
    "time_now": "1604653633.173848",
    "rate_limit_status": 599,
    "rate_limit_reset_ms": 1604653633171,
    "rate_limit": 600
}
```

t(:account_para_getActive)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpoList>/futures/private/order/list</span></code>
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
|data > user_id |integer |t(:row_comment_userID) |
|data > position_idx |integer |t(:row_comment_position_idx)  |
|data > symbol |string |t(:row_comment_symbol) |
|data > side |string |t(:row_comment_side) |
|data > order_type |string |t(:row_comment_order_type) |
|data > price  |string |t(:row_comment_resp_price) |
|data > qty  |string |t(:row_response_comment_qty) |
|data > time_in_force |string |t(:row_comment_timeInForce)  |
|data > order_status |string |t(:row_comment_orderStatus)  |
|data > leaves_qty |string |t(:row_comment_leaves_qty) |
|data > leaves_value |string |t(:row_comment_leaves_value) |
|data > cum_exec_qty |string |t(:linear_resp_field_cum_exec_qty)  |
|data > cum_exec_value |string |t(:linear_resp_field_cum_exec_value)  |
|data > cum_exec_fee |string |t(:linear_resp_field_cum_exec_fee)  |
|data > reject_reason |string |t(:row_comment_reject_reason)  |
|data > order_link_id |string |t(:row_response_comment_orderLinkId)  |
|data > created_at |string |t(:row_comment_created_at)  |
|data > order_id |string |t(:account_row_comment_orderId) |
|data > take_profit |number |t(:row_comment_take_profit)  |
|data > stop_loss |number |t(:row_comment_stop_loss)  |
|data > t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by) |
|data > t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by) |
|cursor |string |t(:row_comment_resp_cursor) |


### t(:cancelactive)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/futures/private/order/cancel \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDM21","order_id":"","timestamp":{timestamp},"sign":"{sign}"}'
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.FuturesOrder.FuturesOrder_cancel(symbol="BTCUSDM21", order_id="").result())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "user_id": 1,
        "order_id": "3bd1844f-f3c0-4e10-8c25-10fea03763f6",
        "symbol": "BTCUSDM21",
        "side": "Buy",
        "order_type": "Limit",
        "price": 8800,
        "qty": 1,
        "time_in_force": "GoodTillCancel",
        "order_status": "New",
        "last_exec_time": 0,
        "last_exec_price": 0,
        "leaves_qty": 1,
        "cum_exec_qty": 0,
        "cum_exec_value": 0,
        "cum_exec_fee": 0,
        "reject_reason": "",
        "order_link_id": "",
        "created_at": "2019-11-30T11:17:18.396Z",
        "updated_at": "2019-11-30T11:18:01.811Z"
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
<code><span id=vpoCancel>/futures/private/order/cancel</span></code>
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
|symbol|string |t(:row_comment_symbol)    |
|side |string |t(:row_comment_side)  |
|order_type |string |t(:row_comment_order_type)  |
|price |number |t(:row_comment_resp_price)  |
|qty |number |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce) |
|order_status |string |t(:row_comment_orderStatus)  |
|last_exec_time |string |t(:row_comment_last_exec_time)  |
|last_exec_price |string |t(:row_comment_last_exec_price)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|cum_exec_qty |number |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |number |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |number |t(:linear_resp_field_cum_exec_fee)  |
|reject_reason |string |t(:row_comment_reject_reason)  |
|order_link_id |string |t(:row_response_comment_orderLinkId)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |

### t(:cancelallactive)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/futures/private/order/cancelAll \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDM21","timestamp":{timestamp},"sign":"{sign}"}'
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.FuturesOrder.FuturesOrder_cancelAll(symbol="BTCUSDM21").result())
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
            "symbol": "BTCUSDM21",                                
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
            "cross_status": "PendingCancel",  // `PendingCancel` means the matching engine received the cancellation but there is no guarantee that the cancellation will be successful.
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
<code><span id=vpoCancelAll>/futures/private/order/cancelAll</span></code>
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
|symbol|string |t(:row_comment_symbol)    |
|side |string |t(:row_comment_side)  |
|order_type |string |t(:row_comment_order_type)  |
|price |number |t(:row_comment_resp_price)  |
|qty |number |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce) |
|create_type |string |t(:row_comment_create_type)  |
|cancel_type |string |t(:row_comment_cancel_type)  |
|order_status |string |t(:row_comment_orderStatus)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|leaves_value |number |t(:row_comment_leaves_value)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|cross_status |string |t(:row_comment_cross_status)  |
|cross_seq |number |t(:row_comment_cross_seq)  |

### t(:replaceactive)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/futures/private/order/replace \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDM21","order_id":"","timestamp":{timestamp},"sign":"{sign}"}'
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.FuturesOrder.FuturesOrder_replace(symbol="BTCUSDM21", order_id="69bd5b88-fa2e-4c33-a489-1860f595191d", p_r_qty="2").result())
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
<code><span id=vpoReplace>/futures/private/order/replace</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoReplace"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|order_link_id |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol). |
|p_r_qty |false |string |t(:row_comment_pRQty) |
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
curl "https://api.bybit.com/futures/private/order?api_key={api_key}&symbol=BTCUSDM21&timestamp={timestamp}order_id={order_id}&sign={sign}"
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.FuturesOrder.FuturesOrder_query(symbol="BTCUSDM21", order_id="").result())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "user_id": 106958,
        "position_idx":0,
        "symbol": "BTCUSDM21",
        "side": "Buy",
        "order_type": "Limit",
        "price": "11756.5",
        "qty": 1,
        "time_in_force": "PostOnly",
        "order_status": "Filled",
        "ext_fields": {
            "o_req_num": -68948112492,
            "xreq_type": "x_create"
        },
        "last_exec_time": "1596304897.847944",
        "last_exec_price": "11756.5",
        "leaves_qty": 0,
        "leaves_value": "0",
        "cum_exec_qty": 1,
        "cum_exec_value": "0.00008505",
        "cum_exec_fee": "-0.00000002",
        "reject_reason": "",
        "cancel_type": "",
        "order_link_id": "",
        "created_at": "2020-08-01T18:00:26Z",
        "updated_at": "2020-08-01T18:01:37Z",
        "order_id": "e66b101a-ef3f-4647-83b5-28e0f38dcae0"
    },
    "time_now": "1597171013.867068",
    "rate_limit_status": 599,
    "rate_limit_reset_ms": 1597171013861,
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
            "user_id": 100228,
            "position_idx":0,
            "symbol": "BTCUSDM21",
            "side": "Sell",
            "order_type": "Limit",
            "price": "17740",
            "qty": 10,
            "time_in_force": "GoodTillCancel",
            "order_status": "New",
            "ext_fields": {
                "o_req_num": 434743,
                "xreq_type": "x_create"
            },
            "last_exec_time": "1608193181.827761",
            "leaves_qty": 10,
            "leaves_value": "0.00056369",
            "cum_exec_qty": 0,
            "cum_exec_value": "0.00008505",
            "cum_exec_fee": "-0.00000002",
            "reject_reason": "EC_NoError",
            "cancel_type": "UNKNOWN",
            "order_link_id": "",
            "created_at": "2020-12-17T08:19:41.827637283Z",
            "updated_at": "2020-12-17T08:19:41.827761Z",
            "order_id": "d570d931-771e-4911-a24e-cdeddedb5b0e"
        },
        ...
        {
            "user_id": 100228,
            "position_idx":0,
            "symbol": "BTCUSDM21",
            "side": "Sell",
            "order_type": "Limit",
            "price": "17740",
            "qty": 10,
            "time_in_force": "GoodTillCancel",
            "order_status": "New",
            "ext_fields": {
                "o_req_num": 434728,
                "xreq_type": "x_create"
            },
            "last_exec_time": "1608193178.955412",
            "leaves_qty": 10,
            "leaves_value": "0.00056369",
            "cum_exec_qty": 0,
            "cum_exec_value": "0.00008505",
            "cum_exec_fee": "-0.00000002",
            "reject_reason": "EC_NoError",
            "cancel_type": "UNKNOWN",
            "order_link_id": "",
            "created_at": "2020-12-17T08:19:38.955297869Z",
            "updated_at": "2020-12-17T08:19:38.955412Z",
            "order_id": "88b91101-7ac1-40af-90b8-72d53fe23622"
        }
    ],
    "time_now": "1608193190.911073",
    "rate_limit_status": 599,
    "rate_limit_reset_ms": 1608193190909,
    "rate_limit": 600
}

```
t(:account_para_queryActive)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpOrder>/futures/private/order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|order_id |false |string | t(:row_comment_order_id)|
|order_link_id |false |string |t(:row_comment_order_link_id) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |number |t(:row_comment_userID)  |
|position_idx |integer |t(:row_comment_position_idx)  |
|symbol|string |t(:row_comment_symbol)    |
|side |string |t(:row_comment_side)  |
|order_type |string |t(:row_comment_order_type)  |
|price |number |t(:row_comment_resp_price)  |
|qty |number |t(:row_response_comment_qty)  |
|time_in_force |string |t(:row_comment_timeInForce)  |
|order_status |string |t(:row_comment_orderStatus)  |
|ext_fields |json |t(:row_comment_ext_fields)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|leaves_value |number |t(:row_comment_leaves_value)  |
|cum_exec_qty |number |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |number |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |order_link_id |string |t(:linear_resp_field_cum_exec_fee)  |
|reject_reason |string |t(:row_comment_reject_reason)  |
|cancel_type |string |t(:row_comment_cancel_type)  |
|order_link_id |string |t(:row_response_comment_orderLinkId)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|order_id |string |t(:row_comment_order_id)  |
|take_profit |number |t(:row_comment_take_profit)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by) |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by) |

## t(:conditionalorders)
### t(:placecond)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/futures/private/stop-order/create \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","order_type":"Limit","side":"Buy","symbol":"BTCUSDM21","qty":1,"price":8100,"base_price":8300,"stop_px":8150,"time_in_force":"GoodTillCancel","order_link_id":"cus_order_id_1","timestamp":{timestamp},"sign":"{sign}"}'
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.FuturesConditional.FuturesConditional_new(order_type="Limit",side="Buy",symbol="BTCUSDM21",qty="1",price="0.2569",base_price="15700",stop_px="0.2119",time_in_force="GoodTillCancel").result())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code":0,
    "ret_msg":"OK",
    "ext_code":"",
    "ext_info":"",
    "result":{
        "user_id":160880,
        "symbol":"BTCUSDM21",
        "side":"Buy",
        "order_type":"Limit",
        "price":"9003",
        "qty":"2",
        "time_in_force":"GoodTillCancel",
        "remark":"127.0.0.1",
        "leaves_qty":"2",
        "leaves_value":"0",
        "stop_px":"8232",
        "reject_reason":"EC_NoError",
        "stop_order_id":"eaf205ac-9dcc-44f6-8731-734e2101e61b",
        "created_at":"2020-11-06T07:48:43.940Z",
        "updated_at":"2020-11-06T07:48:43.940Z"
    },
    "time_now":"1604648923.942177"
}
```

t(:account_para_placeCond)

<aside class="notice">
t(:account_aside_placeCond)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpsoCreate>/futures/private/stop-order/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpsoCreate"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|position_idx |<b>true</b>|integer |t(:row_comment_position_idx)  |
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
|take_profit |false |number |t(:row_comment_takeProfit) |
|stop_loss |false |number |t(:row_comment_stopLoss) |
|t(:row_parameter_tp_trigger_by) |false |string |t(:account_row_comment_tp_trigger_by) |
|t(:row_parameter_sl_trigger_by) |false |string |t(:account_row_comment_sl_trigger_by) |

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
|t(:row_parameter_trigger_price) |string |t(:row_comment_triggerBy)  |
|base_price |string |t(:row_response_comment_basePrice)  |
|remark |string |t(:row_comment_remark)  |
|reject_reason |string |t(:row_comment_reject_reason)  |
|stop_px |string |t(:linear_row_comment_stopPx)  |
|stop_order_id |string |t(:row_comment_stopOrderId) |
|created_at |string |t(:row_comment_created_at)  |
|order_link_id |string |t(:row_response_comment_orderLinkId)  |
|take_profit |false |number |t(:row_comment_take_profit)  |
|stop_loss |false |number |t(:row_comment_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by)  |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by)  |


### t(:getcond)
> t(:codequote_curlExample)

```console
curl "https://api.bybit.com/futures/private/stop-order/list?api_key={api_key}&timestamp={timestamp}&sign={sign}"
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.FuturesConditional.FuturesConditional_getOrders(symbol="BTCUSDM21",stop_order_status="Untriggered").result())
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
                "user_id": 160861,
                "position_idx": 0,
                "stop_order_status": "Active",
                "symbol": "ETHUSD",
                "side": "Buy",
                "order_type": "Market",
                "stop_order_type": "TakeProfit",
                "price": "220",
                "qty": "120",
                "time_in_force": "ImmediateOrCancel",
                "base_price": "258",
                "order_link_id": "",
                "created_at": "2019-08-02T07:37:24Z",
                "updated_at": "2019-08-02T07:38:40Z",
                "stop_px": "224.3",
                "stop_order_id": "6d0dec74-f516-4d95-81f1-c85e60c9a331"
            }
        ],
        "cursor": "zZtvOJ0gc3UOxZOwotsJSZyMTOgyC9tj1DmFyUU6eNHUL0X4NLwZvo8iqI6ltPIc"
    },
    "time_now": "1604653512.292878",
    "rate_limit_status": 599,
    "rate_limit_reset_ms": 1604653512287,
    "rate_limit": 600
}
```

t(:account_para_getCond)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpsoList>/futures/private/stop-order/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpsoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|t(:row_parameter_stop_order) |false |string |t(:account_row_comment_stopOrderStatus) |
|direction |false |string |t(:row_comment_cursor_direction) |
|limit |false |integer |t(:row_comment_limit) |
|cursor |false |string |t(:row_comment_cursor) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|data > user_id |integer |t(:row_comment_userID)  |
|data > position_idx |integer |t(:row_comment_position_idx)  |
|data > t(:row_parameter_stop_order)|string |t(:row_comment_stopOrderStatus)    |
|data > t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|data > t(:row_parameter_side) |string |t(:row_comment_side)  |
|data > t(:row_parameter_order_type) |string |t(:row_comment_orderType)  |
|data > t(:row_parameter_price) |number |t(:row_response_comment_price)  |
|data > t(:row_parameter_quantity) |number |t(:row_response_comment_qty)  |
|data > t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|data > stop_order_type |string |t(:row_comment_stopOrderType)  |
|data > t(:row_parameter_trigger_price) |string |t(:row_comment_triggerBy)  |
|data > base_price |number |t(:row_response_comment_basePrice)  |
|data > order_link_id |string |t(:row_response_comment_orderLinkId)  |
|data > created_at |string |t(:row_comment_created_at)  |
|data > updated_at |string |t(:row_comment_updated_at)  |
|data > stop_px |number |t(:linear_row_comment_stopPx)  |
|data > stop_order_id |string |t(:row_comment_stopOrderId) |
|data > take_profit |number |t(:row_comment_take_profit)  |
|data > stop_loss |number |t(:row_comment_stop_loss)  |
|data > t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by) |
|data > t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by) |
|cursor |string |t(:row_comment_resp_cursor) |


### t(:cancelcond)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/futures/private/stop-order/cancel \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDM21","stop_order_id":"xxx","timestamp":{timestamp},"sign":"{sign}"}'
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.FuturesConditional.FuturesConditional_cancel(symbol="BTCUSDM21", stop_order_id="").result())
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
<code><span id=vpsoCancel>/futures/private/stop-order/cancel</span></code>
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
curl https://api.bybit.com/futures/private/stop-order/cancelAll \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDM21","timestamp":{timestamp},"sign":"{sign}"}'
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.FuturesConditional.FuturesConditional_cancelAll(symbol="BTCUSDM21").result())
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
            "clOrdID": "dea89649-9492-459d-a8c4-c298b87b3d26",
            "user_id": 1,
            "symbol": "BTCUSDM21",
            "side": "Sell",
            "order_type": "Limit",
            "price": "999999",
            "qty": 1,
            "time_in_force": "PostOnly",
            "create_type": "CreateByUser",
            "cancel_type": "CancelByUser",
            "order_status": "",
            "leaves_qty": 1,
            "leaves_value": "0",
            "created_at": "2019-12-17T12:13:20Z",
            "updated_at": "2019-12-27T13:56:33.793799Z",
            "cross_status": "Deactivated",
            "cross_seq": -1,
            "stop_order_type": "Stop",
            "trigger_by": "LastPrice",
            "base_price": "6910.5",
            "expected_direction": "Rising"
        },
        {
            "clOrdID": "a85cd1c0-a9a4-49d3-a1bd-bab5ebe946d5",
            "user_id": 1,
            "symbol": "BTCUSDM21",
            "side": "Buy",
            "order_type": "Limit",
            "price": "8000",
            "qty": 1,
            "time_in_force": "GoodTillCancel",
            "create_type": "CreateByStopOrder",
            "cancel_type": "CancelByUser",
            "order_status": "",
            "leaves_qty": 1,
            "leaves_value": "0",
            "created_at": "2019-12-27T12:48:24.339323Z",
            "updated_at": "2019-12-27T13:56:33.793802Z",
            "cross_status": "Deactivated",
            "cross_seq": -1,
            "stop_order_type": "Stop",
            "trigger_by": "LastPrice",
            "base_price": "7000",
            "expected_direction": "Rising"
        }
    ],
    "time_now": "1577454993.799912",
    "rate_limit_status": 90,
    "rate_limit_reset_ms": 1580885703683,
    "rate_limit": 100
}
```

t(:account_para_cancelAllCond)

<aside class="notice">
t(:account_aside_cancelAllCond)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpsoCancelAll>/futures/private/stop-order/cancelAll</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpsoCancelAll"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|required|type | comments|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|clOrdID |string |t(:row_comment_clOrdID)  |
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_order_type) |string |t(:row_comment_orderType)  |
|t(:row_parameter_price) |number |t(:row_response_comment_price)  |
|t(:row_parameter_quantity) |number |t(:row_response_comment_qty)  |
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|create_type |string |t(:row_comment_create_type)  |
|cancel_type |string |t(:row_comment_cancel_type)  |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|leaves_value |number |t(:row_comment_leaves_value)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|cross_status |string |t(:row_comment_cross_status)  |
|cross_seq |number |t(:row_comment_cross_seq)  |
|stop_order_type |string |t(:row_comment_stopOrderType)  |
|t(:row_parameter_trigger_price) |string |t(:row_comment_triggerBy)  |
|base_price |number |t(:row_response_comment_basePrice)  |
|expected_direction |string |t(:row_comment_expected_direction)  |


### t(:replacecond)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/futures/private/stop-order/replace \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDM21","stop_order_id":"","timestamp":{timestamp},"sign":"{sign}"}'
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.FuturesConditional.FuturesConditional_replace(symbol="BTCUSDM21", stop_order_id="69bd5b88-fa2e-4c33-a489-1860f595191d",p_r_qty="2").result())

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
<code><span id=vpsoReplace>/futures/private/stop-order/replace</span></code>
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
curl "https://api.bybit.com/futures/private/stop-order?api_key={api_key}&symbol=BTCUSDM21&timestamp={timestamp}order_id={order_id}&sign={sign}"
```
```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.FuturesConditional.FuturesConditional_query(symbol="BTCUSDM21", stop_order_id="", p_r_trigger_price="16003").result())

```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "user_id": 1,
        "position_idx": 0,
        "symbol": "BTCUSDM21",
        "side": "Buy",
        "order_type": "Limit",
        "price": "8000",
        "qty": 1,
        "time_in_force": "GoodTillCancel",
        "order_status": "Untriggered",
        "ext_fields": {},
        "leaves_qty": 1,
        "leaves_value": "0.00013333",
        "cum_exec_qty": 0,
        "cum_exec_value": null,
        "cum_exec_fee": null,
        "reject_reason": "",
        "order_link_id": "",
        "created_at": "2019-12-27T19:56:24.052194Z",
        "updated_at": "2019-12-27T19:56:24.052194Z",
        "order_id": "378a1bbc-a93a-4e75-87f4-502ea754ba36"
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
            "user_id": 100328,
            "position_idx": 0,
            "symbol": "EOSUSD",
            "side": "Sell",
            "order_type": "Limit",
            "price": "2.7",
            "qty": 1,
            "stop_px": "2.0000",
            "base_price": "2.7000",
            "time_in_force": "GoodTillCancel",
            "order_status": "Untriggered",
            "ext_fields": {},
            "leaves_qty": 1,
            "leaves_value": "0.37037037",
            "cum_exec_qty": 0,
            "cum_exec_value": null,
            "cum_exec_fee": null,
            "reject_reason": "EC_NoError",
            "cancel_type": "UNKNOWN",
            "order_link_id": "",
            "created_at": "2020-12-17T08:21:15.246331281Z",
            "updated_at": "2020-12-17T08:21:15.246331281Z",
            "order_id": "a0dee45e-ae2a-4eb4-8205-9739075a7a81",
            "trigger_by": "MarkPrice"
        },
        ...
        {
            "user_id": 100328,
            "position_idx": 0,
            "symbol": "EOSUSD",
            "side": "Sell",
            "order_type": "Limit",
            "price": "2.6",
            "qty": 1,
            "stop_px": "2.0000",
            "base_price": "2.7000",
            "time_in_force": "GoodTillCancel",
            "order_status": "Untriggered",
            "ext_fields": {},
            "leaves_qty": 1,
            "leaves_value": "0.38461538",
            "cum_exec_qty": 0,
            "cum_exec_value": null,
            "cum_exec_fee": null,
            "reject_reason": "EC_NoError",
            "cancel_type": "UNKNOWN",
            "order_link_id": "",
            "created_at": "2020-12-17T08:21:10.924193413Z",
            "updated_at": "2020-12-17T08:21:10.924193413Z",
            "order_id": "51d048ba-a71f-40ef-b4c4-897e94590b80",
            "trigger_by": "MarkPrice"
        }
    ],
    "time_now": "1608193281.690286",
    "rate_limit_status": 599,
    "rate_limit_reset_ms": 1608193281687,
    "rate_limit": 600
}
```
t(:account_para_queryConditional)

<aside class="notice">
t(:account_para_queryConditionalNote)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpStopOrder>/futures/private/stop-order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpStopOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|stop_order_id |false |string | t(:row_comment_order_id)|
|order_link_id |false |string |t(:row_comment_order_link_id) |

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
|t(:row_parameter_time_in_force) |string |t(:row_comment_timeInForce)  |
|t(:row_parameter_order_status) |string |t(:row_comment_orderStatus)  |
|ext_fields |json |t(:row_comment_ext_fields)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|leaves_value |number |t(:row_comment_leaves_value)  |
|cum_exec_qty |number |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |number |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |number |t(:linear_resp_field_cum_exec_fee)  |
|reject_reason |string |t(:row_comment_reject_reason)  |
|order_link_id |string |t(:row_response_comment_orderLinkId)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|order_id |string |t(:row_comment_order_id)  |
|base_price |string |t(:row_response_comment_basePrice)  |
|stop_px |string |t(:linear_row_comment_stopPx)  |
|t(:row_parameter_trigger_price) |string |t(:row_comment_triggerBy)  |
|take_profit |number |t(:row_comment_take_profit)  |
|stop_loss |number |t(:row_comment_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by)  |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by)  |


## t(:position)
### t(:myposition)
> t(:codequote_curlExample)

```console
curl "https://api.bybit.com/futures/private/position/list?api_key={api_key}&symbol=BTCUSDM21&timestamp={timestamp}&sign={sign}"
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.FuturesPositions.FuturesPositions_myPosition(symbol="BTCUSDM21").result())
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
            "data": {
                "id": 0,
                "position_idx": 1,
                "mode": 3,
                "user_id": 103669,
                "risk_id": 61,
                "symbol": "BTCUSDM21",
                "side": "Buy",
                "size": 200000,
                "position_value": "3.62934747",
                "entry_price": "55106.32466392",
                "is_isolated": true,
                "auto_add_margin": 0,
                "leverage": "10",
                "effective_leverage": "0",
                "position_margin": "0.36592896",
                "liq_price": "50325.5",
                "bust_price": "50097",
                "occ_closing_fee": "0.0029942",
                "occ_funding_fee": "0",
                "take_profit": "0",
                "stop_loss": "0",
                "trailing_stop": "0",
                "position_status": "Normal",
                "deleverage_indicator": 4,
                "oc_calc_data": "{\"blq\":0,\"slq\":0,\"bmp\":0,\"smp\":0,\"fq\":-200000,\"bv2c\":0.101575,\"sv2c\":0.101425}",
                "order_margin": "0",
                "wallet_balance": "9.95270565",
                "realised_pnl": "-0.00272207",
                "unrealised_pnl": 0,
                "cum_realised_pnl": "-0.00272207",
                "cross_seq": 2392689554,
                "position_seq": 0,
                "created_at": "2021-03-11T08:11:17.747178448Z",
                "updated_at": "2021-03-11T08:24:18.923067183Z"
            },
            "is_valid": true
        },
        {
            "data": {
                "id": 0,
                "position_idx": 0,
                "mode": 0,
                "user_id": 103669,
                "risk_id": 71,
                "symbol": "BTCUSDM21",
                "side": "Buy",
                "size": 2,
                "position_value": "0.00003644",
                "entry_price": "54884.74204171",
                "is_isolated": false,
                "auto_add_margin": 1,
                "leverage": "100",
                "effective_leverage": "0",
                "position_margin": "0.0000004",
                "liq_price": "0.5",
                "bust_price": "0.5",
                "occ_closing_fee": "0.003",
                "occ_funding_fee": "0",
                "take_profit": "0",
                "stop_loss": "0",
                "trailing_stop": "0",
                "position_status": "Normal",
                "deleverage_indicator": 3,
                "oc_calc_data": "{\"blq\":0,\"slq\":0,\"bmp\":0,\"smp\":0,\"fq\":-2,\"bv2c\":0.0115075,\"sv2c\":0.0114925}",
                "order_margin": "0",
                "wallet_balance": "9.95270565",
                "realised_pnl": "0",
                "unrealised_pnl": 0,
                "cum_realised_pnl": "-0.00000002",
                "cross_seq": 2360303954,
                "position_seq": 0,
                "created_at": "2021-02-24T05:56:07.964274148Z",
                "updated_at": "2021-03-11T08:52:06.772110817Z"
            },
            "is_valid": true
        }
    ],
    "time_now": "1615452727.664848",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1615452727660,
    "rate_limit": 120
}
```

t(:account_para_myPosition)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pList>/futures/private/position/list</span></code>
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
curl https://api.bybit.com/futures/private/position/change-position-margin \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDM21",margin:"10","timestamp":{timestamp},"sign":"{sign}"}'
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.FuturesPositions.FuturesPositions_changeMargin(symbol="BTCUSDM21", margin="10").result())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": 9.996e-05,
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
<code><span id=pChangePositionMarginNew>/futures/private/position/change-position-margin</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pChangePositionMarginNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|position_idx |<b>true</b>|integer |t(:row_comment_position_idx)  |
|margin |<b>true</b> |string |t(:row_comment_margin)  |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|result |number |t(:row_comment_margin_result)  |



### t(:tradingstop)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/futures/private/position/trading-stop \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDM21","stop_loss":7000,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.FuturesPositions.FuturesPositions_tradingStop(symbol="BTCUSDM21",take_profit="0", stop_loss="9110", trailing_stop="0", new_trailing_active="0").result())
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
        "symbol": "BTCUSDM21",
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

t(:account_para_tradingStop)

<aside class="notice">
t(:account_aside_tradingStop)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oapTradingStopNew>/futures/private/position/trading-stop</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oapTradingStopNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|position_idx |<b>true</b>|integer |t(:row_comment_position_idx)  |
|take_profit |false |number |t(:account_row_comment_takeProfit) |
|stop_loss |false |number |t(:account_row_comment_stopLoss) |
|trailing_stop |false |number |t(:account_row_comment_trailingStop) |
|t(:row_parameter_tp_trigger_by) | false | string | t(:account_row_comment_tp_trigger_by)
|t(:row_parameter_sl_trigger_by) | false | string | t(:account_row_comment_tp_trigger_by)
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
|position_value |string |t(:row_comment_position_value)  |
|entry_price |string |t(:row_comment_entry_price)  |
|risk_id |number |t(:row_comment_riskId)  |
|auto_add_margin |number |t(:row_comment_auto_add_margin)  |
|leverage |string |t(:resp_field_leverage)  |
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
|cum_realised_pnl |string |t(:row_comment_cum_realised_pnl)  |
|cum_commission |number |t(:row_comment_cum_commission)  |
|cross_seq |number |t(:row_comment_cross_seq)  |
|position_seq |number |t(:row_comment_position_seq)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|ext_fields>trailing_active |string |t(:row_comment_trailing_active)  |
|ext_fields>sl_trigger_by |string |t(:row_comment_sl_trigger_by)  |



### t(:setleverage)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/futures/private/position/leverage/save \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDM21","buy_leverage":14,"sell_leverage":14,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.FuturesPositions.FuturesPositions_saveLeverage(symbol="BTCUSDM21", buy_leverage="14",sell_leverage="14").result())
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
<code><span id=ulSaveNew>/futures/private/position/leverage/save</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ulSaveNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|buy_leverage |<b>true</b> |number |t(:futures_row_comment_leverage) |
|sell_leverage |<b>true</b> |number |t(:futures_row_comment_leverage) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|result |number |t(:row_comment_leverage_result)  |


### t(:switchpositionmode)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/futures/private/position/switch-mode \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDM21","mode":0,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.FuturesPositions.FuturesPositions_switchPositionMode(symbol="BTCUSDM21",mode=0).result())
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

t(:account_para_switchpositionmode)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=ulSwitchMode>/futures/private/position/switch-mode</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ulSwitchMode"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|mode |<b>true</b> |int |t(:row_comment_positionmode) |




### t(:switchmode)
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
<code><span id=fptSwitchMode>/futures/private/tpsl/switch-mode</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#fptSwitchMode"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

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
curl https://api.bybit.com/futures/private/position/switch-isolated \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDM21", "is_isolated":true,"buy_leverage":10,"sell_leverage":20, "timestamp":{timestamp},"sign":"{sign}"}'
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.FuturesPositions.FuturesPositions_switchIsolated(symbol="BTCUSDM21",is_isolated=True, buy_leverage="1", sell_leverage="1").result())
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
<code><span id=ulSwitchMode>/futures/private/position/switch-isolated</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ulSwitchMode"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|is_isolated |<b>true</b> |bool |t(:futures_row_comment_switch_isolated)  |
|buy_leverage |<b>true</b> |number |t(:futures_row_comment_leverage)  |
|sell_leverage |<b>true</b> |number |t(:futures_row_comment_leverage)  |





### t(:usertraderecords)
> t(:codequote_curlExample)

```console
curl "https://api.bybit.com/futures/private/execution/list?api_key={api_key}&symbol=BTCUSDM21&timestamp={timestamp}&sign={sign}"
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.FuturesExecution.FuturesExecution_getTrades(symbol="BTCUSDM21").result())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "order_id": "t(:comment_abandoned)", // t(:comment_abandoned)
        "trade_list": [
            {
                "closed_size": 0, // t(:row_comment_closed_size)
                "cross_seq": 277136382,
                "exec_fee": "0.0000001",
                "exec_id": "256e5ef8-abfe-5772-971b-f944e15e0d68",
                "exec_price": "8178.5",
                "exec_qty": 1,
                "exec_time": "1571676941.70682",    //t(:comment_abandoned)
                "exec_type": "Trade", //t(:enum_exec_type_link)
                "exec_value": "0.00012227",
                "fee_rate": "0.00075",
                "last_liquidity_ind": "RemovedLiquidity", //t(:enum_Liquidity_type_link)
                "leaves_qty": 0,
                "nth_fill": 2,
                "order_id": "7ad50cb1-9ad0-4f74-804b-d82a516e1029",
                "order_link_id": "",
                "order_price": "8178",
                "order_qty": 1,
                "order_type": "Market", //t(:enum_order_type_link)
                "side": "Buy", //t(:enum_side_link)
                "symbol": "BTCUSDM21", //t(:enum_symbol_link)
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
<code><span id=vpeList>/futures/private/execution/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpeList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |false |string |t(:wallet_row_comment_orderId) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:misc_row_comment_symbolNotOrderId) |
|start_time |false |int |t(:row_comment_startTime_ms) |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:row_comment_limit_50_200) |
|<a href="#order-order">order</a> |false |string |t(:row_comment_order) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|closed_size |number |t(:row_comment_closed_size)  |
|cross_seq |number |t(:row_comment_cross_seq)  |
|exec_fee |string |t(:row_comment_exec_fee)    |
|exec_id |string |t(:row_comment_exec_id)  |
|exec_price |number |t(:row_comment_exec_price)    |
|exec_qty |number |t(:row_comment_exec_qty)  |
|t(:row_parameter_exec_type) |string |t(:enum_exec_type_link)  |
|exec_value |string |t(:row_comment_exec_value)  |
|fee_rate |string |t(:row_comment_fee_rate)  |
|last_liquidity_ind |string |t(:enum_Liquidity_type_link)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|nth_fill |number |t(:row_comment_nth_fill)  |
|order_id |string |t(:row_comment_order_id)  |
|order_link_id |string |t(:row_comment_order_link_id)  |
|order_price |string |t(:row_comment_order_price)  |
|order_qty |string |t(:row_comment_order_qty)  |
|t(:row_parameter_order_type) |string |t(:enum_order_type_link)  |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_symbol) |string |t(:enum_symbol_link)  |
|user_id |number |t(:row_comment_user_id)  |
|trade_time_ms |number |t(:row_comment_trade_time)  |


### t(:closedprofitandloss)
> t(:codequote_curlExample)

```console
curl "https://api.bybit.com/futures/private/trade/closed-pnl/list?api_key={api_key}&symbol=BTCUSDM21&timestamp={timestamp}&sign={sign}"
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.FuturesPositions.FuturesPositions_closePnlRecords(symbol="BTCUSDM21").result())
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
                "symbol": "BTCUSDM21",
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
<code><span id=pltcList>/futures/private/trade/closed-pnl/list</span></code>
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
|order_id |string |t(:row_comment_order_id) |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|t(:row_parameter_quantity) |number |t(:row_response_comment_qty)  |
|order_price |number |t(:row_comment_order_price)  |
|t(:row_parameter_order_type) |string |t(:row_comment_orderType)  |
|t(:row_parameter_exec_type) |string |t(:enum_exec_type_link)  |
|closed_size |number |t(:row_comment_closed_size)  |
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
<a href="/docs/inverse#t-getrisklimit">t(:shared_endpoint_desc)</a>

### t(:setrisklimit)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/futures/private/position/risk-limit \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDM21","risk_id":2,"timestamp":{timestamp},"sign":"{sign}"}'
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
t(:account_aside_getRisk)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oawrlList>futures/private/position/risk-limit</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawrlList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|risk_id |<b>true</b> |integer |t(:row_comment_riskId) |
|position_idx |<b>false</b>|integer |t(:row_comment_position_idx)  |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|risk_id |number |t(:row_comment_riskId)  |

## t(:key)
<a href="/docs/inverse#t-key">t(:shared_endpoint_desc)</a>
