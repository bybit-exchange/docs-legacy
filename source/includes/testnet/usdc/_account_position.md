# t(:accountPosition)


## t(:queryPosition)
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
<code><span id=vpoCreate>/usdc/openapi/private/v1/query-position</span></code>
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
|riskId|string|riskId|
|symbol|string|t(:usdcSymbol)|
|side|string|t(:side)|
|size|string|t(:uscdSize)
|entryPrice|string|t(:entryPrice)
|sessionAvgPrice|string|t(:sessionAvgPrice)|
|markPrice|string|t(:markPrice)|
|positionPnl|string|t(:positionPnl)|
|roi|string|t(:roi)|
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
|cumCommission|string|t(:cumCommission)|


## t(:setTakeProfitAndStopLoss) 
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
<code><span id=vpoCreate>/usdc/openapi/private/v1/trading-stop</span></code>
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


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/usdc/openapi/private/v1/tpsl/switch-mode</span></code>
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
        "leverage": 10
    }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/usdc/openapi/private/v1/leverage/save</span></code>
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
<code><span id=vpoCreate>/usdc/openapi/private/v1/closed-pnl/list</span></code>
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


## t(:querySettleLogs) 

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
        "orderId": "1fd26147-247d-4433-9845-a236981c3681",
        "symbol": "1fd26147-247d-4433-9845-a236981c3689",
        "side": "Buy",
        "orderQty": "1",
        "orderPrice": "1",
        "orderType": "Limit",
        "execType": "1",
        "closedSize": "1",
        "cumEntryValue": "1",
        "cumExitValue": "1",
        "avgEntryPrice": "1",
        "avgExitPrice": "1",
        "closedPnl": "1",
        "fillCount": "1",
        "leverage": "0",
        "createdAt": 1232
    }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/usdc/openapi/private/v1/session-settlement</span></code>
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
        "expDate": 20211111,
        "pnl": "ETHUSDT",
        "totalRpl": "162073788655749",
        "sessionUpl": "100",
        "sessionRpl": "1620737886573",
        "im": "1620737886573",
        "mm": "1620737886573"
    }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/usdc/openapi/private/v1/position/exp-date</span></code>
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
|expDate|string|t(:expDate)|
|pnl|string|t(:pnl)|
|totalRpl|string|t(:totalRpl)|
|sessionUpl|string|t(:sessionUpl)|
|sessionRpl|string|t(:sessionRpl)|
|im|string|t(:usdcIm)|
|mm|string|t(:usdcMm)|
