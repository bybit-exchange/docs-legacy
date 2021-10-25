# t(:accountPosition)


## t(:queryPosition)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/option/usdc/openapi/private/v1/query-position \
-H "Content-Type: application/json" \
-D '{"symbol":"BTC-22OCT21-40000-C","category":"option"}'
```

```python

```


> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"成功",
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
        "occFundingFee":"",
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
<code><span id=vpoCreate>/option/usdc/openapi/private/v1/query-position</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|category|<b>true</b>|string|t(:category)|
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
|im|string|t(:usdcMm)|
|createdAt|string|t(:createdAt)|
|updatedAt|string|t(:updatedAt)|
|tpSlMode|string|t(:tpSlMode)|
|positionValue|string|t(:positionValue)|
|leverage|string|t(:leverage)|
|liqPrice|string|t(:liqPrice)|
|trailingStop|string|t(:trailingStop)|
|bustPrice|string|t(:bustPrice)|
|occClosingFee|string|t(:occClosingFee)|
|occFundingFee|string|t(:occFundingFee)|
|trakeProfit|string|t(:trakeProfit)|
|stopLoss|string|t(:stopLoss)|
|positionStatus|string|t(:positionStatus)|
|deleverageIndicator|string|t(:deleverageIndicator)|
|orderMargin|string|t(:orderMargin)|
|unrealisedPnl|string|t(:unrealisedPnl)|
|cumRealisedPnl|string|t(:cumRealisedPnl)|


## t(:setTakeProfitAndStopLoss) 
> t(:codequote_curlExample)

```console

url https://api.bybit.com/v2/private/position/trading-stop \
-H "Content-Type: application/json" \
-d '{"symbol":"BTCUSD","stop_loss":7000}'

```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Positions.Positions_tradingStop(symbol="BTCUSD",stop_loss="7000").result())

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "",
    "extCode": null,
    "extInfo": null,
    "result": {
        "id": "1",
        "userId": "10001",
        "symbol": "",
        "side": "Buy",
        "size": "10"
        "positionValue": "",
        "entryPrice": "1000",
        "leverage": 10,
        "positionMargin": "1000",
        "occClosingFee": "1000",
        "occFundingFee": "1000",
        "takeProfit": "",
        "stopLoss": "",
        "trailingStop": "",
        "positionStatus": "",
        "executedQty": "10",
        "orderMargin": "100",
        "walletBalance": "100",
        "cumCommission": "100",
    }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/perpetual/usdc/openapi/private/v1/trading-stop</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|takeProfit|false|string|t(:tradingStopTakeProfit)|
|stopLoss|false|string|t(:tradingStopLoss)|
|trailingStop|false|string|t(:tradingTrailingStop)|
|tpTriggerBy|string|string|t(:tptriggerby)|
|slTriggerBy|string|string|t(:slTriggerBy)|
|trailingActive|string|string|t(:trailingActive)|
|slSize|string|string|t(:slSize)|
|tpSize|string|string|t(:tpSize)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id|string|t(:usdcId)|
|userId|string|t(:userId)|
|symbol|string|t(:usdcSymbol)|
|side|string|t(:side)|
|size|string|t(:usdcSize)
|positionValue|string|t(:positionValue)
|entryPrice|string|t(:entryPrice)
|leverage|string|t(:leverage)|
|positionMargin|string|t(:positionMargin)|
|occClosingFee|string|t(:occClosingFee)|
|occFundingFee|string|t(:occFundingFee)|
|takeProfit|string|t(:takeProfit)|
|stopLoss|string|t(:stopLoss)|
|trailingStop|string|t(:trailingStop)|
|positionStatus|string|t(:positionStatus)|
|orderMargin|string|t(:orderMargin)|
|walletBalance|string|t(:walletBalance)|
|cumRealisedPnl|string|t(:cumRealisedPnl)|
|cumCommission|string|t(:cumCommission)|

## t(:changeTakeProfitAndStopLoss) 
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
        "tpSlMode": "Partial"
    }
}
```

<aside class="notice">
t(:switchmode_aside)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/perp/usdc/openapi/private/v1/tpsl/switch-mode</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|tpSlMode|<b>true</b>|string|t(:tpSlMode)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|tpSlMode|string|t(:tpSlMode)|


## t(:setPositionLeverage) 
> t(:codequote_curlExample)

```console

curl https://api.bybit.com/perp/usdc/openapi/private/v1/leverage/save \
-H "Content-Type: application/json" \
-d '{"symbol":"BTCUSD","buy_leverage":14,"sell_leverage":14}'

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
        "leverage": 10
    }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/perp/usdc/openapi/private/v1/leverage/save</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|leverage|<b>true</b>|number|t(:usdcLeverage)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|leverage|number|t(:leverage)|


## t(:queryClosingProfitAndLoss) 
> t(:codequote_curlExample)

```console

curl https://api.bybit.com//perp/usdc/openapi/private/v1/closed-pnl/list \
-H "Content-Type: application/json" \
-d '{"symbol":"BTCUSD"}'
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Positions.Positions_closePnlRecords(symbol="BTCUSD").result())

```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "",
    "extCode": null,
    "extInfo": null,
    "result": {
        "orderId": "ETHUSDT",
        "symbol": "ETHUSDT",
        "side": "ETHUSDT",
        "orderType": "ETHUSDT",
        "orderPrice": "ETHUSDT",
        "orderQty": "ETHUSDT",
        "execType": "162073788655749",
        "closedSize": "162073788655749",
        "cumEntryValue": "100",
        "cumExitValue": "1620737886573",
        "avgEntryPrice": "1620737886573",
        "avgExitPrice": "1620737886573",
        "closedPnl": "1620737886573",
        "fillCount": "1620737886573",
        "leverage": "20000",
        "createdAt": "10"
    }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/perp/usdc/openapi/private/v1/closed-pnl/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|startTime|false|number|t(:startTime)|
|endTime|false|number|t(:endTime)|
|execType|false|string|t(:execType)|
|direction|false|string|t(:direction)|
|limit|false|number|t(:usdcMax50Min20)|
|cursor|false|string|t(:cursor)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId|string|t(:usdcOrderId)|
|symbol|string|t(:usdcSymbol)|
|side|string|t(:side)|
|orderQty|string|t(:usdcOrderQty)|
|orderPrice|string|t(:usdcOrderPrice)|
|orderType|string|t(:usdcOrderType)|
|execType|string|t(:execType)|
|closedSize|string|t(:closedSize)|
|cumEntryValue|string|t(:cumEntryValue)|
|cumExitValue|string|t(:cumExitValue)|
|avgEntryPrice|string|t(:avgEntryPrice)|
|avgExitPrice|string|t(:avgExitPrice)|
|closedPnl|string|t(:closedPnl)|
|fillCount|string|t(:fillCount)|
|leverage|string|t(:leverage)|
|createdAt|number|t(:createdAt)|


## t(:queryDeliveryLog)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/option/usdc/openapi/private/v1/query-delivery-list \
-H "Content-Type: application/json" \
-d '{"symbol":"BTC-22OCT21-45000-C"}'
```

```python

```


> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"成功",
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
<code><span id=vpoCreate>/option/usdc/openapi/private/v1/query-delivery-list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

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





## t(:querySettleLogs) 

> t(:codequote_curlExample)

```console
curl https://api.bybit.com/option/usdc/openapi/private/v1/session-settlement \
-H "Content-Type: application/json" \
-d '{"symbol":"BTC-22OCT21-45000-C"}'

```

```python

```


> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"成功",
    "result":{
    "resultTotalSize":1,
      "cursor":"",
      "dataList":[
        {
          "symbol":"1fd26147-247d-4433-9845-a236981c3689",
          "side":"Buy",
          "size":"1",
          "sessionAvgPrice":"1",
          "markPrice":"100",
          "sessionRpl":"100"
        }
    ]
  }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/option/usdc/openapi/private/v1/session-settlement</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

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
|symbol|string|t(:usdcSymbol)|
|side|string|t(:side)|
|size|string|t(:usdcSize)|
|sessionAvgPrice|string|t(:sessionAvgPrice)|
|markPrice|string|t(:markPrice)|
|sessionRpl|string|t(:sessionRpl)|
|cursor|string|t(:cursor)|



## t(:queryPositionInfo) 

> t(:codequote_curlExample)

```console
curl https://api.bybit.com/option/usdc/openapi/private/v1/query-position-exp-date \
-H "Content-Type: application/json" \
-d '{"expDate":"20211010"}'

```

```python

```


> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"成功",
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
<code><span id=vpoCreate>/option/usdc/openapi/private/v1/query-position-exp-date</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

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
