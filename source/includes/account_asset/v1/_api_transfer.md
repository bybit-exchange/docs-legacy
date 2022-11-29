# t(:transfer_api)
t(:transfer_para)


### t(:createinternaltransfer)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/asset/v1/private/transfer' \
--header 'Content-Type: application/json' \
--data-raw '{
    "from_account_type": "SPOT",
    "to_account_type": "CONTRACT",
    "amount": "0.1",
    "coin": "BTC",
    "transfer_id": "b668ce35-db92-4db4-9f81-0b5da57d4df6",
    "api_key": "XXXXXXXXXXX",
    "sign": "{{sign}}",
    "timestamp": "{{timestamp}}",
    "recv_window": "{{recvWindow}}"
}'
```

```python--pybit
from pybit import account_asset
from uuid import uuid4
session_auth = account_asset.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret")
print(session_auth.create_internal_transfer(
    transfer_id=str(uuid4()),
    coin="BTC",
    amount="0.1",
    from_account_type="SPOT",
    to_account_type="CONTRACT"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "result": {
        "transfer_id": "b668ce35-db92-4db4-9f81-0b5da57d4df6"
    },
    "ext_info": null,
    "time_now": 1629951080227,
    "rate_limit_status": 17,
    "rate_limit_reset_ms": 1629951080227,
    "rate_limit": 3
}
```


t(:trigger_transfer)

t(:universaltransfer_join_notice)

<aside class="notice">
t(:transfer_api_notice)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=avpt>/asset/v1/private/transfer</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#avpt"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|transfer_id |<b>true</b> |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |<b>true</b> |string |t(:row_comment_currency) |
|amount |<b>true</b> |string |t(:row_comment_to_amount) |
|<a href="#account-type-from_account_type-to_account_type">from_account_type</a> |<b>true</b> |string |t(:row_comment_accounttype) |
|<a href="#account-type-from_account_type-to_account_type">to_account_type</a> |<b>true</b> |string |t(:row_comment_accounttype) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transfer_id |string |t(:row_comment_transfer_id) |





### t(:createsubaccounttransfer)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/asset/v1/private/sub-member/transfer' \
--header 'Content-Type: application/json' \
--data-raw '{
    "transfer_id": "5f95de18-b10f-43be-9746-7b95c4a37d97",
    "amount": "0.1",
    "coin": "BTC",
    "sub_user_id": 251711,
    "type": "IN",
    "api_key": "XXXXXXXXXXX",
    "sign": "{{sign}}",
    "timestamp": "{{timestamp}}",
    "recv_window": "{{recvWindow}}"
}'
```

```python--pybit
from pybit import account_asset
from uuid import uuid4
session_auth = account_asset.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret")
print(session_auth.create_subaccount_transfer(
    transfer_id=str(uuid4()),
    coin="BTC",
    amount="0.1",
    sub_user_id=251711,
    type="IN"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "result": {
        "transfer_id": "5f95de18-b10f-43be-9746-7b95c4a37d97"
    },
    "ext_info": null,
    "time_now": 1629966770894,
    "rate_limit_status": 18,
    "rate_limit_reset_ms": 1629966770894,
    "rate_limit": 2
}
```

t(:subMember_trigger_transfer)

t(:universaltransfer_join_notice)

<aside class="notice">
t(:createsubaccounttransfer_api_notice)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=avpst>/asset/v1/private/sub-member/transfer</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#avpst"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|transfer_id |<b>true</b> |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |<b>true</b> |string |t(:row_comment_currency) |
|amount |<b>true</b> |string |t(:row_comment_to_amount) |
|sub_user_id |<b>true</b> |string |t(:row_comment_to_subUserId) |
|<a href="#transfer-type-type">type</a> |<b>true</b> |string |t(:row_comment_transfertype) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transfer_id |string |t(:row_comment_transfer_id) |




### t(:querytransferlist)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v1/private/transfer/list'
```

```python--pybit
from pybit import account_asset
from uuid import uuid4
session_auth = account_asset.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret")
print(session_auth.query_transfer_list())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "result": {
        "list": [
            {
                "transfer_id": "selfTransfer_c5ae452d-43e8-47e6-aa7c-d2bab57c0958",
                "coin": "BTC",
                "amount": "1",
                "from_account_type": "CONTRACT",
                "to_account_type": "SPOT",
                "timestamp": "1629965054",
                "status": "SUCCESS"
            },
            {
                "transfer_id": "selfTransfer_9a183347-152d-4bdc-990d-8b20284385f9",
                "coin": "BTC",
                "amount": "1",
                "from_account_type": "SPOT",
                "to_account_type": "CONTRACT",
                "timestamp": "1629963043",
                "status": "SUCCESS"
            },
            {
                "transfer_id": "selfTransfer_5f9bfd6e-1718-4a16-814e-1d1bff4b01eb",
                "coin": "BTC",
                "amount": "20",
                "from_account_type": "SPOT",
                "to_account_type": "CONTRACT",
                "timestamp": "1629874294",
                "status": "SUCCESS"
            }
        ],
        "cursor": "eyJtaW5JRCI6Nzg5NTcsIm1heElEIjo3OTM2NH0="
    },
    "ext_info": null,
    "time_now": 1629971474462,
    "rate_limit_status": 59,
    "rate_limit_reset_ms": 1629971474462,
    "rate_limit": 1
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=avptl>/asset/v1/private/transfer/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#avptl"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|transfer_id |false |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:row_comment_currency) |
|<a href="#transfer-status-status">status</a> |false |string |t(:row_comment_transferstatus) |
|start_time |false |integer |t(:row_comment_startTime) |
|end_time |false |integer |t(:row_comment_endTime) |
|<a href="#page-direction-direction">direction</a> |false |string |t(:row_comment_pageaction) |
|limit |false |integer |t(:row_comment_to_limit) |
|cursor |false |string |t(:withdraw_response_cursor)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transfer_id |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |string |t(:row_comment_currency) |
|amount |string |t(:row_comment_to_amount) |
|<a href="#account-type-from_account_type-to_account_type">from_account_type</a> |string |t(:row_comment_accounttype) |
|<a href="#account-type-from_account_type-to_account_type">to_account_type</a> |string |t(:row_comment_accounttype) |
|timestamp |integer |t(:row_comment_to_timestamp) |
|<a href="#transfer-status-status">status</a> |string |t(:row_comment_transferstatus) |
|cursor |string |t(:withdraw_response_cursor)|






### t(:querysubaccounttransferlist)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v1/private/sub-member/transfer/list'
```

```python--pybit
from pybit import account_asset
from uuid import uuid4
session_auth = account_asset.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret")
print(session_auth.query_subaccount_transfer_list())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "result": {
        "list": [
            {
                "transfer_id": "5f95de18-b10f-43ba-9756-0b95c4a37d07",
                "coin": "BTC",
                "amount": "0.1",
                "user_id": 229988,
                "sub_user_id": 251711,
                "timestamp": "1629968375",
                "status": "SUCCESS",
                "type": "IN"
            },
            {
                "transfer_id": "5f95de18-b10f-43be-9756-0b95c4a37d07",
                "coin": "BTC",
                "amount": "0.1",
                "user_id": 229988,
                "sub_user_id": 251711,
                "timestamp": "1629968351",
                "status": "SUCCESS",
                "type": "IN"
            },
            {
                "transfer_id": "5f95de18-b10f-43be-9746-0b95c4a37d07",
                "coin": "BTC",
                "amount": "0.1",
                "user_id": 229988,
                "sub_user_id": 251711,
                "timestamp": "1629967817",
                "status": "SUCCESS",
                "type": "IN"
            },
            {
                "transfer_id": "5f95de18-b10f-43be-9746-7b95c4a37d97",
                "coin": "BTC",
                "amount": "0.1",
                "user_id": 229988,
                "sub_user_id": 251711,
                "timestamp": "1629966772",
                "status": "SUCCESS",
                "type": "IN"
            }
        ],
        "cursor": "eyJtaW5JRCI6NzkzNzgsIm1heElEIjo3OTQwMH0="
    },
    "ext_info": null,
    "time_now": 1629978073116,
    "rate_limit_status": 59,
    "rate_limit_reset_ms": 1629978073116,
    "rate_limit": 1
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=avpstl>/asset/v1/private/sub-member/transfer/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#avpstl"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|transfer_id |false |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:row_comment_currency) |
|<a href="#transfer-status-status">status</a> |false |string |t(:row_comment_transferstatus) |
|start_time |false |integer |t(:row_comment_startTime) |
|end_time |false |integer |t(:row_comment_endTime) |
|<a href="#page-direction-direction">direction</a> |false |string |t(:row_comment_pageaction) |
|limit |false |integer |t(:row_comment_to_limit) |
|cursor |false |string |t(:withdraw_response_cursor)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transfer_id |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |string |t(:row_comment_currency) |
|amount |string |t(:row_comment_to_amount) |
|user_id |integer |t(:row_comment_to_subUserId) |
|sub_user_id |integer|t(:row_comment_to_subUserId) |
|timestamp |integer |t(:row_comment_to_timestamp) |
|<a href="#transfer-status-status">status</a> |string |t(:row_comment_transferstatus) |
|<a href="#transfer-type-type">type</a> |string |t(:row_comment_transfertype) |
|cursor |string |t(:withdraw_response_cursor)|


### t(:querysubaccountlist)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v1/private/sub-member/member-ids'
```

```python--pybit
from pybit import account_asset
from uuid import uuid4
session_auth = account_asset.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret")
print(session_auth.query_subaccount_list())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "result": {
        "sub_user_id": [
            303936,
            445310,
            445323,
            517292,
            532728,
            545366,
            554286,
            572408
        ],
        "transferable_sub_ids": [
            "303936",
            "445310",
            "445323",
            "517292",
            "532728",
            "545366",
            "554286"
        ]
    },
    "ext_info": null,
    "time_now": 1654676013343,
    "rate_limit_status": 59,
    "rate_limit_reset_ms": 1654676013343,
    "rate_limit": 1
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=gsidlist>/asset/v1/private/sub-member/member-ids</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#gsidlist"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|sub_user_id |Integer Array |t(:row_comment_sub_user_id_list)|
|transferable_sub_ids |string Array |t(:row_comment_transferable_sub_ids_list) |


### t(:enableuniversaltransfer)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/asset/v1/private/transferable-subs/save' \
--header 'Content-Type: application/json' \
--data-raw '{
    "transferable_sub_ids":"303936,445310,445323,517292,532728,545366,554286",
    "sign": "{{signature}}",
    "timestamp": "{{timestamp}}",
    "api_key": "{{bybit-api-key}}",
    "recv_window": "5000"
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "result": {},
    "ext_info": null,
    "time_now": 1654674238364,
    "rate_limit_status": 19,
    "rate_limit_reset_ms": 1654674238364,
    "rate_limit": 1
}
```

<aside class="notice">
t(:universaltransferunderstanding_notice)
</aside>


t(:enableuniversaltransfer_notice)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=stsl>/asset/v1/private/transferable-subs/save</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#stsl"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|transferable_sub_ids |false |string |t(:row_comment_transferable_sub_ids) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |

### t(:createuniversaltransfer)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/asset/v1/private/universal/transfer' \
--header 'Content-Type: application/json' \
--data-raw '{
    "from_account_type": "SPOT",
    "to_account_type": "CONTRACT",
    "amount": "10",
    "coin": "USDT",
    "transfer_id": "21ff1b44-2d5d-4293-913d-4597c5ad2611",
    "from_member_id": "290118",
    "to_member_id": "545366",
    "sign": "{{signature}}",
    "timestamp": "{{timestamp}}",
    "api_key": "{{bybit-api-key}}",
    "recv_window": "5000"
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "result": {
        "transfer_id": "21ff1b44-2d5d-4293-913d-4597c5ad2611"
    },
    "ext_info": null,
    "time_now": 1654674912874,
    "rate_limit_status": 18,
    "rate_limit_reset_ms": 1654674912874,
    "rate_limit": 2
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=avpuTransfer>/asset/v1/private/universal/transfer</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#avpuTransfer"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|transfer_id |<b>true</b> |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |<b>true</b> |string |t(:row_comment_currency) |
|amount |<b>true</b> |string |t(:row_comment_to_amount) |
|from_member_id |<b>true</b> |string |t(:row_comment_from_memberId) |
|to_member_id |<b>true</b> |string |t(:row_comment_to_memberId) |
|<a href="#account-type-from_account_type-to_account_type">from_account_type</a> |<b>true</b> |string |t(:row_comment_from_accountType) |
|<a href="#account-type-from_account_type-to_account_type">to_account_type</a> |<b>true</b> |string |t(:row_comment_to_accountType) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transfer_id |string |t(:row_comment_transfer_id) |


### t(:queryUniverseTransferList)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v1/private/universal/transfer/list'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "result": {
        "list": [
            {
                "transfer_id": "21ff1b44-2d5d-4293-913d-4597c5ad2611",
                "coin": "USDT",
                "amount": "10",
                "timestamp": "1654674913",
                "status": "SUCCESS",
                "fromAccountType": "SPOT",
                "toAccountType": "CONTRACT",
                "fromMemberId": "290118",
                "toMemberId": "545366"
            },
            {
                "transfer_id": "submember_transfer_7e51ba01-8f44-4c60-a780-5ab7fc578f22",
                "coin": "USDT",
                "amount": "10",
                "timestamp": "1654665691",
                "status": "SUCCESS",
                "fromAccountType": "SPOT",
                "toAccountType": "SPOT",
                "fromMemberId": "290118",
                "toMemberId": "572408"
            }
        ],
        "cursor": "eyJtaW5JRCI6MjgxMzM1LCJtYXhJRCI6NDUzNzMwfQ=="
    },
    "ext_info": null,
    "time_now": 1654676488240,
    "rate_limit_status": 59,
    "rate_limit_reset_ms": 1654676488240,
    "rate_limit": 1
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=getuniversaltransferlist>/asset/v1/private/universal/transfer/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#getuniversaltransferlist"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|transfer_id |false |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:row_comment_currency) |
|<a href="#transfer-status-status">status</a> |false |string |t(:row_comment_transferstatus) |
|start_time |false |integer |t(:row_comment_startTime) |
|end_time |false |integer |t(:row_comment_endTime) |
|<a href="#page-direction-direction">direction</a> |false |string |t(:row_comment_pageaction) |
|limit |false |integer |t(:row_comment_limit) |
|cursor |false |string |t(:withdraw_response_cursor)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transfer_id |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |string |t(:row_comment_currency) |
|amount |string |t(:row_comment_to_amount) |
|timestamp |integer |t(:row_comment_to_timestamp) |
|<a href="#transfer-status-status">status</a> |string |t(:row_comment_transferstatus) |
|<a href="#account-type-from_account_type-to_account_type">from_account_type</a> |string |t(:row_comment_accounttype) |
|<a href="#account-type-from_account_type-to_account_type">to_account_type</a> |string |t(:row_comment_accounttype) |
|from_member_id |string |t(:row_comment_from_memberId) |
|to_member_id |string |t(:row_comment_to_memberId) |
|cursor |string |t(:withdraw_response_cursor)|


# t(:withdraw_and_deposit)
t(:transfer_para)

### t(:allowDepositList)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v1/public/deposit/allowed-deposit-list?coin=ETH&chain=ETH&page_index=1&page_size=10'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "result": {
        "config_list": [
            {
                "coin": "ETH",
                "chain": "ETH",
                "coin_show_name": "ETH",
                "chain_type": "ETH",
                "block_confirm_number": 12,
                "min_deposit_amount": "0"
            }
        ],
        "total": "1"
    },
    "ext_info": null,
    "time_now": 1652841868446
}
```

t(:allowDepositListDesc)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=allowDepositList>/asset/v1/public/deposit/allowed-deposit-list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#allowDepositList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|coin |false |string |t(:allowDepositCoin) |
|chain |false |string |t(:allowDepositChain) |
|page_index |false |long |t(:allowDepositPageIndex) |
|page_size |false |long |t(:allowDepositPageSize) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|config_list|Array|Object|
|coin|string|t(:deposit_response_currency_info)|
|chain|string|t(:deposit_response_chainname)|
|coin_show_name|string|t(:coinShowName)|
|chain_type|string|t(:coin_info_chain_type)|
|block_confirm_number|long|t(:coin_info_confirmation)|
|min_deposit_amount|string|t(:minDepositAmount)|


### t(:depositsrecordquery)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v1/private/deposit/record/query?
api_key=XXXXXXXXXXX&coin=LTC&timestamp=1641534660578&recv_window=50000&sign=XXXXXXXXXXX'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "result": {
        "rows": [
            {
                "coin": "LTC",
                "chain": "LTC",
                "amount": "0.156",
                "tx_id": "XXXXXXXXXXXXXXXXXXXXXXXXXX",
                "status": 3,
                "to_address": "XXXXXXXXXXXXXXXXXXXXXXXXXX",
                "tag": "",
                "deposit_fee": "",
                "success_at": "1631697910",
                "confirmations": "0",
                "tx_index": "",
                "block_hash": ""
            },
            {
                "coin": "LTC",
                "chain": "LTC",
                "amount": "0.158",
                "tx_id": "XXXXXXXXXXXXXXXXXXXXXXXXXX",
                "status": 3,
                "to_address": "XXXXXXXXXXXXXXXXXXXXXXXXXX",
                "tag": "",
                "deposit_fee": "",
                "success_at": "1631688429",
                "confirmations": "0",
                "tx_index": "",
                "block_hash": ""
            }
        ],
        "cursor": "eyJtaW5JRCI6NjkxNjExLCJtYXhJRCI6NjkyOTQ5fQ=="
    },
    "ext_info": null,
    "time_now": 1641535748233,
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1641535748233,
    "rate_limit": 1
}
```

t(:depositsrecorddesc)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pdrq>/asset/v1/private/deposit/record/query</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pdrq"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|start_time |false |long |t(:depositwithdrawstarttime) |
|end_time |false |long |t(:depositwithdrawendtime) |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:depositcurrencyinfo) |
|cursor |false |string |t(:depositcursorinfo) |
|<a href="#page-direction-direction">direction</a> |false |string |t(:depositdirectioninfo) |
|limit |false |long |t(:depositlimitinfo) |
|timestamp |<b>true</b>|long |t(:row_comment_to_timestamp) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|coin|string|t(:deposit_response_currency_info)|
|chain|string|t(:deposit_response_chainname)|
|amount|string|t(:deposit_response_amt)|
|tx_id|string|t(:deposit_response_txid)|
|status|int|t(:deposit_response_status)|
|to_address|string|t(:deposit_target_addr)|
|tag|string|t(:deposit_response_tag)|
|deposit_fee|string|t(:deposit_response_depositFee)|
|success_at|int64|t(:deposit_response_updateTime)|
|confirmations|string|t(:deposit_confirmations)|
|tx_index|string|t(:deposit_tx_index)|
|block_hash|string|t(:deposit_block_hash)|
|cursor|string|t(:deposit_response_cursor)|

### t(:withdrawrecordquery)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v1/private/withdraw/record/query?api_key=XXXXXXXXXXX&coin=LTC&limit=1&timestamp=1641789839632&recv_window=50000&sign=XXXXXXXXXXX'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "result": {
        "rows": [
            {
                "coin": "LTC",
                "chain": "LTC",
                "amount": "0.157",
                "tx_id": "XXXXXXXXXXXXXXXXXXXXXXXXXX",
                "status": "success",
                "to_address": "XXXXXXXXXXXXXXXXXXXXXXXXXX",
                "tag": "",
                "withdraw_fee": "0.001",
                "create_time": "1631694166",
                "update_time": "1631694775",
                "withdraw_id":"301121231312"
            },
            {
                "coin": "LTC",
                "chain": "LTC",
                "amount": "0.159",
                "tx_id": "XXXXXXXXXXXXXXXXXXXXXXXXXX",
                "status": "success",
                "toAddress": "XXXXXXXXXXXXXXXXXXXXXXXXXX",
                "tag": "",
                "withdraw_fee": "0.001",
                "create_time": "1631684557",
                "update_time": "1631685384",
                "withdraw_id":"301121231313"
            }
        ],
        "cursor": "eyJtaW5JRCI6MjAxNTM1MywibWF4SUQiOjIwMTU4OTF9"
    },
    "ext_info": null,
    "time_now": 1640921464384,
    "rate_limit_status": 117,
    "rate_limit_reset_ms": 1640921464384,
    "rate_limit": 3
}
```

t(:withdrawrecorddesc)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pwrq>/asset/v1/private/withdraw/record/query</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pwrq"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|withdraw_id |false |long |t(:withdraw_id) |
|start_time |false |long |t(:depositwithdrawstarttime) |
|end_time |false |long |t(:depositwithdrawendtime) |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:depositcurrencyinfo) |
|cursor |false |string |t(:depositcursorinfo) |
|<a href="#page-direction-direction">direction</a> |false |string |t(:depositdirectioninfo) |
|limit |false |long |t(:depositlimitinfo) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|coin|string|t(:withdraw_response_currency_info)|
|chain|string|t(:withdraw_response_chainname)|
|amount|string|t(:withdraw_response_amt)|
|tx_id|string|t(:withdraw_response_txid)|
|status|string|<a href="#withdraw-status-status">t(:withdraw_resp_status)</a>|
|to_address|string|t(:withdraw_target_addr)|
|tag|string|t(:withdraw_response_tag)|
|withdraw_fee|string|t(:withdraw_response_withdrawFee)|
|create_time|int64|t(:withdraw_response_createTime)|
|update_time|int64|t(:withdraw_response_updateTime)|
|cursor|string|t(:withdraw_response_cursor)|
|withdraw_id|string|t(:withdraw_id)|
|withdraw_type|int|t(:withdrawType)|

### t(:coin_info_query)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v1/private/coin-info/query?api_key=XXXXXXXXXXXXXXXXXXXXXXX&timestamp=1641793091931&recv_window=50000&sign=XXXXXXXXXXXXXXXXXXXXXXX'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "result": {
        "rows": [
            {
                "name": "USDT",
                "coin": "USDT",
                "remain_amount": "99999",
                "chains": [
                    {
                        "chain_type": "ETH",
                        "confirmation": "1",
                        "withdraw_fee": "10",
                        "deposit_min": "0.002",
                        "withdraw_min": "20",
                        "chain": "ETH"
                    },
                    {
                        "chain_type": "OMNI",
                        "confirmation": "1",
                        "withdraw_fee": "",
                        "deposit_min": "1",
                        "withdraw_min": "",
                        "chain": "OMNI"
                    }
                ]
            }
        ]
    },
    "ext_info": null,
    "time_now": 1641541870237,
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1641541870237,
    "rate_limit": 1
}
```

t(:coin_info_desc)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pciq>/asset/v1/private/coin-info/query</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pciq"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:coin_info_coin)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|name|string|t(:coin_info_name)|
|coin|string|t(:coin_info_coin)|
|remain_amount|string|t(:coin_info_remain_amt)|
|chains|List|Object|
|chain_type|string|t(:coin_info_chain_type)|
|confirmation|int|t(:coin_info_confirmation)|
|withdraw_fee|string|t(:coin_info_withdraw_fee)|
|deposit_min|string|t(:coin_info_deposit_min)|
|withdraw_min|string|t(:coin_info_withdraw_min)|
|chain|string|t(:deposit_response_chainname)|



### t(:asset_info_query)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v1/private/asset-info/query?api_key=XXXXXXXXXXXXXXX&coin=BIT&timestamp=1641790155961&recv_window=50000&sign=XXXXXXXXXXXXXXX'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "result": {
        "spot": {
            "status": "ACCOUNT_STATUS_NORMAL",
            "assets": [
                {
                    "coin": "BIT",
                    "frozen": "0",
                    "free": "90.62928",
                    "withdraw": ""
                }
            ]
        }
    },
    "ext_info": null,
    "time_now": 1641544103244,
    "rate_limit_status": 56,
    "rate_limit_reset_ms": 1641544103244,
    "rate_limit": 4
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=paiq>/asset/v1/private/asset-info/query</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#paiq"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|account_type|false |string |t(:asset_info_account_type)|
|<a href="#currency-currency-coin">coin</a> |false |string |t(:coin_info_coin)|


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|status|string|t(:asset_info_status)|
|assets|List|Object|
|coin|string|coin|t(:coin_info_coin)
|frozen|string|t(:coin_info_frozen_balance)|
|free|string|t(:asset_info_available_balance)|
|withdraw|string|t(:asset_info_withdraw)|


### t(:withdraw_info)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/asset/v1/private/withdraw' \
--header 'Content-Type: application/json' \
--data-raw '{
    "address": "XXXXXXXXXXXXXXXXXXXXXXXXXX",
    "amount": "0.153",
    "coin": "LTC",
    "chain": "LTC",
    "sign": "XXXXXXXXXXXXXXXXXXXXXXXXXX",
    "timestamp": "1641789512739",
    "api_key": "XXXXXXXXXXXXXXXXXXXXXXXXXX",
    "recv_window": "50000"
}'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "result": {
        "id": "3912530"
    },
    "ext_info": null,
    "time_now": 1641793038330,
    "rate_limit_status": 2,
    "rate_limit_reset_ms": 1641793038330,
    "rate_limit": 1
}
```

t(:withdraw_info_para)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pwith>/asset/v1/private/withdraw</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pwith"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>
<br><p><b>content-type:</b>   application/json</p>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#currency-currency-coin">coin</a> |<b>true</b> |string |t(:coin_info_coin)|
|chain|<b>true</b>|string|t(:deposit_response_chainname)|
|address|<b>true</b>|string|t(:withdraw_addr)|
|tag|false|string|t(:withdraw_tag)|
|amount|<b>true</b>|string|t(:withdraw_amount)|
|force_chain|false|int|t(:account_withdraw_forceChain)|


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|result|Object|result object|
|id|int64|t(:withdraw_id)


### t(:cancel_withdraw)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/asset/v1/private/withdraw/cancel' \
--header 'Content-Type: application/json' \
--data-raw '{
    "id":234234324234,
    "sign": "XXXXXXXXXXXXXXXXXXXXX",
    "timestamp": "1641790660020",
    "api_key": "XXXXXXXXXXXXXXXXXXXXX",
    "recv_window": "50000"
}'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "result": {},
    "ext_info": null,
    "time_now": 1641798821116,
    "rate_limit_status": 9,
    "rate_limit_reset_ms": 1641798821116,
    "rate_limit": 1
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pwcan>/asset/v1/private/withdraw/cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pwcan"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>
<br><p><b>content-type:</b>application/json</p>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|id| <b>true</b> | int64 |t(:withdraw_id)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|result|int|t(:cancel_withdraw_response)|


### t(:deposit_addr_info)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api.bybit.com/asset/v1/private/deposit/address?api_key=XXXXXXXXX&coin=GMT&timestamp=1663074198991&recv_window=5000&sign=73f79d2d8c0d41dddc30fd118b5da0db3fe92deb2f4ea39cd3dbbb8f3745f8b1&chain_type=SOL'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "result": {
        "coin": "GMT",
        "chains": [
            {
                "chain_type": "SOL",
                "address_deposit": "H29uWKkPVux8nkB5xKU1DVxbEtt1UyMjC6tHsPHbMRsn",
                "tag_deposit": "",
                "chain": "SOL"
            }
        ]
    },
    "ext_info": null,
    "time_now": 1663074199341
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pdaddr>/asset/v1/private/deposit/address</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pdaddr"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#currency-currency-coin">coin</a> |<b>true</b> |string |t(:coin_info_coin)|
|chain_type |false |string |t(:coin_info_chain_type)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|result|Object|result object|
|coin |string |t(:coin_info_coin)|
|chains|List|Object
|chain_type|string|t(:coin_info_chain_type)|
|address_deposit|string|t(:deposit_address)|
|tag_deposit|string|t(:deposit_tag)|
|chain|string|t(:deposit_response_chainname)|
