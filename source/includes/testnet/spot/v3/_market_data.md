# t(:marketdata)
t(:market_para_auth)


### t(:getSymbols)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/public/symbols'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "list": [
            {
                "name": "BTCUSDT",
                "alias": "BTCUSDT",
                "baseCoin": "BTC",
                "quoteCoin": "USDT",
                "basePrecision": "0.000001",
                "quotePrecision": "0.00000001",
                "minTradeQty": "0.000001",
                "minTradeAmt": "10",
                "maxTradeQty": "63.01197227",
                "maxTradeAmt": "1000000",
                "minPricePrecision": "0.01",
                "category": "1",
                "showStatus": "1",
                "innovation": "0"
            },
            {
                "name": "ETHUSDT",
                "alias": "ETHUSDT",
                "baseCoin": "ETH",
                "quoteCoin": "USDT",
                "basePrecision": "0.00001",
                "quotePrecision": "0.0000001",
                "minTradeQty": "0.00224",
                "minTradeAmt": "10",
                "maxTradeQty": "100000000",
                "maxTradeAmt": "100000000",
                "minPricePrecision": "0.01",
                "category": "1",
                "showStatus": "1",
                "innovation": "0"
            }
        ]
    },
    "retExtMap": {},
    "retExtInfo": {},
    "time": 1659067662931
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=svPostOrder>/spot/v3/public/symbols</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svPostOrder"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
| t(:column_parameter) | t(:column_required) | t(:column_type) | t(:column_comments) |
|:---------------------|:--------------------|:----------------|---------------------|

<p class="fake_header">t(:responseparameters)</p>
| t(:column_parameter) | t(:column_type) | t(:column_comments)       |
|:---------------------|:----------------|---------------------------|
| name                 | string          | t(:spotSymbol)            |
| alias                | string          | t(:spot_Alias)            |
| baseCoin             | string          | t(:spotBaseCurrency)      |
| quoteCoin            | string          | t(:spotQuoteCurrency)     |
| basePrecision        | string          | t(:spotBasePrecision)     |
| quotePrecision       | string          | t(:spotQuotePrecision)    |
| minTradeQty          | string          | t(:spotMinTradeQuantity)  |
| minTradeAmt          | string          | t(:spotMinTradeAmount)    |
| minPricePrecision    | string          | t(:spotMinPricePrecision) |
| maxTradeQty          | string          | t(:spotmaxTradeQuantity)  |
| maxTradeAmt          | string          | t(:spotmaxTradeAmount)    |
| category             | string          | t(:spotCategory)          |
| innovation           | string          | t(:spotV3_comment_innovation)     |
| showStatus           | string          | t(:spotV3_comment_showStatus)     |

