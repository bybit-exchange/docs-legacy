# t(:withdraw_and_deposit)
t(:transfer_para)

### t(:allowDepositList)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v3/public/deposit/allowed-deposit-list/query?coin=BTC&chain=BTC'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "configList": [
      {
        "coin": "BTC",
        "chain": "BTC",
        "coinShowName": "BTC",
        "chainType": "BTC",
        "blockConfirmNumber": 10000,
        "minDepositAmount": "0.0005"
      }
    ],
      "nextPageCursor": "eyJwYWdlIjoyLCJsaW1pdCI6MX0="
  },
  "retExtInfo": null,
    "time": 1660546221207
}
```

t(:allowDepositListDesc)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=allowDepositList>/asset/v3/public/deposit/allowed-deposit-list/query</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#allowDepositList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|coin |false |string |t(:allowDepositCoin) |
|chain |false |string |t(:allowDepositChain) |
|cursor |false |string |t(:allowDepositPageCursor) |
|limit |false |int |t(:depositlimitinfo) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|configList|Array|Object|
|coin|string|t(:deposit_response_currency_info)|
|chain|string|t(:deposit_response_chainname)|
|coinShowName|string|t(:coinShowName)|
|chainType|string|t(:coin_info_chain_type)|
|blockConfirmNumber|int|t(:coin_info_confirmation)|
|minDepositAmount|string|t(:minDepositAmount)|
|nextPageCursor|string|t(:allowDepositPageCursor)|


### t(:depositsrecordquery)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v3/private/deposit/record/query?startTime=1659283200000&endTime=1660060800000&coin=USDT' \
--header 'X-BAPI-SIGN: fc436a4643d3785bdab20748c64c7e9221da39dc5798b15536667732a7b1cf5c' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1660611015105' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: fc436a4643d3785bdab20748c64c7e9221da39dc5798b15536667732a7b1cf5c'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "rows": [
      {
        "coin": "USDT",
        "chain": "ETH",
        "amount": "11133",
        "txID": "37fcf7893",
        "status": 3,
        "toAddress": "fake-address",
        "tag": "3844562",
        "depositFee": "",
        "successAt": "1658902838000",
        "confirmations": "10000",
        "txIndex": "",
        "blockHash": ""
      }
    ],
      "nextPageCursor": "eyJtaW5JRCI6NTM3MCwibWF4SUQiOjUzNzB9"
  },
  "retExtInfo": null,
    "time": 1660547423085
}
```

t(:depositsrecorddesc)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pdrq>/asset/v3/private/deposit/record/query</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pdrq"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|startTime |false |int |t(:DWstarttimeMS) |
|endTime |false |int |t(:DWendtimeMS) |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:depositcurrencyinfo) |
|cursor |false |string |t(:depositcursorinfo) |
|limit |false |int |t(:depositlimitinfo) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|rows|Array|Object|
|coin|string|t(:deposit_response_currency_info)|
|chain|string|t(:deposit_response_chainname)|
|amount|string|t(:deposit_response_amt)|
|txID|string|t(:deposit_response_txid)|
|status|int|t(:deposit_response_status)|
|toAddress|string|t(:deposit_target_addr)|
|tag|string|t(:deposit_response_tag)|
|depositFee|string|t(:deposit_response_depositFee)|
|successAt|string|t(:deposit_response_updateTime)|
|confirmations|string|t(:deposit_confirmations)|
|txIndex|string|t(:deposit_tx_index)|
|blockHash|string|t(:deposit_block_hash)|
|nextPageCursor|string|t(:deposit_response_cursor)|

### t(:withdrawrecordquery)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v3/private/withdraw/record/query?startTime=1659283200000&endTime=1660060800000&coin=USDT' \
--header 'X-BAPI-SIGN: e1cff93188ab3a1905394cef79db371f63bf577b4061ec6f85676864f51638bf' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1660618971820' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: e1cff93188ab3a1905394cef79db371f63bf577b4061ec6f85676864f51638bf'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "rows": [
      {
        "coin": "BTC",
        "chain": "BTC",
        "amount": "0.02",
        "txID": "",
        "status": "SecurityCheck",
        "toAddress": "mikeNCEUBcbahMfLU7SDgo69UEqciC2D1w",
        "tag": "",
        "withdrawFee": "0.0005",
        "createTime": "1660038232000",
        "updateTime": "1660038233000",
        "withdrawId": "370037"
      },
      {
        "coin": "BTC",
        "chain": "BTC",
        "amount": "0.02",
        "txID": "",
        "status": "SecurityCheck",
        "toAddress": "mikeNCEUBcbahMfLU7SDgo69UEqciC2D1w",
        "tag": "",
        "withdrawFee": "0.0005",
        "createTime": "1660037115000",
        "updateTime": "1660037116000",
        "withdrawId": "370036"
      }
    ],
      "nextPageCursor": "eyJtaW5JRCI6MzcwMDM2LCJtYXhJRCI6MzcwMDM3fQ=="
  },
  "retExtInfo": null,
    "time": 1660548434464
}
```

t(:withdrawrecorddesc)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pwrq>/asset/v3/private/withdraw/record/query</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pwrq"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|withdrawID |false |int64 |t(:withdraw_id) |
|startTime |false |int |t(:DWstarttimeMS) |
|endTime |false |int |t(:DWendtimeMS) |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:depositcurrencyinfo) |
|cursor |false |string |t(:depositcursorinfo) |
|limit |false |int |t(:depositlimitinfo) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|coin|string|t(:withdraw_response_currency_info)|
|chain|string|t(:withdraw_response_chainname)|
|amount|string|t(:withdraw_response_amt)|
|txID|string|t(:withdraw_response_txid)|
|status|string|<a href="#withdraw-status-status">t(:withdraw_resp_status)</a>|
|toAddress|string|t(:withdraw_target_addr)|
|tag|string|t(:withdraw_response_tag)|
|withdrawFee|string|t(:withdraw_response_withdrawFee)|
|createTime|string|t(:withdraw_response_createTime)|
|updateTime|string|t(:withdraw_response_updateTime)|
|withdrawId|string|t(:withdraw_id)|
|nextPageCursor|string|t(:withdraw_response_cursor)|


### t(:withdraw_info)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/asset/v3/private/withdraw/create' \
--header 'X-BAPI-SIGN: fdb267bf07558a7a34f8949f6284305af1bb9a1bf2363d6b2605825a88490291' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1660620568966' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: fdb267bf07558a7a34f8949f6284305af1bb9a1bf2363d6b2605825a88490291' \
--header 'Content-Type: application/json' \
--data-raw '{
    "coin": "USDT",
    "chain": "ETH",
    "address": "0x9ba58f56E420a00a23D3508Cf77fF268C8510A01",
    "tag": null,
    "amount": "20",
    "timestamp": 1660620515481
}'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "id": "370044"
  },
  "retExtInfo": null,
    "time": 1660549283047
}
```

t(:withdraw_info_para)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pwith>/asset/v3/private/withdraw/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pwith"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>
<br><p><b>content-type:</b>   application/json</p>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#currency-currency-coin">coin</a> |<b>true</b> |string |t(:coin_info_coin)|
|chain|<b>true</b>|string|t(:deposit_response_chainname)
|address|<b>true</b>|string|t(:withdraw_addr)
|tag|false|string|t(:withdraw_tag)
|amount|<b>true</b>|string|t(:withdraw_amount)
|timestamp|<b>true</b>|int|t(:assetWithdraw_timestamp)


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|result|Object|result object|
|id|string|t(:withdraw_id)


### t(:cancel_withdraw)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/asset/v3/private/withdraw/cancel' \
--header 'X-BAPI-SIGN: fdb267bf07558a7a34f8949f6284305af1bb9a1bf2363d6b2605825a88490291' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1660620568966' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: fdb267bf07558a7a34f8949f6284305af1bb9a1bf2363d6b2605825a88490291' \
--header 'Content-Type: application/json' \
--data-raw '{
    "id": 7642
}'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "status": 1
  },
  "retExtInfo": null,
    "time": 1660550283220
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pwcan>/asset/v3/private/withdraw/cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pwcan"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>
<br><p><b>content-type:</b>application/json</p>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|id| <b>true</b> | int64 |t(:withdraw_id)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|status|int|t(:cancel_withdraw_response)|


### t(:deposit_addr_info)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v3/private/deposit/address/query?coin=USDT' \
--header 'X-BAPI-SIGN: 5a5ce5b26fd6a959c470b637ec0e9672b871d1ace105737b15e525de672c3fdb' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1660632630317' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: 5a5ce5b26fd6a959c470b637ec0e9672b871d1ace105737b15e525de672c3fdb'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "coin": "BTC",
      "chains": [
      {
        "chainType": "BTC",
        "addressDeposit": "mzy5RaEWoBBMHotVZSvhmphcLbLqq5VPVY",
        "tagDeposit": "",
        "chain": "BTC"
      }
    ]
  },
  "retExtInfo": null,
    "time": 1660203622474
}
```

t(:deposit_addr_info_desc)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pdaddr>/asset/v3/private/deposit/address/query</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pdaddr"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#currency-currency-coin">coin</a> |<b>true</b> |string |t(:coin_info_coin)|
|chainType |false |string |t(:accountAssetV3_chainType)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|result|Object|result object|
|coin |string |t(:coin_info_coin)|
|chains|Array|Object|
|chainType|string|t(:coin_info_chain_type)|
|addressDeposit|string|t(:deposit_address)|
|tagDeposit|string|t(:deposit_tag)|
|chain|string|t(:deposit_response_chainname)|
