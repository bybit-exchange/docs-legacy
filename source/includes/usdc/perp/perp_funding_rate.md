# t(:usdcFundingRate)

## t(:queryLastSessionFundingRate)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com//perpetual/usdc/openapi/private/v1/prev-funding-rate \
-H "Content-Type: application/json" \
-d '{"symbol":"BTCUSD"}'
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
        "fundingRate": "0.00075",
        "fundingRateTimestamp": "1577433600"
    }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/perpetual/usdc/openapi/private/v1/prev-funding-rate</span></code>
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
curl https://api-testnet.bybit.com//perpetual/usdc/openapi/private/v1/prev-funding \
-H "Content-Type: application/json" \
-d '{"symbol":"BTCUSD"}'
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
        "symbol":"BTCUSD",
        "side":"Buy",
        "size":"1",
        "fundingRate":"0.0001",
        "execFee":"0.00000002",
        "execTimestamp":1575907200
      
    }
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/perpetual/usdc/openapi/private/v1/prev-funding</span></code>
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

curl https://api-testnet.bybit.com//perpetual/usdc/openapi/private/v1/predicted-funding \
-H "Content-Type: application/json" \
-d '{"symbol":"BTCUSD"}'

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
        
        "predictedFundingRate":"0.0001",
      "predictedFundingFee":"0"
    }
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/perpetual/usdc/openapi/private/v1/funding/predicted-funding</span></code>
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




