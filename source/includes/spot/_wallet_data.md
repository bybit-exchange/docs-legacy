# t(:wallet)
t(:wallet_para)

## t(:spot_balance)
> t(:codequote_curlExample)

```console
```

```python
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "",
    "ext_code": null,
    "ext_info": null,
    "result": {
        "balances": [
            {
                "coin": "USDT",
                "coinId": "USDT",
                "coinName": "USDT",
                "total": "10",
                "fee": "10",
                "locked": "0"
            }
        ]
    }
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpOrder>/spot/v1/account</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|balances|object|t(:spot_balances)|

<p class="fake_header">balances object</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|coin| string | t(:spot_token)|
|coinId| string | t(:spot_token)|
|coinName| string | t(:spot_token)|
|total| string | t(:spot_total)|
|fee| float| t(:spot_fees)|
|locked| float | t(:spot_locked)
