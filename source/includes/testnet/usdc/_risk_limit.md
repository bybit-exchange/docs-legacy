# t(:riskLimit)


## t(:queryRiskLimits) 


> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com//perpetual/usdc/openapi/public/v1/risk-limit/list \
-H "Content-Type: application/json" \
-d '{"symbol":"BTCUSD"}'
```

```python

```


> t(:codequote_responseExample)

```javascript

```

t(:riskLimitDesc)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/perpetual/usdc/openapi/public/v1/risk-limit/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

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


## t(:setRiskLimits) 


> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/perpetual/usdc/openapi/private/v1/position/set-risk-limit \
-H "Content-Type: application/json" \
-d '{"symbol":"BTCUSD","risk_id":2}'

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
<code><span id=vpoCreate>/perpetual/usdc/openapi/private/v1/position/set-risk-limit</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:usdcSymbol)|
|riskId|<b>true</b>|number|t(:riskId)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|riskId|number|t(:riskId)|





