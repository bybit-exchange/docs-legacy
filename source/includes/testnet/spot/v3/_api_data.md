# t(:api)
t(:api_para)

### t(:servertime)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/spot/v3/public/server-time
```

```python--pybit
from pybit import spot
session_unauth = spot.HTTP(
    endpoint="https://api-testnet.bybit.com"
)
print(session_unauth.server_time())
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "ok",
    "result": {
        "serverTime": 1625799317787
    },
    "time":123456
}
```
t(:api_para_time)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpTime>/spot/v3/public/server-time</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpTime"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

| t(:column_parameter) | t(:column_required) | t(:column_type)  | t(:column_comments) |
|:---------------------|:--------------------|:-----------------|---------------------|

<p class="fake_header">t(:responseparameters)</p>

| t(:column_parameter) | t(:column_type) | t(:column_comments) |
|:---------------------|:----------------|---------------------|
| serverTime           | string          | 服务器时间               |
