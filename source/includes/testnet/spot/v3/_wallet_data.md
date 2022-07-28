# t(:wallet)
t(:wallet_para)

## t(:balance)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com//spot/v3/private/account \
-H "Content-Type: application/x-www-form-urlencoded" \
-d 'api_key={api_key}&side=Buy&symbol=ETHUSDT&type=MARKET&qty=10&timeInForce=GTC&timestamp={timestamp}&sign={signature}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "ok",
    "result": {
        "list": [
            {
                "coin": "USDT",
                "coinId": "USDT",
                "total": "10",
                "free": "10",
                "locked": "0"
            }
        ]
    },
    "time":1234567
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=svAccount>/spot/v3/private/account</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svAccount"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

| t(:column_parameter) | t(:column_required) | t(:column_type) | t(:column_comments) |
|:---------------------|:--------------------|:----------------|---------------------|

<p class="fake_header">t(:responseparameters)</p>

| t(:column_parameter) | t(:column_type) | t(:column_comments)   |
|:---------------------|:----------------|-----------------------|
| coin                 | string          | t(:spot_token)        |
| coinId               | string          | t(:spot_token)        |
| total                | string          | t(:spot_total)        |
| free                 | string          | t(:spot_account_free) |
| locked               | string          | t(:spot_locked)       |

