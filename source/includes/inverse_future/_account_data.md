# t(:accountdata)
t(:account_para)

## t(:activeorders)
### t(:placeactive)
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
    "rate_limit_status": 98,
    "rate_limit_reset_ms": 1580885703683,
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
|<a href="#side-side">side</a> |true |string |t(:row_comment_side)    |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)   |
|<a href="#order-type-order_type">order_type</a> |true |string |t(:row_comment_activeOrderType)   |
|<a href="#quantity-qty">qty</a> |true |integer |t(:row_comment_qty) |
|<a href="#price-price">price</a> |false |number |t(:row_comment_price) |
|<a href="#time-in-force-time_in_force">time_in_force</a> |true |string |t(:row_comment_timeInForce) |
|take_profit |false |number |t(:row_comment_takeProfit) |
|stop_loss |false |number |t(:row_comment_stopLoss) |
|reduce_only |false |bool |t(:row_comment_reduceOnly) |
|close_on_trigger |false |bool |t(:row_comment_closeOnTrigger)
|order_link_id |false |string |t(:row_comment_orderLinkId) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| user_id |number |t(:row_comment_userID) |
| order_id |string |t(:row_comment_orderId) |
|symbol|string |t(:row_comment_symbol)    |
|side |string |t(:row_comment_side)  |
|order_type |string |t(:row_comment_order_type)  |
|price |number |t(:row_comment_price)  |
|qty |number |t(:row_comment_qty)  |
|time_in_force |string |t(:row_comment_timeInForce)  |
|order_status |string |t(:row_comment_orderStatus)  |
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

### t(:getactive)
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
|<a href="#symbol-symbol">symbol</a> |false |string |t(:row_comment_symbol). t(:default) `BTCUSD` |
|order |false |string |t(:row_comment_order)  |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:row_comment_limit) |
|<a href="#order-status-order_status-get">order_status</a> |false |string |t(:account_row_comment_orderStatus) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| user_id |number |t(:row_comment_userID) |
| symbol |string |t(:row_comment_symbol) |
| side |string |t(:row_comment_side) |
| order_type |string |t(:row_comment_order_type) |
| price  |number |t(:row_comment_price) | 
| qty  |number |t(:row_comment_qty) | 
|time_in_force |string |t(:row_comment_timeInForce)  |
|order_status |string |t(:row_comment_orderStatus)  |
| close_on_trigger |bool |t(:row_comment_closeOnTrigger) |
| orig_order_type |string |t(:row_comment_orig_order_type) |
| prior_x_req_price  |number |t(:row_comment_prior_x_req_price) | 
| op_from |string |t(:row_comment_op_from) |
| remark |string |t(:row_comment_remark) |
| o_req_num |number |t(:row_comment_o_req_num) |
| xreq_type |string |t(:row_comment_xreq_type) |
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

### t(:cancelactive)
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
    "rate_limit_status": 98,
    "rate_limit_reset_ms": 1580885703683,
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
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
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
|price |number |t(:row_comment_price)  |
|qty |number |t(:row_comment_qty)  |
|time_in_force |string |t(:row_comment_timeInForce)  |
|order_status |string |t(:row_comment_orderStatus)  |
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


### t(:cancelallactive)
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
|<a href="#symbol-symbol">symbol</a> |true |string | t(:row_comment_symbol) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|clOrdID |string |t(:row_comment_clOrdID)  |
|user_id |number |t(:row_comment_userID)  |
|symbol|string |t(:row_comment_symbol)    |
|side |string |t(:row_comment_side)  |
|order_type |string |t(:row_comment_order_type)  |
|price |number |t(:row_comment_price)  |
|qty |number |t(:row_comment_qty)  |
|time_in_force |string |t(:row_comment_timeInForce)  |
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
|order_id |true |string |t(:row_comment_orderId) |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol). |
|p_r_qty |false |int |t(:row_comment_pRQty) |
|p_r_price |false |number |t(:row_comment_pRPrice) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|order_id |string |t(:account_row_comment_orderId) |

### t(:queryactive)
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
	"time_now": "1571651135.291930",
	"rate_limit_status": 99, // The remaining number of accesses in one minute
	"rate_limit_reset_ms": 1580885703683,
	"rate_limit": 100
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
|order_id |false |string | t(:misc_row_comment_orderIdNotOrderLinkId)|
|order_link_id |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |number |t(:row_comment_userID)  |
|symbol|string |t(:row_comment_symbol)    |
|side |string |t(:row_comment_side)  |
|order_type |string |t(:row_comment_order_type)  |
|price |number |t(:row_comment_price)  |
|qty |number |t(:row_comment_qty)  |
|time_in_force |string |t(:row_comment_timeInForce)  |
|order_status |string |t(:row_comment_orderStatus)  |
|ext_fields |json |t(:row_comment_ext_fields)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|leaves_value |number |t(:row_comment_leaves_value)  |
|cum_exec_qty |number |t(:linear_resp_field_cum_exec_qty)  |
|reject_reason |string |t(:row_comment_reject_reason)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|order_id |string |t(:row_comment_orderId)  |

## t(:conditionalorders)
### t(:placecond)
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
|<a href="#side-side">side</a> |true |string |t(:row_comment_side)    |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)    |
|<a href="#order-type-order_type">order_type</a> |true |string |t(:row_comment_stopOrderType) |
|<a href="#quantity-qty">qty</a> |true |integer |t(:row_comment_qty) |
|<a href="#price-price">price</a> |false | number |t(:row_comment_stopOrderPrice) |
|base_price |true |number | t(:row_comment_basePrice) |
|stop_px | true | number | t(:row_comment_stopPx) |
|<a href="#time-in-force-time_in_force">time_in_force</a> |true |string |t(:row_comment_timeInForce) |
|<a href="#trigger-price-type-trigger_by">trigger_by</a> | false | string | t(:row_comment_triggerBy)|
|close_on_trigger |false |bool |t(:row_comment_closeOnTrigger)
|order_link_id |false |string |t(:row_comment_orderLinkId) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |number |t(:row_comment_userID)  |
|symbol|string |t(:row_comment_symbol)    |
|side |string |t(:row_comment_side)  |
|order_type |string |t(:row_comment_order_type)  |
|price |number |t(:row_comment_price)  |
|qty |number |t(:row_comment_qty)  |
|time_in_force |string |t(:row_comment_timeInForce)  |
|stop_order_type |string |t(:row_comment_stopOrderType)  |
|trigger_by |string |t(:row_comment_triggerBy)  |
|base_price |number |t(:row_comment_basePrice)  |
|order_status |string |t(:row_comment_orderStatus)  |
|stop_order_type |string |t(:row_comment_stopOrderType)  |
|base_price |number |t(:row_comment_basePrice)  |
|expected_direction |string |t(:row_comment_expected_direction)  |
|trigger_price |number |t(:stop_order_trigger_price)  |
|op_from |string |t(:row_comment_op_from)  |
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


### t(:getcond)
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
|<a href="#symbol-symbol">symbol</a> |false |string |t(:row_comment_symbol). Default `BTCUSD`    |
|<a href="#stop-order-status-stop_order_status">stop_order_status</a> |false |string |t(:row_comment_stopOrderStatus)|
|<a href="#order-order">order</a> |false |string |t(:row_comment_order) |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:row_comment_limit) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |number |t(:row_comment_userID)  |
|stop_order_status|string |t(:row_comment_stopOrderStatus)    |
|symbol|string |t(:row_comment_symbol)    |
|side |string |t(:row_comment_side)  |
|order_type |string |t(:row_comment_order_type)  |
|price |number |t(:row_comment_price)  |
|qty |number |t(:row_comment_qty)  |
|time_in_force |string |t(:row_comment_timeInForce)  |
|stop_order_type |string |t(:row_comment_stopOrderType)  |
|trigger_by |string |t(:row_comment_triggerBy)  |
|base_price |number |t(:row_comment_basePrice)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|stop_px |number |t(:linear_row_comment_stopPx)  |
|stop_order_id |string |t(:row_comment_stopOrderId) |


### t(:cancelcond)
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
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)|
|stop_order_id |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|order_link_id |false |string | t(:misc_row_comment_orderLinkIdNotStopOrderId)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |number |t(:row_comment_userID)  |
|stop_order_status|string |t(:row_comment_stopOrderStatus)    |
|symbol|string |t(:row_comment_symbol)    |
|side |string |t(:row_comment_side)  |
|order_type |string |t(:row_comment_order_type)  |
|price |number |t(:row_comment_price)  |
|qty |number |t(:row_comment_qty)  |
|time_in_force |string |t(:row_comment_timeInForce)  |
|stop_order_type |string |t(:row_comment_stopOrderType)  |
|trigger_by |string |t(:row_comment_triggerBy)  |
|base_price |number |t(:row_comment_basePrice)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|stop_px |number |t(:linear_row_comment_stopPx)  |
|stop_order_id |string |t(:row_comment_stopOrderId) |

### t(:cancelallcond)
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
<code><span id=vpsoCancelAll>/v2/private/stop-order/cancelAll</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpsoCancelAll"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|required|type | comments|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|clOrdID |string |t(:row_comment_clOrdID)  |
|user_id |number |t(:row_comment_userID)  |
|symbol|string |t(:row_comment_symbol)    |
|side |string |t(:row_comment_side)  |
|order_type |string |t(:row_comment_order_type)  |
|price |number |t(:row_comment_price)  |
|qty |number |t(:row_comment_qty)  |
|time_in_force |string |t(:row_comment_timeInForce)  |
|create_type |string |t(:row_comment_create_type)  |
|cancel_type |string |t(:row_comment_cancel_type)  |
|order_status |string |t(:row_comment_orderStatus)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|leaves_value |number |t(:row_comment_leaves_value)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|cross_status |string |t(:row_comment_cross_status)  |
|cross_seq |number |t(:row_comment_cross_seq)  |
|stop_order_type |string |t(:row_comment_stopOrderType)  |
|trigger_by |string |t(:row_comment_triggerBy)  |
|base_price |number |t(:row_comment_basePrice)  |
|expected_direction |string |t(:row_comment_expected_direction)  |


### t(:replacecond)
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
|stop_order_id |true |string |t(:row_comment_stopOrderId) |
|order_id |true |string |t(:comment_abandoned) t(:row_comment_stopOrderId) |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol). |
|p_r_qty |false |int |t(:row_comment_pRQty) |
|p_r_price |false |number |t(:row_comment_pRPrice) |
|p_r_trigger_price |false |number |t(:row_comemnt_pRTriggerPrice) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|stop_order_id |string |t(:row_comment_stopOrderId) |      


### t(:querycond)
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
    "rate_limit_status": 99,
    "rate_limit_reset_ms": 1580885703683,
    "rate_limit": 100
}
```

t(:account_para_queryConditional)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpStopOrder>/v2/private/stop-order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpStopOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
|stop_order_id |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|order_link_id |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |number |t(:row_comment_userID)  |
|symbol|string |t(:row_comment_symbol)    |
|side |string |t(:row_comment_side)  |
|order_type |string |t(:row_comment_order_type)  |
|price |number |t(:row_comment_price)  |
|qty |number |t(:row_comment_qty)  |
|time_in_force |string |t(:row_comment_timeInForce)  |
|order_status |string |t(:row_comment_orderStatus)  |
|ext_fields |json |t(:row_comment_ext_fields)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|leaves_value |number |t(:row_comment_leaves_value)  |
|cum_exec_qty |number |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |number |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |number |t(:linear_resp_field_cum_exec_fee)  |
|reject_reason |string |t(:row_comment_reject_reason)  |
|order_link_id |string |t(:row_comment_orderLinkId)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|order_id |string |t(:row_comment_orderId)  |


## t(:position)
### t(:myposition)
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
        "leverage": "1",  //t(:resp_field_leverage)
        "effective_leverage": "1", // t(:resp_field_effective_leverage)
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
    "rate_limit_reset_ms": 1580885703683,
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
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)    |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |number |t(:row_comment_position_id)  |
|user_id |number |t(:row_comment_userID)  |
|risk_id |number |t(:row_comment_riskId)  |
|symbol|string |t(:row_comment_symbol)    |
|side |string |t(:row_comment_side)  |
|size |number |t(:row_comment_position_size)  |
|position_value |string |t(:row_comment_position_value)  |
|entry_price |string |t(:row_comment_entry_price)  |
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
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |


### t(:changemargin)
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
<code><span id=pChangePositionMargin>/position/change-position-margin</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pChangePositionMargin"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)    |
|margin |true |string |t(:row_comment_margin)  |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|result |number |t(:row_comment_margin_result)  |



### t(:tradingstop)
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

t(:account_para_tradingStop)

<aside class="notice">
t(:account_aside_tradingStop)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oapTradingStop>/open-api/position/trading-stop</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oapTradingStop"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
|take_profit |false |number |t(:account_row_comment_takeProfit) |
|stop_loss |false |number |t(:account_row_comment_stopLoss) |
|trailing_stop |false |number |t(:account_row_comment_trailingStop) |
|new_trailing_active |false |number |t(:account_row_comment_trailingStop_active) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |number |t(:row_comment_position_id)  |
|user_id |number |t(:row_comment_userID)  |
|symbol|string |t(:row_comment_symbol)    |
|side |string |t(:row_comment_side)  |
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
|> trailing_active |string |t(:row_comment_trailing_active)  |
|> sl_trigger_by |string |t(:row_comment_sl_trigger_by)  |
|> v |number |t(:row_comment_v)  |
|> mm |number |t(:row_comment_mm)  |

### t(:getleverage)
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



### t(:changeleverage)
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

t(:account_para_changeLeverage)

<aside class="notice">
t(:account_aside_changeLeverage)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=ulSave>/user/leverage/save</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ulSave"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)    |
|leverage |true |number |t(:row_comment_leverage) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|result |number |t(:row_comment_leverage_result)  |

### t(:usertraderecords)
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
                "symbol": "BTCUSD", //t(:enum_symbol_link)
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
|<a href="#symbol-symbol">symbol</a> |true |string |t(:misc_row_comment_symbolNotOrderId) |
|start_time |false |int |t(:row_comment_startTime_ms) |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:row_comment_limit) |
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
|exec_type |string |t(:enum_exec_type_link)  |
|exec_value |string |t(:row_comment_exec_value)  |
|fee_rate |string |t(:row_comment_fee_rate)  |
|last_liquidity_ind |string |t(:enum_Liquidity_type_link)  |
|leaves_qty |number |t(:row_comment_leaves_qty)  |
|nth_fill |number |t(:row_comment_nth_fill)  |
|order_id |string |t(:row_comment_order_id)  |
|order_link_id |string |t(:row_comment_order_link_id)  |
|order_price |string |t(:row_comment_order_price)  |
|order_qty |string |t(:row_comment_order_qty)  |
|order_type |string |t(:enum_order_type_link)  |
|side |string |t(:enum_side_link)  |
|symbol |string |t(:enum_symbol_link)  |
|user_id |number |t(:row_comment_trailing_stop)  |
|trade_time_ms |number |t(:row_comment_trade_time)  |

         

## t(:risklimit)

### t(:getrisklimit)
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
      "created_at": "2018-11-09T13:53:04.000Z",
      "updated_at": "2018-11-09T13:53:04.000Z"
    },
    {
      "id": 11,
      "coin": "ETH",
      "limit": 3000,
      "maintain_margin": "1.00",
      "starting_margin": "2.00",
      "section": [
        "1",
        "2",
        "3",
        "5",
        "15",
        "30",
        "40",
        "50"
      ],
      "is_lowest_risk": 1,
      "created_at": "2019-01-25T08:31:54.000Z",
      "updated_at": "2019-01-25T08:31:54.000Z"
    }
  ],
  "ext_info": null,
  "time_now": "1577587907.157396",
  "rate_limit_status": 99,
  "rate_limit_reset_ms": 1577587907162,
  "rate_limit": 100
}
```

t(:wallet_para_getRisk)

<aside class="notice">
t(:wallet_aside_getRisk)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oawrlList>/open-api/wallet/risk-limit/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawrlList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |number |t(:row_comment_margin_id)  |
|coin |string |t(:row_comment_coin)  |
|limit |number |t(:row_comment_limit)    |
|maintain_margin |string |t(:row_comment_maintain_margin)  |
|starting_margin |string |t(:row_comment_starting_margin)  |
|section |string |t(:row_comment_section)  |
|is_lowest_risk |number |t(:row_comment_is_lowest_risk)    |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |


### t(:setrisklimit)
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

t(:wallet_para_setRisk)

<aside class="notice">
t(:wallet_aside_getRisk)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oawRiskLimit>/open-api/wallet/risk-limit</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawRiskLimit"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
|risk_id |true |integer |t(:row_comment_riskId) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|position > id |number |t(:row_comment_position_id)  |
|user_id |number |t(:row_comment_userID)  |
|symbol|string |t(:row_comment_symbol)    |
|side |string |t(:row_comment_side)  |
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
|> trailing_active |string |t(:row_comment_trailing_active)  |
|> v |number |t(:row_comment_v)  |
|risk > id |number |t(:row_comment_margin_id)  |
|coin |string |t(:row_comment_coin)  |
|limit |number |t(:row_comment_limit)    |
|maintain_margin |string |t(:row_comment_maintain_margin)  |
|starting_margin |string |t(:row_comment_starting_margin)  |
|section |string |t(:row_comment_section)  |
|is_lowest_risk |number |t(:row_comment_is_lowest_risk)    |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |


## t(:funding)
### t(:fundingRate)
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

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oafPrevFundingRate>/open-api/funding/prev-funding-rate</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oafPrevFundingRate"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)    |

### t(:mylastfundingfee)
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
        "exec_fee": 0.00000002,  // Funding fee.
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

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oafPrevFunding>/open-api/funding/prev-funding</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oafPrevFunding"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)    |



### t(:predictedfunding)
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
<code><span id=oafPredictedFunding>/open-api/funding/predicted-funding</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oafPredictedFunding"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)    |


## t(:key)
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
            "read_only": false
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
<code><span id=oaApiKey>/open-api/api-key</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaApiKey"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |


## t(:lcp)
> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": [
        {
            "date": "2020-04-27",
            "self_ratio": 1.1251,
            "platform_ratio": 0.001254,
            "score": 0.1459
        },
        {
            "date": "2020-04-26",
            "self_ratio": 1.1251,
            "platform_ratio": 0.001254,
            "score": 0.1459
        }
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
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)    |
