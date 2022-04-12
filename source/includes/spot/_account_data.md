# t(:accountdata)
t(:account_para)

### t(:placeactive)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/spot/v1/order \
-H "Content-Type: application/x-www-form-urlencoded" \
-d 'api_key={api_key}&side=Buy&symbol=ETHUSDT&type=MARKET&qty=10&timeInForce=GTC&timestamp={timestamp}&sign={signature}'
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="",
               spot=True)
print(session.place_active_order(
    symbol="ETHUSDT",
    side="Buy",
    type="MARKET",
    qty=10,
    timeInForce="GTC"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "",
    "ext_code": null,
    "ext_info": null,
    "result": {
        "accountId": "1",
        "symbol": "ETHUSDT",
        "symbolName": "ETHUSDT",
        "orderLinkId": "162073788655749",
        "orderId": "889208273689997824",
        "transactTime": "1620737886573",
        "price": "20000",
        "origQty": "10",
        "executedQty": "0",
        "status": "NEW",
        "timeInForce": "GTC",
        "type": "LIMIT",
        "side": "BUY"
    }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=svPostOrder>/spot/v1/order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svPostOrder"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol)|<b>true</b>|string|t(:spotSymbol)|
|qty|<b>true</b>|number|t(:spotQtyPlaceOrder)|
|t(:row_parameter_side)|<b>true</b>|string|t(:spotSide)|
|t(:row_parameter_type)|<b>true</b>|string|t(:spotOrderType)|
|t(:row_parameter_timeInForce)|false|string|t(:row_comment_timeInForce)|
|price|false|number|t(:spotPostOrderPrice)|
|orderLinkId|false|string|t(:spotOrderLinkId)|



<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|integer|t(:spotOrderId)|
|orderLinkId|string|t(:spotOrderLinkId)
|symbol|string|t(:spotSymbol)|
|transactTime|int|t(:spotTransactTime)|
|price|float|t(:spotPrice)|
|origQty|float|t(:spotOriQty)|
|<a href="#order-type-type-ordertypes">type</a>|string|t(:spotOrderType)|
|side|string|t(:spotSide)|
|t(:spot_row_parameter_orderStatus)|string|t(:spotStatus)|
|t(:row_parameter_timeInForce)|string|t(:row_comment_timeInForce)|
|accountId|long|t(:spotAccountId)|
|symbolName|string|t(:spotSymbolName)|
|executedQty|string|t(:spotExecQty)|

### t(:getactive)
> t(:codequote_curlExample)

```console
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="",
               spot=True)
print(session.get_active_order(
    orderId="889826641228952064"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "",
    "ext_code": null,
    "ext_info": null,
    "result": {
        "accountId": "1054",
        "exchangeId": "301",
        "symbol": "ETHUSDT",
        "symbolName": "ETHUSDT",
        "orderLinkId": "162081160171552",
        "orderId": "889826641228952064",
        "price": "20000",
        "origQty": "10",
        "executedQty": "0",
        "cummulativeQuoteQty": "0",
        "avgPrice": "0",
        "status": "NEW",
        "timeInForce": "GTC",
        "type": "LIMIT",
        "side": "BUY",
        "stopPrice": "0.0",
        "icebergQty": "0.0",
        "time": "1620811601728",
        "updateTime": "1620811601743",
        "isWorking": true
    }
}
```

t(:getactive)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=svGetOrder>/spot/v1/order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svGetOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|orderId|false|string|t(:misc_row_comment_orderIdNotOrderLinkId_spot)|
|orderLinkId|false|string|t(:misc_row_comment_orderLinkIdNotOrderId_spot)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|accountId|long |t(:spotAccountId)|
|exchangeId|long|t(:spotOrderId)|
|symbol|string|t(:spotSymbol)|
|symbolName|string|t(:spotSymbol)|
|orderLinkId|string|t(:spotOrderLinkId)|
|orderId|long|t(:spotOrderId)|
|price|float|t(:spotOPrice)|
|origQty|float|t(:spotOriQty)|
|executedQty|float|t(:spotExecQty2)|
|cummulativeQuoteQty|float|t(:spotCummulativeQuoteQty)|
|avgPrice|float|t(:spotAvgPrice)|
|t(:spot_row_parameter_orderStatus)|string|t(:spotStatus)|
|t(:row_parameter_timeInForce)|string|t(:row_comment_timeInForce)|
|<a href="#order-type-type-ordertypes">type</a>|string|t(:spotOrderType)|
|side|string|t(:spotSide)|
|stopPrice|float|t(:spotStopPrice)|
|icebergQty|float|t(:spotIcebergQty)|
|time|long|t(:spotTime)|
|updateTime|long|t(:spotUpdateTime)|
|isWorking|boolean|t(:spotIsWorking)|


### t(:cancelactive)
> t(:codequote_curlExample)

```console
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="",
               spot=True)
print(session.cancel_active_order(
    orderId="889826641228952064"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "",
    "ext_code": null,
    "ext_info": null,
    "result": {
        "accountId": "10054",
        "symbol": "ETHUSDT",
        "orderLinkId": "162081160171552",
        "orderId": "889826641228952064",
        "transactTime": "1620811601728",
        "price": "20000",
        "origQty": "10",
        "executedQty": "0",
        "status": "CANCELED",
        "timeInForce": "GTC",
        "type": "LIMIT",
        "side": "BUY"
    }
}
```


<p class="fake_header">t(:httprequest)</p>
DELETE
<code><span id=svDeleteOrder>/spot/v1/order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svDeleteOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|orderId|false|string|t(:misc_row_comment_orderIdNotOrderLinkId_spot)|
|orderLinkId|false|string|t(:misc_row_comment_orderLinkIdNotOrderId_spot)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|integer|t(:spotOrderId)|
|orderLinkId|string|t(:spotOrderLinkId)
|symbol|string|t(:spotSymbol)|
|t(:spot_row_parameter_orderStatus)|string|t(:spotStatus)|
|accountId|long|t(:spotAccountId)|
|transactTime|long|t(:spotTransactTime)|
|price|float|t(:spotOPrice)|
|origQty|float|t(:spotOriQty)|
|executedQty|float|t(:spotExecQty2)|
|t(:row_parameter_timeInForce)|string|t(:row_comment_timeInForce)|
|t(:row_parameter_type)|string|t(:spotOrderType)|
|side|string|t(:spotSide)|



### t(:fastcancelactiveorder)
> t(:codequote_curlExample)

```console
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="",
               spot=True)
print(session.fast_cancel_active_order(
    symbolId="ETHUSDT",
    orderId="889826641228952064"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "",
    "ext_code": null,
    "ext_info": null,
    "result": {
        "isCancelled": true
    }
}
```


<aside class="notice">
t(:spotNormalCancelTips)
</aside>

<p class="fake_header">t(:httprequest)</p>
DELETE
<code><span id=svoFast>/spot/v1/order/fast</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svoFast"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbolId|<b>true</b>|string|t(:spotSymbol)|
|orderId|false|string|t(:misc_row_comment_orderIdNotOrderLinkId_spot)|
|orderLinkId|false|string|t(:misc_row_comment_orderLinkIdNotOrderId_spot)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|isCancelled|bool|t(:spot_message)|

### t(:batchcancelactiveorder)
> t(:codequote_curlExample)

```console

```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="",
               spot=True)
print(session.batch_cancel_active_order(
    symbol="ETHUSDT",
    orderTypes="LIMIT,LIMIT_MAKER"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "",
    "ext_code": null,
    "ext_info": null,
    "result": {
        "success": true
    }
}
```

<aside class="notice">
t(:spotCancelTips)
</aside>

<p class="fake_header">t(:httprequest)</p>
DELETE
<code><span id=soBatchCancel>/spot/order/batch-cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#soBatchCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:spotSymbol)|
|side|false|string|t(:spotSide)|
|<a href="#order-type-type-ordertypes">orderTypes</a>|false|string|t(:batchcancel_spotOrderTypes)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|success|boolean|t(:spot_message)|



### t(:batchfastcancelactiveorder)
> t(:codequote_curlExample)

```console

```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="",
               spot=True)
print(session.batch_fast_cancel_active_order(
    symbol="ETHUSDT",
    orderTypes="LIMIT,LIMIT_MAKER"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "",
    "ext_code": null,
    "ext_info": null,
    "result": {
        "success": true
    }
}
```

<aside class="notice">
t(:spotFastCancelTips)
</aside>


<p class="fake_header">t(:httprequest)</p>
DELETE
<code><span id=soBatchFastCancel>/spot/order/batch-fast-cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#soBatchFastCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:spotSymbol)|
|side|false|string|t(:spotSide)|
|orderTypes|fasle|string|t(:batchcancel_spotOrderTypes)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|success|boolean|t(:spot_message)|



### t(:batchcancelactiveorderbyids)
> t(:codequote_curlExample)

```console

```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="",
               spot=True)
print(session.batch_cancel_active_order_by_ids(
    orderIds="889208273689997824,889826641228952064"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "",
    "ext_code": null,
    "ext_info": null,
    "result": [
        {
          "orderId": "889208273689997824",
          "code": "1139"
        }
    ]
}
```

<aside class="notice">
t(:spotNormalCancelTips)
</aside>

<p class="fake_header">t(:httprequest)</p>
DELETE
<code><span id=soBatchCancelIds>/spot/order/batch-cancel-by-ids</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#soBatchCancelIds"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|orderIds|<b>true</b>|string|t(:spotCancelOrderIds)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|integer|t(:spotOrderId)|
|code|integer|t(:errors)|




### t(:openorders)
> t(:codequote_curlExample)

```console
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="",
               spot=True)
print(session.query_active_order(
    symbol="ETHUSDT"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "",
    "ext_code": null,
    "ext_info": null,
    "result": [
        {
            "accountId": "10054",
            "exchangeId": "301",
            "symbol": "ETHUSDT",
            "symbolName": "ETHUSDT",
            "orderLinkId": "162080709527252",
            "orderId": "889788838461927936",
            "price": "20000",
            "origQty": "10",
            "executedQty": "0",
            "cummulativeQuoteQty": "0",
            "avgPrice": "0",
            "status": "NEW",
            "timeInForce": "GTC",
            "type": "LIMIT",
            "side": "BUY",
            "stopPrice": "0.0",
            "icebergQty": "0.0",
            "time": "1620807095287",
            "updateTime": "1620807095307",
            "isWorking": true
        },
        {
            "accountId": "10054",
            "exchangeId": "301",
            "symbol": "ETHUSDT",
            "symbolName": "ETHUSDT",
            "orderLinkId": "162063873503148",
            "orderId": "888376530389004800",
            "price": "20000",
            "origQty": "10",
            "executedQty": "0",
            "cummulativeQuoteQty": "0",
            "avgPrice": "0",
            "status": "NEW",
            "timeInForce": "GTC",
            "type": "LIMIT",
            "side": "BUY",
            "stopPrice": "0.0",
            "icebergQty": "0.0",
            "time": "1620638735044",
            "updateTime": "1620638735062",
            "isWorking": true
        }
    ]
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=svOpenOrders>/spot/v1/open-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svOpenOrders"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|false|string|t(:spotSymbol)|
|orderId|false|string|t(:spotOrderId4Pagination)|
|limit|false|integer|t(:spot_order_list_limit)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|accountId|long |t(:spotAccountId)|
|exchangeId|long|t(:spotOrderId)|
|symbol|string|t(:spotSymbol)|
|symbolName|string|t(:spotSymbol)|
|orderLinkId|string|t(:spotOrderLinkId)|
|orderId|long|t(:spotOrderId)|
|price|float|t(:spotOPrice)|
|origQty|float|t(:spotOriQty)|
|executedQty|float|t(:spotExecQty2)|
|cummulativeQuoteQty|float|t(:spotCummulativeQuoteQty)|
|avgPrice|float|t(:spotAvgPrice)|
|t(:spot_row_parameter_orderStatus)|string|t(:spotStatus)|
|t(:row_parameter_timeInForce)|string|t(:row_comment_timeInForce)|
|<a href="#order-type-type-ordertypes">type</a>|string|t(:spotOrderType)|
|side|string|t(:spotSide)|
|stopPrice|float|t(:spotStopPrice)|
|icebergQty|float|t(:spotIcebergQty)|
|time|long|t(:spotTime)|
|updateTime|long|t(:spotUpdateTime)|
|isWorking|boolean|t(:spotIsWorking)|




### t(:orderhistory)
> t(:codequote_curlExample)

```console

```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="",
               spot=True)
print(session.query_active_order(
    symbol="ETHUSDT"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "",
    "ext_code": null,
    "ext_info": null,
    "result": [
        {
            "accountId": "10054",
            "exchangeId": "301",
            "symbol": "ETHUSDT",
            "symbolName": "ETHUSDT",
            "orderLinkId": "1620615771764",
            "orderId": "888183901021893120",
            "price": "5000",
            "origQty": "1",
            "executedQty": "0",
            "cummulativeQuoteQty": "0",
            "avgPrice": "0",
            "status": "CANCELED",
            "timeInForce": "GTC",
            "type": "LIMIT",
            "side": "BUY",
            "stopPrice": "0.0",
            "icebergQty": "0.0",
            "time": "1620615771836",
            "updateTime": "1620617056334",
            "isWorking": true
        }
    ]
}
```

<aside class="notice">
t(:spotOrdersHistoryTips)
</aside>
<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=svHistoryOrders>/spot/v1/history-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svHistoryOrders"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|false|string|t(:spotSymbol)|
|orderId|false|string|t(:spotOrderId4Pagination)|
|limit|false|integer|t(:spot_order_list_limit)|
|startTime|false|long|t(:spot_start_time)|
|endTime|false|long|t(:spot_end_time)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|accountId|long |t(:spotAccountId)|
|exchangeId|long|t(:spotOrderId)|
|symbol|string|t(:spotSymbol)|
|symbolName|string|t(:spotSymbol)|
|orderLinkId|string|t(:spotOrderLinkId)|
|orderId|long|t(:spotOrderId)|
|price|float|t(:spotPrice)|
|origQty|float|t(:spotOriQty)|
|executedQty|float|t(:spotExecQty2)|
|cummulativeQuoteQty|float|t(:spotCummulativeQuoteQty)|
|avgPrice|float|t(:spotAvgPrice)|
|t(:spot_row_parameter_orderStatus)|string|t(:spotStatus)|
|t(:row_parameter_timeInForce)|string|t(:row_comment_timeInForce)|
|<a href="#order-type-type-ordertypes">type</a>|string|t(:spotOrderType)|
|side|string|t(:spotSide)|
|stopPrice|float|t(:spotStopPrice)|
|icebergQty|float|t(:spotIcebergQty)|
|time|long|t(:spotTime)|
|updateTime|long|t(:spotUpdateTime)|
|isWorking|boolean|t(:spotIsWorking)|




### t(:tradehistory)
> t(:codequote_curlExample)

```console
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="",
               spot=True)
print(session.user_trade_records(
    symbol="BTCUSDT"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "",
    "ext_code": null,
    "ext_info": null,
    "result": [
       {
            "id": "931975237315196160",
            "symbol": "BTCUSDT",
            "symbolName": "BTCUSDT",
            "orderId": "931975236946097408",
            "ticketId": "1057753175328833537",
            "matchOrderId": "931975113180558592",
            "price": "20000.00001",
            "qty": "0.01",
            "commission": "0.02000000001",
            "commissionAsset": "USDT",
            "time": "1625836105890",
            "isBuyer": false,
            "isMaker": false,
            "fee": {
                "feeTokenId": "USDT",
                "feeTokenName": "USDT",
                "fee": "0.02000000001"
            },
            "feeTokenId": "USDT",
            "feeAmount": "0.02000000001",
            "makerRebate": "0"
       }
    ]
}
```

<aside class="notice">
t(:spotTradesHistoryTips)
</aside>
<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=svMyTrades>/spot/v1/myTrades</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svMyTrades"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|false|string|t(:spotSymbol)|
|limit|false|integer|t(:spot_trades_history_limit)|
|fromTicketId|false|integer|t(:spot_from_id)|
|toTicketId|false|integer|t(:spot_to_id)|
|orderId|false|integer|t(:spotOrderId)|
|startTime|false|long|t(:spot_start_time)|
|endTime|false|long|t(:spot_end_time)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|symbol|string|t(:spotSymbol)|
|id| int |t(:spotId)|
|orderId|integer|t(:spotOrderId)|
|ticketId|integer|t(:spotTicketId)|
|price|float|t(:spotPrice)|
|qty|float|t(:spotQty)|
|commission|float|t(:spotCommission)|
|commissionAsset|float|t(:spotCommissionAsset)|
|time|long|t(:spotTime)|
|isBuyer|float|t(:spotIsBuyer)|
|isMaker|float|t(:spotIsMaker)|
|symbolName|string|t(:spotSymbolName)|
|matchOrderId|long|t(:spot_match_order_id)|
|fee|object|t(:spot_fee)|
|feeTokenId|string|t(:spotFeeTokenId)|
|feeAmount|float|t(:spot_fee)|
|makerRebate|float|t(:spotMakerRebate)|


<p class="fake_header">fee object</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|feeTokenId|long|t(:spotFeeTokenId)|
|feeTokenName|string|t(:spotFeeTokenName)|
|fee|float|t(:spot_fee)|
