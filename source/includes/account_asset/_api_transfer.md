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
    "api_key": "YtcjswsO9WjAmQVUx7",
    "sign": "{{sign}}",
    "timestamp": "{{timestamp}}",
    "recv_window": "{{recvWindow}}"
}'
```

```python--pybit
from pybit import HTTP
from uuid import uuid4
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.create_internal_transfer(
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
    "api_key": "YtcjswsO9WjAmQVUx7",
    "sign": "{{sign}}",
    "timestamp": "{{timestamp}}",
    "recv_window": "{{recvWindow}}"
}'
```

```python--pybit
from pybit import HTTP
from uuid import uuid4
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.create_subaccount_transfer(
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
from pybit import HTTP
from uuid import uuid4
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.query_transfer_list())
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
|start_time |false |integer |t(:row_comment_startTime_ms) |
|end_time |false |integer |t(:row_comment_endTime_ms) |
|<a href="#page-direction-direction">direction</a> |false |string |t(:row_comment_pageaction) |
|limit |false |integer |t(:row_comment_to_limit) |
|cursor |false |string |t(:row_comment_cursor)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transfer_id |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |string |t(:row_comment_currency) |
|amount |string |t(:row_comment_to_amount) |
|<a href="#accounttype-type-accounttype">from_account_type</a> |string |t(:row_comment_accounttype) |
|<a href="#accounttype-type-accounttype">to_account_type</a> |string |t(:row_comment_accounttype) |
|timestamp |integer |t(:row_comment_to_timestamp) |
|<a href="#transfer-status-status">status</a> |string |t(:row_comment_transferstatus) |
|cursor |string |t(:row_comment_cursor)|






### t(:querysubaccounttransferlist)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v1/private/sub-member/transfer/list'
```

```python--pybit
from pybit import HTTP
from uuid import uuid4
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.query_subaccount_transfer_list())
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
|start_time |false |integer |t(:row_comment_startTime_ms) |
|end_time |false |integer |t(:row_comment_endTime_ms) |
|<a href="#page-direction-direction">direction</a> |false |string |t(:row_comment_pageaction) |
|limit |false |integer |t(:row_comment_to_limit) |
|cursor |false |string |t(:row_comment_cursor)|

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
|cursor |string |t(:row_comment_cursor)|






### t(:querysubaccountlist)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v1/private/sub-member/member-ids'
```

```python--pybit
from pybit import HTTP
from uuid import uuid4
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.query_subaccount_list())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "result": {
        "sub_user_id": [
            251711
        ]
    },
    "ext_info": null,
    "time_now": 1629979703311,
    "rate_limit_status": 59,
    "rate_limit_reset_ms": 1629979703311,
    "rate_limit": 1
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oawwListNew>/asset/v1/private/sub-member/member-ids</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawwListNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|sub_user_id |integer|t(:row_comment_to_subUserId) |

# t(:withdraw_and_deposit)
t(:transfer_para)

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
                "txId": "XXXXXXXXXXXXXXXXXXXXXXXXXX",
                "status": 3,
                "toAddress": "XXXXXXXXXXXXXXXXXXXXXXXXXX",
                "tag": "",
                "depositFee": "",
                "updateTime": "1631697910"
            },
            {
                "coin": "LTC",
                "chain": "LTC",
                "amount": "0.158",
                "txId": "XXXXXXXXXXXXXXXXXXXXXXXXXX",
                "status": 3,
                "toAddress": "XXXXXXXXXXXXXXXXXXXXXXXXXX",
                "tag": "",
                "depositFee": "",
                "updateTime": "1631688429"
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
|startTime |false |long |t(:depositwithdrawstarttime) |
|endTime |false |long |t(:depositwithdrawendtime) |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:depositcurrencyinfo) |
|cursor |false |string |t(:depositcursorinfo) |
|<a href="#page-direction-direction">direction</a> |false |aaa |t(:depositdirectioninfo) |
|limit |false |long |t(:depositlimitinfo) |
|timestamp |<b>true</b>|long |t(:row_comment_to_timestamp) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|coin|string|t(:deposit_response_currency_info)|
|chain|string|t(:deposit_response_chainname)|
|amount|string|t(:deposit_response_amt)|
|txid|string|t(:deposit_response_txid)|
|status|int|t(:deposit_response_status)|
|toAddress|string|t(:deposit_target_addr)|
|tag|string|t(:deposit_response_tag)|
|depositFee|string|t(:deposit_response_depositFee)|
|updateTime|int64|t(:deposit_response_updateTime)|
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
                "txId": "XXXXXXXXXXXXXXXXXXXXXXXXXX",
                "status": "success",
                "toAddress": "XXXXXXXXXXXXXXXXXXXXXXXXXX",
                "tag": "",
                "withdrawFee": "0.001",
                "createTime": "1631694166",
                "updateTime": "1631694775"
            },
            {
                "coin": "LTC",
                "chain": "LTC",
                "amount": "0.159",
                "txId": "XXXXXXXXXXXXXXXXXXXXXXXXXX",
                "status": "success",
                "toAddress": "XXXXXXXXXXXXXXXXXXXXXXXXXX",
                "tag": "",
                "withdrawFee": "0.001",
                "createTime": "1631684557",
                "updateTime": "1631685384"
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
|startTime |false |long |t(:depositwithdrawstarttime) |
|endTime |false |long |t(:depositwithdrawendtime) |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:depositcurrencyinfo) |
|cursor |false |string |t(:depositcursorinfo) |
|<a href="#page-direction-direction">direction</a> |false |aaa |t(:depositdirectioninfo) |
|limit |false |long |t(:depositlimitinfo) |
|timestamp |<b>true</b>|long |t(:row_comment_to_timestamp) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|coin|string|t(:withdraw_response_currency_info)|
|chain|string|t(:withdraw_response_chainname)|
|amount|string|t(:withdraw_response_amt)|
|txid|string|t(:withdraw_response_txid)|
|status|int|t(:withdraw_response_status)|
|toAddress|string|t(:withdraw_target_addr)|
|tag|string|t(:withdraw_response_tag)|
|WithdrawFee|string|t(:withdraw_response_withdrawFee)|
|createTime|int64|t(:withdraw_response_createTime)|
|updateTime|int64|t(:withdraw_response_updateTime)|
|cursor|string|t(:withdraw_response_cursor)|


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
                        "chain_type": "TRX",
                        "confirmation": "100",
                        "withdraw_fee": "1",
                        "deposit_min": "1",
                        "withdraw_min": "10"
                    },
                    {
                        "chain_type": "ETH",
                        "confirmation": "1",
                        "withdraw_fee": "10",
                        "deposit_min": "0.002",
                        "withdraw_min": "20"
                    },
                    {
                        "chain_type": "OMNI",
                        "confirmation": "1",
                        "withdraw_fee": "",
                        "deposit_min": "1",
                        "withdraw_min": ""
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
|accountType|false |string |t(:asset_info_account_type)|
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


### t(:withdraw)
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

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pwith>/asset/v1/private/withdraw</span></code>
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


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|result|Object|result object|
|id|int64|t(:withdraw_request_id)


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
POST
<code><span id=pwcan>/asset/v1/private/withdraw/cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pwcan"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>
<br><p><b>content-type:</b>application/json</p>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|id| <b>true</b> | int64 |t(:withdraw_request_id)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|result|int|t(:cancel_withdraw_response)|


### t(:deposit_addr_info)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v1/private/deposit/address?api_key=XXXXXXXXXXXXXXXXXXX&coin=LTC&timestamp=1641789312824&recv_window=50000&sign=XXXXXXXXXXXXXXXXXXX' 
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
        "coin": "LTC",
        "chains": [
            {
                "chain_type": "LTC",
                "address_deposit": "XXXXXXXXXXXXXXXXXXXX",
                "tag_deposit": ""
            }
        ]
    },
    "ext_info": null,
    "time_now": 1641789383364,
    "rate_limit_status": 28,
    "rate_limit_reset_ms": 1641789383364,
    "rate_limit": 2
}
```

t(:deposit_addr_info_desc)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pdaddr>/asset/v1/private/deposit/address</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pdaddr"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#currency-currency-coin">coin</a> |<b>true</b> |string |t(:coin_info_coin)|
|chain|false|string|t(:deposit_addr_chain_info)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|result|Object|result object|
|coin |string |t(:coin_info_coin)|
|chains|List|Object
|chain_type|string|t(:coin_info_chain_type)
|address_deposit|string|t(:deposit_address)
|tag_deposit|string|t(:deposit_tag)