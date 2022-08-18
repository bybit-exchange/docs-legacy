# t(:transfer_api)
t(:transfer_para)

### t(:createinternaltransfer)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/asset/v3/private/transfer/inter-transfer'
--header 'Content-Type: application/json' \
--header 'X-BAPI-TIMESTAMP: 1660794864052' \
--header 'X-BAPI-API-KEY: tmp8i2paQ2rSQYzoOq' \
--header 'X-BAPI-RECV-WINDOW: 999999999' \
--header 'X-BAPI-SIGN: c4f6cbc0581a8afa81cade431c9389a62ff7817e3e6c4aee456fd3f86796f619' \
--data-raw '{
    "transferId": "xxxxxxx",
    "coin": "BTC",
    "amount": "0.11",
    "fromAccountType": "SPOT",
    "toAccountType": "CONTRACT",
}'
```

> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"OK",
    "result":{
    "transferId": "xxxxxxxxxxx"
  },
  "retExtInfo":{},
  "time":1652841868446
}
```

t(:trigger_transfer)

t(:universaltransfer_join_notice)

<aside class="notice">
t(:transfer_api_v3_notice)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=avpt>/asset/v3/private/transfer/inter-transfer</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#avpt"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|transferId |<b>true</b> |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |<b>true</b> |string |t(:row_comment_currency) |
|amount |<b>true</b> |string |t(:row_comment_to_amount) |
|<a href="#account-type-from_account_type-to_account_type">fromAccountType</a> |<b>true</b> |string |t(:row_comment_accounttype) |
|<a href="#account-type-from_account_type-to_account_type">toAccountType</a> |<b>true</b> |string |t(:row_comment_accounttype) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transferId |string |t(:row_comment_transfer_id) |


### t(:createsubaccounttransfer)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/asset/v3/private/transfer/sub-member-transfer' \
--header 'Content-Type: application/json' \
--header 'X-BAPI-TIMESTAMP: 1660794864052' \
--header 'X-BAPI-API-KEY: tmp8i2paQ2rSQYzoOq' \
--header 'X-BAPI-RECV-WINDOW: 999999999' \
--header 'X-BAPI-SIGN: c4f6cbc0581a8afa81cade431c9389a62ff7817e3e6c4aee456fd3f86796f619' \
--data-raw '{
    "transferId": "xxxxxxx",
    "coin": "BTC",
    "amount": "0.11",
    "subMemberId": 12,
    "type": "IN",
}'
```

> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"OK",
    "result":{
    "transferId": "xxxxxxxxxxx"
  },
  "retExtInfo":{},
  "time":1652841868446
}
```

t(:subMember_trigger_transfer)

t(:universaltransfer_join_notice)

<aside class="notice">
t(:createsubaccounttransfer_api_v3_notice)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=avpst>/asset/v3/private/transfer/sub-member-transfer</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#avpst"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|transferId |<b>true</b> |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |<b>true</b> |string |t(:row_comment_currency) |
|amount |<b>true</b> |string |t(:row_comment_to_amount) |
|subMemberId |<b>true</b> |string |t(:row_comment_to_subUserId) |
|<a href="#transfer-type-type">type</a> |<b>true</b> |string |t(:row_comment_transfertype) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transferId |string |t(:row_comment_transfer_id) |


### t(:querytransferlist)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v3/private/transfer/inter-transfer/list/query' \
--header 'X-BAPI-TIMESTAMP: 1660794864052' \
--header 'X-BAPI-API-KEY: tmp8i2paQ2rSQYzoOq' \
--header 'X-BAPI-RECV-WINDOW: 999999999' \
--header 'X-BAPI-SIGN: c4f6cbc0581a8afa81cade431c9389a62ff7817e3e6c4aee456fd3f86796f619' \
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "success",
    "result": {
        "list": [
            {
                "transferId": "selfTransfer_cafc74cc-e28a-4ff6-b0e6-9e711376fc90",
                "coin": "USDT",
                "amount": "1000",
                "fromAccountType": "UNIFIED",
                "toAccountType": "SPOT",
                "timestamp": "1658986298000",
                "status": "SUCCESS"
            }
        ],
        "nextPageCursor": "eyJtaW5JRCI6NTY2NDc3LCJtYXhJRCI6NTY2NDc3fQ=="
    },
    "retExtInfo": null,
    "time": 1660807573275
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=avptl>/asset/v3/private/transfer/inter-transfer/list/query</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#avptl"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|transferid |false |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:row_comment_currency) |
|<a href="#transfer-status-status">status</a> |false |string |t(:row_comment_transferstatus) |
|startTime |false |integer |t(:row_comment_startTime_ms) |
|endTime |false |integer |t(:row_comment_endTime_ms) |
|limit |false |integer |t(:row_comment_to_limit) |
|cursor |false |string |t(:row_comment_cursor)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transferId |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |string |t(:row_comment_currency) |
|amount |string |t(:row_comment_to_amount) |
|<a href="#account-type-from_account_type-to_account_type">fromAccountType</a> |string |t(:row_comment_accounttype) |
|<a href="#account-type-from_account_type-to_account_type">toAccountType</a> |string |t(:row_comment_accounttype) |
|timestamp |integer |t(:row_comment_to_timestamp) |
|<a href="#transfer-status-status">status</a> |string |t(:row_comment_transferstatus) |
|nextPageCursor |string |t(:row_comment_cursor)|


### t(:querysubaccounttransferlist)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v3/private/transfer/sub-member-transfer/list/query' \
--header 'X-BAPI-TIMESTAMP: 1660794864052' \
--header 'X-BAPI-API-KEY: tmp8i2paQ2rSQYzoOq' \
--header 'X-BAPI-RECV-WINDOW: 999999999' \
--header 'X-BAPI-SIGN: c4f6cbc0581a8afa81cade431c9389a62ff7817e3e6c4aee456fd3f86796f619' \
```

> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"OK",
    "result":{
    "list":[
      {
        "transferId":"selfTransfer_c5ae452d-d2bab57c0958",
        "coin":"BTC",
        "amount":"1",
        "fromAccountType":"CONTRACT",
        "toAccountType":"SPOT",
        "timestamp":"1629965054",
        "status":"SUCCESS"
      }
    ],
      "nextPageCursor":"eyJtaW5JRCI6MjgxMzM1LCJtYXhJRCI6NDUzNzMwfQ=="
  },
  "retExtInfo":{

  },
  "time":1652841868446
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=avpstl>/asset/v3/private/transfer/sub-member-transfer/list/query</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#avpstl"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|transferId |false |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:row_comment_currency) |
|<a href="#transfer-status-status">status</a> |false |string |t(:row_comment_transferstatus) |
|startTime |false |integer |t(:row_comment_startTime) |
|endTime |false |integer |t(:row_comment_endTime) |
|limit |false |integer |t(:row_comment_to_limit) |
|cursor |false |string |t(:row_comment_cursor)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transferId |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |string |t(:row_comment_currency) |
|amount |string |t(:row_comment_to_amount) |
|memberId |integer |t(:row_comment_to_subUserId) |
|subMemberId |integer|t(:row_comment_to_subUserId) |
|timestamp |integer |t(:row_comment_to_timestamp) |
|<a href="#transfer-status-status">status</a> |string |t(:row_comment_transferstatus) |
|<a href="#transfer-type-type">type</a> |string |t(:row_comment_transfertype) |
|cursor |string |t(:row_comment_cursor)|


### t(:querysubaccountlist)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v3/private/transfer/sub-member/list/query' \
--header 'X-BAPI-TIMESTAMP: 1660794864052' \
--header 'X-BAPI-API-KEY: tmp8i2paQ2rSQYzoOq' \
--header 'X-BAPI-RECV-WINDOW: 999999999' \
--header 'X-BAPI-SIGN: c4f6cbc0581a8afa81cade431c9389a62ff7817e3e6c4aee456fd3f86796f619' \
```

> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"OK",
    "result":{
        "subMemberIds": [1,2,3],
        "transferablSubMemberIds": [1,3]
  },
  "retExtInfo":{},
  "time":1652841868446
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=gsidlist>/asset/v3/private/transfer/sub-member/list/query</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#gsidlist"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|subMemberIds |Integer Array |t(:row_comment_sub_user_id_list)|
|transferablSubMemberIds |string Array |t(:row_comment_transferable_sub_ids_list) |


### t(:enableuniversaltransfer)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/asset/v3/private/transfer/transfer-sub-member-save' \
--header 'Content-Type: application/json' \
--header 'X-BAPI-TIMESTAMP: 1660794864052' \
--header 'X-BAPI-API-KEY: tmp8i2paQ2rSQYzoOq' \
--header 'X-BAPI-RECV-WINDOW: 999999999' \
--header 'X-BAPI-SIGN: c4f6cbc0581a8afa81cade431c9389a62ff7817e3e6c4aee456fd3f86796f619' \
--data-raw '{
    "subMemberIds": "xx,xx,xx"
}'
```

> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"OK",
    "result":{},
  "retExtInfo":{},
  "time":1652841868446
}
```

<aside class="notice">
t(:universaltransferunderstanding_notice)
</aside>


t(:enableuniversaltransfer_notice)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=stsl>/asset/v3/private/transfer/transfer-sub-member-save</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#stsl"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|subMemberIds |false |string |t(:row_comment_transferable_sub_ids) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:createuniversaltransfer)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/asset/v3/private/transfer/universal-transfer' \
--header 'Content-Type: application/json' \
--header 'X-BAPI-TIMESTAMP: 1660794864052' \
--header 'X-BAPI-API-KEY: tmp8i2paQ2rSQYzoOq' \
--header 'X-BAPI-RECV-WINDOW: 999999999' \
--header 'X-BAPI-SIGN: c4f6cbc0581a8afa81cade431c9389a62ff7817e3e6c4aee456fd3f86796f619' \
--data-raw '{
    "transferId": "xxxxxxx",
    "coin": "BTC",
    "amount": "0.11",
    "fromMemberId": "1",
    "toMemberId": "2",
    "fromAccountType": "SPOT",
    "toAccountType": "CONTRACT"
}'
```

> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"OK",
    "result":{
    "transferId": "xxxxxxxxxxx"
  },
  "retExtInfo":{},
  "time":1652841868446
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=avpuTransfer>/asset/v3/private/transfer/universal-transfer</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#avpuTransfer"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|transferId |<b>true</b> |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |<b>true</b> |string |t(:row_comment_currency) |
|amount |<b>true</b> |string |t(:row_comment_to_amount) |
|fromMemberId |<b>true</b> |string |t(:row_comment_from_memberId) |
|toMemberId |<b>true</b> |string |t(:row_comment_to_memberId) |
|<a href="#account-type-from_account_type-to_account_type">fromAccountType</a> |<b>true</b> |string |t(:row_comment_from_accountType) |
|<a href="#account-type-from_account_type-to_account_type">toAccountType</a> |<b>true</b> |string |t(:row_comment_to_accountType) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transferId |string |t(:row_comment_transfer_id) |


### t(:queryUniverseTransferList)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v3/private/transfer/universal-transfer/list/query' \
--header 'X-BAPI-TIMESTAMP: 1660794864052' \
--header 'X-BAPI-API-KEY: tmp8i2paQ2rSQYzoOq' \
--header 'X-BAPI-RECV-WINDOW: 999999999' \
--header 'X-BAPI-SIGN: c4f6cbc0581a8afa81cade431c9389a62ff7817e3e6c4aee456fd3f86796f619' \
```

> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"OK",
    "result":{
    "list":[
      {
        "transferId":"21ff1b44-2d5d-4293-913d-4597c5ad2611",
        "coin":"USDT",
        "amount":"10",
        "timestamp":"1654674913",
        "status":"SUCCESS",
        "fromAccountType":"SPOT",
        "toAccountType":"CONTRACT",
        "fromMemberId":"290118",
        "toMemberId":"545366"
      }
    ],
      "nextPageCursor":"eyJtaW5JRCI6MjgxMzM1LCJtYXhJRCI6NDUzNzMwfQ=="
  },
  "retExtInfo":{

  },
  "time":1652841868446
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=getuniversaltransferlist> /asset/v3/private/transfer/universal-transfer/list/query</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#getuniversaltransferlist"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|transferId |false |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:row_comment_currency) |
|<a href="#transfer-status-status">status</a> |false |string |t(:row_comment_transferstatus) |
|startTime |false |integer |t(:row_comment_startTime) |
|endTime |false |integer |t(:row_comment_endTime) |
|limit |false |integer |t(:row_comment_to_limit) |
|cursor |false |string |t(:row_comment_cursor)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transferId |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |string |t(:row_comment_currency) |
|amount |string |t(:row_comment_to_amount) |
|timestamp |integer |t(:row_comment_to_timestamp) |
|<a href="#transfer-status-status">status</a> |string |t(:row_comment_transferstatus) |
|<a href="#account-type-from_account_type-to_account_type">fromAccountType</a> |string |t(:row_comment_accounttype) |
|<a href="#account-type-from_account_type-to_account_type">toAccountType</a> |string |t(:row_comment_accounttype) |
|fromMemberId |string |t(:row_comment_from_memberId) |
|toMemberId |string |t(:row_comment_to_memberId) |
|nextPageCursor |string |t(:row_comment_cursor)|


### t(:querytransfercoinlist)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v3/private/transfer/transfer-coin/list/query?fromAccountType=SPOT&toAccountType=CONTRACT' \
--header 'X-BAPI-TIMESTAMP: 1660794864052' \
--header 'X-BAPI-API-KEY: tmp8i2paQ2rSQYzoOq' \
--header 'X-BAPI-RECV-WINDOW: 999999999' \
--header 'X-BAPI-SIGN: c4f6cbc0581a8afa81cade431c9389a62ff7817e3e6c4aee456fd3f86796f619' \
```

> t(:codequote_responseExample)

```javascript
{
    "retCode":0,
    "retMsg":"OK",
    "result":{
        "list": ["BTC", "ETH", "USDT"]
    },
    "retExtInfo":{},
    "time":1652841868446
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=querytransfercoinlist> /asset/v3/private/transfer/transfer-coin/list/query</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#getuniversaltransferlist"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#account-type-from_account_type-to_account_type">fromAccountType</a> |<b>true</b> |string |t(:row_comment_from_accountType) |
|<a href="#account-type-from_account_type-to_account_type">toAccountType</a> |<b>true</b> |string |t(:row_comment_to_accountType) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|coins |string Array |t(:row_comment_transfer_coin_list) |



### t(:queryaccountcoinbalance)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com//asset/v3/private/transfer/account-coin/balance/query?memberId=123&accountType=CONTRACT&coin=BTC&withBonus=0' \
--header 'X-BAPI-TIMESTAMP: 1660794864052' \
--header 'X-BAPI-API-KEY: tmp8i2paQ2rSQYzoOq' \
--header 'X-BAPI-RECV-WINDOW: 999999999' \
--header 'X-BAPI-SIGN: c4f6cbc0581a8afa81cade431c9389a62ff7817e3e6c4aee456fd3f86796f619' \
```

> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"OK",
    "result":{
    "accountType": "CONTRACT",
      "bizType": 1,
      "accountId": 1234,
      "memberId": 123,
      "balance": {
      "coin": "BTC",
        "walletBalance": "10",
        "transferBalance": "9.12",
        "bonus": "0"
    }
  },
  "retExtInfo":{},
  "time":1652841868446
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=queryaccountcoinbalance> /asset/v3/private/transfer/account-coin/balance/query</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#getuniversaltransferlist"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|memberId |false |string |t(:row_comment_userID) |
|<a href="#account-type-from_account_type-to_account_type">accountType</a> |string |t(:row_comment_accounttype) |
|<a href="#currency-currency-coin">coin</a> |string |t(:row_comment_currency) |
|withBonus |string |t(:row_comment_with_bonus) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|<a href="#account-type-from_account_type-to_account_type">accountType</a> |string |t(:row_comment_accounttype) |
|accountId |string |t(:row_comment_accountID) |
|memberID |string |t(:row_comment_userID) |
|<a href="#currency-currency-coin">balance.coin</a> |string |t(:row_comment_currency) |
|balance.walletBalance |string |t(:row_comment_wallet_balance) |
|balance.transferBalance |string |t(:row_comment_transferable_balance) |
|balance.bonus |string |t(:row_comment_bonus) |


### t(:queryassetinfo)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v3/private/transfer/asset-info/query?accountType=SPOT&coin=BTC' \
--header 'X-BAPI-TIMESTAMP: 1660794864052' \
--header 'X-BAPI-API-KEY: tmp8i2paQ2rSQYzoOq' \
--header 'X-BAPI-RECV-WINDOW: 999999999' \
--header 'X-BAPI-SIGN: c4f6cbc0581a8afa81cade431c9389a62ff7817e3e6c4aee456fd3f86796f619' \
```

> t(:codequote_responseExample)

```javascript
{
  "retCode":0,
    "retMsg":"OK",
    "result":{
    "spot":{
      "status":1,
        "assets":[
        {
          "coin":"BTC",
          "frozen":"0.1",
          "free":"0.5",
          "withdraw":"0.1"
        }
      ]
    }
  },
  "retExtInfo":{},
  "time":1652841868446
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=queryassetinfo> /asset/v3/private/transfer/asset-info/query</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#getuniversaltransferlist"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#account-type-from_account_type-to_account_type">accountType</a> | true |string |t(:row_comment_accounttype) |
|<a href="#currency-currency-coin">coin</a> |string |t(:row_comment_currency) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|status |integer |t(:row_comment_spot_status) |
|<a href="#currency-currency-coin">coin</a> |string |t(:row_comment_currency) |
|frozen |string |t(:row_comment_frozen) |
|free |string |t(:row_comment_free) |
|withdraw |string |t(:row_comment_withdraw) |

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

