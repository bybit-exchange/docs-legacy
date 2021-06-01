# t(:accountdata)
t(:account_para)

### t(:spotOrderCreate)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/spot/v1/order \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","side"="Buy","symbol"="ETHUSDT","order_type":"Market","qty":10,"time_in_force":"GoodTillCancel","timestamp":{timestamp},"sign":"{sign}"}'

```

```python

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
        "clientOrderId": "162073788655749",
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
<code><span id=vpoCreate>/spot/v1/order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol)|<b>true</b>|string|t(:spotSymbol)|
|qty|<b>true</b>|number|t(:spotQuantity)|
|t(:row_parameter_side)|<b>true</b>|string|t(:spotSide)|
|t(:row_parameter_type)|<b>true</b>|string|t(:spotOrderType)|
|t(:row_parameter_timeInForce)|false|string|t(:spotTimeInForce)|
|price|false|number|t(:spotPrice)|
|order_link_id|false|string|t(:tOrderClientOrdID)|



<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|integer|t(:spotOrderID)|
|order_link_id|string|t(:tOrderClientOrdID)
|symbol|string|t(:spotSymbol)|
|transactTime|int|t(:spotTransactTime)|
|price|float|t(:spotPrice)|
|origQty|float|t(:spotOriQty)|
|executedQty|float|t(:spotExecQty)|
|avgPrice|float|t(:spotAvgPrice)|
|type|string|t(:spotType)|
|side|string|t(:spotSide)|
|status|string|t(:spotStatus)|
|timeInForce|string|t(:spotTimeInForce)|

### t(:spot_get_order)
> t(:codequote_curlExample)

```console
```

```python
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
        "clientOrderId": "162081160171552",
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

t(:spot_get_order)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpoList>/spot/v1/order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|orderId|OPTIONAL|string|t(:spotOrderID)|
|order_link_id|OPTIONAL|string|t(:tOrderClientOrdID)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|accountId|long |t(:spotAccountId)|
|exchangeId|long|t(:spotOrderID)|
|symbol|string|t(:spotSymbol)|
|symbolName|string|t(:spotSymbol)|
|order_link_id|string|t(:spotOrderLinkId)|
|orderId|long|t(:spotOrderId)|
|price|float|t(:spotPrice)|
|origQty|float|t(:spotOriQty)|
|executedQty|float|t(:spotExecQty)|
|cummulativeQuoteQty|float|t(:spotCummulativeQuoteQty)|
|avgPrice|float|t(:spotAvgPrice)|
|status|string|t(:spotStatus)|
|timeInForce|string|t(:spotTimeInForce)|
|type|string|t(:spotType)|
|side|string|t(:spotSide)|
|stopPrice|float|t(:spotStopPrice)|
|icebergQty|float|t(:spotIcebergQty)|
|time|long|t(:spotTime)|
|updateTime|long|t(:spotUpdateTime)|
|isWorking|boolean|t(:spotIsWorking)|


### t(:cancel_spot_order)
> t(:codequote_curlExample)

```console
```

```python

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
        "clientOrderId": "162081160171552",
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
<code><span id=vpoCancel>/spot/v1/order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|orderId|false|string|t(:spotOrderID)|
|order_link_id|false|string|t(:tOrderClientOrdID)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|integer|t(:spotOrderID)|
|order_link_id|string|t(:tOrderClientOrdID)
|symbol|string|t(:spotSymbol)|
|status|string|t(:spotStatus)|



### t(:cancel_spot_order)
> t(:codequote_curlExample)

```console

```

```python

```

> t(:codequote_responseExample)

```javascript
{
    success: true
}
```


<p class="fake_header">t(:httprequest)</p>
DELETE
<code><span id=vpoCancel>/spot/api/order/batch_cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|accountId|false|long|t(:spotAccountId)|
|symbol|false|string|t(:spotSymbol)|
|side|false|string|t(:side)|


### t(:spot_order_list)
> t(:codequote_curlExample)

```console
```

```python
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
            "clientOrderId": "162080709527252",
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
            "clientOrderId": "162063873503148",
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
<code><span id=vpoCancelAll>/spot/v1/open_orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancelAll"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|false|string|t(:spotSymbol)|
|orderId|false|string|t(:spotOrderID)|
|limit|false|integer|t(:spot_order_list_limit)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|accountId|long |t(:spotAccountId)|
|exchangeId|long|t(:spotOrderID)|
|symbol|string|t(:spotSymbol)|
|symbolName|string|t(:spotSymbol)|
|order_link_id|string|t(:spotOrderLinkId)|
|orderId|long|t(:spotOrderId)|
|price|float|t(:spotPrice)|
|origQty|float|t(:spotOriQty)|
|executedQty|float|t(:spotExecQty)|
|cummulativeQuoteQty|float|t(:spotCummulativeQuoteQty)|
|avgPrice|float|t(:spotAvgPrice)|
|status|string|t(:spotStatus)|
|timeInForce|string|t(:spotTimeInForce)|
|type|string|t(:spotType)|
|side|string|t(:spotSide)|
|stopPrice|float|t(:spotStopPrice)|
|icebergQty|float|t(:spotIcebergQty)|
|time|long|t(:spotTime)|
|updateTime|long|t(:spotUpdateTime)|
|isWorking|boolean|t(:spotIsWorking)|




### t(:spot_history_orders)
> t(:codequote_curlExample)

```console

```

```python
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
            "clientOrderId": "1620615771764",
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


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpoReplace>/spot/v1//history-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoReplace"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|orderType|false|string|t(:spotOrderType)|
|symbol|false|string|t(:spotSymbol)|
|orderId|false|string|t(:spotOrderID)|
|limit|false|integer|t(:spot_order_list_limit)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|accountId|long |t(:spotAccountId)|
|exchangeId|long|t(:spotOrderID)|
|symbol|string|t(:spotSymbol)|
|symbolName|string|t(:spotSymbol)|
|order_link_id|string|t(:spotOrderLinkId)|
|orderId|long|t(:spotOrderId)|
|price|float|t(:spotPrice)|
|origQty|float|t(:spotOriQty)|
|executedQty|float|t(:spotExecQty)|
|cummulativeQuoteQty|float|t(:spotCummulativeQuoteQty)|
|avgPrice|float|t(:spotAvgPrice)|
|status|string|t(:spotStatus)|
|timeInForce|string|t(:spotTimeInForce)|
|type|string|t(:spotType)|
|side|string|t(:spotSide)|
|stopPrice|float|t(:spotStopPrice)|
|icebergQty|float|t(:spotIcebergQty)|
|time|long|t(:spotTime)|
|updateTime|long|t(:spotUpdateTime)|
|isWorking|boolean|t(:spotIsWorking)|




### t(:spot_my_trades)
> t(:codequote_curlExample)

```console
```

```python
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
          "symbol": "ETHBTC",
          "id": 28457,
          "orderId": 100234,
          "price": "4.00000100",
          "qty": "12.00000000",
          "commission": "10.10000000",
          "commissionAsset": "ETH",
          "time": 1499865549590,
          "isBuyer": true,
          "isMaker": false
       }
    ]
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpOrder>/spot/v1/myTrades</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|true|string|t(:spotSymbol)|
|limit|false|integer|t(:spot_order_list_limit)|
|fromId|false|integer|t(:spot_from_id)|
|toId|false|integer|t(:spot_to_id)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|symbol|string|t(:spotSymbol)|
|id| int |t(:spotId)|
|orderId|integer|t(:spotOrderID)|
|price|float|t(:spotPrice)|
|qty|float|t(:spotQty)|
|commission|float|t(:spotCommission)|
|commissionAsset|float|t(:spotCommissionAsset)|
|time|long|t(:spotTime)|
|isBuyer|float|t(:spotIsBuyer)|
|isMaker|float|t(:spotIsMaker)|
