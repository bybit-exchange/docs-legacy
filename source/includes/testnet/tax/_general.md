# t(:taxEndpoint)
## t(:registerDate)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/fht/compliance/tax/v3/private/registertime' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: bf0ca3e3b68efacad6f321a71dfd71e1d418e6b57a705d495abe339662d4deee' \
--header 'X-BAPI-API-KEY: KAMz86BfHkKT5yWKWE' \
--header 'X-BAPI-TIMESTAMP: 1669015205125' \
--header 'X-BAPI-RECV-WINDOW: 500000' \
--header 'Content-Type: application/json' \
--data-raw '{}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0, 
  "retMsg": "OK", 
  "result": {
      "registerTime": "2019-07-10"
      }, 
  "retExtInfo": {}, 
  "time": 1669025088771
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoL2>/fht/compliance/tax/v3/private/registertime</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#taxregistertime"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

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
curl --location --request POST 'https://api-testnet.bybit.com/fht/compliance/tax/v3/private/create' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: d1208daf6143c0546dfd68e0348769c2726cc0ba67b0b5ce9255664bfd551a90' \
--header 'X-BAPI-API-KEY: KAMz86BfHkKT5yWKWE' \
--header 'X-BAPI-TIMESTAMP: 1669009028135' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{"startTime":"1667966793","endTime":"1668672407","type":"TRADE","number":"1"}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "queryId": "1594565554910400512"
    },
    "retExtInfo": {},
    "time": 1669009028592
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoL2>/fht/compliance/tax/v3/private/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#taxcreate"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|type |<b>true</b> |string |<a href="#reporttype-reporttype">Report Type</a> |
|number |<b>true</b> |string |<a href="#reportnumber-reportnumber">Report Number</a> |
|startTime |<b>true</b> |integer |t(:taxStartTime) |
|endTime |<b>true</b> |integer |t(:taxEndTime) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|queryId |string |t(:taxQueryId) |


## t(:exportReportStatus)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/fht/compliance/tax/v3/private/status' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: d7001831e2cc8a19af5b5a22be6a4ffd415f53f25f6fb1b0b7fdb7ade23ad949' \
--header 'X-BAPI-API-KEY: KAMz86BfHkKT5yWKWE' \
--header 'X-BAPI-TIMESTAMP: 1669009157386' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{"queryId":"1594565554910400512"}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "status": "2"
    },
    "retExtInfo": {},
    "time": 1669009157660
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoL2>/fht/compliance/tax/v3/private/status</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#taxstatus"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|queryId |<b>true</b> |string |t(:taxQueryId) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|status |number |t(:taxExportStatus) |


## t(:retrieveDataExport)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/fht/compliance/tax/v3/private/url' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 8bed4ac7cb1b63d042b617f23086a5d3d68f78b195472024daec967cabde63d5' \
--header 'X-BAPI-API-KEY: KAMz86BfHkKT5yWKWE' \
--header 'X-BAPI-TIMESTAMP: 1669009463077' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{"queryId":"1594565554910400512"}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "url": "{\"Files\":[\"20221121/8ba8b974-fdcd-4064-8f2b-7e6c4acb2e69/_SUCCESS\",\"20221121/8ba8b974-fdcd-4064-8f2b-7e6c4acb2e69/part-00000-15c42bbd-30ae-41b4-804e-6deba556374f-c000\"],\"Basepath\":\"https://testnet-bybit-tax-api-170593-ap-southeast-1-xaky06.s3.ap-southeast-1.amazonaws.com\"}"
    },
    "retExtInfo": {},
    "time": 1669009463401
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoL2>/fht/compliance/tax/v3/private/url</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#taxurl"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|queryId |<b>true</b> |string |t(:taxQueryId) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|url |string |t(:taxReportUrl) |



