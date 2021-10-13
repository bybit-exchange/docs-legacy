# t(:accountdata)
t(:account_para)

### t(:usdcPlaceOrder)
> t(:codequote_curlExample)

```console

```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "",
    "extCode": null,
    "extInfo": null,
    "result": {
        "symbol": "ETHUSDT",
        "orderType": "ETHUSDT",
        "side": "ETHUSDT",
        "orderPrice": "ETHUSDT",
        "orderLinkId": "162073788655749",
        "iv": "100",
        "placeMode": "1620737886573",
        "placeType": "1620737886573",
        "timeInForce": "1620737886573",
        "outRequestId": "1620737886573",
        "reduceOnly": "1620737886573",
        "orderPrice": "20000",
        "orderQty": "10",
        "executedQty": "0",
        "status": "NEW",
        "timeInForce": "GTC",
        "orderType": "LIMIT",
        "side": "Buy"
    }
}
```
t(:placeOrderInfo)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/usdc/openapi/private/v1/place-order/{category}</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|orderType|<b>true</b>|string|t(:usdcOrderType)|
|side|<b>true</b>|string|t(:side)|
|orderPrice|false|string|t(:usdcOrderPrice)|
|orderQty|<b>true</b>|string|t(:usdcOrderQty)|
|iv|false|string|t(:optionIv)|
|placeMode|false|string|t(:optionPlaceMode)|
|placeType|false|string|t(:optionPlaceType)|
|timeInForce|false|string|t(:row_parameter_time_in_force)|
|outRequestId|false|string|t(:optionOutRequestId)|
|orderLinkId|false|string|t(:orderLinkId)|
|reduceOnly|false|bool|t(:reduceOnly)|
|closeOnTrigger|false|bool|t(:closeOnTrigger)|
|takeProfit|false|string|t(:takeProfit)|
|stopLoss|false|string|t(:stopLoss)|
|tptriggerby|false|number|t(:tptriggerby)|
|slTriggerBy|false|string|t(:slTriggerBy)|
|triggerPrice|false|string|t(:triggerPrice)|
|triggerBy|false|number|t(:triggerBy)|
|positionIdx|false|number|t(:positionIdx)|
|mmp|false|string|t(:mmp)|



<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)
|symbol|string|t(:usdcSymbol)|
|orderPrice|string|t(:usdcOrderPrice)|
|orderQty|string|t(:usdcOrderQty)|
|orderType|string|t(:uscdOrderType)|
|side|string|t(:side)|

### t(:usdcBatchOrders)
支持用户批量下单，一次请求里最多包含4条记录。

```console

```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "",
    "extCode": null,
    "extInfo": null,
    "result": [{
        "symbol": "ETHUSDT",
        "orderType": "ETHUSDT",
        "side": "ETHUSDT",
        "orderPrice": "ETHUSDT",
        "orderLinkId": "162073788655749",
        "iv": "100",
        "placeMode": "1620737886573",
        "placeType": "1620737886573",
        "timeInForce": "1620737886573",
        "outRequestId": "1620737886573",
        "reduceOnly": "1620737886573",
        "orderPrice": "20000",
        "orderQty": "10",
        "executedQty": "0",
        "status": "NEW",
        "timeInForce": "GTC",
        "orderType": "LIMIT",
        "side": "Buy"
    }]
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/usdc/openapi/private/v1/batch-place-order/{category}</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|orderRequest|<b>true</b>|list|t(:usdcList)|

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|orderType|<b>true</b>|string|t(:usdcOrderType)|
|side|<b>true</b>|string|t(:side)|
|orderPrice|false|string|t(:usdcOrderPrice)|
|orderQty|<b>true</b>|string|t(:usdcOrderQty)|
|iv|false|string|t(:optionIv)|
|placeMode|false|string|t(:optionPlaceMode)|
|placeType|false|string|t(:optionPlaceType)|
|timeInForce|false|string|t(:row_parameter_time_in_force)|
|outRequestId|false|string|t(:optionOutRequestId)|
|orderLinkId|false|string|t(:orderLinkId)|
|reduceOnly|false|bool|t(:reduceOnly)|
|closeOnTrigger|false|bool|t(:closeOnTrigger)|
|takeProfit|false|number|t(:takeProfit)|
|stopLoss|false|number|t(:stopLoss)|
|tptriggerby|false|number|t(:tptriggerby)|
|slTriggerBy|false|string|t(:slTriggerBy)|
|triggerPrice|false|string|t(:triggerPrice)|
|triggerBy|false|number|t(:triggerBy)|
|positionIdx|false|number|t(:positionIdx)|
|mmp|false|string|t(:mmp)|



<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)
|symbol|string|t(:usdcSymbol)|
|orderPrice|string|t(:usdcOrderPrice)|
|orderQty|string|t(:usdcOrderQty)|
|orderType|string|t(:uscdOrderType)|
|side|string|t(:side)|

### t(:usdcReplaceOrder)


```console

```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "",
    "extCode": null,
    "extInfo": null,
    "result": {
        "outRequestId": "out1111111",
        "symbol": "ETHUSDT",
        "orderId": "123",
        "orderLinkId": "162073788655749",
        "orderPrice": "100.1",
        "orderQty": "10"
    }
}
```

t(:replaceInfo)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/usdc/openapi/private/v1/replace-order/{category}</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|outRequestId|<b>true</b>|string|t(:optionOutRequestId)|
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|orderId|false|string|t(:usdcReplaceOrderId)|
|orderLinkId|false|string|t(:usdcOrderLinkId)|
|orderPrice|false|string|t(:usdcOrderPrice)|
|orderQty|false|string|t(:usdcOrderQty)|
|iv|false|string|t(:optionIv)|
|takeProfit|false|string|t(:takeProfit)|
|stopLoss|false|string|t(:stopLoss)|
|tptriggerby|false|string|t(:tptriggerby)|
|slTriggerBy|false|string|t(:slTriggerBy)|
|orderFilter|false|string|t(:usdcOrderFilter)|
|triggerPrice|false|string|t(:triggerPrice)|



<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)



### t(:usdcBatchReplaceOrders)


```console

```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "",
    "extCode": null,
    "extInfo": null,
    "result": [{
        "outRequestId": "out1111111",
        "symbol": "ETHUSDT",
        "orderId": "123",
        "orderLinkId": "162073788655749",
        "orderPrice": "100.1",
        "orderQty": "10"
    },{
    "outRequestId": "out1111111",
    "symbol": "ETHUSDT",
    "orderId": "123",
    "orderLinkId": "162073788655749",
    "orderPrice": "100.1",
    "orderQty": "10"
  }]
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/usdc/openapi/private/v1/batch-replace-order/{category}</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|replaceOrderRequest|<b>true</b>|list|t(:usdcList)|


|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|outRequestId|<b>true</b>|string|t(:optionOutRequestId)|
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|orderId|false|string|t(:usdcReplaceOrderId)|
|orderLinkId|false|string|t(:usdcOrderLinkId)|
|orderPrice|false|string|t(:usdcOrderPrice)|
|orderQty|false|string|t(:usdcOrderQty)|
|iv|false|string|t(:optionIv)|
|takeProfit|false|string|t(:takeProfit)|
|stopLoss|false|string|t(:stopLoss)|
|tptriggerby|false|string|t(:tptriggerby)|
|slTriggerBy|false|string|t(:slTriggerBy)|
|orderFilter|false|string|t(:usdcOrderFilter)|
|triggerPrice|false|string|t(:triggerPrice)|



<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)



### t(:usdcCancelOrder)


```console

```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "",
    "extCode": null,
    "extInfo": null,
    "result": {
        "orderId": "123"
    }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/usdc/openapi/private/v1/cancel-order/{category}</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|outRequestId|false|string|t(:optionOutRequestId)|
|orderId|false|string|t(:usdcReplaceOrderId)|
|orderLinkId|false|string|t(:usdcOrderLinkId)|
|orderFilter|false|string|t(:usdcOrderFilter)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|





### t(:usdcBatchCancelOrders)



```console

```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "",
    "extCode": null,
    "extInfo": null,
    "result": [{
        "orderId": "123"
    }]
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/usdc/openapi/private/v1/batch-cancel-order/{category}</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|cancelRequest|<b>true</b>|list|t(:usdcList)|

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|outRequestId|false|string|t(:optionOutRequestId)|
|orderId|false|string|t(:usdcReplaceOrderId)|
|orderLinkId|false|string|t(:usdcOrderLinkId)|
|orderFilter|false|string|t(:usdcOrderFilter)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|



### t(:usdcCancelAll)


```console

```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "extCode": null,
    "extInfo": null,
    "result": null
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/usdc/openapi/private/v1/cancel-all/{category}</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>
|:----- |:-------|:-----|----- |
|outRequestId|false|string|t(:optionOutRequestId)|

t(:cancelAllResponse)


### t(:usdcQryUnOrPartFilled)


```console

```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "",
    "extCode": null,
    "extInfo": null,
    "result": {
        "outRequestId": "out1111111",
        "symbol": "ETHUSDT",
        "orderId": "123",
        "orderLinkId": "162073788655749",
        "orderPrice": "100.1",
        "orderQty": "10"
    }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/usdc/openapi/private/v1/query-open-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category|<b>true</b>|string|t(:usdcCategory)|
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|orderId|false|string|t(:usdcOrderId)|
|orderLinkId|false|string|t(:orderLinkId)|
|orderFilter|false|string|t(:usdcOrderFilter)|
|direction|false|string|t(:direction)|
|limit|false|number|t(:row_comment_limit)|
|cursor|false|string|t(:cursor)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)|
|symbol|string|t(:usdcSymbol)|
|orderType|string|t(:usdcOrderType)|
|side|string|t(:side)|
|orderQty|string|t(:usdcOrderQty)|
|orderPrice|string|t(:usdcOrderPrice)|
|iv|string|t(:optionIv)|
|timeInForce|string|t(:row_parameter_time_in_force)|
|leavesValue|string|t(:leavesValue)|
|cumExecQty|string|t(:cumExecQty)|
|cumExecValue|string|t(:cumExecValue)|
|cumExecFee|string|t(:cumExecFee)|
|im|string|t(:im)|
|orderStatus|string|t(:orderStatus)|
|takeProfit|string|t(:takeProfit)|
|stopLoss|string|t(:stopLoss)|
|tpTriggerBy|string|t(:tptriggerby)|
|slTriggerBy|string|t(:slTriggerBy)|
|lastExecPrice|string|t(:lastExecPrice)|
|basePrice|string|t(:basePrice)|
|triggerPrice|string|t(:triggerPrice)|
|triggerBy|string|t(:triggerBy)|
|reduceOnly|string|t(:reduceOnly)|
|closeOnTrigger|string|t(:closeOnTrigger)|
|createdAt|number|t(:createdAt)|
|cursor|string|t(:cursor)|



### t(:usdcQryOrderHistory)


```console

```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "",
    "extCode": null,
    "extInfo": null,
    "result": 
        [{
        "outRequestId": "out1111111",
        "symbol": "ETHUSDT",
        "orderId": "123",
        "orderLinkId": "162073788655749",
        "orderPrice": "100.1",
        "orderQty": "10"
    }]
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/usdc/openapi/private/v1/query-order-history</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category|<b>true</b>|string|t(:usdcCategory)|
|symbol|false|string|t(:usdcSymbol)|
|orderId|false|string|t(:usdcOrderId)|
|orderLinkId|false|string|t(:orderLinkId)|
|orderStatus|false|string|t(:orderStatus)|
|orderFilter|false|string|t(:usdcOrderFilter)|
|direction|false|string|t(:direction)|
|limit|false|number|t(:row_comment_limit)|
|cursor|false|string|t(:cursor)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)|
|symbol|string|t(:usdcSymbol)|
|orderType|string|t(:usdcOrderType)|
|side|string|t(:side)|
|orderQty|string|t(:usdcOrderQty)|
|orderPrice|string|t(:usdcOrderPrice)|
|iv|string|t(:optionIv)|
|timeInForce|string|t(:row_parameter_time_in_force)|
|leavesValue|string|t(:leavesValue)|
|cumExecQty|string|t(:cumExecQty)|
|cumExecValue|string|t(:cumExecValue)|
|cumExecFee|string|t(:cumExecFee)|
|im|string|t(:im)|
|cashFlow|string|t(:cashFlow)|
|realisedPnl|string|t(:realisedPnl)|
|orderStatus|string|t(:orderStatus)|
|takeProfit|string|t(:takeProfit)|
|stopLoss|string|t(:stopLoss)|
|tpTriggerBy|string|t(:tptriggerby)|
|slTriggerBy|string|t(:slTriggerBy)|
|lastExecPrice|string|t(:lastExecPrice)|
|basePrice|string|t(:basePrice)|
|triggerPrice|string|t(:triggerPrice)|
|triggerBy|string|t(:triggerBy)|
|reduceOnly|bool|t(:reduceOnly)|
|closeOnTrigger|string|t(:closeOnTrigger)|
|createdAt|number|t(:createdAt)|
|updatedAt|number|t(:updatedAt)|
|cursor|string|t(:cursor)|







