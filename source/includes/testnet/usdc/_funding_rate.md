# t(:usdcFundingRate)

## t(:queryLastSessionFundingRate)
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


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/usdc/openapi/private/v1/prev-funding-rate</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|symbol|string|t(:usdcSymbol)|
|fundingRate|string|t(:usdcPreFundingRate)|
|fundingRateTimestamp|number|t(:fundingRateTimestamp)|


## t(:queryLastSessionFundingInfo)

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
        "":
    }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/usdc/openapi/private/v1/prev-funding</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|symbol|string|t(:usdcSymbol)|
|side|string|t(:side)|
|size|string|t(:usdcSize)|
|fundingRate|string|t(:usdcPreFundingRate)|
|execFee|string|t(:execFee)|
|execTimestamp|number|t(:execTimestamp)|



## t(:predictedFundingRateAndFee)

> t(:codequote_curlExample)

```console
curl https://api.bybit.com/spot/v1/order \
-H "Content-Type: application/x-www-form-unlencoded" \
-d 'api_key={api_key}&side=Buy&symbol=ETHUSDT&orderType=MARKET&qty=10&timeInForce=GTC&timestamp={timestamp}&sign={signature}'

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
        
    }
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/usdc/openapi/private/v1/funding/predicted-funding</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|predictedFundingRate|string|t(:predictedFundingRate)|
|predictedFundingFee|string|t(:predictedFundingFee)|




