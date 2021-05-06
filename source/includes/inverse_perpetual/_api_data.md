# t(:api)
t(:api_para)

### t(:servertime)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/public/time
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Common.Common_get().result())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {},
    "time_now": "1577444332.192859"
}
```
t(:api_para_time)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpTime>/v2/public/time</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpTime"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

### t(:announcement)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/v2/public/announcement
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": [
        {
            "id": 2,
            "title": "2019-12-02 RELEASE",
            "link": "https://github.com/bybit-exchange/bybit-official-api-docs/blob/master/en/CHANGELOG.md",
            "summary": "<p>New `cancel all` endpoint is here now!</p><p>Additionally, we strongly recommend that you use the new released place and cancel active V2 endpoints, which are more stable and efficient.The old ones are deprecated (although still working for the time be",
            "created_at": "2019-12-02T11:33:42Z"
        }
    ],
    "time_now": "1577444818.227082"
}
```

t(:api_para_announcement)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpAnnouncement>/v2/public/announcement</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpAnnouncement"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |


### t(:getrisklimit)
> t(:codequote_curlExample)

```console
curl "https://api.bybit.com/v2/public/risk-limit/list?api_key={api_key}&timestamp={timestamp}&sign={sign}"
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": [
        {
            "id": 1,
            "coin": "BTC",
            "symbol": "BTCUSD",
            "limit": 150,
            "maintain_margin": "0.50",
            "starting_margin": "1.00",
            "section": [
                "1",
                "2",
                "3",
                "5",
                "10",
                "25",
                "50",
                "100"
            ],
            "is_lowest_risk": 1,
            "created_at": "2018-09-21T11:34:11.000Z",
            "updated_at": "2018-09-21T11:34:11.000Z",
            "max_leverage": "100.00"
        },
        {
            "id": 10,
            "coin": "BTC",
            "symbol": "BTCUSD",
            "limit": 1500,
            "maintain_margin": "5.00",
            "starting_margin": "5.50",
            "section": [
                "1",
                "2",
                "3",
                "4",
                "5",
                "10",
                "15",
                "18"
            ],
            "is_lowest_risk": 0,
            "created_at": "2018-09-21T11:34:11.000Z",
            "updated_at": "2018-09-21T11:34:11.000Z",
            "max_leverage": "18.18"
        }
    ],
    "ext_info": null,
    "time_now": "1616568086.769014",
    "rate_limit_status": 599,
    "rate_limit_reset_ms": 1616568086777,
    "rate_limit": 600
}
```

t(:wallet_para_getRisk)

<aside class="notice">
t(:wallet_aside_getRisk)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oawrlList>v2/public/risk-limit/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawrlList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>false</b> |string |t(:row_comment_symbol)   |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |number |t(:row_comment_riskId)  |
|coin |string |t(:row_comment_coin_type)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)   |
|limit |number |t(:row_comment_risk_limit)    |
|maintain_margin |string |t(:row_comment_maintain_margin)  |
|starting_margin |string |t(:row_comment_starting_margin)  |
|section |string |t(:row_comment_section)  |
|is_lowest_risk |number |t(:row_comment_is_lowest_risk)    |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|max_leverage |string |t(:row_comment_max_leverage)  |
