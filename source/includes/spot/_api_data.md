# t(:api)
t(:api_para)

### t(:servertime)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/spot/v1/time
```

> t(:codequote_responseExample)

```javascript
{
	"ret_code": 0,
	"ret_msg": "",
	"ext_code": null,
	"ext_info": null,
	"result": {
		"serverTime": 1625799317787
	}
}
```
t(:api_para_time)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpTime>/spot/v1/time</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpTime"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
