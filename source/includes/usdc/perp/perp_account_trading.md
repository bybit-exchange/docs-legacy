# t(:accountdata)
t(:account_para)

## t(:usdcTradeApi)
### t(:usdcPlaceOrder)

> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/perpetual/usdc/openapi/private/v1/place-order \
-H "Content-Type: application/json" \
-D '{
    "symbol": "BTCPERP",
    "orderType": "Market",
    "orderFilter": "Order",
    "side": "Sell",
    "orderQty": "0.002",
    "timeInForce": "GoodTillCancel",
    "orderLinkId": "usdcP10001",
    "reduceOnly": false,
    "closeOnTrigger": false,
    "takeProfit": "19600",
    "stopLoss": "23000"
}'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "",
    "result": {
        "orderId": "3710f92a-3f71-42c3-bc3c-253a81c190ef",
        "orderLinkId": "usdcP10001",
        "mmp": false,
        "symbol": "BTCPERP",
        "orderType": "Market",
        "side": "Sell",
        "orderQty": "0.00500000",
        "orderPrice": "20272.50",
        "iv": "0",
        "timeInForce": "ImmediateOrCancel",
        "orderStatus": "Created",
        "createdAt": "1655173222148884",
        "basePrice": "0.00",
        "triggerPrice": "0.00",
        "takeProfit": "19600.00",
        "stopLoss": "23000.00",
        "slTriggerBy": "MarkPrice",
        "tpTriggerBy": "MarkPrice"
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
|t(:row_parameter_symbol) |<b>true</b>|string|t(:usdcSymbol)|
|orderType|<b>true</b>|string|t(:usdcPerpOrderType)|
|orderFilter|<b>true</b>|string|t(:usdcOrderFilter)|
|t(:row_parameter_side) |<b>true</b>|string|t(:side)|
|orderPrice|false|string|t(:usdc_perp_order_price)|
|orderQty|<b>true</b>|string|t(:usdcOrderQty)|
|t(:row_parameter_timeInForce)|false|string|t(:row_comment_timeInForce)|
|orderLinkId|false|string|t(:orderLinkId)|
|reduceOnly|false|bool|t(:reduceOnly)|
|closeOnTrigger|false|bool|t(:closeOnTrigger)|
|takeProfit|false|string|t(:takeProfit)|
|stopLoss|false|string|t(:stopLoss)|
|tptriggerby|false|string|t(:usdcTptriggerby)|
|slTriggerBy|false|string|t(:usdcSlTriggerBy)|
|basePrice|false|string|t(:perpBasePrice)|
|triggerPrice|false|string|t(:triggerPrice)|
|triggerBy|false|string|t(:usdcTriggerBy)|
|mmp|false|bool|t(:mmp)|



<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)
|mmp|bool|t(:mmp)
|t(:row_parameter_symbol) |string|t(:usdcSymbol)|
|orderType|string|t(:usdcPerpOrderType)|
|t(:row_parameter_side) |string|t(:side)|
|orderQty|string|t(:usdcOrderQty)|
|orderPrice|string|t(:usdcOrderPrice)|
|iv|string|t(:optionIv)|
|t(:row_parameter_timeInForce)|string|t(:row_comment_timeInForce)|
|t(:usdcOptionOrderStatus)|string|t(:row_comment_orderStatus)|
|createdAt|string|t(:createdAt)|
|basePrice|string|t(:basePrice)|
|triggerPrice|string|t(:triggerPrice)|
|takeProfit|string|t(:takeProfit)|
|stopLoss|string|t(:stopLoss)|
|slTriggerBy|string|t(:usdcSlTriggerBy)|
|tpTriggerBy|string|t(:usdcTptriggerby)|


### t(:usdcReplaceOrder)

t(:perpUsdcReplaceOrderDesc)


```console
curl https://api-testnet.bybit.com/perpetual/usdc/openapi/private/v1/replace-order \
-H "Content-Type: application/json" \
-D '{
{
    "symbol": "BTCPERP",
    "orderFilter": "StopOrder",
    "orderLinkId": "usdcP10002",
    "orderPrice": "20000",
    "orderQty": "0.002",
    "takeProfit": "17000",
    "stopLoss": "23000",
    "tptriggerby": "LastPrice",
    "slTriggerBy": "MarkPrice",
    "triggerPrice": "20900",
    "triggerBy": "MarkPrice"
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
        "orderId": "3727c054-ef45-4385-a5e6-0fa0b76ad5da",
        "orderLinkId": "usdcP10002",
        "createdAt": "1655177751954588",
        "updatedAt": "0",
        "symbol": "BTCPERP",
        "orderType": "UNKNOWN",
        "side": "None",
        "qty": "0.00200000",
        "price": "20000.00",
        "timeInForce": "UNKNOWN",
        "orderStatus": "UNKNOWN",
        "triggerPrice": "20900.00"
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
|t(:row_parameter_symbol) |<b>true</b>|string|t(:usdcSymbol)|
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
|createdAt|string|t(:createdAt)
|updatedAt|string|t(:updatedAt)
|t(:row_parameter_symbol)|string|t(:usdcSymbol)
|orderType|string|t(:usdcPerpOrderType)
|side|string|t(:side)
|qty|string|t(:usdcOrderQty)
|price|string|t(:usdcOrderPrice)
|timeInForce|string|t(:row_comment_timeInForce)
|t(:usdcOptionOrderStatus)|string|t(:row_comment_orderStatus)
|triggerPrice|string|t(:triggerPrice)



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
|t(:row_parameter_symbol) |<b>true</b>|string|t(:usdcSymbol)|
|orderFilter|<b>true</b>|string|t(:usdcOrderFilter)|
|orderId|false|string|t(:usdcOrderId)|
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

t(:cancelAllResponse)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=uopvCancelAll>/perpetual/usdc/openapi/private/v1/cancel-all</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopvCancelAll"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b>|string|t(:usdcSymbol)|
|orderFilter|<b>true</b>|string|t(:usdcOrderFilter)|


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
|t(:row_parameter_symbol) |false|string|t(:usdcSymbol)|
|<a href="#base-coin-basecoin">baseCoin</a> |false|string|t(:usdcBaseCoin)|
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
|t(:row_parameter_symbol) |string|t(:usdcSymbol)|
|orderType|string|t(:usdcPerpOrderType)|
|orderLinkId|string|t(:orderLinkId)|
|orderId|string|t(:usdcOrderId)|
|stopOrderType|string|t(:usdcStopOrderType)|
|t(:usdcOptionOrderStatus)|string|t(:row_comment_orderStatus)|
|takeProfit|string|t(:takeProfit)|
|cumExecValue|string|t(:cumExecValue)|
|createdAt|string|t(:createdAt)|
|orderPnl|string|t(:usdcOrderPnl)|
|t(:row_parameter_price) |string|t(:usdcOrderPrice)|
|tpTriggerBy|string|t(:usdcTptriggerby)|
|t(:row_parameter_timeInForce)|string|t(:row_comment_timeInForce)|
|basePrice|string|t(:basePrice)|
|t(:row_parameter_side) |string|t(:side)|
|triggerPrice|string|t(:triggerPrice)|
|cumExecFee|string|t(:cumExecFee)|
|leavesQty|string|t(:leavesQty)|
|slTriggerBy|string|t(:usdcSlTriggerBy)|
|iv|string|t(:optionIv)|
|closeOnTrigger|string|t(:closeOnTrigger)|
|cumExecQty|string|t(:cumExecQty)|
|reduceOnly|bool|t(:reduceOnly)|
|qty|string|t(:usdcOrderQty)|
|stopLoss|string|t(:stopLoss)|
|lastExecPrice|string|t(:lastExecPrice)|
|triggerBy|string|t(:usdcTriggerBy)|
|orderIM|string|t(:im)|



### t(:usdcQryOrderHistory)

```console

curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/query-order-history \
-H "Content-Type: application/json" \
-D '{
    "category": "PERPETUAL",
    "limit":1
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
          "symbol": "ETHPERP",
          "orderType": "Limit",
          "orderLinkId": "",
          "orderId": "c04ad17d-ca85-45d1-859e-561e7236f6db",
          "cancelType": "UNKNOWN",
          "stopOrderType": "UNKNOWN",
          "orderStatus": "Filled",
          "updateTimeStamp": "1666178097006",
          "takeProfit": "0.0000",
          "cumExecValue": "12.9825",
          "createdAt": "1666178096996",
          "blockTradeId": "",
          "orderPnl": "",
          "price": "1300.0",
          "tpTriggerBy": "UNKNOWN",
          "timeInForce": "GoodTillCancel",
          "updatedAt": "1666178097006",
          "basePrice": "",
          "realisedPnl": "0.0000",
          "side": "Buy",
          "triggerPrice": "0.0",
          "cumExecFee": "0.0078",
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
|category|<b>true</b>|string|t(:usdcPerpCategory)|
|t(:row_parameter_symbol) |false|string|t(:usdcSymbol)|
|<a href="#base-coin-basecoin">baseCoin</a> |false|string|t(:usdcBaseCoin)|
|orderId|false|string|t(:usdcOrderId)|
|orderLinkId|false|string|t(:orderLinkId)|
|t(:usdcOptionOrderStatus)|false|string|t(:row_comment_orderStatus)|
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
|t(:row_parameter_symbol) |string|t(:usdcSymbol)|
|orderType|string|t(:usdcPerpOrderType)|
|orderLinkId|string|t(:orderLinkId)|
|orderId|string|t(:usdcOrderId)|
|cancelType|string|t(:cancelType)|
|stopOrderType|string|t(:usdcStopOrderType)|
|t(:usdcOptionOrderStatus)|string|t(:row_comment_orderStatus)|
|updateTimeStamp|string|t(:row_resp_comment_updateTime)|
|takeProfit|string|t(:takeProfit)|
|createdAt|string|t(:createdAt)|
|orderPnl|string|t(:usdcOrderPnl)|
|t(:row_parameter_price) |string|t(:usdcOrderPrice)|
|tpTriggerBy|string|t(:usdcTptriggerby)|
|t(:row_parameter_timeInForce)|string|t(:row_comment_timeInForce)|
|updatedAt|string|t(:updateAt_usdc_orderHistory)|
|basePrice|string|t(:basePrice)|
|realisedPnl|string|t(:realisedPnl)|
|t(:row_parameter_side) |string|t(:side)|
|triggerPrice|string|t(:triggerPrice)|
|cumExecFee|string|t(:cumExecFee)|
|leavesQty|string|t(:leavesQty)|
|cashFlow|string|t(:cashFlow)|
|slTriggerBy|string|t(:usdcSlTriggerBy)|
|iv|string|t(:optionIv)|
|closeOnTrigger|string|t(:closeOnTrigger)|
|cumExecQty|string|t(:cumExecQty)|
|reduceOnly|bool|t(:reduceOnly)|
|qty|string|t(:usdcOrderQty)|
|stopLoss|string|t(:stopLoss)|
|triggerBy|string|t(:usdcTriggerBy)|
|orderIM|string|t(:im)|


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
|category|<b>true</b>|string|t(:usdcPerpCategory)|
|t(:row_parameter_symbol) |false|string|t(:usdcSymbol)|
|<a href="#base-coin-basecoin">baseCoin</a> |false|string|t(:usdcBaseCoin)|
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
|tradeTime|number|t(:tradeTime)|
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
|type|false|string|t(:usdcTransactionType)|
|baseCoin|false|string|t(:usdcBaseCoin_transLog)|
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
|transactionTime|string|t(:transactionTime)|
|t(:row_parameter_symbol) |string|t(:usdcSymbol)
|type|string|t(:usdcType)|
|t(:row_parameter_side) |string|t(:side)|
|tradePrice|string|t(:tradePrice)|
|funding|string|t(:usdcFunding)|
|qty|string|t(:usdcOrderQty)|
|size|string|t(:uscdSize)|
|fee|string|t(:fee)|
|cashFlow|string|t(:cashFlow)|
|change|string|t(:usdcChange)|
|walletBalance|string|t(:cashBalance)|
|feeRate|string|t(:feeRate)|
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)|
|tradeId|string|t(:tradeId)|
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
    "result": {
        "walletBalance": "233694603.2386",
        "accountMM": "197.8124",
        "bonus": "0.0000",
        "accountIM": "392.2333",
        "totalSessionRPL": "",
        "equity": "233694453.2634",
        "totalRPL": "-8180.6277",
        "marginBalance": "233694603.2454",
        "availableBalance": "233694211.0121",
        "totalSessionUPL": ""
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
|totalSessionRPL|string|t(:sessionRpl)|
|equity|string|t(:equity)|
|totalRPL|string|t(:totalRpl)|
|marginBalance|string|t(:marginBalance)|
|availableBalance|string|t(:availableBalance)|
|totalSessionUPL|string|t(:sessionUpl)|


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

<aside class="warning">
t(:setMarginModeWarning)
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
        "cursor": "BTCPERP%3A1655184421732%2CBTCPERP%3A1655184421732",
        "resultTotalSize": 1,
        "dataList": [
            {
                "symbol": "BTCPERP",
                "leverage": "10.00",
                "occClosingFee": "0.0000",
                "liqPrice": "",
                "positionValue": "22.9450",
                "takeProfit": "25000.0",
                "riskId": "10001",
                "trailingStop": "0.0000",
                "unrealisedPnl": "0.0000",
                "createdAt": "1655184421732",
                "markPrice": "22912.41",
                "cumRealisedPnl": "0.0000",
                "positionMM": "0.1302",
                "positionIM": "2.3100",
                "updatedAt": "1655184421732",
                "tpSLMode": "UNKNOWN",
                "side": "Buy",
                "bustPrice": "",
                "deleverageIndicator": 0,
                "entryPrice": "22945.0",
                "size": "0.001",
                "sessionRPL": "-5.3255",
                "positionStatus": "NORMAL",
                "sessionUPL": "-0.0326",
                "stopLoss": "19000.0",
                "orderMargin": "0.0000",
                "sessionAvgPrice": "22945.0"
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
|t(:row_parameter_symbol) |false|string|t(:usdcSymbol)|
|<a href="#base-coin-basecoin">baseCoin</a> |false|string|t(:usdcBaseCoin)|
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
|leverage |string|t(:usdcLeverage)|
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
|t(:row_parameter_symbol) |<b>true</b>|string|t(:usdcSymbol)|
|leverage|<b>true</b>|string|t(:usdcLeverage)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|leverage|number|t(:leverage)|



### t(:querySettleLogs)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/option/usdc/openapi/private/v1/session-settlement \
-H "Content-Type: application/json" \
-d '{"symbol":"BTCPERP"}'

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

<aside class="notice">
t(:usdcQueryLimit)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=upovSession>/option/usdc/openapi/private/v1/session-settlement</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#upovSession"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b>|string|t(:usdcSymbol)|
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
|time|string|t(:settlementTime)|
|t(:row_parameter_symbol) |string|t(:usdcSymbol)|
|t(:row_parameter_side) |string|t(:side)|
|size|string|t(:usdcSize)|
|sessionAvgPrice|string|t(:sessionAvgPrice)|
|markPrice|string|t(:usdcMarkPrice)|
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
{
    "retCode": 0,
    "retMsg": "",
    "result": [
        {
            "riskId": "10001",
            "symbol": "BTCPERP",
            "limit": "1000000",
            "startingMargin": "0.0100",
            "maintainMargin": "0.0050",
            "isLowestRisk": true,
            "section": [
                "1",
                "2",
                "3",
                "5",
                "10",
                "25",
                "50",
                "100"
            ],
            "maxLeverage": "100.00"
        }
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=uopv>/perpetual/usdc/openapi/public/v1/risk-limit/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#uopv"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b>|string|t(:usdcSymbol)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_symbol) |string|t(:usdcSymbol)|
|riskId|string|t(:riskId)|
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
|t(:row_parameter_symbol) |<b>true</b>|string|t(:usdcSymbol)|
|riskId|<b>true</b>|number|t(:riskId)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|riskId|number|t(:riskId)|


## t(:usdcFundingApi)
### t(:fundingRate)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/perpetual/usdc/openapi/public/v1/prev-funding-rate?symbol=BTCPERP \

```

```python

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "",
    "result": {
        "symbol": "BTCPERP",
        "fundingRate": "0.00010000",
        "fundingRateTimestamp": "1652313600000"
    }
}
```

t(:account_para_myLastFunding)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=usdcPerpPrevFunding>/perpetual/usdc/openapi/public/v1/prev-funding-rate</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#usdcPerpPrevFunding"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|symbol|string|t(:usdcSymbol)|
|fundingRate |string |t(:row_comment_funding_rate)  |
|fundingRateTimestamp |string |t(:row_comment_exec_timestamp)  |


### t(:predictedfunding)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/perpetual/usdc/openapi/private/v1/predicted-funding \
-H "Content-Type: application/json" \
-d '{"symbol":"BTCPERP"}'

```

```python

```

> t(:codequote_responseExample)

```javascript
{
    "result": {
        "predictedFundingRate": "0.00010",
        "predictedFundingFee": "29.0848836700"
    },
    "retCode": 0,
    "retMsg": "success"
}
```
t(:account_para_predictedFunding)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=usdcPerpPredictedFunding>/perpetual/usdc/openapi/private/v1/predicted-funding</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#usdcPerpPredictedFunding"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|predictedFundingRate |string |t(:row_comment_predicted_funding_rate)    |
|predictedFundingFee |string |t(:row_comment_predicted_funding_fee)  |
