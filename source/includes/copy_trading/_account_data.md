# t(:accountdata)
t(:account_para)

## t(:ct_order)
### t(:ct_create_order)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/contract/v3/private/copytrading/order/create \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","side":"Buy","symbol":"BTCUSDT","orderType":"Market","qty":"10","timestamp":{timestamp},"sign":"{sign}"}'

```

```python--pybit

```


> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "orderId": "419190fe-016c-469a-810e-936bef2f5d59",
    "orderLinkId": "234590fe-016c-44f6-fg78"
  }
}
```

t(:ct_create_order)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/contract/v3/private/copytrading/order/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_side) |<b>true</b> |string |t(:row_comment_side)    |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)   |
|t(:row_parameter_copytrading_order_type) |<b>true</b> |string |t(:row_comment_activeOrderType)   |
|t(:row_parameter_quantity) |<b>true</b> |string |t(:row_comment_qty) |
|t(:row_parameter_price) |<b>true</b> |string |t(:row_comment_resp_price) |
|orderLinkId |false |string |t(:row_comment_orderLinkId) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId |string |t(:row_comment_order_id) |
|orderLinkId |string |t(:row_comment_orderLinkId)  |


### t(:ct_order_list)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/contract/v3/private/copytrading/order/list?api_key={api_key}&timestamp={timestamp}&sign={sign}&symbol=ETHUSDT"
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "list": [
      {
        "orderId": "ae0700f6-c990-4de5-9d6e-0fdf8d5aabea",
        "symbol": "ETHUSDT",
        "orderLinkId": "234500f6-c45f-4de5-9d6e",
        "side": "Sell",
        "copyTradeOrderStatus": "New",
        "price": "4000.00",
        "qty": "5.55",
        "timeInForce": "GoodTillCancel",
        "leavesQty": "5.55",
        "isIsolated": true,
        "leavesValue": "22200",
        "leverage": "44",
        "cumExecValue": "0",
        "cumExecFee": "0",
        "createdTime": "1652216213331",
        "updatedTime": "1652216213365"
      }
    ]
  }
}
```

t(:ct_order_list)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpoList>/contract/v3/private/copytrading/order/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |false |string |t(:row_comment_symbol) |
|orderId |false |string |t(:row_comment_order_id)|
|orderLinkId |false |string |t(:row_comment_orderLinkId)|
|copyTradeOrderType |false |string |t(:row_parameter_copytrading_order_type_query)|


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId |string |t(:row_comment_order_id) |
|orderLinkId |string |t(:row_comment_orderLinkId)  |
|symbol |string |t(:row_comment_symbol) |
|side |string |t(:row_comment_side) |
|price  |string |t(:row_comment_resp_price) |
|qty  |string |t(:row_response_comment_qty) |
|timeInForce |string |t(:row_comment_timeInForce)  |
|isIsolated |boolean |t(:row_comment_isolated) |
|leverage |string |t(:resp_field_leverage) |
|copyTradeOrderStatus |string |t(:copy_trade_row_comment_order_type) |
|leavesQty |string |t(:row_comment_leaves_qty) |
|leavesValue |string |t(:row_comment_leaves_value) |
|cumExecValue |string |t(:linear_resp_field_cum_exec_value)  |
|cumExecFee |string |t(:linear_resp_field_cum_exec_fee)  |
|createdTime |string |t(:row_comment_created_at)  |
|updatedTime |string |t(:row_comment_updated_at)  |

### t(:ct_cancel_order)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/contract/v3/private/copytrading/order/cancel \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","orderId":"419190fe-016c-469a-810e-936bef2f5d59","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit

```


> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "orderId": "419190fe-016c-469a-810e-936bef2f5d59",
    "orderLinkId": ""
  }
}
```

t(:ct_cancel_order)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCancel>/contract/v3/private/copytrading/order/cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|orderId |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|orderLinkId |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId |string |t(:row_comment_order_id) |
|orderLinkId |string |t(:row_comment_orderLinkId)  |


### t(:ct_close_order)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/contract/v3/private/copytrading/order/close \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","orderId":"419190fe-016c-469a-810e-936bef2f5d59","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "orderId": "419190fe-016c-469a-810e-936bef2f5d59",
    "orderLinkId": ""
  }
}
```

t(:ct_close_order)

<aside class="notice">
t(:account_aside_cancelAllActive)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCancelAll>/contract/v3/private/copytrading/order/close</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancelAll"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |false |string |t(:row_comment_symbol)   |
|orderLinkId |false |string |t(:row_comment_orderLinkId) |
|parentOrderId |false |string |t(:copy_trade_row_comment_parentOrderIdNotparentOrderLinkId) |
|parentOrderLinkId |false |string |t(:copy_trade_row_comment_parentOrderLinkIdNotOrderId) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId |string |t(:row_comment_userID)  |
|orderLinkId |string |t(:row_comment_orderLinkId)  |


## t(:position)
### t(:ct_positon_list)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/contract/v3/private/copytrading/position/list?apiKey={api_key}&symbol=XRPUSDT&timestamp={timestamp}&sign={sign}"
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "list": [
      {
        "symbol": "XRPUSDT",
        "side": "Buy",
        "size": "4",
        "positionValue": "3.28",
        "entryPrice": "0.82",
        "liqPrice": "0.0001",
        "bustPrice": "0.0001",
        "markPrice": "0.5047",
        "leverage": "10",
        "isIsolated": false,
        "positionMargin": "0.0415737",
        "occClosingFee": "0.0000003",
        "occFundingFee": "0",
        "cumRealisedPnl": "-0.36682",
        "freeQty": "-4",
        "unrealisedPnl": "-1.2612",
        "positionIdx": "1",
        "createdTime": "1651594009009",
        "updatedTime": "1652223355185"
      },
      {
        "symbol": "XRPUSDT",
        "side": "Sell",
        "size": "28",
        "positionValue": "22.6984",
        "entryPrice": "0.81065714",
        "liqPrice": "199.9998",
        "bustPrice": "199.9998",
        "markPrice": "0.5047",
        "leverage": "10",
        "isIsolated": false,
        "positionMargin": "88881979.32381973",
        "occClosingFee": "4.1999958",
        "occFundingFee": "0",
        "cumRealisedPnl": "1.76750995",
        "freeQty": "28",
        "unrealisedPnl": "8.5668",
        "positionIdx": "2",
        "createdTime": "1651594009009",
        "updatedTime": "1652223355185"
      }
    ]
  }
}
```

t(:ct_positon_list)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pList>/contract/v3/private/copytrading/position/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |false |string |t(:row_comment_symbol)    |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |string |t(:row_comment_position_size)  |
|positionValue |string |t(:row_comment_position_value)  |
|entryPrice |string |t(:row_comment_entry_price)  |
|liqPrice |string |t(:row_comment_liq_price)  |
|bustPrice |string |t(:row_comment_bust_price)  |
|markPrice |string |t(:row_comment_resp_mark_price)  |
|leverage |string |t(:resp_field_leverage)  |
|isIsolated | boolean | t(:row_comment_isolated) |
|positionMargin |string |t(:row_comment_position_margin)  |
|occClosingFee |string |t(:row_comment_occ_closing_fee)  |
|occFundingFee |string |t(:row_comment_occ_funding_fee)  |
|cumRealisedPnl |string |t(:row_comment_cum_realised_pnl)  |
|freeQty |string |t(:linear_resp_field_free_qty)  |
|unrealisedPnl |string |t(:row_comment_unrealised_pnl)  |
|positionIdx |string |t(:copy_trade_row_comment_position_idx)  |
|createdTime |string |t(:row_comment_created_at)  |
|updatedTime |string |t(:row_comment_updated_at)  |


### t(:ct_positon_close)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/contract/v3/private/copytrading/position/close \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT",positionIdx:"2","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {}
}
```

t(:ct_positon_close)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pChangePositionMarginNew>/contract/v3/private/copytrading/position/close</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pChangePositionMarginNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|positionIdx |<b>true</b>|string |t(:copy_trade_row_comment_position_idx)  |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |



### t(:ct_set_leverage)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/contract/v3/private/copytrading/position/set-leverage \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","buyLeverage":"14","sellLeverage":"14",timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {}
}
```

t(:ct_set_leverage_desc)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=ulSaveNew>/contract/v3/private/copytrading/position/set-leverage</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ulSaveNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol |<b>true</b> |string |t(:row_comment_symbol)    |
|buyLeverage |<b>true</b> |string |t(:copy_trade_comment_leverage) |
|sellLeverage |<b>true</b> |string |t(:copy_trade_comment_leverage) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |




