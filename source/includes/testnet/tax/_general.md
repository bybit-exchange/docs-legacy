# t(:taxEndpoint)
## t(:registerDate)
> t(:codequote_curlExample)

```console

```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpoL2>/fht/compliance/tax/v3/private/registertime</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoL2"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|registerTime |DateTime |t(:taxRegisterDate) |


## t(:requestExportRepot)
> t(:codequote_curlExample)

```console

```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpoL2>/fht/compliance/tax/v3/private/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoL2"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|reportType |<b>true</b> |string |<a href="#reporttype-reporttype">Report Type</a> |
|reportNumber |<b>true</b> |number |<a href="#reportnumber-reportnumber">Report Number</a> |
|startTime |<b>true</b> |number |t(:taxStartTime) |
|endTime |<b>true</b> |number |t(:taxEndTime) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|respExample |string | |


## t(:exportReportStatus)
> t(:codequote_curlExample)

```console

```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoL2>/fht/compliance/tax/v3/private/status</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoL2"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|queryid |<b>true</b> |string |t(:taxQueryId) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|Result |number |t(:taxExportStatus) |


## t(:retrieveDataExport)
> t(:codequote_curlExample)

```console

```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpoL2>/fht/compliance/tax/v3/private/url</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoL2"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|queryid |<b>true</b> |string |t(:taxQueryId) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|report |string |t(:taxReportUrl) |



