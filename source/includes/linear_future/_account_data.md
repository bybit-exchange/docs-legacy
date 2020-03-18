# t(:accountdata)
t(:account_para)

## t(:activeorders)
### t(:placev2active)
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

#### t(:httprequest)
POST
<code><span id=vpoCreate>/v2/private/order/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

#### t(:requestparameters)
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

#### t(:httprequest)
GET
<code><span id=oaoList>/open-api/order/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |false |string |t(:account_row_comment_orderId) |
|order_link_id |false |string |t(:row_comment_orderLinkId) |
|<a href="#symbol-symbol">symbol</a> |false |string |t(:row_comment_symbol). t(:default) `BTCUSD` |
|order |false |string |t(:row_comment_order)  |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:row_comment_limit) |
|<a href="#order-status-order_status-get">order_status</a> |false |string |t(:account_row_comment_orderStatus) |


### t(:cancelv2active)
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

#### t(:httprequest)
POST
<code><span id=vpoCancel>/v2/private/order/cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
|order_id |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|order_link_id |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |



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

#### t(:httprequest)
GET
<code><span id=vpOrder>/v2/private/order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |false |string | t(:misc_row_comment_orderIdNotOrderLinkId)|
|order_link_id |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |



## t(:position)
### t(:linear_position)
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
    "rate_limit_reset_ms": 1580885703683,
    "rate_limit": 120
}
```

t(:account_para_myPosition)

#### t(:httprequest)
GET
<code><span id=pList>/v2/private/position/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
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

#### t(:httprequest)
GET
<code><span id=oaApiKey>/open-api/api-key</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaApiKey"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
