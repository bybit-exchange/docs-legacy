# API Data Endpoints
The following API data endpoint does not require authentication.

### Announcement
> Response Example

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

Get Bybit OpenAPI announcements in the last 30 days.

##### HTTP Request
GET
<code><span id=vpAnnouncement>/v2/public/announcement</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpAnnouncement"><img src="images/copy_to_clipboard.png" height=15 width=15></a></button>

##### Request Parameters
|parameter|required|type|comments|
|:----- |:-------|:-----|----- |
