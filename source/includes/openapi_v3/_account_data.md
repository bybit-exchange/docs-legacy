# t(:accountdata)
t(:account_para)

## t(:orders)
### t(:placeorder)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/contract/v3/private/order/create \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","side":"Buy","order_type":"Order","symbol":"BTCUSD","order_type":"Market","qty":"10","time_in_force":"GoodTillCancel","timestamp":{timestamp},"sign":"{sign}"}'

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
<code><span id=vpoCreate>contract/v3/private/order/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_side) |<b>true</b> |string |t(:row_comment_side)    |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)   |
|position_idx |integer |t(:row_comment_position_idx)  |
|t(:row_parameter_order_type) |<b>true</b> |string |t(:row_comment_activeOrderType)   |
|t(:row_parameter_qty) |<b>true</b> |string |t(:row_comment_quantity) |
|t(:row_parameter_price) |false |string |t(:row_comment_resp_price) |
|base_price |false |string | t(:row_comment_basePrice) |
|trigger_price |false |string | t(:) |
|t(:row_parameter_time_in_force) |<b>true</b> |string |t(:row_comment_timeInForce) |
|close_on_trigger |false |bool |t(:row_comment_closeOnTrigger)
|order_link_id |false |string |t(:row_comment_orderLinkId) |
|take_profit |false |string |t(:row_comment_takeProfit) |
|stop_loss |false |string |t(:row_comment_stopLoss) |
|t(:row_parameter_tp_trigger_by) |false |string |t(:account_row_comment_tp_trigger_by) |
|t(:row_parameter_sl_trigger_by) |false |string |t(:account_row_comment_sl_trigger_by) |
|reduce_only |false |bool |t(:row_comment_reduceOnly) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| order_id |string |t(:row_comment_orderId) |

### t(:getorderlist)
> t(:codequote_curlExample)

```console
curl "https://api.bybit.com/contract/v3/private/order/list?api_key={api_key}&timestamp={timestamp}&sign={sign}&symbol=BTCUSD"
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
                "order_status": "Cancelled",
                "symbol": "BTCUSD",
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
<code><span id=vpoList>/contract/v3/private/order/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|t(:row_parameter_order_status) |false |string |t(:account_row_comment_orderStatus) |
|t(:row_parameter_order_filter) |false |string |t(:row_comment_orderFilter)   |
|direction |false |string |t(:row_comment_cursor_direction) |
|limit |false |integer |t(:row_comment_limit) |
|cursor |false |string |t(:row_comment_cursor) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|data > user_id |integer |t(:row_comment_userID) |
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
|data > take_profit |string |t(:row_comment_take_profit)  |
|data > stop_loss |string |t(:row_comment_stop_loss)  |
|data > t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by) |
|data > t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by) |
|cursor |string |t(:row_comment_resp_cursor) |


### t(:cancelorder)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/contract/v3/private/order/cancel \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","order_id":"","order_filter":"Order","timestamp":{timestamp},"sign":"{sign}"}'
```


> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "order_id": "3bd1844f-f3c0-4e10-8c25-10fea03763f6",
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
<code><span id=vpoCancel>/contract/v3/private/order/cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|t(:row_parameter_order_filter) |<b>true</b>|string |t(:row_comment_orderFilter)   |
|order_id |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|order_link_id |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|order_id |string |t(:account_row_comment_orderId) |



## t(:cancelbatch)
> t(:codequote_curlExample)
```console
curl https://api.bybit.com/contract/v3/private/order/cancelAll \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","timestamp":{timestamp},"sign":"{sign}"}'
```



### t(:cancelall)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/contract/v3/private/order/cancelAll \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","timestamp":{timestamp},"sign":"{sign}"}'
```


> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,      
    "ret_msg": "OK",    
    "ext_code": "",     
    "ext_info": "",
    "result": {
            "order_ids": {
                "item": "89a38056-80f1-45b2-89d3-4d8e3a203a79",
             },  
        },
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
<code><span id=vpoCancelAll>contract/v3/private/order/cancelAll</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancelAll"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string | t(:row_comment_symbol) |
|t(:row_parameter_order_filter) |false|string |t(:row_comment_orderFilter)   |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|order_ids |string |t(:row_comment_order_ids)  |

### t(:replaceorder)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/contract/v3/private/order/replace \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","order_id":"","timestamp":{timestamp},"sign":"{sign}"}'
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
<code><span id=vpoReplace>/contract/v3/private/order/replace</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoReplace"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|order_link_id |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|t(:row_parameter_order_filter) |<b>true</b> |string |t(:row_comment_orderFilter)   |
|p_r_trigger_price |false |string |t(:row_comment_r_trigger_price) |
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

### t(:queryactiveorder)
> t(:codequote_curlExample)

```console
curl "https://api.bybit.com/contract/v3/private/active-orders?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}order_id={order_id}&sign={sign}"
```


> t(:codequote_responseExample)

```javascript

//t(:resp_field_order_list)
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": [
        {
            "user_id": 100228,
            "symbol": "BTCUSD",
            "side": "Sell",
            "order_type": "Limit",
            "price": "17740",
            "qty": "10",
            "time_in_force": "GoodTillCancel",
            "order_status": "New",
            "last_exec_time": "1608193181.827761",
            "leaves_qty": "10",
            "leaves_value": "0.00056369",
            "cum_exec_qty": "0",
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
            "symbol": "BTCUSD",
            "side": "Sell",
            "order_type": "Limit",
            "price": "17740",
            "qty": "10",
            "time_in_force": "GoodTillCancel",
            "order_status": "New",
            "last_exec_time": "1608193178.955412",
            "leaves_qty": "10",
            "leaves_value": "0.00056369",
            "cum_exec_qty": "0",
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
<code><span id=vpOrder>/contract/v3/private/active-orders</span></code>
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
|symbol|string |t(:row_comment_symbol)    |
|side |string |t(:row_comment_side)  |
|order_type |string |t(:row_comment_order_type)  |
|price |string |t(:row_comment_resp_price)  |
|qty |string |t(:row_response_comment_qty)  |
|time_in_force |string |t(:row_comment_timeInForce)  |
|order_status |string |t(:row_comment_orderStatus)  |
|leaves_qty |string |t(:row_comment_leaves_qty)  |
|leaves_value |string |t(:row_comment_leaves_value)  |
|cum_exec_qty |string |t(:linear_resp_field_cum_exec_qty)  |
|cum_exec_value |string |t(:linear_resp_field_cum_exec_value)  |
|cum_exec_fee |order_link_id |string |t(:linear_resp_field_cum_exec_fee)  |
|reject_reason |string |t(:row_comment_reject_reason)  |
|cancel_type |string |t(:row_comment_cancel_type)  |
|order_link_id |string |t(:row_response_comment_orderLinkId)  |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|order_id |string |t(:row_comment_order_id)  |
|take_profit |string |t(:row_comment_take_profit)  |
|stop_loss |string |t(:row_comment_stop_loss)  |
|t(:row_parameter_tp_trigger_by) |string |t(:account_row_comment_tp_trigger_by)  |
|t(:row_parameter_sl_trigger_by) |string |t(:account_row_comment_sl_trigger_by)  |




## t(:position)
### t(:myposition)
> t(:codequote_curlExample)

```console
curl "https://api.bybit.com/contract/v3/private/position/list?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}&sign={sign}"
```

> t(:codequote_responseExample)

```javascript

//t(:resp_field_position_list)
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": [
        {
            "is_valid": true, //t(:resp_field_position_list_valid)
            "data": { //t(:resp_field_position_list_data)
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
            "is_valid": true, //t(:resp_field_position_list_valid)
            "data": { //t(:resp_field_position_list_data)
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
<code><span id=pList>/contract/v3/private/position/list</span></code>
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
|unrealised_pnl |string |t(:row_comment_unrealised_pnl)  |
|cum_realised_pnl |string |t(:row_comment_cum_realised_pnl)  |
|position_seq |number |t(:row_comment_position_seq)  |
|created_at |string |t(:row_comment_created_at_position)  |
|t(:row_parameter_tp_sl_mode) |string |t(:linear_resp_tp_sl_mode)  |


### t(:changemargin)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/contract/v3/private/position/change-position-margin \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD",margin:"10","timestamp":{timestamp},"sign":"{sign}"}'
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": ,
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
<code><span id=pChangePositionMarginNew>/contract/v3/private/position/change-position-margin</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pChangePositionMarginNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|margin |<b>true</b> |string |t(:row_comment_margin)  |
|position_idx |false |integer |t(:row_comment_position_idx)  |




### t(:tradingstop)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/contract/v3/private/position/trading-stop \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","stop_loss":7000,"timestamp":{timestamp},"sign":"{sign}"}'
```


> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": ,
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
<code><span id=oapTradingStopNew>/contract/v3/private/position/trading-stop</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oapTradingStopNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|take_profit |false |string |t(:account_row_comment_takeProfit) |
|stop_loss |false |string |t(:account_row_comment_stopLoss) |
|trailing_stop |false |string |t(:account_row_comment_trailingStop) |
|t(:row_parameter_tp_trigger_by) | false | string | t(:account_row_comment_tp_trigger_by)
|t(:row_parameter_sl_trigger_by) | false | string | t(:account_row_comment_sl_trigger_by)
|new_trailing_active |false |string |t(:account_row_comment_trailingStop_active) |
|sl_size |false |string |t(:row_comment_sl_size) |
|tp_size |false |string |t(:row_comment_tp_size) |


### t(:setleverage)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/contract/v3/private/position/leverage/save \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","buy_leverage":14,"sell_leverage":14,"timestamp":{timestamp},"sign":"{sign}"}'
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
<code><span id=ulSaveNew>/contract/v3/private/position/leverage/save</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ulSaveNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|buy_leverage |<b>true</b> |number |t(:futures_row_comment_leverage) |
|sell_leverage |<b>true</b> |number |t(:futures_row_comment_leverage) |


### t(:usertraderecords)
> t(:codequote_curlExample)

```console
curl "https://api.bybit.com/contract/v3/private/execution/list?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}&sign={sign}"
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
<code><span id=vpeList>/contract/v3/private/execution/list</span></code>
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
curl "https://api.bybit.com/contract/v3/private/position/closed-pnl/list?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}&sign={sign}"
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
<code><span id=pltcList>/contract/v3/private/position/closed-pnl/list</span></code>
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
|user_id |number |t(:row_comment_userID)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|order_id |string |t(:row_comment_order_id) |
|t(:row_parameter_side) |string |t(:row_response_closedPnlSide)  |
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


### t(:switchmode)
> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {},
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
<code><span id=vptSwitchMode>/contract/v3/private/position/tpsl/switch-mode</span></code>
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
curl https://api.bybit.com/contract/v3/private/position/switch-isolated \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD", "is_isolated":true,"buy_leverage":10,"sell_leverage":20, "timestamp":{timestamp},"sign":"{sign}"}'
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
<code><span id=ulSwitchIsolated>/contract/v3/private/position/switch-isolated</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ulSwitchIsolated"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|is_isolated |<b>true</b> |bool |t(:futures_row_comment_switch_isolated)  |
|buy_leverage |<b>true</b> |string |t(:inverse_row_comment_leverage)  |
|sell_leverage |<b>true</b> |string |t(:inverse_row_comment_leverage)  |



## t(:risklimit)
### t(:getrisklimit)
> t(:codequote_curlExample)

```console
curl "https://api.bybit.com/contract/v3/public/risk-limit/list?symbol=BTCUSD"
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Wallet.Wallet_getRiskLimit().result())
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
t(:account_aside_getRisk)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oawrlList>/contract/v3/public/risk-limit/list</span></code>
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
|starting_margin |number |t(:row_comment_starting_margin)  |
|section |string |t(:row_comment_section)  |
|is_lowest_risk |number |t(:row_comment_is_lowest_risk)    |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|max_leverage |string |t(:row_comment_max_leverage)  |
### t(:setrisklimit)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/contract/v3/private/position/set-risk-limit \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","risk_id":2,"timestamp":{timestamp},"sign":"{sign}"}'
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
<code><span id=oawrlList>/contract/v3/private/position/risk-limit</span></code>
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


### t(:mylastfundingfee)
> t(:codequote_curlExample)

```console
curl "https://api.bybit.com/contract/v3/private/funding/personal-prev-funding?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}&sign={sign}"
```

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
<code><span id=oafPrevFundingNew>/contract/v3/private/funding/personal-prev-funding</span></code>
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

### t(:fundingRate)
> t(:codequote_curlExample)

```console
curl "https://api.bybit.com/contract/v3/public/funding/prev-funding-rate?symbol=BTCUSD"
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

t(:market_para_fundingRate)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oafPrevFundingRateNew>/contract/v3/public/funding/prev-funding-rate</span></code>
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



## t(:lcp)
> t(:codequote_curlExample)

```console
curl "https://api.bybit.com/contract/v3/private/account/lcp?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}&sign={sign}"
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
            "score": "0.1459"
        },
        {
            "date": "2020-04-26",
            "score": "0.1459"
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
<code><span id=oaApiLcp>/contract/v3/private/account/lcp</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaApiLcp"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|date |string |t(:row_comment_lcp_date)    |
|score |string |t(:row_comment_lcp_score)  |
