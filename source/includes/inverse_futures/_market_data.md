# t(:marketdata)
t(:market_para_auth)

### t(:orderbook)
<a href="/docs/inverse#t-orderbook">t(:shared_endpoint_desc)</a>

### t(:querykline)
<a href="/docs/inverse#t-querykline">t(:shared_endpoint_desc)</a>

### t(:latestsymbolinfo)
<a href="/docs/inverse#t-latestsymbolinfo">t(:shared_endpoint_desc)</a>

### t(:publictradingrecords)
<a href="/docs/inverse#t-publictradingrecords">t(:shared_endpoint_desc)</a>

### t(:querysymbol)
<a href="/docs/inverse#t-querysymbol">t(:shared_endpoint_desc)</a>

### t(:query_liqrecords)
<a href="/docs/inverse#t-query_liqrecords">t(:shared_endpoint_desc)</a>

### t(:markpricekline)
<a href="/docs/inverse#t-markpricekline">t(:shared_endpoint_desc)</a>

### t(:queryindexpricekline)
<a href="/docs/inverse#t-queryindexpricekline">t(:shared_endpoint_desc)</a>

## t(:advanceddata)
### t(:marketopeninterest)
<a href="/docs/inverse#t-marketopeninterest">t(:shared_endpoint_desc)</a>
### t(:marketbigdeal)
<a href="/docs/inverse#t-marketbigdeal">t(:shared_endpoint_desc)</a>
### t(:marketaccountratio)
<a href="/docs/inverse#t-marketaccountratio">t(:shared_endpoint_desc)</a>
### t(:querysettlerecord)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/futures/public/settle-record?symol=BTCUSDH21 \
```

```python
```

> t(:codequote_responseExample)

```javascript
{
  "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
    "data": [
      {

        "symbol_name": "BTCUSD1225",
        "settle_price_e4": 23609.2628,
        "settle_time_e9": "2020-12-25 15:30:00",
      }
    ],
      "cursor": "w01XFyyZc8lhtCLl6NgAaYBRfsN9Qtpp1f2AUy3AS4+fFDzNSlVKa0od8DKCqgAn"
  },
  "time_now": "1608881400.173848",
    "rate_limit_status": 599,
    "rate_limit_reset_ms": 1604653633171,
    "rate_limit": 600
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpoList>/futures/public/settle-record</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|data > symbol_name |string |t(:row_comment_symbol) |
|data > SettlePriceE4 |number |t(:row_comment_settle_price_e4)
|data > settle_time_e9 |string |t(:row_comment_settle_time_e9)
