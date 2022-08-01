# t(:accountdata)
t(:account_para)

## t(:usdcTradeApi)
### t(:usdcPlaceOrder)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/place-order \
-H "Content-Type: application/json" \
-D '{"symbol":"BTC-26NOV21-58000-P","orderType":"Limit","side":"Buy","orderQty":"1","orderPrice":"1","timeInForce":"GoodTillCancel"}'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "orderId": "8c65df91-91fc-461d-9b14-786379ef138c",
        "orderLinkId": "AAAAA41133",
        "symbol": "BTC-13MAY22-40000-C",
        "orderType": "Limit",
        "side": "Buy",
        "orderQty": "0.01",
        "orderPrice": "5"
    },
    "retExtMap": {}
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
|t(:row_parameter_symbol) |<b>true</b>|string|t(:usdcSymbol)|
|orderType|<b>true</b>|string|t(:usdcOptionOrderType)|
|t(:row_parameter_side) |<b>true</b>|string|t(:side)|
|orderPrice|false|string|t(:usdcOptionPlaceOrderPrice)|
|orderQty|<b>true</b>|string|t(:usdcOrderQty)|
|iv|false|string|t(:optionIv_order)|
|t(:row_parameter_timeInForce)|false|string|t(:row_comment_timeInForce)|
|orderLinkId|<b>true</b>|string|t(:orderLinkId)|
|reduceOnly|false|bool|t(:reduceOnly)|
|mmp|false|string|t(:mmp)|



<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)
|t(:row_parameter_symbol) |string|t(:usdcSymbol)|
|orderPrice|string|t(:usdcOrderPrice)|
|orderQty|string|t(:usdcOrderQty)|
|orderType|string|t(:uscdOrderType)|
|t(:row_parameter_side) |string|t(:side)|

### t(:usdcBatchOrders)

t(:usdcBatchOrdersDesc)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/batch-place-orders \
-H "Content-Type: application/json" \
-D '{"orderRequest":[{"symbol":"BTC-26NOV21-58000-P","orderType":"Limit","side":"Buy","orderQty":"1","orderPrice":"1","timeInForce":"GoodTillCancel"}]}'


```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": [
        {
            "orderId": "fa6cd740-56ed-477d-9385-90ccbfee49ca",
            "orderLinkId": "AAAAA4112",
            "symbol": "BTC-13MAY22-40000-C",
            "orderType": "Limit",
            "side": "Buy",
            "orderQty": "0.01",
            "orderPrice": "5",
            "extMap": {},
            "errorCode": 0,
            "errorDesc": ""
        }
    ],
    "retExtMap": {}
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvBatchPlace>/option/usdc/openapi/private/v1/batch-place-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvBatchPlace"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|orderRequest|<b>true</b>|list|t(:usdcList)|

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b>|string|t(:usdcSymbol)|
|orderType|<b>true</b>|string|t(:usdcOptionOrderType)|
|t(:row_parameter_side) |<b>true</b>|string|t(:side)|
|orderPrice|false|string|t(:usdcOptionPlaceOrderPrice)|
|orderQty|<b>true</b>|string|t(:usdcOrderQty)|
|iv|false|string|t(:optionIv_order)|
|t(:row_parameter_timeInForce)|false|string|t(:row_comment_timeInForce)|
|orderLinkId|<b>true</b>|string|t(:orderLinkId)|
|reduceOnly|false|bool|t(:reduceOnly)|
|mmp|false|string|t(:mmp)|



<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)
|t(:row_parameter_symbol) |string|t(:usdcSymbol)|
|orderPrice|string|t(:usdcOrderPrice)|
|orderQty|string|t(:usdcOrderQty)|
|orderType|string|t(:uscdOrderType)|
|t(:row_parameter_side) |string|t(:side)|
|extMap |map|t(:usdcExtMap)|
|errorCode |string|t(:usdcErrorCode)|
|errorDesc |string|t(:usdcErrorDesc)|

### t(:usdcReplaceOrder)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/replace-order \
-H "Content-Type: application/json" \
-D '{"symbol":"BTC-26NOV21-58000-P","orderId":"be6c87be-da18-4876-9a64-6b7ccc859071","orderQty":"1","orderPrice":"1"}'


```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "outRequestId": "",
        "symbol": "BTC-13MAY22-40000-C",
        "orderId": "8c65df91-91fc-461d-9b14-786379ef138c",
        "orderLinkId": "AAAAA41133"
    },
    "retExtMap": {}
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
|t(:row_parameter_symbol) |<b>true</b>|string|t(:usdcSymbol)|
|orderId|false|string|t(:usdcOrderLinkId)|
|orderLinkId|false|string|t(:usdcOrderLinkId)|
|orderPrice|false|string|t(:usdcOrderPrice)|
|orderQty|false|string|t(:usdcOrderQty)|
|iv|false|string|t(:optionIv)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|outRequestId|string|t(:outRequestId)|
|symbol|string|t(:usdcSymbol)|
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)|

### t(:usdcBatchReplaceOrders)

t(:usdcBatchOrdersDesc)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/batch-replace-orders \
-H "Content-Type: application/json" \
-D '{"replaceOrderRequest":[{"symbol":"BTC-26NOV21-58000-P","orderId":"be6c87be-da18-4876-9a64-6b7ccc859071","orderQty":"1","orderPrice":"1"}]}'


```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": [
        {
            "outRequestId": "",
            "symbol": "BTC-13MAY22-40000-C",
            "orderId": "8c65df91-91fc-461d-9b14-786379ef138c",
            "extMap": {},
            "errorCode": 0,
            "errorDesc": "",
            "orderLinkId": "AAAAA41133"
        }
    ],
    "retExtMap": {}
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
|t(:row_parameter_symbol) |<b>true</b>|string|t(:usdcSymbol)|
|orderId|false|string|t(:usdcOrderLinkId)|
|orderLinkId|false|string|t(:usdcOrderLinkId)|
|orderPrice|false|string|t(:usdcOrderPrice)|
|orderQty|false|string|t(:usdcOrderQty)|
|iv|false|string|t(:optionIv)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|outRequestId|string|t(:outRequestId)|
|symbol|string|t(:usdcSymbol)|
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)|
|extMap |map|t(:usdcExtMap)|
|errorCode |string|t(:usdcErrorCode)|
|errorDesc |string|t(:usdcErrorDesc)|


### t(:usdcCancelOrder)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/cancel-order \
-H "Content-Type: application/json" \
-D '{"symbol":"BTC-26NOV21-58000-P","orderId":"ec6d8081-8950-491b-bf43-22ddb09df0fc"}'

```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "outRequestId": "",
        "symbol": "BTC-13MAY22-40000-C",
        "orderId": "8c65df91-91fc-461d-9b14-786379ef138c",
        "orderLinkId": ""
    },
    "retExtMap": {}
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvCancel>/option/usdc/openapi/private/v1/cancel-order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvCancel"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b>|string|t(:usdcSymbol)|
|orderId|false|string|t(:usdcOrderLinkId)|
|orderLinkId|false|string|t(:usdcOrderLinkId)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|outRequestId|string|t(:outRequestId)|
|symbol|string|t(:usdcSymbol)|
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)|


### t(:usdcBatchCancelOrders)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/batch-cancel-orders \
-H "Content-Type: application/json" \
-D '{"cancelRequest":[{"symbol":"BTC-26NOV21-58000-P","orderId":"1a69653f-c3c7-40b4-a492-17316a2086a2"}]}'


```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "retExtMap": {},
    "result": [
        {
            "outRequestId": "",
            "symbol": "BTC-13MAY22-40000-C",
            "orderId": "720b97b4-8e7c-44c9-8417-1160ed82f990",
            "orderLinkId": "AAAAA41134",
            "errorCode": 0,
            "errorDesc": ""
        }
    ]
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
|t(:row_parameter_symbol) |<b>true</b>|string|t(:usdcSymbol)|
|orderId|false|string|t(:usdcOrderLinkId)|
|orderLinkId|false|string|t(:usdcOrderLinkId)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|outRequestId|string|t(:outRequestId)|
|symbol|string|t(:usdcSymbol)|
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)|
|errorCode |string|t(:usdcErrorCode)|
|errorDesc |string|t(:usdcErrorDesc)|


### t(:usdcCancelAll)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/cancel-all \
-H "Content-Type: application/json" \
-D '{}'


```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "retExtMap": {},
    "result": [
        {
            "outRequestId": "cancelAll-290119-1652176443114-0",
            "symbol": "BTC-13MAY22-40000-C",
            "orderId": "fa6cd740-56ed-477d-9385-90ccbfee49ca",
            "orderLinkId": "",
            "errorCode": 0,
            "errorDesc": ""
        }
    ]
}
```

t(:cancelAllResponse)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvCancelAll>/option/usdc/openapi/private/v1/cancel-all</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvCancelAll"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|outRequestId|string|t(:outRequestId)|
|symbol|string|t(:usdcSymbol)|
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)|
|errorCode |string|t(:usdcErrorCode)|
|errorDesc |string|t(:usdcErrorDesc)|


### t(:usdcQryUnOrPartFilled_new)
t(:usdcQryUnOrPartFilled_new_para)

```console
curl GET 'https://api-testnet.bybit.com/option/usdc/openapi/private/v1/trade/query-active-orders?orderLinkId=option0005&symbol=BTC-30SEP22-28000-C' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-SIGN: c657feac222cc8b66d6162802c707c0df47592ee7532a060cb613679aad174f7' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-TIMESTAMP: 1658126609521' \
--header 'X-BAPI-RECV-WINDOW: 10000' \
```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "resultTotalSize": 2,
        "cursor": "id%3D1657785223205%23cd05e436-1e04-4391-94db-82b660638364",
        "dataList": [
            {
                "orderId": "bd4a5ce3-cefd-455c-ac8d-1eaf2ae76b24",
                "orderLinkId": "1426a049-f999-0000026",
                "symbol": "BTC-14JUL22-10000-P",
                "orderStatus": "New",
                "orderPrice": "0.2",
                "side": "Sell",
                "remainingQty": "0.01",
                "orderType": "Limit",
                "qty": "0.01"
            },
            {
                "orderId": "cd05e436-1e04-4391-94db-82b660638364",
                "orderLinkId": "1426a049-f999-0000027",
                "symbol": "BTC-14JUL22-10000-P",
                "orderStatus": "New",
                "orderPrice": "0.2",
                "side": "Sell",
                "remainingQty": "0.01",
                "orderType": "Limit",
                "qty": "0.01"
            }
        ]
    }
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=uopvQueryActiveNew>/option/usdc/openapi/private/v1/trade/query-active-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvQueryActiveNew"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|orderId|false|string|t(:usdcOrderId)|
|orderLinkId|false|string|t(:orderLinkId)|
|t(:row_parameter_symbol) |<b>true</b>|string|t(:usdcSymbol)|
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
|orderId|string |t(:usdcOrderId)|
|orderLinkId |string|t(:orderLinkId)|
|t(:row_parameter_symbol) |string|t(:usdcSymbol)|
|orderStatus |string|t(:usdcOptionOrderStatus)|
|t(:row_parameter_price) |string|t(:usdcOrderPrice)|
|t(:row_parameter_side) |string|t(:side)|
|remainingQty |string|t(:row_comment_leaves_qty)|
|orderType|string|t(:uscdOrderType)|
|qty|string|t(:usdcOrderQty)|


### t(:usdcQryUnOrPartFilled)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/query-active-orders \
-H "Content-Type: application/json" \
-D '{"category": "OPTION", "symbol": "BTC-14JUN22-24500-C"}'

```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "result": {
        "cursor": "9843d39e-dd8f-4499-bd8e-988f4c597980%3A1655092443445%2C9843d39e-dd8f-4499-bd8e-988f4c597980%3A1655092443445",
        "resultTotalSize": 1,
        "dataList": [
            {
                "symbol": "BTC-14JUN22-24500-C",
                "orderType": "Limit",
                "orderLinkId": "option10006",
                "orderId": "9843d39e-dd8f-4499-bd8e-988f4c597980",
                "stopOrderType": "UNKNOWN",
                "orderStatus": "New",
                "takeProfit": "",
                "cumExecValue": "0.0000",
                "createdAt": "1655092443445",
                "orderPnl": "",
                "price": "600.0",
                "tpTriggerBy": "",
                "timeInForce": "GoodTillCancel",
                "basePrice": "",
                "side": "Buy",
                "triggerPrice": "",
                "cumExecFee": "0.0000",
                "leavesQty": "0.220",
                "slTriggerBy": "",
                "iv": "0.000",
                "closeOnTrigger": "",
                "cumExecQty": "0.000",
                "reduceOnly": 0,
                "qty": "0.220",
                "stopLoss": "",
                "lastExecPrice": "",
                "triggerBy": "",
                "orderIM": "133.6895"
            }
        ]
    },
    "retCode": 0,
    "retMsg": "Success."
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
|t(:row_parameter_symbol) |false|string|t(:usdcSymbol)|
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
|t(:row_parameter_symbol) |string|t(:usdcSymbol)|
|orderType |string|t(:row_comment_order_type)|
|orderLinkId |string|t(:orderLinkId)|
|orderId|string |t(:usdcOrderId)|
|stopOrderType |string|t(:usdcStopOrderType)|
|orderStatus |string|t(:usdcOptionOrderStatus)|
|takeProfit |string|t(:takeProfit)|
|cumExecValue |string|t(:cumExecValue)|
|createdAt |string|t(:createdAt)|
|orderPnl |string|t(:usdcOrderPnl)|
|t(:row_parameter_price) |string|t(:usdcOrderPrice)|
|tpTriggerBy |string|t(:usdcTptriggerby)
|t(:row_parameter_timeInForce)|string|t(:row_comment_timeInForce)|
|basePrice |string|t(:basePrice)|
|t(:row_parameter_side) |string|t(:side)|
|triggerPrice |string|t(:triggerPrice)|
|cumExecFee |string|t(:cumExecFee)|
|leavesQty |string|t(:row_comment_leaves_qty)|
|slTriggerBy |string|t(:usdcSlTriggerBy)|
|iv |string|t(:optionIv)|
|closeOnTrigger |bool|t(:closeOnTrigger)|
|cumExecQty |string|t(:cumExecQty)|
|reduceOnly |number|t(:reduceOnly)|
|qty|string|t(:usdcOrderQty)|
|stopLoss|string|t(:stopLoss)|
|lastExecPrice |string|t(:lastExecPrice)|
|triggerBy |string|t(:triggerBy)|
|orderIM |string|t(:im)|


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
  "result": {
    "cursor": "cc27c6ff-a4ec-4739-96bc-6d2b266606d4%3A1640843817698%2Ccc27c6ff-a4ec-4739-96bc-6d2b266606d4%3A1640843817698",
      "resultTotalSize": 1,
      "dataList": [
      {
        "symbol": "BTC-31DEC21-18000-P",
        "orderType": "Limit",
        "orderLinkId": "test2021122417000221",
        "orderId": "cc27c6ff-a4ec-4739-96bc-6d2b266606d4",
        "cancelType": "UNKNOWN",
        "stopOrderType": "UNKNOWN",
        "orderStatus": "Filled",
        "takeProfit": "",
        "createdAt": "1640843817698",
        "orderPnl": "0.0000",
        "price": "1.0",
        "tpTriggerBy": "",
        "timeInForce": "GoodTillCancel",
        "updatedAt": "1640843817698",
        "basePrice": "",
        "realisedPnl": "0.0000",
        "side": "Sell",
        "triggerPrice": "",
        "cumExecFee": "0.0010",
        "leavesQty": "0.000",
        "cashFlow": "0.0100",
        "slTriggerBy": "",
        "iv": "5.2820",
        "closeOnTrigger": "",
        "cumExecQty": "0.010",
        "reduceOnly": 0,
        "qty": "0.010",
        "stopLoss": "",
        "triggerBy": "",
        "orderIM": "0.0000"
      }
    ]
  },
  "retCode": 0,
    "retMsg": "Success."
}
```

<aside class="notice">
t(:usdcQueryLimit)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvQueryHistory>/option/usdc/openapi/private/v1/query-order-history</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvQueryHistory"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category|<b>true</b>|string|t(:usdcCategory)|
|t(:row_parameter_symbol) |false|string|t(:usdcSymbol)|
|orderId|false|string|t(:usdcOrderId)|
|orderLinkId|false|string|t(:orderLinkId)|
|orderStatus|false|string|t(:usdcOptionOrderStatus)|
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
|t(:row_parameter_symbol) |string|t(:usdcSymbol)|
|orderType |string|t(:row_comment_order_type)|
|orderLinkId |string|t(:orderLinkId)|
|orderId|string |t(:usdcOrderId)|
|cancelType|string|t(:usdcCancelType)|
|stopOrderType |string|t(:usdcStopOrderType)|
|orderStatus |string|t(:usdcOptionOrderStatus)|
|takeProfit |string|t(:takeProfit)|
|createdAt|number|t(:createdAt)|
|orderPnl |string|t(:usdcOrderPnl)|
|t(:row_parameter_price) |string|t(:usdcOrderPrice)|
|tpTriggerBy |string|t(:usdcTptriggerby)
|t(:row_parameter_timeInForce)|string|t(:row_comment_timeInForce)|
|updatedAt|number|t(:updatedAt)|
|basePrice |string|t(:basePrice)|
|realisedPnl|string|t(:realisedPnl)|
|t(:row_parameter_side) |string|t(:side)|
|triggerPrice |string|t(:triggerPrice)|
|cumExecFee |string|t(:cumExecFee)|
|leavesQty |string|t(:row_comment_leaves_qty)|
|cashFlow|string|t(:cashFlow)|
|slTriggerBy |string|t(:usdcSlTriggerBy)|
|iv |string|t(:optionIv)|
|closeOnTrigger |bool|t(:closeOnTrigger)|
|cumExecQty |string|t(:cumExecQty)|
|reduceOnly |number|t(:reduceOnly)|
|qty|string|t(:usdcOrderQty)|
|stopLoss|string|t(:stopLoss)|
|triggerBy |string|t(:triggerBy)|
|orderIM |string|t(:im)|


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
  "result": {
    "cursor": "34%3A0%2C34%3A0",
      "resultTotalSize": 1,
      "dataList": [
      {
        "symbol": "BTC-31DEC21-18000-P",
        "tradeTime": "1640834911093",
        "orderLinkId": "test2021122417000218",
        "side": "Sell",
        "orderId": "13ad19bf-5e23-479b-8261-54f1baf290e1",
        "execPrice": "1.00",
        "lastLiquidityInd": "TAKER",
        "execValue": "",
        "execType": "TRADE",
        "execQty": "0.010",
        "execFee": "0.0010",
        "feeRate": "0.000300",
        "tradeId": "77fdaeef-b931-51f4-96c8-33f97c722053"
      }
    ]
  },
  "retCode": 0,
    "retMsg": "Success."
}

```

<aside class="notice">
t(:usdcQueryLimitWithInput)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvExecution>/option/usdc/openapi/private/v1/execution-list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvExecution"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category|<b>true</b>|string|t(:usdcCategory)|
|t(:row_parameter_symbol) |false|string|t(:usdcSymbol)|
|orderId|false|string|t(:usdcOrderId)|
|orderLinkId|false|string|t(:usdcOrderLinkId)|
|startTime|false|string|t(:usdcStartTime_ms)|
|direction|false|string|t(:direction)|
|limit|false|string|t(:row_comment_limit)|
|cursor|false|string|t(:cursor)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|resultTotalSize|number|t(:resultTotalSize)|
|cursor|string|t(:cursor)|
|dataList|list|t(:dataList)|

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_symbol) |string|t(:usdcSymbol)|
|tradeTime|string|t(:tradeTime)|
|orderLinkId|string|t(:orderLinkId)|
|t(:row_parameter_side) |string|t(:side)|
|orderId|string|t(:usdcOrderId)|
|execPrice|string|t(:tradePrice)|
|lastLiquidityInd|string|t(:lastLiquidityInd)|
|execValue|string|t(:execValue)|
|execType|string|t(:execType)|
|execQty|string|t(:uscdSize)|
|execFee|string|t(:fee)|
|feeRate|string|t(:feeRate)|
|tradeId|string|t(:usdcTradeId)|


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

<aside class="notice">
t(:usdcQueryLimitWithInput)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvQueryTransaction>/option/usdc/openapi/private/v1/query-transaction-log</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvQueryTransaction"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|type|<b>true</b>|string|t(:usdcTransactionType)|
|startTime|false|string|t(:usdcStartTime_ms)|
|endTime|false|string|t(:usdcEndTime)|
|direction|false|string|t(:direction)|
|limit|false|string|t(:row_comment_limit)|
|cursor|false|string|t(:cursor)|
|category|false|string|t(:usdcCategory)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|resultTotalSize|number|t(:resultTotalSize)|
|cursor|string|t(:cursor)|
|dataList|list|t(:dataList)|

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transactionTime|number|t(:transactionTime)|
|t(:row_parameter_symbol) |string|t(:usdcSymbol)
|type|string|t(:usdcType)|
|t(:row_parameter_side) |string|t(:side)|
|qty|string|t(:usdcOrderQty)|
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
-H "Content-Type: application/json" \
-D '{}'

```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "result": {
        "walletBalance": "1000.0000",
        "accountMM": "0.0000",
        "bonus": "0.0000",
        "accountIM": "133.6697",
        "totalSessionRPL": "0.0000",
        "equity": "1000.0000",
        "totalRPL": "0.0000",
        "marginBalance": "1000.0000",
        "availableBalance": "866.3303",
        "totalSessionUPL": "0.0000"
    },
    "retCode": 0,
    "retMsg": "Success."
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvQueryBalance>/option/usdc/openapi/private/v1/query-wallet-balance</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvQueryBalance"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|walletBalance|string|t(:cashBalance)
|accountMM|string|t(:accountMm)|
|bonus|string|t(:bonus)|
|accountIM|string|t(:accountIm)|
|totalSessionRPL|string|t(:totalSessionRpl)|
|equity|string|t(:equity)|
|totalRPL|string|t(:totalRpl)|
|marginBalance|string|t(:marginBalance)|
|availableBalance|string|t(:availableBalance)|
|totalSessionUPL|string|t(:totalSessionUpl)|


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
|totalRpl|string|t(:totalRpl)|
|sessionUpl|string|t(:sessionUpl)|
|sessionRpl|string|t(:sessionRpl)|
|im|string|t(:usdcIm)|
|mm|string|t(:usdcMm)|

### t(:setMarginMode)
<aside class="notice">
t(:setMarginModeNotice)
</aside>

> t(:codequote_curlExample)

```console

curl https://api-testnet.bybit.com/option/usdc/private/asset/account/setMarginMode \
-H "Content-Type: application/json" \
-D '{"setMarginMode":"PORTFOLIO_MARGIN"}'
```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "Request accepted",
    "result": {
        "reasons": []
    }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=setMarginMode>/option/usdc/private/asset/account/setMarginMode</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#setMarginMode"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|setMarginMode|<b>true</b>|string|t(:usdcMarginMode)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


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
  "result": {
    "cursor": "BTC-31DEC21-24000-P%3A1640834421431%2CBTC-31DEC21-24000-P%3A1640834421431",
      "resultTotalSize": 1,
      "dataList": [
      {
        "symbol": "BTC-31DEC21-24000-P",
        "leverage": "",
        "occClosingFee": "",
        "liqPrice": "",
        "positionValue": "",
        "takeProfit": "",
        "riskId": "",
        "trailingStop": "",
        "unrealisedPnl": "",
        "createdAt": "1640834421431",
        "markPrice": "0.00",
        "cumRealisedPnl": "",
        "positionMM": "359.5271",
        "positionIM": "467.0633",
        "updatedAt": "1640834421431",
        "tpSLMode": "",
        "side": "Sell",
        "bustPrice": "",
        "deleverageIndicator": 0,
        "entryPrice": "1.4",
        "size": "-0.100",
        "sessionRPL": "0.0000",
        "positionStatus": "",
        "sessionUPL": "0.1450",
        "stopLoss": "",
        "orderMargin": "",
        "sessionAvgPrice": "1.5"
      }
    ]
  },
  "retCode": 0,
    "retMsg": "Success."
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
|t(:row_parameter_symbol) |false|string|t(:usdcSymbol)|
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
|t(:row_parameter_symbol) |string|t(:usdcSymbol)|
|leverage |string|t(:usdcSymbol)|
|occClosingFee |string|t(:occClosingFee)|
|liqPrice|string|t(:liqPrice)|
|positionValue|string|t(:positionValue)|
|takeProfit|string|t(:trakeProfit)|
|riskId|string|riskId|
|trailingStop|string|t(:trailingStop)|
|unrealisedPnl|string|t(:unrealisedPnl)|
|createdAt|string|t(:createdAt)|
|markPrice|string|t(:usdcMarkPrice)|
|cumRealisedPnl|string|t(:cumRealisedPnl)|
|positionMM|string|t(:usdcMm)|
|positionIM|string|t(:usdcIm)|
|updatedAt|string|t(:updatedAt)|
|tpSLMode|string|t(:tpSlMode)|
|t(:row_parameter_side) |string|t(:side)|
|bustPrice|string|t(:bustPrice)|
|deleverageIndicator|integer|t(:deleverageIndicator)|
|entryPrice|string|t(:entryPrice)
|size|string|t(:uscdSize)
|sessionRPL|string|t(:sessionRpl)|
|positionStatus|string|t(:positionStatus)|
|sessionUPL|string|t(:sessionUpl)|
|stopLoss|string|t(:stopLoss)|
|orderMargin|string|t(:orderMargin)|
|sessionAvgPrice|string|t(:sessionAvgPrice)|

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

<aside class="notice">
t(:usdcQueryLimit)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvQueryDelivery>/option/usdc/openapi/private/v1/query-delivery-list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvQueryDelivery"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b>|string|t(:usdcSymbol)|
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
|t(:row_parameter_symbol) |string|t(:usdcSymbol)|
|t(:row_parameter_side) |string|t(:side)|
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
|im|string|t(:usdcIm)|
|mm|string|t(:usdcMm)|
|sessionRpl|string|t(:sessionRpl)|
|sessionUpl|string|t(:sessionUpl)|




## t(:usdcMmp)

### t(:whatIsUsdcMmp)

t(:whatIsUsdcMmpDesc)


### t(:enableMmp)

t(:enableMmpDesc)

t(:usdcMmpDefault)


|t(:column_parameter)|t(:column_type)|t(:column_comments)|t(:column_default)|
|:----- |:-----|----- |----- |
|currency|string|t(:usdcCurrency)|BTC|
|windowMs|string|t(:usdcWindowMs)|5000|
|frozenPeriodMs|string|t(:usdcFrozenPeriodMs)|100|
|qtyLimit|string|t(:usdcQtyLimit)|100|
|deltaLimit|string|t(:usdcDeltaLimit)|100|



### t(:modifyMmp)

> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/mmp-modify \
-H "Content-Type: application/json" \
-d '{
    "currency":"BTC",
    "windowMs":500000,
    "frozenPeriodMs":300,
    "qtyLimit":"10",
    "deltaLimit":"100"
}'

```

```python

```


> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
   "retMsg":"OK"
}
```

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



> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/mmp-reset \
-H "Content-Type: application/json" \
-d '{
    "currency":"BTC"
}'

```

```python

```


> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
   "retMsg":"OK"
}
```

<p class="fake_header">t(:httprequest)</p>

POST
<code><span id=mmpReset>/option/usdc/openapi/private/v1/mmp-reset</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#mmpReset"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|currency |<b>true</b>|string|t(:usdcCurrency) |


### t(:queryMMPState)

> t(:codequote_curlExample)

```console

curl https://api-testnet.bytick.com/option/usdc/openapi/private/v1/get-mmp-state \
-H "Content-Type: application/json" \
-D '{"baseCoin":"BTC"}'
```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": [
        {
            "baseCoin": "",
            "mmpEnabled": false,
            "mmpUserConfigurable": false,
            "windowMs": "0",
            "frozenPeriodMs": "0",
            "qtyLimit": "",
            "deltaLimit": "",
            "mmpFrozenUntilMs": "0",
            "mmpFrozen": false
        }
    ]
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=mmpState>/option/usdc/openapi/private/v1/get-mmp-state</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#mmpState"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|baseCoin|<b>true</b>|string|t(:usdcBaseCoin)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|baseCoin|string|t(:usdcBaseCoin)|
|mmpEnabled|boolean|t(:usdcMmpEnabled)|
|mmpUserConfigurable|boolean|t(:usdcMmpUserConfigurable)|
|windowMs|string|t(:usdcWindowMs)|
|frozenPeriodMs|string|t(:usdcFrozenPeriodMs)|
|qtyLimit|string|t(:usdcQtyLimit)|
|deltaLimit|string|t(:usdcDeltaLimit)|
|mmpFrozenUntilMs|string|t(:usdcMmpFrozenUntilMs)|
|mmpFrozen|boolean|t(:usdcMmpFrozen)|
