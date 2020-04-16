# t(:accountdata)
t(:account_para)

## t(:activeorders)
### t(:linear_place_active)
> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "order_id":"bd1844f-f3c0-4e10-8c25-10fea03763f6",
        "user_id": 1,
        "symbol": "BTCUSDT",
        "side": "Sell",
        "order_type": "Limit",
        "price": 8083,
        "qty": 10,
        "time_in_force": "GoodTillCancel",
        "order_status": "New",
        "last_exec_price": 8083,    //t(:linear_resp_field_last_exec_price)
        "cum_exec_qty": 0,          //t(:linear_resp_field_cum_exec_qty)
        "cum_exec_value": 0,        //t(:linear_resp_field_cum_exec_value)
        "cum_exec_fee": 0,          //t(:linear_resp_field_cum_exec_fee)
        "reduce_only": false,       //t(:linear_resp_field_reduce_only)
        "order_link_id": "",
        "created_time": "2019-10-21T07:28:19.396246Z",
        "updated_time": "2019-10-21T07:28:19.396246Z",
    },
    "time_now": "1575111823.458705",
    "rate_limit_status": 98,
    "rate_limit_reset_ms": 1580885703683,
    "rate_limit": 100
}
```

t(:linear_account_para_placeActive)

#### t(:httprequest)
POST
<code><span id=vpoCreate>/private/linear/order/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#side-side">side</a> |true |string |t(:row_comment_side)    |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)   |
|<a href="#order-type-order_type">order_type</a> |true |string |t(:row_comment_activeOrderType)   |
|<a href="#quantity-qty">qty</a> |true |number |t(:linear_row_comment_qty) |
|<a href="#price-price">price</a> |false |number |t(:row_comment_price) |
|<a href="#time-in-force-time_in_force">time_in_force</a> |true |string |t(:row_comment_timeInForce) |
|take_profit |false |number |t(:row_comment_takeProfit) |
|stop_loss |false |number |t(:row_comment_stopLoss) |
|tp_trigger_by |false |string |t(:row_comment_triggerBy) |
|sl_trigger_by |false |string |t(:row_comment_triggerBy) |
|reduce_only |true |bool |t(:linear_row_comment_reduceOnly) |
|close_on_trigger |true |bool |t(:linear_row_comment_closeOnTrigger)
|order_link_id |false |string |t(:row_comment_orderLinkId) |


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
                "order_id":"bd1844f-f3c0-4e10-8c25-10fea03763f6",
                "user_id": 1,
                "symbol": "BTCUSDT",
                "side": "Sell",
                "order_type": "Limit",
                "price": 8083,
                "qty": 10,
                "time_in_force": "GoodTillCancel",
                "order_status": "New",
                "last_exec_price": 8083,
                "cum_exec_qty": 0,
                "cum_exec_value": 0,
                "cum_exec_fee": 0,
                "order_link_id": "",
                "reduce_only": false,
                "created_time": "2019-10-21T07:28:19.396246Z",
                "updated_time": "2019-10-21T07:28:19.396246Z",
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

#### t(:httprequest)
GET
<code><span id=oaoList>/private/linear/order/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |false |string |t(:account_row_comment_orderId) |
|order_link_id |false |string |t(:row_comment_orderLinkId) |
|<a href="#symbol-symbol">symbol</a> |false |string |t(:row_comment_symbol). t(:default) `BTCUSDT` |
|order |false |string |t(:row_comment_order)  |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:row_comment_limit) |
|<a href="#order-status-order_status-get">order_status</a> |false |string |t(:linear_account_row_comment_orderStatus) |


### t(:linear_cancel_active)
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

#### t(:httprequest)
POST
<code><span id=vpoCancel>/private/linear/order/cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
|order_id |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|order_link_id |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |



### t(:cancelallactive)
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

#### t(:httprequest)
POST
<code><span id=vpoCancelAll>/private/linear/order/cancel-all</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancelAll"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string | t(:row_comment_symbol) |



### t(:queryactive)
> t(:codequote_responseExample)

```javascript
{
	"ret_code": 0,
	"ret_msg": "OK",
	"ext_code": "",
	"ext_info": "",
	"result": {
	    "order_id":"bd1844f-f3c0-4e10-8c25-10fea03763f6",
        "user_id": 1,
        "symbol": "BTCUSDT",
        "side": "Sell",
        "order_type": "Limit",
        "price": 8083,
        "qty": 10,
        "time_in_force": "GoodTillCancel",
        "order_status": "New",
        "last_exec_price": 8083,
        "cum_exec_qty": 0,
        "cum_exec_value": 0,
        "cum_exec_fee": 0,
        "reduce_only": false,
        "order_link_id": "",
        "created_time": "2019-10-21T07:28:19.396246Z",
        "updated_time": "2019-10-21T07:28:19.396246Z",
	},
	"time_now": "1571651135.291930",
	"rate_limit_status": 99, // The remaining number of accesses in one minute
	"rate_limit_reset_ms": 1580885703683,
	"rate_limit": 100
}
```


t(:account_para_queryActive)

#### t(:httprequest)
GET
<code><span id=vpOrder>/private/linear/order/search</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |false |string | t(:misc_row_comment_orderIdNotOrderLinkId)|
|order_link_id |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |


















## t(:conditionalorders)
### t(:placecond)
> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
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
       "created_at": "2019-10-21T07:28:19.396246Z",
       "updated_at": "2019-10-21T07:28:19.396246Z",
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

#### t(:httprequest)
POST
<code><span id=oasoCreate>/private/linear/stop-order/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oasoCreate"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#side-side">side</a> |true |string |t(:row_comment_side)    |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)    |
|<a href="#order-type-order_type">order_type</a> |true |string |t(:row_comment_stopOrderType) |
|<a href="#quantity-qty">qty</a> |true |integer |t(:row_comment_qty) |
|<a href="#price-price">price</a> |false | number |t(:row_comment_stopOrderPrice) |
|base_price |true |number | t(:linear_row_comment_basePrice) |
|stop_px | true | number | t(:linear_row_comment_stopPx) |
|<a href="#time-in-force-time_in_force">time_in_force</a> |true |string |t(:row_comment_timeInForce) |
|<a href="#trigger-price-type-trigger_by">trigger_by</a> | false | string | t(:row_comment_triggerBy)|
|close_on_trigger |true |bool |t(:row_comment_closeOnTrigger)
|order_link_id |false |string |t(:row_comment_orderLinkId) |
|reduce_only |true |bool |t(:linear_row_comment_reduceOnly) |


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
                 "created_at": "2019-10-21T07:28:19.396246Z",
                 "updated_at": "2019-10-21T07:28:19.396246Z",
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
                 "created_at": "2019-10-21T07:28:19.396246Z",
                 "updated_at": "2019-10-21T07:28:19.396246Z",
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

#### t(:httprequest)
GET
<code><span id=oasoList>/private/linear/stop-order/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oasoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|stop_order_id |false |string |t(:row_comment_stopOrderId) |
|order_link_id |false |string |t(:row_comment_orderLinkId)|
|<a href="#symbol-symbol">symbol</a> |false |string |t(:row_comment_symbol). Default `BTCUSDT`    |
|<a href="#stop-order-status-stop_order_status">stop_order_status</a> |false |string |t(:row_comment_stopOrderStatus)|
|order |false |string |t(:row_comment_order) |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:row_comment_limit) |


### t(:cancelcond)
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

#### t(:httprequest)
POST
<code><span id=oasoCancel>/private/linear/stop-order/cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oasoCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|required|type | comments|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)|
|stop_order_id |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|order_link_id |false |string | t(:misc_row_comment_orderLinkIdNotStopOrderId)|
|<a href="#symbol-symbol">symbol</a> |false |string |t(:row_comment_symbol). Default `BTCUSDT`    |


### t(:cancelallcond)
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
t(:account_aside_cancelAllCond)
</aside>

#### t(:httprequest)
POST
<code><span id=vpsoCancelAll>/private/linear/stop-order/cancel-all</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpsoCancelAll"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|required|type | comments|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)|



### t(:querycond)
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
        "created_at": "2019-10-21T07:28:19.396246Z",
        "updated_at": "2019-10-21T07:28:19.396246Z",
    },
    "time_now": "1577476584.386958",
    "rate_limit_status": 99,
    "rate_limit_reset_ms": 1580885703683,
    "rate_limit": 100
}
```

t(:account_para_queryConditional)

#### t(:httprequest)
GET
<code><span id=vpStopOrder>/private/linear/stop-order/search</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpStopOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
|stop_order_id |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|order_link_id |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |




















## t(:position)
### t(:linear_position)
> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": [
       {
               "user_id":100004,
               "symbol":"BTCUSDT",
               "side":"Buy",
               "size":0,
               "position_value":0,      //t(:linear_resp_field_position_value)
               "entry_price":0,         //t(:linear_resp_field_entry_price)
               "liq_price":1,           //t(:linear_resp_field_liq_price)
               "bust_price":100,        //t(:linear_resp_field_bust_price)
               "leverage":0,
               "position_margin":0,     //t(:linear_resp_field_position_margin)
               "occ_closing_fee":0,     //t(:linear_resp_field_occ_closing_fee)
               "realised_pnl":0,        //t(:linear_resp_field_realised_pnl)
               "cum_realised_pnl":0,    //t(:linear_resp_field_cum_realised_pnl)
               "free_qty": 30,          //t(:linear_resp_field_free_qty)
           },
           {
               "user_id":100004,
               "symbol":"BTCUSDT",
               "side":"Buy",
               "size":0,
               "position_value":0,
               "entry_price":0,
               "liq_price":1,
               "bust_price":100,
               "leverage":0,
               "position_margin":0,
               "occ_closing_fee":0,
               "realised_pnl":0,
               "cum_realised_pnl":0,
               "free_qty": 30,
           }
    ],
    "time_now": "1577480599.097287",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1580885703683,
    "rate_limit": 120
}
```

t(:account_para_myPosition)

#### t(:httprequest)
GET
<code><span id=pList>/private/linear/position/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)    |



### t(:linear_set_auto_add_margin)
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

#### t(:httprequest)
POST
<code><span id=pSetAutoAddMargin>/private/linear/position/set-auto-add-margin</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pSetAutoAddMargin"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)    |
|<a href="#side-side">side</a> |true |string |t(:row_comment_side)    |
|auto_add_margin |true |bool |t(:linear_row_comment_set_auto_margin)  |


### t(:linear_set_leverage)
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

#### t(:httprequest)
POST
<code><span id=pSetLeverage>/private/linear/position/set-leverage</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pSetLeverage"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)    |
|buy_leverage |true |number |t(:linear_row_comment_leverage)  |
|sell_leverage |true |number |t(:linear_row_comment_leverage)  |




### t(:linear_switch_isolated)
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













#### t(:httprequest)
POST
<code><span id=pSwitchIsolated>/private/linear/position/switch-isolated</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pSwitchIsolated"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)    |
|is_isolated |true |bool |t(:linear_row_comment_switch_isolated)  |
|buy_leverage |true |number |t(:linear_row_comment_leverage)  |
|sell_leverage |true |number |t(:linear_row_comment_leverage)  |


### t(:tradingstop)
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

t(:account_para_tradingStop)

<aside class="notice">
t(:account_aside_tradingStop)
</aside>

#### t(:httprequest)
POST
<code><span id=pSetTpSlTs>/private/linear/position/trading-stop</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pSetTpSlTs"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
|<a href="#side-side">side</a> |true |string |t(:row_comment_side)    |
|take_profit |false |string |t(:account_row_comment_takeProfit) |
|stop_loss |false |string |t(:account_row_comment_stopLoss) |
|trailing_stop |false |string |t(:account_row_comment_trailingStop) |
|tp_trigger_by |false |string |t(:row_comment_triggerBy) |
|sl_trigger_by |false |string |t(:row_comment_triggerBy) |

















### t(:linear_add_margin)
> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "PositionListResult": {
            "user_id": 160815,
            "symbol": "BTCUSDT",
            "side": "Buy",
            "size": 3.14,
            "position_value": 18843.14,
            "entry_price": 6001,
            "liq_price": 5428,
            "bust_price": 5398,
            "leverage": 10,
            "position_margin": 1907.0331195,
            "occ_closing_fee": 12.71229,
            "realised_pnl": 3052.20905294,
            "cum_realised_pnl": 75628.40815795,
            "free_qty": 0
        },
        "wallet_balance": 68738.01696765,
        "available_balance": 66830.98384815
    },
     "time_now": "1577480599.097287",
     "rate_limit_status": 119,
     "rate_limit_reset_ms": 1580885703683,
     "rate_limit": 120
}
```

t(:linear_account_para_addMargin)


#### t(:httprequest)
POST
<code><span id=pAddMargin>/private/linear/position/add-margin</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pAddMargin"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
|<a href="#side-side">side</a> |true |string |t(:row_comment_side)    |
|margin |true |number |t(:linear_account_row_comment_margin) |














### t(:usertraderecords)
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
                    "order_id": "5195243c-e613-4974-a97e-e1d1eaf51b4c",
                    "side": "Buy",
                    "symbol": "BTCUSDT",
                    "exec_id": "2bc03d9e-bc46-54bf-a319-fe6931c84bc2",
                    "price": 6100,
                    "order_qty": 0.01,
                    "exec_type": "Trade",
                    "exec_qty": 0.01,
                    "exec_fee": 0.0450075,
                    "trade_time": 1577480599,           //t(:comment_abandoned)
                    "trade_time_ms": 1577480599000
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

#### t(:httprequest)
GET
<code><span id=vpeList>/private/linear/trade/execution/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpeList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:misc_row_comment_symbolNotOrderId) |
|start_time |false |int |t(:row_comment_startTime) |
|end_time |false |int |t(:row_comment_endTime) |
|<a href="#exec-type-exec_type">exec_type</a> |false |string |t(:linear_exec_type) |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:linear_row_comment_limit) |




















### t(:closedprofitandloss)
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
                 "closed_size": 0.5,        //t(:linear_resp_field_closed_size)
                 "cum_entry_value": 3000,   //t(:linear_resp_field_cum_entry_value)
                 "avg_entry_price": 6000,   //t(:linear_resp_field_avg_entry_price)
                 "cum_exit_value": 3000.5,  //t(:linear_resp_field_cum_exit_value)
                 "avg_exit_price": 6001,    //t(:linear_resp_field_avg_exit_price)
                 "closed_pnl": -5.000375,   //t(:linear_resp_field_closed_pnl)
                 "fill_count": 1,           //t(:linear_resp_field_fill_count)
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

<aside class="notice">
t(:wallet_aside_tradeRecords)
</aside>

#### t(:httprequest_wallet)
GET
<code><span id=pltcList>/private/linear/trade/closed-pnl/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pltcList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters_wallet)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:misc_row_comment_symbolNotOrderId) |
|start_time |false |int |t(:row_comment_startTime) |
|end_time |false |int |t(:row_comment_endTime) |
|<a href="#exec-type-exec_type">exec_type</a> |false |string |t(:linear_exec_type) |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:linear_row_comment_limit) |

















## t(:risklimit)

### t(:getrisklimit)
> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": [
        {
            "id": 1,
            "symbol": "BTCUSDT",
            "limit": 1000000,
            "maintain_margin": 0.005,
            "starting_margin": 0.01,
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
            "created_at": "2020-01-06T09:45:28.000Z",
            "updated_at": "2020-01-06T09:45:28.000Z"
        },
        {
            "id": 2,
            "symbol": "BTCUSDT",
            "limit": 1500000,
            "maintain_margin": 0.01,
            "starting_margin": 0.015,
            "section": [
                "1",
                "2",
                "3",
                "5",
                "10",
                "25",
                "50",
                "66"
            ],
            "is_lowest_risk": 0,
            "created_at": "2020-01-06T09:45:28.000Z",
            "updated_at": "2020-01-06T09:45:28.000Z"
        },
        {
            "id": 3,
            "symbol": "BTCUSDT",
            "limit": 2000000,
            "maintain_margin": 0.015,
            "starting_margin": 0.02,
            "section": [
                "1",
                "2",
                "3",
                "5",
                "10",
                "25",
                "33",
                "50"
            ],
            "is_lowest_risk": 0,
            "created_at": "2020-01-06T09:45:28.000Z",
            "updated_at": "2020-01-06T09:45:28.000Z"
        },
        {
            "id": 4,
            "symbol": "BTCUSDT",
            "limit": 2500000,
            "maintain_margin": 0.02,
            "starting_margin": 0.025,
            "section": [
                "1",
                "2",
                "3",
                "5",
                "10",
                "25",
                "33",
                "40"
            ],
            "is_lowest_risk": 0,
            "created_at": "2020-01-06T09:45:28.000Z",
            "updated_at": "2020-01-06T09:45:28.000Z"
        },
        {
            "id": 5,
            "symbol": "BTCUSDT",
            "limit": 3000000,
            "maintain_margin": 0.025,
            "starting_margin": 0.03,
            "section": [
                "1",
                "2",
                "3",
                "5",
                "10",
                "15",
                "25",
                "33"
            ],
            "is_lowest_risk": 0,
            "created_at": "2020-01-06T09:45:28.000Z",
            "updated_at": "2020-01-06T09:45:28.000Z"
        },
        {
            "id": 6,
            "symbol": "BTCUSDT",
            "limit": 3500000,
            "maintain_margin": 0.03,
            "starting_margin": 0.035,
            "section": [
                "1",
                "2",
                "3",
                "5",
                "10",
                "15",
                "20",
                "28"
            ],
            "is_lowest_risk": 0,
            "created_at": "2020-01-06T09:45:28.000Z",
            "updated_at": "2020-01-06T09:45:28.000Z"
        },
        {
            "id": 7,
            "symbol": "BTCUSDT",
            "limit": 4000000,
            "maintain_margin": 0.035,
            "starting_margin": 0.04,
            "section": [
                "1",
                "2",
                "3",
                "5",
                "10",
                "15",
                "20",
                "25"
            ],
            "is_lowest_risk": 0,
            "created_at": "2020-01-06T09:45:28.000Z",
            "updated_at": "2020-01-06T09:45:28.000Z"
        },
        {
            "id": 8,
            "symbol": "BTCUSDT",
            "limit": 4500000,
            "maintain_margin": 0.04,
            "starting_margin": 0.045,
            "section": [
                "1",
                "2",
                "3",
                "5",
                "10",
                "15",
                "20",
                "22"
            ],
            "is_lowest_risk": 0,
            "created_at": "2020-01-06T09:45:28.000Z",
            "updated_at": "2020-01-06T09:45:28.000Z"
        },
        {
            "id": 9,
            "symbol": "BTCUSDT",
            "limit": 5000000,
            "maintain_margin": 0.045,
            "starting_margin": 0.05,
            "section": [
                "1",
                "2",
                "3",
                "4",
                "5",
                "10",
                "15",
                "20"
            ],
            "is_lowest_risk": 0,
            "created_at": "2020-01-06T09:45:28.000Z",
            "updated_at": "2020-01-06T09:45:28.000Z"
        },
        {
            "id": 10,
            "symbol": "BTCUSDT",
            "limit": 5500000,
            "maintain_margin": 0.05,
            "starting_margin": 0.055,
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
            "created_at": "2020-01-06T09:45:29.000Z",
            "updated_at": "2020-01-06T09:45:29.000Z"
        }
    ],
    "time_now": "1586780586.850288"
}
```

t(:wallet_para_getRisk)

<aside class="notice">
t(:wallet_aside_getRisk)
</aside>

#### t(:httprequest1)
GET
<code><span id=oawrlList>/public/linear/risk-limit</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawrlList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters1)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |


























## t(:funding)
### t(:linear_prve_funding)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/private/linear/funding/prev-funding?symbol=BTCUSDT
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

t(:market_para_records)

#### t(:httprequest)
GET
<code><span id=vpPreFunding>/private/linear/funding/prev-funding</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpPreFunding"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |









### t(:predictedfunding)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/private/linear/funding/predicted-funding?symbol=BTCUSDT
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

#### t(:httprequest)
GET
<code><span id=vpPreFunding>/private/linear/funding/predicted-funding</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpPreFunding"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
















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

#### t(:httprequest)
GET
<code><span id=oaApiKey>/open-api/api-key</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaApiKey"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
