# t(:wallet)
t(:wallet_para)

## t(:balance)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/private/account' \
--header 'X-BAPI-SIGN: 6f5c1a9543ea9033013b4ec0a6d05a74e2d05d109c60ad464ab7f9c6e86ad0d4' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1659346886605' \
--header 'X-BAPI-RECV-WINDOW: 5000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "balances": [
            {
                "coin": "BTC",
                "coinId": "BTC",
                "total": "0.20378018343",
                "free": "0.20378018343",
                "locked": "0"
            },
            {
                "coin": "BTC3L",
                "coinId": "BTC3L",
                "total": "743.03560386",
                "free": "743.03560386",
                "locked": "0"
            },
            {
                "coin": "BTC3S",
                "coinId": "BTC3S",
                "total": "0.999",
                "free": "0.999",
                "locked": "0"
            }
        ]
    },
    "retExtMap": {},
    "retExtInfo": {},
    "time": 1659346887407
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

