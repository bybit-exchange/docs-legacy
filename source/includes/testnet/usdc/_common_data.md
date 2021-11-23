# t(:api)
t(:api_para)

### t(:servertime)
> t(:codequote_curlExample)

```console

curl https://api-testnet.bybit.com/v2/public/time

```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {},
    "time_now": "1637635413.927628"
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
curl https://api-testnet.bybit.com/v2/public/announcement
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "extCode": "",
    "extInfo": "",
    "result": [
        {
            "id": 2,
            "title": "2021-09-30 RELEASE",
            "link": "https://github.com/bybit-exchange/bybit-official-api-docs/blob/master/en/CHANGELOG.md",
            "summary": "<p>New `cancel all` endpoint is here now!</p><p>Additionally, we strongly recommend that you use the new released place and cancel active V2 endpoints, which are more stable and efficient.The old ones are deprecated (although still working for the time be",
            "created_at": "2021-09-30T11:33:42Z"
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
