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
      "registerTime": "1562760001000"
  }, 
  "retExtInfo": {}, 
  "time": 1669025088771
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=taxregistertime>/fht/compliance/tax/v3/private/registertime</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#taxregistertime"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|registerTime |string |t(:taxRegisterDate) |


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
<code><span id=taxcreate>/fht/compliance/tax/v3/private/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#taxcreate"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|type |<b>true</b> |string |<a href="#reporttype-reporttype">Report Type</a> |
|number |<b>true</b> |string |<a href="#reportnumber-reportnumber">Report Number</a> |
|startTime |<b>true</b> |string |t(:taxStartTime) |
|endTime |<b>true</b> |string |t(:taxEndTime) |

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
<aside class="notice">
t(:exportReportStatusDesc)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=taxstatus>/fht/compliance/tax/v3/private/status</span></code>
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
        "url": "{\"Files\":[\"20221121/8ba8b974-fdcd-4064-8f2b-7e6c4acb2e69/_SUCCESS\",\"20221121/8ba8b974-fdcd-4064-8f2b-7e6c4acb2e69/part-00000-15c42bbd-30ae-41b4-804e-6deba556374f-c000\"],\"Basepath\":\"https://testnet-bybit-tax-api-170593-ap-southeast-1-xaky06.s3.ap-southeast-1.amazonaws.com/\"}"
    },
    "retExtInfo": {},
    "time": 1669009463401
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=taxurl>/fht/compliance/tax/v3/private/url</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#taxurl"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|queryId |<b>true</b> |string |t(:taxQueryId) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|url |string |t(:taxReportUrl) |


<aside class="notice">
t(:convertFileToCsv)
</aside>
t(:convertFileToCsvDesc)

> t(:codequote_Example)

```python

import pandas as pd
import os

class Bases(object):
    @staticmethod
    def path_list(path):
        """
        :param path:
        :return: list of file paths
        """
        file_list = []
        if os.path.isdir(path):
            print("it's a directory")
            for root, dirs, files in os.walk(path):
                for f in files:
                    file = os.path.join(root, f)
                    file_list.append(file)
            return file_list
        elif os.path.isfile(path):
            print("it's a normal file")
            return [path]

class pd_service(Bases):
    def get_data(self, file_path):
        """
        Read s3 files, merge forms
        :param file_path:
        :return:
        """
        df_all = pd.DataFrame()
        for paths in self.path_list(path=file_path):
            df_all = pd.concat([df_all, pd.read_orc(paths)], axis=0)
        print('Row number of tables：', df_all[df_all.columns[1]].count())
        print(df_all.columns.values)
        df_all.sort_values("TradeTime", inplace=True)
        df_all.to_csv("test_data_s3.csv", header=True, index=False)
        print(df_all)
        return df_all

if __name__ == '__main__':
    # file path
    path = 'XXXX'
    test = pd_service()
    test.get_data(file_path=path)
```
