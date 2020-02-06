# t(:account_heading)
The following account data endpoints require authentication.

## t(:account_heading_active)
### t(:account_heading_placeActive)
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
        "symbol": "BTCUSD",
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
    "rate_limit_status": 99,
    "rate_limit_reset_ms": 1575111823448987,
    "rate_limit": 100
}
```

t(:account_para_placeActive)

##### t(:heading_http_request)
POST
<code><span id=vpoCreate>/v2/private/order/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#t-enums_header-side-side">side</a> |true |string |Side    |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol).    |
|<a href="#t-enums_header-order-type-order_type">order_type</a> |true |string |Active order type   |
|<a href="#t-enums_header-quantity-qty">qty</a> |true |integer |t(:row_comment_qty) |
|<a href="#t-enums_header-price-price">price</a> |false |number |t(:row_comment_price) |
|<a href="#t-enums_header-time-in-force-time_in_force">time_in_force</a> |true |string |t(:row_comment_timeInForce) |
|take_profit |false |number |t(:row_comment_takeProfit) |
|stop_loss |false |number |t(:row_comment_stopLoss) |
|trailing_stop|false |number |t(:row_comment_trailingStop) |
|reduce_only |false |bool |t(:row_comment_reduceOnly) |
|close_on_trigger |false |bool |t(:row_comment_closeOnTrigger)
|order_link_id |false |string |t(:row_comment_orderLinkId) |


### t(:account_heading_getActive)
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
                "cum_exec_fee": 2.2e-07,
                "reject_reason": "NoError",
                "order_link_id": "",
                "created_at": "2019-12-27T12:08:01.000Z",
                "updated_at": "2019-12-27T12:08:01.000Z",
                "order_id": "f185806b-b801-40ff-adec-52289370ed62"
            },
            {
                "user_id": 1,
                "symbol": "BTCUSD",
                "side": "Buy",
                "order_type": "Market",
                "price": 7079.5,
                "qty": 1,
                "time_in_force": "ImmediateOrCancel",
                "order_status": "Filled",
                "ext_fields": {
                    "op_from": "api",
                    "o_req_num": -34795932763,
                    "xreq_type": "x_create"
                },
                "last_exec_time": "1577448415.236019",
                "last_exec_price": 7079.5,
                "leaves_qty": 0,
                "leaves_value": 0,
                "cum_exec_qty": 1,
                "cum_exec_value": 0.00014125,
                "cum_exec_fee": 1.1e-07,
                "reject_reason": "NoError",
                "order_link_id": "",
                "created_at": "2019-12-27T12:06:55.000Z",
                "updated_at": "2019-12-27T12:06:55.000Z",
                "order_id": "3057c483-c688-4af8-a0eb-639e3ab7a753"
            }
        ]
    },
    "ext_info": null,
    "time_now": "1577448922.437871",
    "rate_limit_status": 599,
    "rate_limit_reset_ms": 1577448922444,
    "rate_limit": 600
}
```

t(:account_para_getActive)

##### t(:heading_http_request)
GET
<code><span id=oaoList>/open-api/order/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |false |string |t(:account_row_comment_orderId) |
|order_link_id |false |string |t(:row_comment_orderLinkId) |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |false |string |t(:row_comment_symbol). t(:default) `BTCUSD` |
|order |false |string |t(:row_comment_order)  |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:row_comment_limit) |
|<a href="#t-enums_header-order-status-order_status-get">order_status</a> |false |string |t(:account_row_comment_orderStatus) |


### t(:account_heading_cancelActive)
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
        "symbol": "BTCUSD",
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
    "rate_limit_status": 99,
    "rate_limit_reset_ms": 1575112681807671,
    "rate_limit": 100
}
```

t(:account_para_cancelActive)

##### t(:heading_http_request)
POST
<code><span id=vpoCancel>/v2/private/order/cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
|order_id |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|order_link_id |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |


### t(:account_heading_cancelAllActive)
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
            "cross_status": "PendingCancel",  // `PendingCancel` means the matching engine received the cancellation but there is no guarantee that the cancellation will be successful.
            "cross_seq": 387734027                              
        }
    ],
    "time_now": "1575110339.105675",
    "rate_limit_status": 98,
    "rate_limit_reset_ms": 1575110339100545,
    "rate_limit": 100
}
```

t(:account_para_cancelAllActive)

##### t(:heading_http_request)
POST
<code><span id=vpoCancelAll>/v2/private/order/cancelAll</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancelAll"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |true |string | t(:row_comment_symbol) |


### t(:account_heading_replaceActive)
> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,    //Error code,
    "ret_msg": "ok",  //Error message,
    "ext_code": "",
    "result": "ok",
    "time_now": "1539778407.210858",    // UTC timestamp
    "rate_limit_status": 0,             // The remaining number of accesses in one minute
}
```

t(:account_para_replaceActive)

<aside class="notice">
t(:account_aside_replaceActive)
</aside>

##### t(:heading_http_request)
POST
<code><span id=oaoReplace>/open-api/order/replace</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaoReplace"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |true |string |t(:row_comment_orderId) |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol). |
|p_r_qty |false |int |t(:row_comment_pRQty) |
|p_r_price |false |number |t(:row_comment_pRPrice) |


### t(:account_heading_queryActive)
> t(:codequote_responseExample)

```javascript
{
  "ret_code": 0,
  "ret_msg": "OK",
  "ext_code": "",
  "ext_info": "",
  "result": {
    "user_id": 1,
    "symbol": "BTCUSD",
    "side": "Sell",
    "order_type": "Limit",
    "price": "8083",
    "qty": 10,
    "time_in_force": "GoodTillCancel",
    "order_status": "New",
    "ext_fields": {
      "o_req_num": -308787,
      "xreq_type": "x_create",
      "xreq_offset": 4154640
    },
    "leaves_qty": 10,
    "leaves_value": "0.00123716",
    "cum_exec_qty": 0,
    "reject_reason": "",
    "order_link_id": "",
    "created_at": "2019-10-21T07:28:19.396246Z",
    "updated_at": "2019-10-21T07:28:19.396246Z",
    "order_id": "efa44157-c355-4a98-b6d6-1d846a936b93"
  },
  "time_now": "1571651135.291930"
}
```

t(:account_para_queryActive)

##### t(:heading_http_request)
GET
<code><span id=vpOrder>/v2/private/order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |false |string | t(:row_comment_orderId). **Required** if not pass order_link_id. |
|order_link_id |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |


## t(:account_heading_cond)
### t(:account_heading_placeCond)
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

##### t(:heading_http_request)
POST
<code><span id=oasoCreate>/open-api/stop-order/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oasoCreate"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#t-enums_header-side-side">side</a> |true |string |Side    |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)    |
|<a href="#t-enums_header-order-type-order_type">order_type</a> |true |string |Conditional order type |
|<a href="#t-enums_header-quantity-qty">qty</a> |true |integer |t(:row_comment_qty) |
|<a href="#t-enums_header-price-price">price</a> |false | number |t(:row_comment_price) |
|base_price |true |number | It will be used to compare with the value of 'stop_px', to decide whether your conditional order will be triggered by crossing trigger price from upper side or lower side. Mainly used to identify the expected direction of the current conditional order. |
|stop_px | true | number | Trigger price |
|<a href="#t-enums_header-time-in-force-time_in_force">time_in_force</a> |true |string |t(:row_comment_timeInForce) |
|<a href="#t-enums_header-trigger-price-type-trigger_by">trigger_by</a> | false | string | Trigger price type. Default `LastPrice` |
|close_on_trigger |false |bool |t(:row_comment_closeOnTrigger)
|order_link_id |false |string |t(:row_comment_orderLinkId) |


### t(:account_heading_getCond)
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

##### t(:heading_http_request)
GET
<code><span id=oasoList>/open-api/stop-order/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oasoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|stop_order_id |false |string |t(:row_comment_stopOrderId) |
|order_link_id |false |string |Agency customized order ID|
|<a href="#t-enums_header-symbol-symbol">symbol</a> |false |string |t(:row_comment_symbol). Default `BTCUSD`    |
|<a href="#t-enums_header-stop-order-status-stop_order_status">stop_order_status</a> |false |string |stop order status   |
|order |false |string |t(:row_comment_order) |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:row_comment_limit) |


### t(:account_heading_cancelCond)
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

##### t(:heading_http_request)
POST
<code><span id=oasoCancel>/open-api/stop-order/cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oasoCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|required|type | comments|
|:----- |:-------|:-----|----- |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)|
|stop_order_id |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|order_link_id |false |string | Agency customized order ID. **Required** if not pass stop_order_id|


### t(:account_heading_cancelAllCond)
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
            "symbol": "BTCUSD",
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
            "symbol": "BTCUSD",
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
    "rate_limit_reset_ms": 1577454993789325,
    "rate_limit": 100
}
```

t(:account_para_cancelAllCond)

##### t(:heading_http_request)
POST
<code><span id=vpsoCancelAll>/v2/private/stop-order/cancelAll</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpsoCancelAll"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|required|type | comments|
|:----- |:-------|:-----|----- |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)|


### t(:account_heading_replaceCond)
> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": [],
    "ext_info": null,
    "time_now": "1577475760.604942",
    "rate_limit_status": 96,
    "rate_limit_reset_ms": 1577475760612,
    "rate_limit": "100"
}
```


<aside class="notice">
t(:account_aside_replaceCond)
</aside>

##### t(:heading_http_request)
POST
<code><span id=oasoReplace>/open-api/stop-order/replace</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oasoReplace"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |true |string |t(:row_comment_orderId) |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol). |
|p_r_qty |false |int |t(:row_comment_pRQty) |
|p_r_price |false |number |t(:row_comment_pRPrice) |
|p_r_trigger_price |false |number |t(:row_comemnt_pRTriggerPrice) |


### t(:account_heading_queryConditional)
> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "user_id": 1,
        "symbol": "BTCUSD",
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
    "rate_limit_status": 599,
    "rate_limit_reset_ms": 1577476584383388,
    "rate_limit": 600
}
```

t(:account_para_queryConditional)

##### t(:heading_http_request)
GET
<code><span id=vpStopOrder>/v2/private/stop-order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpStopOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
|stop_order_id |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|order_link_id |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |


## t(:account_heading_leverage)
### t(:account_heading_userLeverage)
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

##### t(:heading_http_request)
GET
<code><span id=uLeverage>/user/leverage</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uLeverage"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |


### t(:account_heading_changeLeverage)
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
    "rate_limit": "75"
}
```

t(:account_para_changeLeverage)

##### t(:heading_http_request)
POST
<code><span id=ulSave>/user/leverage/save</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ulSave"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)    |
|leverage |true |string |t(:row_comment_leverage) |


## t(:account_heading_position)
### t(:account_heading_myPosition)
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
        "auto_add_margin": 0,
        "leverage": "1",
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
    },
    "time_now": "1577480599.097287",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1577480599093605,
    "rate_limit": 120
}
```

t(:account_para_myPosition)

##### t(:heading_http_request)
GET
<code><span id=pList>/v2/private/position/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pList"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)    |


### t(:account_heading_changeMargin)
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
    "rate_limit": "75"
}
```

t(:account_para_changeMargin)

<aside class="notice">
t(:account_aside_changeMargin)
</aside>

##### t(:heading_http_request)
POST
<code><span id=pChangePositionMargin>/position/change-position-margin</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pChangePositionMargin"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)    |
|margin |true |string |margin  |


### t(:account_heading_tradingStop)
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
            "sl_trigger_by": "LastPrice",
            "v": 221,
            "mm": 0
        }
    },
    "ext_info": null,
    "time_now": "1577481447.436689",
    "rate_limit_status": 73,
    "rate_limit_reset_ms": 1577481447443,
    "rate_limit": "75"
}
```

t(:account_para_tradingStop)

<aside class="notice">
t(:account_aside_tradingStop)
</aside>

##### t(:heading_http_request)
POST
<code><span id=oapTradingStop>/open-api/position/trading-stop</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oapTradingStop"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
|take_profit |false |string |t(:account_row_comment_takeProfit) |
|stop_loss |false |string |t(:account_row_comment_stopLoss) |
|trailing_stop |false |string |t(:account_row_comment_trailingStop) |


## t(:account_heading_funding)
### t(:market_heading_fundingRate)
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

t(:market_para_fundingRate)

##### t(:heading_http_request)
GET
<code><span id=oafPrevFundingRate>/open-api/funding/prev-funding-rate</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oafPrevFundingRate"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)    |

### t(:account_heading_myLastFunding)
> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": {
        "symbol": "BTCUSD",
        "side": "Buy",  // Your position side at the time of settlement
        "size": 1,      // Your position size at the time of settlement
        "funding_rate": 0.0001,  // Funding rate for settlement. When the funding rate is positive, longs pay shorts. When it is negative, shorts pay longs.
        "exec_fee": 2e-08,  // Funding fee.
        "exec_timestamp": 1575907200  // The time of funding settlement occurred, UTC timestamp
    },
    "ext_info": null,
    "time_now": "1577446900.717204",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1577446900724,
    "rate_limit": 120
}
```

t(:account_para_myLastFunding)

##### t(:heading_http_request)
GET
<code><span id=oafPrevFunding>/open-api/funding/prev-funding</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oafPrevFunding"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |


### t(:account_heading_predictedFunding)
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

##### t(:heading_http_request)
GET
<code><span id=oafPredictedFunding>/open-api/funding/predicted-funding</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oafPredictedFunding"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)    |


## t(:account_heading_key)
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
            "read_only": false
        }
    ],
    "ext_info": null,
    "time_now": "1577445138.790150",
    "rate_limit_status": 599,
    "rate_limit_reset_ms": 1577445138812,
    "rate_limit": 600
}
```

t(:account_para_key)

##### t(:heading_http_request)
GET
<code><span id=oaApiKey>/open-api/api-key</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaApiKey"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
