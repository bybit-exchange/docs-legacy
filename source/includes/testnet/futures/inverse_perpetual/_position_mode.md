## t(:switchpositionmode)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/private/position/switch-mode \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","mode":0,"timestamp":{timestamp},"sign":"{sign}"}'
```


> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": null,
    "ext_info": null,
    "time_now": "1577477968.175013",
    "rate_limit_status": 74,
    "rate_limit_reset_ms": 1577477968183,
    "rate_limit": 75
}
```

t(:account_para_switchpositionmode)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=ulSwitchMode>/v2/private/position/switch-mode</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ulSwitchMode"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|mode |<b>true</b> |int |t(:row_comment_positionmode) |
