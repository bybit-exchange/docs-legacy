# t(:accountdata)
t(:account_para)

## t(:usdcTradeApi)
### t(:usdcPlaceOrder)

> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/perpetual/usdc/openapi/private/v1/place-order \
-H "Content-Type: application/json" \
-D '{
    "side": "Buy",
    "orderType": "Limit",
    "orderFilter": "Order",
    "orderQty": "0.01",
    "orderPrice": "64300",
    "timeInForce": "GoodTillCancel",
    "closeOnTrigger": false,
    "outRequestId": "",
    "reduceOnly": false,
    "symbol": "BTCPERP",
    "orderLinkId": "",
    "positionIdx": 0,
    "mmp": false
}'
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "",
    "result": {
    "orderId": "29373a80-ba76-4e5c-9c5d-17efa02804ea",
      "orderLinkId": "",
      "mmp": false,
      "symbol": "BTCPERP",
      "orderType": "Limit",
      "side": "Buy",
      "orderQty": "0.01000000",
      "orderPrice": "59925.00",
      "iv": "0",
      "timeInForce": "GoodTillCancel",
      "orderStatus": "Created",
      "createdAt": "1638340762484732",
      "basePrice": "0.00",
      "triggerPrice": "0.00",
      "takeProfit": "0.00",
      "stopLoss": "0.00",
      "slTriggerBy": "UNKNOWN",
      "tpTriggerBy": "UNKNOWN"
  }
}
```
t(:placeOrderInfo)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvPlace>/perpetual/usdc/openapi/private/v1/place-order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvPlace"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|orderType|<b>true</b>|string|t(:usdcPerpOrderType)|
|orderFilter|<b>true</b>|string|t(:usdcOrderFilter)|
|side|<b>true</b>|string|t(:side)|
|orderPrice|false|string|t(:usdc_perp_order_price)|
|orderQty|<b>true</b>|string|t(:usdcOrderQty)|
|t(:row_parameter_timeInForce)|false|string|t(:row_comment_timeInForce)|
|orderLinkId|false|string|t(:orderLinkId)|
|reduceOnly|false|bool|t(:reduceOnly)|
|closeOnTrigger|false|bool|t(:closeOnTrigger)|
|takeProfit|false|string|t(:takeProfit)|
|stopLoss|false|string|t(:stopLoss)|
|tptriggerby|false|number|t(:usdcTptriggerby)|
|slTriggerBy|false|string|t(:usdcSlTriggerBy)|
|triggerPrice|false|string|t(:triggerPrice)|
|triggerBy|false|number|t(:usdcTriggerBy)|
|mmp|false|bool|t(:mmp)|



<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)
|symbol|string|t(:usdcSymbol)|
|orderPrice|string|t(:usdcOrderPrice)|
|orderQty|string|t(:usdcOrderQty)|
|orderType|string|t(:usdcPerpOrderType)|
|side|string|t(:side)|

### t(:usdcReplaceOrder)

t(:perpUsdcReplaceOrderDesc)


```console
curl https://api-testnet.bybit.com/perpetual/usdc/openapi/private/v1/replace-order \
-H "Content-Type: application/json" \
-D '{
"symbol":"BTCPERP",
"orderLinkId":"",
"orderId":"29373a80-ba76-4e5c-9c5d-17efa02804ea",
"orderQty":"0.02",
"orderPrice":"59888.3",
"iv":"10",
"takeProfit":"",
"stopLoss":"",
"orderFilter":"Order"
}'


```

```python

```


> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "",
    "result": {
      "orderId": "61f22ac5-6774-46e6-9697-fc3f2621ee09",
      "orderLinkId": ""
  }
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvReplace>/perpetual/usdc/openapi/private/v1/replace-order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvReplace"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|orderFilter|<b>true</b>|string|t(:usdcOrderFilter)|
|orderId|false|string|t(:usdcOrderId)|
|orderLinkId|false|string|t(:usdcOrderLinkId)|
|orderPrice|false|string|t(:usdcOrderPrice)|
|orderQty|false|string|t(:usdcOrderQty)|
|takeProfit|false|string|t(:takeProfit)|
|stopLoss|false|string|t(:stopLoss)|
|tptriggerby|false|string|t(:usdcTptriggerby)|
|slTriggerBy|false|string|t(:usdcSlTriggerBy)|
|triggerPrice|false|string|t(:triggerPrice)|



<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)



### t(:usdcCancelOrder)


```console
curl https://api-testnet.bybit.com/perpetual/usdc/openapi/private/v1/cancel-order \
-H "Content-Type: application/json" \
-D '
{
"symbol":"BTCPERP",
"orderLinkId":"",
"orderFilter":"Order",
"orderId":"752cff9a-6941-44d3-a405-bd297b1df4bc"
}
'

```

```python

```


> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "",
    "result": {
    "orderId": "752cff9a-6941-44d3-a405-bd297b1df4bc"
  }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvCancel>/perpetual/usdc/openapi/private/v1/cancel-order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvCancel"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|orderFilter|<b>true</b>|string|t(:usdcOrderFilter)|
|orderId|false|string||
|orderLinkId|false|string|t(:usdcOrderLinkId)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|





### t(:usdcCancelAll)

```console
curl https://api-testnet.bybit.com/perpetual/usdc/openapi/private/v1/cancel-order \
-H "Content-Type: application/json" \
-D '{
    "symbol": "BTCPERP",
    "orderFilter": "Order"
}'


```

```python

```


> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": ""
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvCancelAll>/perpetual/usdc/openapi/private/v1/cancel-all</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvCancelAll"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|orderFilter|false|string|t(:usdcOrderFilter)|

<p>
t(:cancelAllResponse)
</p>

### t(:usdcQryUnOrPartFilled)


```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/query-active-orders \
-H "Content-Type: application/json" \
-D '{
    "category": "PERPETUAL",
    "symbol": "BTCPERP"
}'

```

```python

```


> t(:codequote_responseExample)

```javascript
{
  "result": {
    "cursor": "3dd0f4a4-b726-4921-9a23-723e0c0fdbd3%3A1640856463068%2C3dd0f4a4-b726-4921-9a23-723e0c0fdbd3%3A1640856463068",
      "resultTotalSize": 1,
      "dataList": [
      {
        "symbol": "BTCPERP",
        "orderType": "Limit",
        "orderLinkId": "",
        "orderId": "3dd0f4a4-b726-4921-9a23-723e0c0fdbd3",
        "stopOrderType": "UNKNOWN",
        "orderStatus": "New",
        "takeProfit": "0.0000",
        "cumExecValue": "0.0000",
        "createdAt": "1640856463065",
        "orderPnl": "-",
        "price": "38000.0",
        "tpTriggerBy": "UNKNOWN",
        "timeInForce": "GoodTillCancel",
        "basePrice": "",
        "side": "Buy",
        "triggerPrice": "0.0000",
        "cumExecFee": "0.0000",
        "leavesQty": "0.010",
        "slTriggerBy": "UNKNOWN",
        "iv": "",
        "closeOnTrigger": "UNKNOWN",
        "cumExecQty": "",
        "reduceOnly": 0,
        "qty": "0.010",
        "stopLoss": "0.0000",
        "lastExecPrice": "0.0",
        "triggerBy": "UNKNOWN",
        "orderIM": ""
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
|category|<b>true</b>|string|t(:usdcPerpCategory)|
|symbol|false|string|t(:usdcSymbol)|
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
|orderType|string|t(:usdcPerpOrderType)|
|side|string|t(:side)|
|qty|string|t(:usdcOrderQty)|
|price|string|t(:usdcOrderPrice)|
|t(:row_parameter_timeInForce)|string|t(:row_comment_timeInForce)|
|cumExecQty|string|t(:cumExecQty)|
|cumExecValue|string|t(:cumExecValue)|
|cumExecFee|string|t(:cumExecFee)|
|orderIM|string|t(:im)|
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
|stopOrderType|string|t(:usdcStopOrderType)|
|closeOnTrigger|string|t(:closeOnTrigger)|
|createdAt|number|t(:createdAt)|



### t(:usdcQryOrderHistory)

```console

curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/query-order-history \
-H "Content-Type: application/json" \
-D '{
    "category": "PERPETUAL",
    "limit":2
}'

```

```python

```


> t(:codequote_responseExample)

```javascript
{
  "result": {
    "cursor": "640034d1-97ec-4382-9983-694898c03ba3%3A1640854950675%2C640034d1-97ec-4382-9983-694898c03ba3%3A1640854950675",
      "resultTotalSize": 1,
      "dataList": [
      {
        "symbol": "BTCPERP",
        "orderType": "Market",
        "orderLinkId": "",
        "orderId": "640034d1-97ec-4382-9983-694898c03ba3",
        "cancelType": "UNKNOWN",
        "stopOrderType": "UNKNOWN",
        "orderStatus": "Filled",
        "takeProfit": "0.0000",
        "createdAt": "1640854950672",
        "orderPnl": "-",
        "price": "49192.5",
        "tpTriggerBy": "UNKNOWN",
        "timeInForce": "ImmediateOrCancel",
        "updatedAt": "1640854950675",
        "basePrice": "",
        "realisedPnl": "0.0000",
        "side": "Buy",
        "triggerPrice": "0.0",
        "cumExecFee": "0.3514",
        "leavesQty": "0.000",
        "cashFlow": "",
        "slTriggerBy": "UNKNOWN",
        "iv": "",
        "closeOnTrigger": "UNKNOWN",
        "cumExecQty": "0.010",
        "reduceOnly": 0,
        "qty": "0.010",
        "stopLoss": "0.0000",
        "triggerBy": "UNKNOWN",
        "orderIM": ""
      }
    ]
  },
  "retCode": 0,
    "retMsg": "Success."
}

```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvQueryHistory>/option/usdc/openapi/private/v1/query-order-history</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvQueryHistory"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category|<b>true</b>|string|t(:usdcPerpCategory)|
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
|orderType|string|t(:usdcPerpOrderType)|
|side|string|t(:side)|
|qty|string|t(:usdcOrderQty)|
|price|string|t(:usdcOrderPrice)|
|t(:row_parameter_timeInForce)|string|t(:row_comment_timeInForce)|
|leavesValue|string|t(:leavesValue)|
|cumExecQty|string|t(:cumExecQty)|
|cumExecValue|string|t(:cumExecValue)|
|cumExecFee|string|t(:cumExecFee)|
|orderIM|string|t(:im)|
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
|stopOrderType|string|t(:usdcStopOrderType)|
|closeOnTrigger|string|t(:closeOnTrigger)|
|createdAt|number|t(:createdAt)|
|updatedAt|number|t(:updatedAt)|


### t(:usdcTradeHistory)

> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/execution-list \
-H "Content-Type: application/json" \
-D '{
    "category": "PERPETUAL",
    "limit": 1
}'
```

```python

```


> t(:codequote_responseExample)

```javascript
{
  "result": {
    "cursor": "52%3A1%2C52%3A1",
      "resultTotalSize": 1,
      "dataList": [
      {
        "symbol": "BTCPERP",
        "tradeTime": "1640854950675",
        "orderLinkId": "",
        "side": "Buy",
        "orderId": "640034d1-97ec-4382-9983-694898c03ba3",
        "execPrice": "46851.50",
        "lastLiquidityInd": "TAKER",
        "execValue": "468.5150",
        "execType": "TRADE",
        "execQty": "0.010",
        "execFee": "0.3514",
        "feeRate": "0.000750",
        "tradeId": "22f7e871-e11b-50f0-aa6f-40dc52f57322"
      }
    ]
  },
  "retCode": 0,
    "retMsg": "Success."
}

```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvExecution>/option/usdc/openapi/private/v1/execution-list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvExecution"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category|<b>true</b>|string|t(:usdcPerpCategory)|
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
|symbol|string|t(:usdcSymbol)|
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)|
|side|string|t(:side)|
|execPrice|string|t(:tradePrice)|
|execQty|string|t(:uscdSize)|
|execFee|string|t(:fee)|
|feeRate|string|t(:feeRate)|
|tradeTime|number|t(:tradeTime)|
|execType|string|t(:execType)|
|lastLiquidityInd|string|t(:lastLiquidityInd)|
|execValue|string|t(:execValue)|
|tradeId|string|t(:tradeId)|


## t(:account_wallet)
t(:wallet_para)

### t(:transactionLog)

> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/query-transaction-log \
-H "Content-Type: application/json" \
-D '{
    "type": "TRADE",
    "limit": 1
}'
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
      "cursor": "289037_BTCPERP_1176501331%3A1638341411994%3A9806%2C289037_BTCPERP_1176501331%3A1638341411994%3A9806",
      "dataList": [
      {
        "transactionTime": "1638341411994",
        "symbol": "BTCPERP",
        "type": "TRADE",
        "side": "Buy",
        "tradePrice": "57168.5",
        "funding": "0.0000",
        "qty": "0.020",
        "size": "1.150",
        "fee": "0.8576",
        "cashFlow": "-",
        "change": "-0.8575",
        "walletBalance": "24080.5708",
        "feeRate": "0.0008",
        "orderId": "61f22ac5-6774-46e6-9697-fc3f2621ee09",
        "orderLinkId": "",
        "tradeId": "14c7eb47-15e7-565a-b622-9633d09a5389",
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
-D '{
    "category": "PERPETUAL"
}'
```

```python

```


> t(:codequote_responseExample)

```javascript
{
  "result": {
    "cursor": "BTCPERP%3A1640856463080%2CBTCPERP%3A1640856463080",
      "resultTotalSize": 1,
      "dataList": [
      {
        "symbol": "BTCPERP",
        "leverage": "10.00",
        "occClosingFee": "0.0000",
        "liqPrice": "-",
        "positionValue": "1403.8050",
        "takeProfit": "0.0",
        "riskId": "10001",
        "trailingStop": "0.0000",
        "unrealisedPnl": "0.0000",
        "createdAt": "1640856463080",
        "markPrice": "46891.81",
        "cumRealisedPnl": "0.0000",
        "positionMM": "7.9666",
        "positionIM": "141.3281",
        "updatedAt": "1640856463080",
        "tpSLMode": "UNKNOWN",
        "side": "Buy",
        "bustPrice": "-",
        "deleverageIndicator": 0,
        "entryPrice": "46793.5",
        "size": "0.030",
        "sessionRPL": "0.0000",
        "positionStatus": "NORMAL",
        "sessionUPL": "0.3391",
        "stopLoss": "0.0",
        "orderMargin": "38.5415",
        "sessionAvgPrice": "46880.5"
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
|category|<b>true</b>|string|t(:usdcPerpCategory)|
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
|sessionUPL|string|t(:sessionUpl)|
|sessionRPL|string|t(:sessionRpl)|
|positionIM|string|t(:usdcIm)|
|positionMM|string|t(:usdcMm)|
|createdAt|string|t(:createdAt)|
|updatedAt|string|t(:updatedAt)|
|tpSlMode|string|t(:tpSlMode)|
|positionValue|string|t(:positionValue)|
|leverage|string|t(:leverage)|
|liqPrice|string|t(:liqPrice)|
|bustPrice|string|t(:bustPrice)|
|occClosingFee|string|t(:occClosingFee)|
|takeProfit|string|t(:trakeProfit)|
|stopLoss|string|t(:stopLoss)|
|positionStatus|string|t(:positionStatus)|
|deleverageIndicator|string|t(:deleverageIndicator)|
|orderMargin|string|t(:orderMargin)|
|unrealisedPnl|string|t(:unrealisedPnl)|
|cumRealisedPnl|string|t(:cumRealisedPnl)|

### t(:setPositionLeverage)

Only for REGULAR_MARGIN.

> t(:codequote_curlExample)

```console

curl https://api-testnet.bybit.com/perpetual/usdc/openapi/private/v1/position/leverage/save \
-H "Content-Type: application/json" \
-d '{
    "symbol": "BTCPERP",
    "leverage": "1"
}'

```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Positions.Positions_saveLeverage(symbol="BTCUSD", leverage="14").result())

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "",
    "extCode": null,
    "extInfo": null,
    "result": {
        "leverage": 1
    }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvLeverageSave>/perpetual/usdc/openapi/private/v1/position/leverage/save</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvLeverageSave"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|leverage|<b>true</b>|number|t(:usdcLeverage)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|leverage|number|t(:leverage)|



### t(:querySettleLogs)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/session-settlement \
-H "Content-Type: application/json" \
-d '{"symbol":"BTC-22OCT21-45000-C"}'

```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "Success.",
    "result": {
        "resultTotalSize": 20,
        "cursor": "4327:0,4286:0",
        "dataList": [
            {
                "time": "1650240000000",
                "symbol": "BTCPERP",
                "side": "Buy",
                "size": "0.001",
                "sessionAvgPrice": "39685.53",
                "markPrice": "39686.28",
                "sessionRpl": "-0.7730"
            }
        ]
    }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=upovSession>/option/usdc/openapi/private/v1/session-settlement</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#upovSession"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
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
|time|number|(t:settlementTime)
|symbol|string|t(:usdcSymbol)|
|side|string|t(:side)|
|size|string|t(:usdcSize)|
|sessionAvgPrice|string|t(:sessionAvgPrice)|
|markPrice|string|t(:markPrice)|
|sessionRpl|string|t(:sessionRpl)|



## t(:riskLimit)


### t(:queryRiskLimits)

> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/perpetual/usdc/openapi/public/v1/risk-limit/list \
-H "Content-Type: application/json" \
-d '{"symbol":"BTCPERP"}'
```

```python

```


> t(:codequote_responseExample)

```javascript

```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopv>/perpetual/usdc/openapi/public/v1/risk-limit/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopv"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|symbol|string|t(:usdcSymbol)|
|riskId|number|t(:riskId)|
|limit|string|t(:usdcRiskLimit)|
|maintainMargin|string|t(:maintainMargin)|
|startingMargin|string|t(:startingMargin)|
|section|string|t(:section)|
|isLowestRisk|string|t(:isLowestRisk)|
|maxLeverage|string|t(:maxLeverage)|


### t(:setRiskLimits)

> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/perpetual/usdc/openapi/private/v1/position/set-risk-limit \
-H "Content-Type: application/json" \
-d '{"symbol":"BTCPERP","riskId":2}'

```

```python

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "riskId": 2
  }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvSetRisk>/perpetual/usdc/openapi/private/v1/position/set-risk-limit</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvSetRisk"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|riskId|<b>true</b>|number|t(:riskId)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|riskId|number|t(:riskId)|


