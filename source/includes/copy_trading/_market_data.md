# t(:marketdata)
t(:market_para_auth)

### t(:ct_symbol_list)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/contract/v3/public/copytrading/symbol/list
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Symbol.Symbol_list().result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com")
print(session.symbol_list())
```


> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "list": [
      {
        "symbol": "BTCUSDT",
        "baseCurrency": "BTC",
        "quoteCurrency": "USDT",
        "priceScale": "1",
        "takerFee": "0.00075",
        "makerFee": "-0.00025",
        "fundingInterval": "480",
        "leverageFilter": {
          "maxLeverage": "100",
          "minLeverage": "1"
        },
        "priceFilter": {
          "minPrice": "0.5",
          "maxPrice": "999999.0",
          "tickSize": "0.5"
        },
        "lotSizeFilter": {
          "qtyStep": "0.001",
          "maxOrderQty": "100.000",
          "minOrderQty": "0.001"
        }
      }
    ]
  }
}
```

t(:ct_symbol_list)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpSymbols>/contract/v3/public/copytrading/symbol/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpSymbols"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)   |
|baseCurrency |string |t(:row_response_comment_base_currency)    |
|quoteCurrency |string |t(:row_response_comment_quote_currency)    |
|priceScale |string |t(:row_response_comment_price_scale)    |
|takerFee |string |t(:row_response_comment_taker_fee)    |
|makerFee |string |t(:row_response_comment_maker_fee)    |
|fundingInterval |string |t(:row_response_funding_interval)    |
|leverageFilter |object[] ||
|maxLeverage |string |t(:row_response_comment_public_max_leverage)    |
|minLeverage |string |t(:row_response_comment_min_leverage)    |
|priceFilter |object[] ||
|minPrice |string |t(:row_response_comment_min_price)    |
|maxPrice |string |t(:row_response_comment_max_price)    |
|tickSize |string |t(:row_response_comment_tick_size)    |
|lotSizeFilter |object[] ||
|qtyStep |string |t(:row_response_comment_qty_step)    |
|maxOrderQty |string |t(:row_response_comment_max_trading_qty)    |
|minOrderQty |string |t(:row_response_comment_min_trading_qty)    |



