# t(:accountdata)
t(:account_para)

### t(:usdcPlaceOrder)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/option//usdc/openapi/private/v1/place-order \
-H "Content-Type: application/json" \
-D '{"outRequestId":"021f276a-0a5f-4f35-9859-5f32353ce0ad","symbol":"BTC-26NOV21-58000-P","orderType":"Limit","side":"Buy","orderQty":"1","orderPrice":"1","timeInForce":"GoodTillCancel","placeMode":1,"placeType":1}'
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
        "orderType": "Limit",
        "side": "Buy",
        "orderPrice": "1",
        "orderLinkId": "162073788655749",
        "iv": "100",
        "placeMode": 1,
        "placeType": 1,
        "timeInForce": "PostOnly",
        "outRequestId": "1620737886573",
        "reduceOnly": true,
        "orderPrice": "20000",
        "orderQty": "10"
    }
}
```
t(:placeOrderInfo)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/{category}/usdc/openapi/private/v1/place-order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|orderType|<b>true</b>|string|t(:usdcOrderType)|
|side|<b>true</b>|string|t(:side)|
|orderPrice|false|string|t(:usdcPlaceOrderPrice)|
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
|tptriggerby|false|number|t(:usdcTptriggerby)|
|slTriggerBy|false|string|t(:usdcSlTriggerBy)|
|triggerPrice|false|string|t(:triggerPrice)|
|triggerBy|false|number|t(:usdcTriggerBy)|
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

t(:usdcBatchOrdersDesc)

```console
curl https://api.bybit.com/option/usdc/openapi/private/v1/batch-place-order \
-H "Content-Type: application/json" \
-D '{"orderRequest":[{"outRequestId":"4c77b34a-9093-4bca-9cad-727cd6efed7e","symbol":"Hello","orderType":"Limit","side":"Buy","orderQty":"1","orderPrice":"1","timeInForce":"GoodTillCancel","placeMode":1,"placeType":1}]}'


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

Option only.

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/option/usdc/openapi/private/v1/batch-place-order</span></code>
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
|orderPrice|false|string|t(:usdcPlaceOrderPrice)|
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
|tptriggerby|false|number|t(:usdcTptriggerby)|
|slTriggerBy|false|string|t(:usdcSlTriggerBy)|
|triggerPrice|false|string|t(:triggerPrice)|
|triggerBy|false|number|t(:usdcTriggerBy)|
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
curl https://api.bybit.com/option/usdc/openapi/private/v1/replace-order \
-H "Content-Type: application/json" \
-D '{"outRequestId":"89befe89-0869-405a-a07c-2599324d009d","symbol":"BTC-26NOV21-58000-P","orderId":"be6c87be-da18-4876-9a64-6b7ccc859071","orderQty":"1","orderPrice":"1"}'


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
<code><span id=vpoCreate>/{category}/usdc/openapi/private/v1/replace-order</span></code>
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
|tptriggerby|false|string|t(:usdcTptriggerby)|
|slTriggerBy|false|string|t(:usdcSlTriggerBy)|
|orderFilter|false|string|t(:usdcOrderFilter)|
|triggerPrice|false|string|t(:triggerPrice)|



<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)



### t(:usdcBatchReplaceOrders)


```console
curl https://api.bybit.com/option/usdc/openapi/private/v1/batch-replace-orders \
-H "Content-Type: application/json" \
-D '{"replaceOrderRequest":[{"outRequestId":"89befe89-0869-405a-a07c-2599324d009d","symbol":"BTC-26NOV21-58000-P","orderId":"be6c87be-da18-4876-9a64-6b7ccc859071","orderQty":"1","orderPrice":"1"}]}'


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

Option only.
<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/option/usdc/openapi/private/v1/batch-replace-orders</span></code>
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
|tptriggerby|false|string|t(:usdcTptriggerby)|
|slTriggerBy|false|string|t(:usdcSlTriggerBy)|
|orderFilter|false|string|t(:usdcOrderFilter)|
|triggerPrice|false|string|t(:triggerPrice)|



<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)



### t(:usdcCancelOrder)


```console
curl https://api.bybit.com/option/usdc/openapi/private/v1/cancel-order \
-H "Content-Type: application/json" \
-D '{"outRequestId":"01f90031-4697-4b1f-affe-eb0032c58212","symbol":"BTC-26NOV21-58000-P","orderId":"ec6d8081-8950-491b-bf43-22ddb09df0fc"}'

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
<code><span id=vpoCreate>/{category}/usdc/openapi/private/v1/cancel-order</span></code>
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
curl https://api.bybit.com/option/usdc/openapi/private/v1/batch-cancel-orders \
-H "Content-Type: application/json" \
-D '{"cancelRequest":[{"outRequestId":"0d3a1844-a7ba-4a95-9e2a-47843112f412","symbol":"BTC-26NOV21-58000-P","orderId":"1a69653f-c3c7-40b4-a492-17316a2086a2"}]}'


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

Option only.
<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/option/usdc/openapi/private/v1/batch-cancel-orders</span></code>
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
curl https://api.bybit.com/option/usdc/openapi/private/v1/cancel-order \
-H "Content-Type: application/json" \
-D '{"outRequestId":"cdde8186-fda8-457d-9451-5b83b7780ad4"}'


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
<code><span id=vpoCreate>{category}/usdc/openapi/private/v1/cancel-all</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|outRequestId|<b>true</b>|string|t(:optionOutRequestId)|

<p>
t(:cancelAllResponse)
</p>

### t(:usdcQryUnOrPartFilled)


```console
curl https://api.bybit.com/option/usdc/openapi/private/v1/query-active-orders \
-H "Content-Type: application/json" \
-D '{"category":"option"}'

```

```python

```


> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"OK",
    "result":{
    "resultTotalSize":1,
      "cursor":"e3d0eff2-7567-4ca1-af1c-9eb9a39ac119%3A1634291502127%2C0b9c9c0c-4098-4d30-a266-6aa87dc26f7f%3A1634285036815",
      "dataList":[
      {
        "orderId":"e3d0eff2-7567-4ca1-af1c-9eb9a39ac119",
        "orderLinkId":"",
        "createdAt":"1634291502127",
        "symbol":"BTC-16OCT21-21000-P",
        "orderType":"Limit",
        "side":"Buy",
        "orderQty":"2.10",
        "orderPrice":"30.0",
        "iv":"852.00%",
        "timeInForce":"GoodTillCancel",
        "leavesQty":"0.10",
        "leavesValue":"3.0000",
        "cumExecQty":"2.00",
        "cumExecValue":"60.0000",
        "cumExecFee":"6.0000",
        "im":"69.3000",
        "orderStatus":"PartiallyFilled",
        "takeProfit":"",
        "stopLoss":"",
        "tpTriggerBy":"",
        "slTriggerBy":"",
        "lastExecPrice":"",
        "basePrice":"",
        "triggerPrice":"",
        "triggerBy":"",
        "reduceOnly":0,
        "closeOnTrigger":""
      }
    ]
  }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/option/usdc/openapi/private/v1/query-active-orders</span></code>
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
|resultTotalSize|number|t(:resultTotalSize)|
|cursor|string|t(:cursor)|
|dataList|list|t(:dataList)|

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
|tpTriggerBy|string|t(:usdcTptriggerby)|
|slTriggerBy|string|t(:usdcSlTriggerBy)|
|lastExecPrice|string|t(:lastExecPrice)|
|basePrice|string|t(:basePrice)|
|triggerPrice|string|t(:triggerPrice)|
|triggerBy|string|t(:usdcTriggerBy)|
|reduceOnly|string|t(:reduceOnly)|
|closeOnTrigger|string|t(:closeOnTrigger)|
|createdAt|number|t(:createdAt)|
|cursor|string|t(:cursor)|



### t(:usdcQryOrderHistory)


```console

curl https://api.bybit.com/option/usdc/openapi/private/v1/query-order-history \
-H "Content-Type: application/json" \
-D '{"category":"option"}'

```

```python

```


> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"OK",
    "result":{
    "resultTotalSize":1,
      "cursor":"5e42be7e-c92f-4388-91fc-30ec1f321e32%3A1634286322771%2C6ad08ad0-14d8-43a6-9a38-6a01d7d7c833%3A1634285916577",
      "dataList":[
      {
        "orderId":"5e42be7e-c92f-4388-91fc-30ec1f321e32",
        "orderLinkId":"",
        "createdAt":"1634286322771",
        "updatedAt":"1634286322771",
        "symbol":"BTC-22OCT21-30000-C",
        "orderType":"Limit",
        "side":"Sell",
        "orderQty":"0.30",
        "orderPrice":"39000.0",
        "iv":"958.70%",
        "timeInForce":"GoodTillCancel",
        "leavesQty":"0.00",
        "cumExecQty":"0.30",
        "cumExecFee":"4.4338",
        "im":"0.0000",
        "cashFlow":"11700.0000",
        "realisedPnl":"0.0000",
        "orderStatus":"Filled",
        "closeOnTrigger":"",
        "reduceOnly":0,
        "takeProfit":"",
        "stopLoss":"",
        "tpTriggerBy":"",
        "slTriggerBy":"",
        "basePrice":"",
        "triggerPrice":"",
        "triggerBy":""
      }
    ]
  }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/option/usdc/openapi/private/v1/query-order-history</span></code>
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
|resultTotalSize|number|t(:resultTotalSize)|
|cursor|string|t(:cursor)|
|dataList|list|t(:dataList)|

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
|tpTriggerBy|string|t(:usdcTptriggerby)|
|slTriggerBy|string|t(:usdcSlTriggerBy)|
|lastExecPrice|string|t(:lastExecPrice)|
|basePrice|string|t(:basePrice)|
|triggerPrice|string|t(:triggerPrice)|
|triggerBy|string|t(:usdcTriggerBy)|
|reduceOnly|bool|t(:reduceOnly)|
|closeOnTrigger|string|t(:closeOnTrigger)|
|createdAt|number|t(:createdAt)|
|updatedAt|number|t(:updatedAt)|
|cursor|string|t(:cursor)|







