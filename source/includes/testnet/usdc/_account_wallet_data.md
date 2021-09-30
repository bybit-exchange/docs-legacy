# t(:account_wallet)
t(:wallet_para)

### t(:transactionLog)

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
        "transactionTime": 111111,
        "orderType": "Limit",
        "type": "",
        "side": "Buy",
        "orderPrice": "1.1",
        "orderQty": "10",
        "size": "1o",
        "tradePrice": "100.1",
        "funding": "100",
        "fee": "100",
        "cashFlow": "100",
        "change": "100",
        "cashBalance": "100",
         "feeRate": "0.075",
        "tradeId": "1fd26147-247d-4433-9845-a236981c3689",
        "orderId": "1fd26147-247d-4433-9845-a236981c3689",
        "orderLinkId": "1fd26147-247d-4433-9845-a236981c3689"
    }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/usdc/openapi/private/v1/query-transaction-log</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|type|<b>true</b>|string|t(:usdcType)|
|startTime|<b>true</b>|string|t(:usdcStartTime)|
|endTime|<b>true</b>|string|t(:usdcEndTime)|
|direction|false|string|t(:direction)|
|limit|<b>true</b>|string|t(:row_comment_limit)|
|cursor|false|string|t(:cursor)|


<p class="fake_header">t(:responseparameters)</p>

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
|cashBalance|string|t(:cashBalance)|
|feeRate|string|t(:feeRate)|
|tradeId|string|t(:tradeId)|
|orderId|string|t(:usdcOrderId)|
|orderLinkId|string|t(:orderLinkId)|
|info|string|t(:usdcInfo)|


### t(:accountInfo)

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
        "equity": "ETHUSDT",
        "cashBalance": "ETHUSDT",
        "availableBalance": "ETHUSDT",
        "marginBalance": "ETHUSDT",
        "accountIm": "162073788655749",
        "accountMm": "100",
        "totalRpl	": "1620737886573",
        "totalSessionUpl": "1620737886573",
        "totalSessionRpl": "1620737886573"
    }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/usdc/openapi/private/v1/query-account-info</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|equity|number|t(:equity)|
|cashBalance|string|t(:cashBalance)
|availableBalance|string|t(:availableBalance)|
|marginBalance|string|t(:marginBalance)|
|accountIm|string|t(:accountIm)|
|accountMm|string|t(:accountMm)|
|totalRpl|string|t(:totalRpl)|
|totalSessionUpl|string|t(:totalSessionUpl)|
|totalSessionRpl|string|t(:totalSessionRpl)|


### t(:assetInfo)

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
    "result": [
        {
          "baseCoin": "ETHUSDT",
          "totalDelta": "ETHUSDT",
          "totalGamma": "ETHUSDT",
          "totalVega": "ETHUSDT",
          "totalTheta": "162073788655749",
          "im": "100",
          "mm": "1620737886573",
          "totalRpl": "1620737886573",
          "sessionUpl": "1620737886573",
          "sessionRpl": "1620737886573"
        }
    ]
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/usdc/openapi/private/v1/query-asset-info</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|baseCoin|false|string|t(:usdcBaseCoin)|

<p class="fake_header">t(:responseparameters)</p>

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


### t(:setMarginMode)

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
    "result": [
        {
          "marginMode": "ETHUSDT"
        }
    ]
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/usdc/openapi/private/v1/set-margin-mode</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|marginMode|<b>true</b>|string|t(:usdcMarginMode)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|marginMode|string|t(:usdcMarginMode)|



### t(:queryMarginMode)
coming on soon



