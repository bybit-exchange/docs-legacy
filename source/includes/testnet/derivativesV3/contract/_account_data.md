# t(:accountdata)
t(:account_para)

## t(:order)
### t(:dv_placeOrder)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/contract/v3/private/order/create' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: f02a18137c25c40d64b2c474f575c01a62ba076124946d38619238e19c86a2f2' \
--header 'X-BAPI-API-KEY: PXOXCIFKHCWCAJTPKW' \
--header 'X-BAPI-TIMESTAMP: 1658884339826' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "symbol": "ETHUSDT",
    "side": "Sell",
    "positionIdx": 2,
    "orderType": "Limit",
    "qty": "0.5",
    "price": "1450",
    "triggerDirection": 2,
    "triggerPrice": "1500",
    "triggerBy": "MarkPrice",
    "timeInForce": "GoodTillCancel",
    "orderLinkId": "a003",
    "takeProfit": "1100",
    "stopLoss": "1700",
    "reduce_only": false,
    "closeOnTrigger": false
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode":0,
    "retMsg":"OK",
    "result":{
        "orderId":"a09a43f1-7a65-4255-8758-034103447a4e",
        "orderLinkId":""
  },
    "retExtInfo":null,
    "time":1658850321861
}
```

t(:contract_order_para)

<aside class="warning">
t(:account_aside_placeActive_linear_warn)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/contract/v3/private/order/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol |<b>true</b> |string |t(:row_comment_symbol)   |
|side |<b>true</b> |string |t(:row_comment_side)    |
|positionIdx |false |integer |t(:row_comment_position_idx_create_order)  |
|orderType |<b>true</b> |string |t(:row_comment_activeOrderType)   |
|qty |<b>true</b> |number |t(:linear_row_comment_qty) |
|price |false |number |t(:row_comment_price) |
|triggerDirection |false |number |t(:row_comment_triggerDirection) |
|triggerPrice |false |string |t(:row_comment_triggerPrice) |
|<a href="#trigger-price-type-triggerby">triggerBy</a> |false |string |t(:row_comment_linear_triggerBy) |
|tpTriggerBy |false |string |t(:account_row_comment_tp_trigger_by) |
|slTriggerBy |false |string |t(:account_row_comment_sl_trigger_by) |
|t(:row_parameter_timeInForce) |<b>true</b> |string |t(:row_comment_timeInForce) |
|orderLinkId |false |string |t(:row_comment_orderLinkId) |
|takeProfit |false |number |t(:row_comment_takeProfit) |
|stopLoss |false |number |t(:row_comment_stopLoss) |
|reduceOnly |<b>true</b> |bool |t(:linear_row_comment_reduceOnly) |
|closeOnTrigger |<b>true</b> |bool |t(:linear_row_comment_closeOnTrigger)


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| orderId |string |t(:row_comment_order_id) |
|orderLinkId |string |t(:row_comment_orderLinkId)  |


### t(:getactive)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/contract/v3/private/order/list?api_key={api_key}&timestamp={timestamp}&sign={sign}&symbol=BTCUSDT"
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

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oaoList>/contract/v3/private/order/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|orderId |false |string |t(:account_row_comment_orderId) |
|orderLinkId |false |string |t(:row_comment_orderLinkId) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|orderStatus |false |string |t(:linear_account_row_comment_orderStatus) |
|orderFilter |false |string |t(:row_comment_orderFilter) |
|limit |false |integer |t(:row_comment_limit) |
|cursor |false |string |t(:row_comment_cursor) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|symbol |string |t(:row_comment_symbol) |
|side |string |t(:row_comment_side) |
|orderType |string |t(:row_comment_order_type) |
|price  |string |t(:row_comment_resp_price) |
|qty  |string |t(:linear_row_comment_qty) |
|reduceOnly |bool |t(:linear_resp_field_reduce_only)  |
|timeInForce |string |t(:row_comment_timeInForce)  |
|orderStatus |string |t(:row_comment_orderStatus)  |
|leavesQty |string |t(:row_comment_leavesQty)  |
|leavesValue |string |t(:row_comment_leavesValue)  |
|cumExecQty |string |t(:linear_resp_field_cum_exec_qty)  |
|cumExecValue |string |t(:linear_resp_field_cum_exec_value)  |
|cumExecFee |string |t(:linear_resp_field_cum_exec_fee)  |
|lastPriceOnCreated |string |t(:row_comment_last_exec_price)  |
|rejectReason |string |t(:row_comment_query_rejectReason_v3) |
|createdTime |string |t(:row_comment_created_at)  |
|updatedTime |string |t(:row_comment_updated_at)  |
|orderLinkId |string |t(:row_comment_orderLinkId)  |
|orderId |string |t(:account_row_comment_orderId) |
|stopOrderType |string |t(:row_comment_stopOrderType) |
|triggerDirection |number |t(:row_comment_triggerDirection) |
|closeOnTrigger |bool |t(:row_response_close_on_trigger)  |
|takeProfit |string |t(:row_comment_take_profit)  |
|stopLoss |string |t(:row_comment_stop_loss)  |
|tpTriggerBy |string |t(:account_row_comment_tp_trigger_by) |
|tpTriggerBy |string |t(:account_row_comment_tp_trigger_by) |
|triggerPrice |string |t(:row_comment_triggerPrice) |
|nextPageCursor |string |t(:row_comment_nextPageCursor) |


### t(:cancelactive)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/contract/v3/private/order/cancel \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","orderId":"","timestamp":{timestamp},"sign":"{sign}"}'
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
  "retCode":0,
    "retMsg":"OK",
    "result":{
    "orderId":"a09a43f1-7a65-4255-8758-034103447a4e",
      "orderLinkId":""
  },
  "retExtInfo":null,
    "time":1658850321861
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
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|orderId |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|orderLinkId |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId |string |t(:account_row_comment_orderId) |
|orderLinkId |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |


### t(:cancelallactive)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/contract/v3/private/order/cancel-all \
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
<code><span id=vpoCancelAll>/contract/v3/private/order/cancel-all</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancelAll"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol |<b>true</b> |string | t(:row_comment_symbol) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId |string |t(:account_row_comment_orderId) |
|orderLinkId |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |


### t(:replaceactive)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/contract/v3/private/order/replace \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","orderId":"","qty":2,"timestamp":{timestamp},"sign":"{sign}"}'
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
  {
    "retCode":0,
    "retMsg":"OK",
    "result":{
    "orderId":"a09a43f1-7a65-4255-8758-034103447a4e",
      "orderLinkId":""
     },
    "retExtInfo":null,
    "time":1658850321861
  }          
}
```

t(:account_para_replaceActive)

<aside class="notice">
t(:account_aside_replaceActive)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oaoReplace>/contract/v3/private/order/replace</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaoReplace"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|orderId |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|orderLinkId |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|qty |false |string |t(:row_comment_pRQty) |
|price |false |string |t(:row_comment_pRPrice) |
|takeProfit |false |string |t(:row_comemnt_replace_take_profit)  |
|stopLoss |false |string |t(:row_comemnt_replace_stop_loss)  |
|tpTriggerBy |false |string |t(:account_row_comment_tp_trigger_by) |
|slTriggerBy |false |string |t(:account_row_comment_sl_trigger_by) |
|triggerBy |false |string |t(:account_row_comment_sl_trigger_by) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|order_id |string |t(:account_row_comment_orderId) |
|orderLinkId |string |t(:row_comment_orderLinkId)  |


### t(:queryactive)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/contract/v3/private/order/unfilled-orders?api_key={api_key}&symbol=BTCUSDT&timestamp={timestamp}orderId={order_id}&sign={sign}"
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
    "retCode":0,
    "retMsg":"OK",
    "result":{
    "list":[
      {
        "symbol":"BTCUSDT",
        "orderId":"788b483e-39d2-486a-b158-829388d32013",
        "side":"Buy",
        "orderType":"Limit",
        "stopOrderType":"Stop",
        "price":"50990.00",
        "qty":"1.000",
        "timeInForce":"GoodTillCancel",
        "orderStatus":"UnTriggered",
        "triggerPrice":"45990.00",
        "orderLinkId":"",
        "createdTime":"1658851097073",
        "updatedTime":"1658851097073",
        "takeProfit":"0.00",
        "stopLoss":"0.00",
        "tpTriggerBy":"UNKNOWN",
        "slTriggerBy":"UNKNOWN",
        "triggerBy":"LastPrice",
        "reduceOnly":false,
        "leavesQty":"1.000",
        "leavesValue":"50990",
        "cumExecQty":"0.000",
        "cumExecValue":"0",
        "cumExecFee":"0",
        "triggerDirection":1
      }
    ]
  },
    "retExtInfo":null,
    "time":1658851147336
}



```


t(:account_para_queryActive)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpOrder>/contract/v3/private/order/unfilled-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|order_id |false |string | t(:misc_row_comment_orderIdNotOrderLinkId)|
|order_link_id |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |
|settleCoin |false |string | t(:row_comment_settleCoin)|
|orderFilter |false |string | t(:row_comment_orderFilter)|
|limit |<b>true</b> |number |t(:row_comment_limit) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|symbol |string |t(:row_comment_symbol)    |
| order_id |string |t(:row_comment_order_id) |
|side |string |t(:row_comment_side)  |
|orderType |string |t(:row_comment_order_type)  |
|triggerDirection |number |t(:row_comment_order_triggerDirection)  |
|price |number |t(:row_comment_resp_price)  |
|qty |number |t(:linear_row_comment_qty)  |
|timeInForce |string |t(:row_comment_timeInForce)  |
|orderStatus |string |t(:row_comment_orderStatus)  |
|triggerPrice |string |t(:row_comment_triggerPrice)  |
|triggerBy |string |t(:account_row_comment_sl_trigger_by) |
|tpTriggerBy |string |t(:account_row_comment_tp_trigger_by) |
|slTriggerBy |string |t(:account_row_comment_sl_trigger_by) |
|orderLinkId |string |t(:row_comment_orderLinkId)  |
|createdTime |string |t(:row_comment_created_at)  |
|updatedTime |string |t(:row_comment_updated_at)  |
|takeProfit |number |t(:row_comment_take_profit)  |
|stopLoss |number |t(:row_comment_stop_loss)  |
|reduce_only |bool |t(:linear_resp_field_reduce_only)  |
|cumExecQty |string |t(:linear_resp_field_cum_exec_qty)  |
|cumExecValue |string |t(:linear_resp_field_cum_exec_value)  |
|cumExecFee |string |t(:linear_resp_field_cum_exec_fee)  |
|leavesQty |number |t(:row_comment_leavesQty)  |
|leavesValue |number |t(:row_comment_leavesValue)  |


## t(:position)
### t(:myposition)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/contract/v3/private/position/list?api_key={api_key}&symbol=BTCUSDT&timestamp={timestamp}&sign={sign}"
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="cCrMK2P55002rmQh1z",
    api_secret="eTXOcGvu6Ue9MA916oO5ymqbj2UzBfSLKcti"
)
print(session_auth.my_position(
    symbol="BTCUSDT"
))
```

> t(:codequote_responseExample)

```javascript
{
    "retCode":0,
    "retMsg":"OK",
    "result":{
    "list": [
      {
        "positionIdx":0,
        "riskId":"10",
        "symbol":"BTCUSDT",
        "side":"None",
        "size":"0.000",
        "positionValue":"0",
        "entryPrice":"0",
        "tradeMode":1,
        "autoAddMargin":0,
        "leverage":"3.5",
        "positionBalance":"0",
        "liqPrice":"0.00",
        "bustPrice":"0.00",
        "takeProfit":"0.00",
        "stopLoss":"0.00",
        "trailingStop":"0.00",
        "unrealisedPnl":"0",
        "createdTime":"1655199040377",
        "updatedTime":"1658808420807",
        "tpSlMode":"Partial",
        "riskLimitValue":"10000000",
        "activePrice":"0.00"
      }
    ]
  }
    "retExtInfo":null,
    "time":1658848204275
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
|t(:row_parameter_symbol) |false |string |t(:row_comment_symbol)    |
|t(:row_parameter_symbol) |false |string |t(:row_comment_symbol)    |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|positionIdx |integer |t(:row_comment_position_idx)  |
|riskId  |integer |t(:row_comment_riskId) |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |string |t(:row_comment_position_size)  |
|positionValue |string |t(:linear_resp_field_position_value)  |
|entryPrice |string |t(:linear_resp_field_entry_price)  |
|tradeMode |number |t(:row_comment_isolated) |
|autoAddMargin |number |t(:row_comment_auto_add_margin)  |
|leverage |number |t(:resp_field_leverage)  |
|positionBalance |string |t(:row_comment_positionBalance)  |
|liqPrice |string |t(:linear_resp_field_liq_price)  |
|bustPrice |string |t(:linear_resp_field_bust_price)  |
|takeProfit |string |t(:row_comment_take_profit)  |
|stopLoss |string |t(:row_comment_stop_loss)  |
|trailingStop |string |t(:row_comment_trailing_stop)  |
|unrealisedPnl |string |t(:row_comment_unrealised_pnl)  |
|t(:row_parameter_tp_sl_mode) |string |t(:linear_resp_tp_sl_mode)  |
|trailingStop | string | t(:row_comment_trailingStop) |
|activePrice | string | t(:row_comment_activePrice) |
|createdTime |string |t(:row_comment_created_at)  |
|updatedTime |string |t(:row_comment_updated_at)  |
|nextPageCursor | string | t(:row_comment_nextPageCursor) |

### t(:setautoaddmargin)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/contract/v3/private/position/set-auto-add-margin \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","side":"Sell","auto_add_margin":false,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="cCrMK2P55002rmQh1z",
    api_secret="eTXOcGvu6Ue9MA916oO5ymqbj2UzBfSLKcti"
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
<code><span id=pSetAutoAddMargin>/contract/v3/private/position/set-auto-add-margin</span></code>
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
curl https://api-testnet.bybit.com/contract/v3/private/position/switch-isolated \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","tradeMode":1,"buyLeverage":"1","sellLeverage":"1","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="cCrMK2P55002rmQh1z",
    api_secret="eTXOcGvu6Ue9MA916oO5ymqbj2UzBfSLKcti"
)
print(session_auth.cross_isolated_margin_switch(
    symbol="BTCUSDT",
    is_isolated=True,
    buy_leverage=1,
    sell_leverage=1
))
```


t(:linear_account_para_switchIsolated)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pSwitchIsolated>/contract/v3/private/position/switch-isolated</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pSwitchIsolated"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|tradeMode |<b>true</b> |number |t(:linear_row_comment_switch_isolated)  |
|buyLeverage |<b>true</b> |string |t(:linear_row_comment_leverage)  |
|sellLeverage |<b>true</b> |string |t(:linear_row_comment_leverage)  |


### t(:switchpositionmode)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/contract/v3/private/position/switch-mode \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","mode":"MergedSingle","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="cCrMK2P55002rmQh1z",
    api_secret="eTXOcGvu6Ue9MA916oO5ymqbj2UzBfSLKcti"
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

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=ulSwitchMode>/contract/v3/private/position/switch-mode</span></code>
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
    api_key="cCrMK2P55002rmQh1z",
    api_secret="eTXOcGvu6Ue9MA916oO5ymqbj2UzBfSLKcti"
)
print(session_auth.full_partial_position_tp_sl_switch(
    symbol="BTCUSDT",
    tp_sl_mode="Partial"
))
```


t(:linear_private_switchmode)

<aside class="notice">
t(:switchmode_aside)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pltcList>/contract/v3/private/position/switch-tpsl-mode</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pltcList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|tpSlMode |<b>true</b> |string |t(:linear_resp_tp_sl_mode)  |



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
    api_key="cCrMK2P55002rmQh1z",
    api_secret="eTXOcGvu6Ue9MA916oO5ymqbj2UzBfSLKcti"
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


### t(:setleverage)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/contract/v3/private/position/set-leverage \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","buyLeverage":"10","sellLeverage":"10"sign":"{sign}"}'
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="cCrMK2P55002rmQh1z",
    api_secret="eTXOcGvu6Ue9MA916oO5ymqbj2UzBfSLKcti"
)
print(session_auth.set_leverage(
    symbol="BTCUSDT",
    buy_leverage=10,
    sell_leverage=10
))
```

t(:linear_account_para_setLeverage)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pSetLeverage>/contract/v3/private/position/set-leverage</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pSetLeverage"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|buyLeverage |<b>true</b> |string |t(:linear_row_comment_leverage)  |
|sellLeverage |<b>true</b> |string |t(:linear_row_comment_leverage)  |


### t(:tradingstop)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/contract/v3/private/position/trading-stop \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","side":"Buy","takeProfit":10,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="cCrMK2P55002rmQh1z",
    api_secret="eTXOcGvu6Ue9MA916oO5ymqbj2UzBfSLKcti"
)
print(session_auth.set_trading_stop(
    symbol="BTCUSDT",
    side="Buy",
    take_profit=10
))
```


t(:account_para_tradingStop_linear)

<aside class="notice">
t(:account_aside_tradingStop)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pSetTpSlTs>/contract/v3/private/position/trading-stop</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pSetTpSlTs"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|takeProfit |false |string |t(:account_row_comment_takeProfit) |
|stopLoss |false |string |t(:account_row_comment_stopLoss) |
|trailingStop |false |string |t(:account_row_comment_trailingStop) |
|activePrice |false |string |t(:account_row_comment_trailingStop) |
|tpTriggerBy | false | string | t(:account_row_comment_tp_trigger_by)
|slTriggerBy | false | string | t(:account_row_comment_sl_trigger_by)
|slSize |false |string |t(:row_comment_sl_size) |
|tpSize |false |string |t(:row_comment_tp_size) |
|positionIdx |false |integer |t(:row_comment_position_idx)  |


### t(:setrisklimit)

> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/contract/v3/private/position/set-risk-limit \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","riskId":2,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="cCrMK2P55002rmQh1z",
    api_secret="eTXOcGvu6Ue9MA916oO5ymqbj2UzBfSLKcti"
)
print(session_auth.set_risk_limit(
    symbol="BTCUSDT",
    side="Buy",
    risk_id=1
))
```

t(:account_para_setRisk)

<aside class="notice">
t(:account_aside_getRisk_linear)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=plpSetRisk>/contract/v3/private/position/set-risk-limit</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#plpSetRisk"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|riskId |<b>true</b> |integer |t(:row_comment_riskId) |
|positionIdx |false |integer |t(:row_comment_position_idx)  |




### t(:usertraderecords)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/private/linear/trade/execution/list?api_key={api_key}&symbol=BTCUSDT&timestamp={timestamp}&sign={sign}"
```

```python--pybit
from pybit import usdt_perpetual
session_auth = usdt_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="cCrMK2P55002rmQh1z",
    api_secret="eTXOcGvu6Ue9MA916oO5ymqbj2UzBfSLKcti"
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
    api_key="cCrMK2P55002rmQh1z",
    api_secret="eTXOcGvu6Ue9MA916oO5ymqbj2UzBfSLKcti"
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
    api_key="cCrMK2P55002rmQh1z",
    api_secret="eTXOcGvu6Ue9MA916oO5ymqbj2UzBfSLKcti"
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
    "ret_code":0,
    "ret_msg":"OK",
    "ext_code":"",
    "ext_info":"",
    "result":[
        {
            "id":1,
            "symbol":"BTCUSDT",
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
            "symbol":"BTCUSDT",
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
    api_key="cCrMK2P55002rmQh1z",
    api_secret="eTXOcGvu6Ue9MA916oO5ymqbj2UzBfSLKcti"
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
    api_key="cCrMK2P55002rmQh1z",
    api_secret="eTXOcGvu6Ue9MA916oO5ymqbj2UzBfSLKcti"
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
<a href="/docs/inverse#t-key">t(:shared_endpoint_desc)</a>

## t(:lcp)
<a href="/docs/inverse#t-lcp">t(:shared_endpoint_desc)</a>
