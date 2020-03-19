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
        "symbol": "BTCUSD",
        "side": "Sell",
        "order_type": "Limit",
        "price": "8083",
        "qty": 10,
        "time_in_force": "GoodTillCancel",
        "order_status": "New",
        "last_exec_time": "2019-10-21T07:28:19.396246Z",
        "last_exec_price": "8083",
        "leaves_qty": 10,
        "cum_exec_qty": 0,
        "cum_exec_value": 0,
        "cum_exec_fee": 0,
        "reject_reason": "",
        "order_link_id": "",
        "created_at": "2019-10-21T07:28:19.396246Z",
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
|<a href="#quantity-qty">qty</a> |true |integer |t(:row_comment_qty) |
|<a href="#price-price">price</a> |false |number |t(:row_comment_price) |
|<a href="#time-in-force-time_in_force">time_in_force</a> |true |string |t(:row_comment_timeInForce) |
|take_profit |false |number |t(:row_comment_takeProfit) |
|stop_loss |false |number |t(:row_comment_stopLoss) |
|tp_trigger_by |false |string |t(:row_comment_triggerBy) |
|sl_trigger_by |false |string |t(:row_comment_triggerBy) |
|reduce_only |false |bool |t(:linear_row_comment_reduceOnly) |
|close_on_trigger |false |bool |t(:linear_row_comment_closeOnTrigger)
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
               "symbol": "BTCUSD",
               "side": "Sell",
               "order_type": "Limit",
               "price": "8083",
               "qty": 10,
               "time_in_force": "GoodTillCancel",
               "order_status": "New",
               "last_exec_time": "2019-10-21T07:28:19.396246Z",
               "last_exec_price": "8083",
               "leaves_qty": 10,
               "cum_exec_qty": 0,
               "cum_exec_value": 0,
               "cum_exec_fee": 0,
               "reject_reason": "",
               "order_link_id": "",
               "created_at": "2019-10-21T07:28:19.396246Z",
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
|<a href="#symbol-symbol">symbol</a> |false |string |t(:row_comment_symbol). t(:default) `BTCUSD` |
|order |false |string |t(:row_comment_order)  |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:row_comment_limit) |
|<a href="#order-status-order_status-get">order_status</a> |false |string |t(:account_row_comment_orderStatus) |


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
        "user_id": 1,
        "symbol": "BTCUSD",
        "side": "Sell",
        "order_type": "Limit",
        "price": "8083",
        "qty": 10,
        "time_in_force": "GoodTillCancel",
        "order_status": "New",
        "last_exec_time": "2019-10-21T07:28:19.396246Z",
        "last_exec_price": "8083"
        "leaves_qty": 10,
        "cum_exec_qty": 0,
        "cum_exec_value": 0,
        "cum_exec_fee": 0,
        "reject_reason": "",
        "order_link_id": "",
        "created_at": "2019-10-21T07:28:19.396246Z",
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
<code><span id=vpoCancelAll>private/linear/order/cancel-all</span></code>
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
		"symbol": "BTCUSD",
		"side": "Sell",
		"order_type": "Limit",
		"price": "8083",
		"qty": 10,
		"time_in_force": "GoodTillCancel",
		"order_status": "New",
		"last_exec_time": "2019-10-21T07:28:19.396246Z",
		"last_exec_price": "8083"
		"leaves_qty": 10,
		"cum_exec_qty": 0,
		"cum_exec_value": 0,
		"cum_exec_fee": 0,
		"reject_reason": "",
		"order_link_id": "",
		"created_at": "2019-10-21T07:28:19.396246Z",
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
                   "userId":100004,
                   "symbol":"BTCUSDT",
                   "side":"Buy",
                   "size":0,
                   "positionValue":0,
                   "entryPrice":0,
                   "riskId":1,
                   "leverage":100,
                   "positionMargin":0,
                   "liqPrice":0,
                   "bustPrice":0,
                   "occClosingFee":0,
                   "takeProfit":0,
                   "tpTriggerBy":"LastPriceOld",
                   "slTriggerBy":"LastPriceOld",
                   "stopLoss":0,
                   "trailingStop":0,
                   "positionStatus":"Normal",
                   "deleverageIndicator":0,
                   "todayRealisedPnl":0,
                   "cumRealisedPnl":0,
                   "isAutoAddMargin":false,
                   "freeQty":0,
                   "adlRankIndicator":0,
                   "unRealisedPnlByMp":0,
                   "unRealisedPnlByLp":0,
                   "unRealisedPnl":0,
                   "isIsolated":false,
                   "openValueLimit":1000000,
                   "extraAddedMargin":0,
                   "availableBalance":999884.925,
                   "walletBalance":1000000,
                   "buyValueToCost":0.0114925,
                   "sellValueToCost":0,
                   "minPositionCost":0,
                   "positionBalance":0,
                   "createdAt":"2020-03-18T07:06:31.704Z",
                   "updatedAt":"2020-03-18T07:45:52.798Z"
               },
               {
                   "userId":100004,
                   "symbol":"BTCUSDT",
                   "side":"Sell",
                   "size":0,
                   "positionValue":0,
                   "entryPrice":0,
                   "riskId":1,
                   "leverage":100,
                   "positionMargin":0,
                   "liqPrice":0,
                   "bustPrice":0,
                   "occClosingFee":0,
                   "takeProfit":0,
                   "tpTriggerBy":"LastPriceOld",
                   "slTriggerBy":"LastPriceOld",
                   "stopLoss":0,
                   "trailingStop":0,
                   "positionStatus":"Normal",
                   "deleverageIndicator":0,
                   "todayRealisedPnl":0,
                   "cumRealisedPnl":0,
                   "isAutoAddMargin":false,
                   "freeQty":0,
                   "adlRankIndicator":0,
                   "unRealisedPnlByMp":0,
                   "unRealisedPnlByLp":0,
                   "unRealisedPnl":0,
                   "isIsolated":false,
                   "openValueLimit":1000000,
                   "extraAddedMargin":0,
                   "availableBalance":999884.925,
                   "walletBalance":1000000,
                   "buyValueToCost":0,
                   "sellValueToCost":0.0115075,
                   "minPositionCost":0,
                   "positionBalance":0,
                   "createdAt":"2020-03-18T07:06:31.705Z",
                   "updatedAt":"2020-03-18T07:45:52.799Z"
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
