# t(:accountdata)
t(:account_para)

## t(:usdcTradeApi)
### t(:usdcPlaceOrder)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/place-order \
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
        "symbol": "BTC-26NOV21-58000-P",
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
<code><span id=uopvPlace>/option/usdc/openapi/private/v1/place-order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvPlace"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

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
|t(:row_parameter_timeInForce)|false|string|t(:row_comment_timeInForce)|
|outRequestId|false|string|t(:optionOutRequestId)|
|orderLinkId|<b>true</b>|string|t(:orderLinkId)|
|reduceOnly|false|bool|t(:reduceOnly)|
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
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/batch-place-order \
-H "Content-Type: application/json" \
-D '{"orderRequest":[{"outRequestId":"4c77b34a-9093-4bca-9cad-727cd6efed7e","symbol":"BTC-26NOV21-58000-P","orderType":"Limit","side":"Buy","orderQty":"1","orderPrice":"1","timeInForce":"GoodTillCancel","placeMode":1,"placeType":1}]}'


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
        "symbol": "BTC-26NOV21-58000-P",
        "orderType": "Limit",
        "side": "Buy",
        "orderPrice": "1",
        "orderLinkId": "162073788655749",
        "placeMode": "1",
        "placeType": "1",
        "timeInForce": "PostOnly",
        "outRequestId": "1620737886573",
        "orderPrice": "1",
        "orderQty": "1",
    }]
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvBatchPlace>/option/usdc/openapi/private/v1/batch-place-order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvBatchPlace"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

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
|t(:row_parameter_timeInForce)|false|string|t(:row_comment_timeInForce)|
|outRequestId|false|string|t(:optionOutRequestId)|
|orderLinkId|false|string|t(:orderLinkId)|
|reduceOnly|false|bool|t(:reduceOnly)|
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
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/replace-order \
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
        "outRequestId": "89befe89-0869-405a-a07c-2599324d009d",
        "symbol": "BTC-26NOV21-58000-P",
        "orderId": "be6c87be-da18-4876-9a64-6b7ccc859071"
    }
}
```

t(:replaceInfo)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvReplace>/option/usdc/openapi/private/v1/replace-order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvReplace"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|outRequestId|<b>true</b>|string|t(:optionOutRequestId)|
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|orderId|<b>true</b>|string|t(:usdcReplaceOrderId)|
|orderLinkId|false|string|t(:usdcOrderLinkId)|
|orderPrice|false|string|t(:usdcOrderPrice)|
|orderQty|false|string|t(:usdcOrderQty)|
|iv|false|string|t(:optionIv)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)

### t(:usdcBatchReplaceOrders)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/batch-replace-orders \
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
        "outRequestId": "89befe89-0869-405a-a07c-2599324d009d",
        "symbol": "BTC-26NOV21-58000-P",
        "orderId": "be6c87be-da18-4876-9a64-6b7ccc859071"
    }]
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvBatchReplace>/option/usdc/openapi/private/v1/batch-replace-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvBatchReplace"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|replaceOrderRequest|<b>true</b>|list|t(:usdcList)|


|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|outRequestId|<b>true</b>|string|t(:optionOutRequestId)|
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|orderId|<b>true</b>|string|t(:usdcReplaceOrderId)|
|orderLinkId|false|string|t(:usdcOrderLinkId)|
|orderPrice|false|string|t(:usdcOrderPrice)|
|orderQty|false|string|t(:usdcOrderQty)|
|iv|false|string|t(:optionIv)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)



### t(:usdcCancelOrder)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/cancel-order \
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
        "orderId": "ec6d8081-8950-491b-bf43-22ddb09df0fc"
    }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvCancel>/option/usdc/openapi/private/v1/cancel-order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvCancel"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|outRequestId|false|string|t(:optionOutRequestId)|
|orderId|<b>true</b>|string|t(:usdcReplaceOrderId)|
|orderLinkId|false|string|t(:usdcOrderLinkId)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|


### t(:usdcBatchCancelOrders)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/batch-cancel-orders \
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
        "orderId": "1a69653f-c3c7-40b4-a492-17316a2086a2"
    }]
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvBatchCancel>/option/usdc/openapi/private/v1/batch-cancel-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvBatchCancel"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|cancelRequest|<b>true</b>|list|t(:usdcList)|

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|outRequestId|false|string|t(:optionOutRequestId)|
|orderId|<b>true</b>|string|t(:usdcReplaceOrderId)|
|orderLinkId|false|string|t(:usdcOrderLinkId)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|



### t(:usdcCancelAll)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/cancel-order \
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
<code><span id=uopvCancelAll>/option/usdc/openapi/private/v1/cancel-all</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvCancelAll"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|outRequestId|<b>true</b>|string|t(:optionOutRequestId)|

<p>
t(:cancelAllResponse)
</p>

### t(:usdcQryUnOrPartFilled)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/query-active-orders \
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
<code><span id=uopvQueryActive>/option/usdc/openapi/private/v1/query-active-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvQueryActive"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category|<b>true</b>|string|t(:usdcCategory)|
|symbol|false|string|t(:usdcSymbol)|
|orderId|false|string|t(:usdcOrderId)|
|orderLinkId|false|string|t(:orderLinkId)|
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
|t(:row_parameter_timeInForce)|string|t(:row_comment_timeInForce)|
|leavesValue|string|t(:leavesValue)|
|cumExecQty|string|t(:cumExecQty)|
|cumExecValue|string|t(:cumExecValue)|
|cumExecFee|string|t(:cumExecFee)|
|im|string|t(:im)|
|orderStatus|string|t(:orderStatus)|
|reduceOnly|string|t(:reduceOnly)|
|createdAt|number|t(:createdAt)|
|cursor|string|t(:cursor)|


### t(:usdcQryOrderHistory)

```console

curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/query-order-history \
-H "Content-Type: application/json" \
-D '{"category":"OPTION"}'

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
<code><span id=uopvQueryHistory>/option/usdc/openapi/private/v1/query-order-history</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvQueryHistory"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category|<b>true</b>|string|t(:usdcCategory)|
|symbol|false|string|t(:usdcSymbol)|
|orderId|false|string|t(:usdcOrderId)|
|orderLinkId|false|string|t(:orderLinkId)|
|orderStatus|false|string|t(:orderStatus)|
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
|t(:row_parameter_timeInForce)|string|t(:row_comment_timeInForce)|
|leavesValue|string|t(:leavesValue)|
|cumExecQty|string|t(:cumExecQty)|
|cumExecValue|string|t(:cumExecValue)|
|cumExecFee|string|t(:cumExecFee)|
|im|string|t(:im)|
|cashFlow|string|t(:cashFlow)|
|realisedPnl|string|t(:realisedPnl)|
|orderStatus|string|t(:orderStatus)|
|basePrice|string|t(:basePrice)|
|reduceOnly|bool|t(:reduceOnly)|
|createdAt|number|t(:createdAt)|
|updatedAt|number|t(:updatedAt)|
|cursor|string|t(:cursor)|


### t(:usdcTradeHistory)

> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/execution-list \
-H "Content-Type: application/json" \
-D '{"startTime":"1633687786728","symbol":"1633797786728","category":"OPTION","type":"Settlement","orderId":"70bc3d92-009c-464b-8399-010b9d4aac2b"}'
```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode":0,
    "retMsg":"Success.",
    "result":{
        "resultTotalSize":1,
        "cursor":"512e57a4-758d-57c5-8531-4b639e737211%3A1637053904869%3A9544%2C512e57a4-758d-57c5-8531-4b639e737211%3A1637053904869%3A9544",
        "dataList":[
            {
                "orderId":"70bc3d92-009c-464b-8399-010b9d4aac2b",
                "orderLinkId":"",
                "symbol":"BTC-19NOV21-55000-P",
                "execPrice":"102.00",
                "execQty":"0.010",
                "execFee":"0.1020",
                "feeRate":"0.0250%",
                "tradeTime":"1637053904869",
                "execType":"TRADE",
            }
        ]
    }
}

```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvExecution>/option/usdc/openapi/private/v1/execution-list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvExecution"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category|<b>true</b>|string|t(:usdcCategory)|
|symbol|false|string|t(:usdcSymbol)|
|orderId|false|string|t(:usdcOrderId)|
|orderLinkId|false|string|t(:usdcOrderLinkId)|
|startTime|<b>true</b>|string|t(:usdcStartTime)|
|direction|false|string|t(:direction)|
|limit|<b>true</b>|string|t(:row_comment_limit)|
|cursor|false|string|t(:cursor)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|resultTotalSize|number|t(:resultTotalSize)|
|cursor|string|t(:cursor)|
|dataList|list|t(:dataList)|

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|symbol|string|t(:usdcSymbol)
|orderId|string|t(:usdcOrderId)
|orderLinkId|string|t(:orderLinkId)
|execPrice|string|t(:tradePrice)|
|execQty|string|t(:uscdSize)|
|execFee|string|t(:fee)|
|feeRate|string|t(:feeRate)|
|tradeTime|string|t(:tradeTime)|
|execType|string|t(:execType)|


## t(:account_wallet)
t(:wallet_para)

### t(:transactionLog)

> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/query-transaction-log \
-H "Content-Type: application/json" \
-D '{"type":"TRADE","limit":1}'
```

```python

```


> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "Success.",
    "result": {
    "resultTotalSize": 1,
      "cursor": "9893%3A0%2C9893%3A0",
      "dataList": [
      {
        "transactionTime": "1638842921038",
        "symbol": "BTCPERP",
        "type": "TRADE",
        "side": "Sell",
        "tradePrice": "50830.0",
        "funding": "0.0000",
        "qty": "0.010",
        "size": "1.110",
        "fee": "0.3813",
        "cashFlow": "2.8159",
        "change": "2.4346",
        "walletBalance": "16906.4074",
        "feeRate": "0.0008",
        "orderId": "dd216843-fe5d-43bc-b2c7-ab6a5958cd90",
        "orderLinkId": "",
        "tradeId": "f256315f-c80b-5d3e-a9c3-2a1de95e9637",
        "info": ""
      }
    ]
  }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvQueryTransaction>/option/usdc/openapi/private/v1/query-transaction-log</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvQueryTransaction"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|type|<b>true</b>|string|t(:usdcTransactionType)|
|startTime|<b>true</b>|string|t(:usdcStartTime)|
|endTime|<b>true</b>|string|t(:usdcEndTime)|
|direction|false|string|t(:direction)|
|limit|<b>true</b>|string|t(:row_comment_limit)|
|cursor|false|string|t(:cursor)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|resultTotalSize|number|t(:resultTotalSize)|
|cursor|string|t(:cursor)|
|dataList|list|t(:dataList)|

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transactionTime|number|t(:transactionTime)|
|symbol|string|t(:usdcSymbol)
|type|string|t(:usdcType)|
|side|string|t(:side)|
|orderQty|string|t(:usdcOrderQty)|
|size|string|t(:uscdSize)|
|tradePrice|string|t(:tradePrice)|
|funding|string|t(:usdcFunding)|
|fee|string|t(:fee)|
|cashFlow|string|t(:cashFlow)|
|change|string|t(:usdcChange)|
|walletBalance|string|t(:cashBalance)|
|feeRate|string|t(:feeRate)|
|tradeId|string|t(:tradeId)|
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)|
|info|string|t(:usdcInfo)|


### t(:usdcAccountInfo)

For USDC Account.

> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/query-wallet-balance \

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
        "equity": "1",
        "walletBalance": "1",
        "availableBalance": "1",
        "accountIM": "162073788655749",
        "accountMM": "100",
        "totalRPL": "1620737886573",
        "totalSessionUPL": "1620737886573",
        "totalSessionRPL": "1620737886573"
    }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvQueryBalance>/option/usdc/openapi/private/v1/query-wallet-balance</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvQueryBalance"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|equity|number|t(:equity)|
|walletBalance|string|t(:cashBalance)
|availableBalance|string|t(:availableBalance)|
|marginBalance|string|t(:marginBalance)|
|accountIM|string|t(:accountIm)|
|accountMM|string|t(:accountMm)|
|totalRPL|string|t(:totalRpl)|
|totalSessionUPL|string|t(:totalSessionUpl)|
|totalSessionRPL|string|t(:totalSessionRpl)|


### t(:assetInfo)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/query-asset-info \
-H "Content-Type: application/json" \
-D '{"baseCoin":"BTC"}'

```


> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"OK",
    "result":{
    "resultTotalSize":1,
      "dataList":[
      {
        "baseCoin":"BTC",
        "totalDelta":"-0.1093",
        "totalGamma":"0.00000",
        "totalVega":"1.8799",
        "totalTheta":"-19.2038",
        "totalRPL":"-3773.8879",
        "sessionUPL":"-16.0781",
        "sessionRPL":"-13.0000",
        "im":"28940.8205",
        "mm":"14997.4532"
      }
    ]
  }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvAsset>/option/usdc/openapi/private/v1/query-asset-info</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvAsset"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|baseCoin|false|string|t(:usdcBaseCoin)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|resultTotalSize|int|t(:resultTotalSize)|
|dataList|list| t(:dataList)|

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|baseCoin|string|t(:usdcBaseCoin)|
|totalDelta|string|t(:totalDelta)
|totalGamma|string|t(:totalGamma)|
|totalVega|string|t(:totalVega)|
|totalTheta|string|t(:totalTheta)|
|im|string|t(:usdcIm)|
|mm|string|t(:usdcMm)|
|totalRpl|string|t(:totalRpl)|
|sessionUpl|string|t(:sessionUpl)|
|sessionRpl|string|t(:sessionRpl)|



### t(:queryMarginMode)
For USDC ACCOUNT.

> t(:codequote_curlExample)

```console

curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/query-margin-info \

```

```python

```


> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"OK",
    "result":{
    "marginMode":"REGULAR_MARGIN"
  }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvMargin>/option/usdc/openapi/private/v1/query-margin-info</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvMargin"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|marginMode|string|t(:usdcMarginMode)|


## t(:accountPosition)


### t(:queryPosition)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/query-position \
-H "Content-Type: application/json" \
-D '{"symbol":"BTC-22OCT21-40000-C","category":"OPTION"}'
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
      "cursor":"BTC-22OCT21-40000-C%3A1634287448443%2CBTC-22OCT21-40000-C%3A1634287448443",
      "dataList":[
      {
        "riskId":"",
        "symbol":"BTC-22OCT21-40000-C",
        "side":"Buy",
        "size":"0.20",
        "entryPrice":"19000.0",
        "sessionAvgPrice":"19000.0",
        "markPrice":"19136.49",
        "sessionUPL":"27.2974",
        "sessionRPL":"0.0000",
        "IM":"0.0000",
        "MM":"0.0000",
        "createdAt":"1634287448443",
        "updatedAt":"1634287448443",
        "tpSLMode":"",
        "positionValue":"",
        "leverage":"",
        "liqPrice":"",
        "trailingStop":"",
        "bustPrice":"",
        "occClosingFee":"",
        "trakeProfit":"",
        "stopLoss":"",
        "positionStatus":0,
        "deleverageIndicator":0,
        "orderMargin":"",
        "unrealisedPnl":"",
        "cumRealisedPnl":""
      }
    ]
  }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvPosition>/option/usdc/openapi/private/v1/query-position</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvPosition"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category|<b>true</b>|string|t(:usdcCategory)|
|symbol|false|string|t(:usdcSymbol)|
|cursor|false|string|t(:cursor)|
|direction|false|string|t(:direction)|
|limit|number|string|t(:usdcPositionLimit)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|resultTotalSize|number|t(:resultTotalSize)|
|cursor|string|t(:cursor)|
|dataList|list|t(:dataList)|

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|riskId|string|riskId|
|symbol|string|t(:usdcSymbol)|
|side|string|t(:side)|
|size|string|t(:uscdSize)
|entryPrice|string|t(:entryPrice)
|sessionAvgPrice|string|t(:sessionAvgPrice)|
|markPrice|string|t(:markPrice)|
|positionPnl|string|t(:positionPnl)|
|sessionUpl|string|t(:sessionUpl)|
|sessionRpl|string|t(:sessionRpl)|
|IM|string|t(:usdcIm)|
|MM|string|t(:usdcMm)|
|createdAt|string|t(:createdAt)|
|updatedAt|string|t(:updatedAt)|
|tpSlMode|string|t(:tpSlMode)|
|positionValue|string|t(:positionValue)|
|leverage|string|t(:leverage)|
|liqPrice|string|t(:liqPrice)|
|trailingStop|string|t(:trailingStop)|
|bustPrice|string|t(:bustPrice)|
|occClosingFee|string|t(:occClosingFee)|
|trakeProfit|string|t(:trakeProfit)|
|stopLoss|string|t(:stopLoss)|
|positionStatus|string|t(:positionStatus)|
|deleverageIndicator|string|t(:deleverageIndicator)|
|orderMargin|string|t(:orderMargin)|
|unrealisedPnl|string|t(:unrealisedPnl)|
|cumRealisedPnl|string|t(:cumRealisedPnl)|

### t(:queryDeliveryLog)

> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/query-delivery-list \
-H "Content-Type: application/json" \
-d '{"symbol":"BTC-22OCT21-45000-C"}'
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
      "cursor":"ccc62b1a-e1a0-42b6-86b5-3570e22cfbdf%3A1634284800789%2Cb09397d8-4da1-4d32-b70f-c59efd381f66%3A1634284800769",
      "dataList":[
      {
        "deliveryTime":"1634284800789",
        "symbol":"BTC-15OCT21-30000-P",
        "side":"Buy",
        "position":"0.00",
        "deliveryPrice":"59307.0",
        "strike":"30000",
        "fee":"0.0000",
        "deliveryRpl":"0.0000"
      }
    ]
  }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvQueryDelivery>/option/usdc/openapi/private/v1/query-delivery-list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvQueryDelivery"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|expDate|false|string|t(:usdcExpDateRepsonse)|
|direction|false|string|t(:direction)|
|limit|false|number|t(:usdcMax50Min20)|
|cursor|false|string|t(:cursor)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|resultTotalSize|number|t(:resultTotalSize)|
|cursor|string|t(:cursor)|
|dataList|list|t(:dataList)|

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|deliveryTime|number|t(:usdcDeliveryTime)|
|symbol|string|t(:usdcSymbol)|
|side|string|t(:side)|
|position|string|t(:usdcPosition)|
|deliveryPrice|string|t(:usdcDeliveryPrice)|
|strike|string|t(:usdcStrike)|
|fee|string|t(:fee)|
|deliveryRpl|string|t(:usdcDeliveryRpl)|





### t(:queryPositionInfo)


> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/query-position-exp-date \
-H "Content-Type: application/json" \
-d '{"expDate":"20211010"}'

```

```python

```


> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"OK",
    "result":{
    "resultTotalSize":2,
      "cursor":"22OCT21:0,15OCT21:0",
      "dataList":[
      {
        "expDate":"22OCT21",
        "pnl":"1062.0157",
        "totalRPL":"0.0000",
        "im":"14792.2241",
        "mm":"10653.4193",
        "sessionRPL":"1587.0000",
        "sessionUPL":"1172.4930"
      },
      {
        "expDate":"16OCT21",
        "pnl":"-12.1500",
        "totalRPL":"487.5000",
        "im":"5891.6831",
        "mm":"4184.0030",
        "sessionRPL":"0.0000",
        "sessionUPL":"0.0000"
      }
    ]
  }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=upovPositionExp>/option/usdc/openapi/private/v1/query-position-exp-date</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#upovPositionExp"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|expDate|false|number|t(:expDate)|
|direction|false|string|t(:direction)|
|limit|false|number|t(:usdcMax50Min20)|
|cursor|false|string|t(:cursor)|


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|resultTotalSize|number|t(:resultTotalSize)|
|cursor|string|t(:cursor)|
|dataList|list|t(:dataList)|

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|expDate|string|t(:expDate)|
|pnl|string|t(:pnl)|
|totalRpl|string|t(:totalRpl)|
|sessionUpl|string|t(:sessionUpl)|
|sessionRpl|string|t(:sessionRpl)|
|im|string|t(:usdcIm)|
|mm|string|t(:usdcMm)|




## t(:usdcMmp)

### t(:whatIsUsdcMmp)

t(:whatIsUsdcMmpDesc)


### t(:enableMmp)

t(:enableMmpDesc)

The default settings are as follows：

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|currency|string|t(:usdcCurrency)|
|windowMs|string|t(:usdcWindowMs)|
|frozenPeriodMs|string|t(:usdcFrozenPeriodMs)|
|qtyLimit|string|t(:usdcQtyLimit)|
|deltaLimit|string|t(:usdcDeltaLimit)|



### t(:modifyMmp)

<p class="fake_header">t(:httprequest)</p>

POST
<code><span id=mmpModify>/option/usdc/openapi/private/v1/mmp-modify</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#mmpModify"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|currency |<b>true</b>|string|t(:usdcCurrency) |
|windowMs |<b>true</b>|number|t(:usdcWindowMs) |
|frozenPeriodMs |<b>true</b>|number|t(:usdcFrozenPeriodMs) |
|qtyLimit |<b>true</b>|string|t(:usdcQtyLimit) |
|deltaLimit |<b>true</b>|string|t(:usdcDeltaLimit) |



### t(:resetMmp)

<p class="fake_header">t(:httprequest)</p>

POST
<code><span id=mmpReset>/option/usdc/openapi/private/v1/mmp-reset</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#mmpReset"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|currency |<b>true</b>|string|t(:usdcCurrency) |

