# t(:user_apikey_api)
t(:user_apikey_para)

<aside class="notice">
t(:user_apikey_notice)
</aside>

### t(:create_sub_uid)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/user/v3/private/create-sub-member' \
--header 'X-BAPI-SIGN: 522eb685adce4873738f5bdcbad4eb552c3b0a954e28d33ef2a3afe563041543' \
--header 'X-BAPI-API-KEY: XXXX' \
--header 'X-BAPI-TIMESTAMP: 1665386966479' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "username": "ciakf2ifhd06",
    "memberType": 1,
    "switch": 1,
    "note": "6th sub uid"
}'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "uid": "1037883",
        "username": "ciakf2ifhd06",
        "memberType": 1,
        "status": 1,
        "remark": "test 9th sub uid"
    },
    "retExtInfo": null,
    "time": 1665714504296
}
```

t(:createSubUid_para)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=crsume>/user/v3/private/create-sub-member</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#crsume"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|username |<b>true</b> |string |t(:user_username_req_comment) |
|memberType |<b>true</b> |int |t(:user_memberType_req_comment) |
|switch |false |int |t(:user_switch_req_comment) |
|note |false |string |t(:user_note_req_comment) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|uid |int |t(:user_uid_resp_comment) |
|username |string |t(:user_username_req_comment) |
|memberType |int |t(:user_memberType_req_comment) |
|switch |int |t(:user_switch_req_comment) |
|remark |string |t(:user_note_req_comment) |


### t(:create_subuser_apikey)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/user/v3/private/create-sub-api' \
--header 'X-BAPI-SIGN: b5ab130814235091bc56884289d163ab9dca637824c818cebb4d59fe0d4f9b17' \
--header 'X-BAPI-API-KEY: XXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1665715086395' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "subuid": 1037883,
    "note": "remakkkkkk for sub uid",
    "readOnly": 0,
    "permissions": {
        "Wallet": [
            "AccountTransfer"
        ]
    }
}'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "id": "350666",
        "note": "remakkkkkk for sub uid",
        "apiKey": "B20h175nOlwUpU5uh8",
        "readOnly": 0,
        "secret": "XXXXXXXXXXXXXX",
        "permissions": {
            "ContractTrade": [],
            "Spot": [],
            "Wallet": [
                "AccountTransfer"
            ],
            "Options": [],
            "Derivatives": [],
            "CopyTrading": [],
            "BlockTrade": [],
            "Exchange": [],
            "NFT": []
        }
    },
    "retExtInfo": null,
    "time": 1665715090979
}
```

t(:create_subuser_apikey_para)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=crsai>/user/v3/private/create-sub-api</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#crsai"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|subuid |<b>true</b> |string |t(:row_comment_transfer_id) |
|note |false |string |t(:row_comment_currency) |
|readOnly |<b>true</b> |int |t(:row_comment_to_amount) |
|ips |false |array[string] |t(:row_comment_to_subUserId) |
|permissions |<b>true</b> |Object |t(:row_comment_transfertype) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |string |t(:row_comment_transfer_id) |
|note |string |t(:row_comment_currency) |
|apiKey |t(:row_comment_currency) |
|readOnly |string |t(:row_comment_currency) |
|secret |string |t(:row_comment_currency) |
|permissions |Object |t(:row_comment_currency) |
|> ContractTrade |array |t(:row_comment_currency) |
|> Spot |array |t(:row_comment_currency) |
|> Wallet |array |t(:row_comment_currency) |
|> Options |array |t(:row_comment_currency) |
|> CopyTrading |array |t(:row_comment_currency) |
|> BlockTrade |array |t(:row_comment_currency) |
|> Exchange |array |t(:row_comment_currency) |
|> NFT |array |t(:row_comment_currency) |


### t(:get_sub_members_list)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/user/v3/private/query-sub-members' \
--header 'X-BAPI-TIMESTAMP: 1660794864052' \
--header 'X-BAPI-API-KEY: XXXXXXXXXXX' \
--header 'X-BAPI-RECV-WINDOW: 999999999' \
--header 'X-BAPI-SIGN: c4f6cbc0581a8afa81cade431c9389a62ff7817e3e6c4aee456fd3f86796f619' \
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "subMembers": [
            {
                "uid": "1037883",
                "username": "mnaskk0002",
                "memberType": 1,
                "status": 1,
                "remark": "test 9th sub uid"
            },
            {
                "uid": "554117",
                "username": "asiiikkk001",
                "memberType": 1,
                "status": 1,
                "remark": "test key 001"
            }
        ]
    },
    "retExtInfo": null,
    "time": 1665990044209
}
```
t(:get_sub_members_list_parap)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=qusume>/user/v3/private/query-sub-members</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#qusume"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|subMembers |array |t(:row_comment_transfer_id) |
|uid |string |t(:row_comment_transfer_id) |
|username |string |t(:row_comment_transfer_id) |
|memberType |string |t(:row_comment_transfer_id) |
|status |string |t(:row_comment_transfer_id) |
|remark |string |t(:row_comment_transfer_id) |


### t(:froze_sub_uid)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/user/v3/private/frozen-sub-member' \
--header 'X-BAPI-SIGN: bdbdbe19ac9cc28c133676195ea9fc8edb425dd07e476c770223a1bedf8a1c54' \
--header 'X-BAPI-API-KEY: XXXXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1665990666773' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: bdbdbe19ac9cc28c133676195ea9fc8edb425dd07e476c770223a1bedf8a1c54' \
--header 'Content-Type: application/json' \
--data-raw '{
    "subuid": 1037883,
    "frozen": 1
}'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {},
    "retExtInfo": null,
    "time": 1665990662595
}
```

t(:froze_sub_uid_para)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=frsume>/user/v3/private/frozen-sub-member</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#frsume"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|subuid |<b>true</b> |integer |t(:row_comment_startTime_ms) |
|frozen |<b>true</b> |integer |t(:row_comment_endTime_ms) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:get_api_key_info)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/user/v3/private/query-api' \
--header 'X-BAPI-SIGN: 1e9136b0387ad89e853622296dd7a681053384a04879146872275a19e6c93fdf' \
--header 'X-BAPI-API-KEY: XXXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1665990908443' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: 1e9136b0387ad89e853622296dd7a681053384a04879146872275a19e6c93fdf' \
--header 'Content-Type: application/json'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "id": "220315",
        "note": "testApiKey",
        "apiKey": "XXXXXXXXXX",
        "readOnly": 0,
        "secret": "",
        "permissions": {
            "ContractTrade": [
                "Order",
                "Position"
            ],
            "Spot": [
                "SpotTrade"
            ],
            "Wallet": [
                "AccountTransfer",
                "SubMemberTransfer"
            ],
            "Options": [
                "OptionsTrade"
            ],
            "Derivatives": [
                "DerivativesTrade"
            ],
            "CopyTrading": [
                "CopyTrading"
            ],
            "BlockTrade": [],
            "Exchange": [
                "ExchangeHistory"
            ],
            "NFT": []
        },
        "ips": [
            "*"
        ],
        "type": 1,
        "deadlineDay": 87,
        "expiredAt": "2023-01-13T03:47:43Z",
        "createdAt": "2022-07-08T06:43:11Z"
    },
    "retExtInfo": null,
    "time": 1665990908666
}
```

t(:get_api_key_info_para)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=quapi>/user/v3/private/query-api</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#quapi"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |string |t(:row_comment_transfer_id) |
|note |string |t(:row_comment_currency) |
|apiKey |string |t(:row_comment_currency) |
|readOnly |string |t(:row_comment_currency) |
|secret |string |t(:row_comment_currency) |
|permissions |Object |t(:row_comment_currency) |
|> ContractTrade |array |t(:row_comment_currency) |
|> Spot |array |t(:row_comment_currency) |
|> Wallet |array |t(:row_comment_currency) |
|> Options |array |t(:row_comment_currency) |
|> CopyTrading |array |t(:row_comment_currency) |
|> BlockTrade |array |t(:row_comment_currency) |
|> Exchange |array |t(:row_comment_currency) |
|> NFT |array |t(:row_comment_currency) |
|ips |array |t(:row_comment_currency) |
|type |int |t(:row_comment_currency) |
|deadlineDay |int |t(:row_comment_currency) |
|expiredAt |datetime |t(:row_comment_currency) |
|createdAt |datetime |t(:row_comment_currency) |


### t(:modify_master_api_key)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/user/v3/private/update-api' \
--header 'X-BAPI-SIGN: 2a90cf0f52736c829698ba11bb6eeed2edea45a58b109a44f5616e9db02d0715' \
--header 'X-BAPI-API-KEY: XXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1665996421845' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: 2a90cf0f52736c829698ba11bb6eeed2edea45a58b109a44f5616e9db02d0715' \
--header 'Content-Type: application/json' \
--data-raw '{
    "readOnly": 0,
    "ips": ["*"],
    "permissions": {
            "ContractTrade": [
                "Order",
                "Position"
            ],
            "Spot": [
                "SpotTrade"
            ],
            "Wallet": [
                "AccountTransfer",
                "SubMemberTransfer"
            ],
            "Options": [],
            "Derivatives": [],
            "CopyTrading": [],
            "BlockTrade": [],
            "Exchange": [],
            "NFT": []
        }
}'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "id": "220315",
        "note": "testApiKey",
        "apiKey": "XXXXXXXXXX",
        "readOnly": 0,
        "secret": "",
        "permissions": {
            "ContractTrade": [
                "Order",
                "Position"
            ],
            "Spot": [
                "SpotTrade"
            ],
            "Wallet": [
                "AccountTransfer",
                "SubMemberTransfer"
            ],
            "Options": [],
            "Derivatives": [],
            "CopyTrading": [],
            "BlockTrade": [],
            "Exchange": [],
            "NFT": []
        },
        "ips": [
            "*"
        ]
    },
    "retExtInfo": null,
    "time": 1665996422184
}
```

t(:modify_master_api_key_para)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=updateapi>/user/v3/private/update-api</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#updateapi"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|readOnly |<b>true</b> |string |t(:row_comment_transferable_sub_ids) |
|ips |false |string |t(:row_comment_transferable_sub_ids) |
|permissions |<b>true</b> |string |t(:row_comment_transferable_sub_ids) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |string |t(:row_comment_transfer_id) |
|note |string |t(:row_comment_currency) |
|apiKey |string |t(:row_comment_currency) |
|readOnly |string |t(:row_comment_currency) |
|secret |string |t(:row_comment_currency) |
|permissions |Object |t(:row_comment_currency) |
|> ContractTrade |array |t(:row_comment_currency) |
|> Spot |array |t(:row_comment_currency) |
|> Wallet |array |t(:row_comment_currency) |
|> Options |array |t(:row_comment_currency) |
|> CopyTrading |array |t(:row_comment_currency) |
|> BlockTrade |array |t(:row_comment_currency) |
|> Exchange |array |t(:row_comment_currency) |
|> NFT |array |t(:row_comment_currency) |
|ips |array |t(:row_comment_currency) |


### t(:delete_master_api_key)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/user/v3/private/delete-api' \
--header 'X-BAPI-SIGN: 2a90cf0f52736c829698ba11bb6eeed2edea45a58b109a44f5616e9db02d0715' \
--header 'X-BAPI-API-KEY: XXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1665996421845' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: 2a90cf0f52736c829698ba11bb6eeed2edea45a58b109a44f5616e9db02d0715' \
--header 'Content-Type: application/json' \
--data-raw '{}'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {},
    "retExtInfo": null,
    "time": 1665997272757
}
```

t(:delete_master_api_key_para)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=demapikey>/user/v3/private/delete-api</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#demapikey"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:modify_sub_api_key)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/user/v3/private/update-sub-api' \
--header 'X-BAPI-SIGN: 2a90cf0f52736c829698ba11bb6eeed2edea45a58b109a44f5616e9db02d0715' \
--header 'X-BAPI-API-KEY: XXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1665996421845' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: 2a90cf0f52736c829698ba11bb6eeed2edea45a58b109a44f5616e9db02d0715' \
--header 'Content-Type: application/json' \
--data-raw '{
    "readOnly": 0,
    "ips": ["*"],
    "permissions": {
            "ContractTrade": [
                "Order",
                "Position"
            ],
            "Spot": [
                "SpotTrade"
            ],
            "Wallet": [
                "AccountTransfer"
            ],
            "Options": [],
            "Derivatives": [],
            "CopyTrading": [], 
            "BlockTrade": [],
            "Exchange": [],
            "NFT": []
        }
}'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "id": "220315",
        "note": "testApiKey",
        "apiKey": "XXXXXXXXXX",
        "readOnly": 0,
        "secret": "",
        "permissions": {
            "ContractTrade": [
                "Order",
                "Position"
            ],
            "Spot": [
                "SpotTrade"
            ],
            "Wallet": [
                "AccountTransfer"
            ],
            "Options": [],
            "Derivatives": [],
            "CopyTrading": [],
            "BlockTrade": [],
            "Exchange": [],
            "NFT": []
        },
        "ips": [
            "*"
        ]
    },
    "retExtInfo": null,
    "time": 1665996422184
}
```

t(:modify_sub_api_key_para)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=updatesubapi>/user/v3/private/update-sub-api</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#updatesubapi"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|readOnly |<b>true</b> |string |t(:row_comment_transferable_sub_ids) |
|ips |false |string |t(:row_comment_transferable_sub_ids) |
|permissions |<b>true</b> |string |t(:row_comment_transferable_sub_ids) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |string |t(:row_comment_transfer_id) |
|note |string |t(:row_comment_currency) |
|apiKey |string |t(:row_comment_currency) |
|readOnly |string |t(:row_comment_currency) |
|secret |string |t(:row_comment_currency) |
|permissions |Object |t(:row_comment_currency) |
|> ContractTrade |array |t(:row_comment_currency) |
|> Spot |array |t(:row_comment_currency) |
|> Wallet |array |t(:row_comment_currency) |
|> Options |array |t(:row_comment_currency) |
|> CopyTrading |array |t(:row_comment_currency) |
|> BlockTrade |array |t(:row_comment_currency) |
|> Exchange |array |t(:row_comment_currency) |
|> NFT |array |t(:row_comment_currency) |
|ips |array |t(:row_comment_currency) |


### t(:delete_sub_api_key)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/user/v3/private/delete-sub-api' \
--header 'X-BAPI-SIGN: 2a90cf0f52736c829698ba11bb6eeed2edea45a58b109a44f5616e9db02d0715' \
--header 'X-BAPI-API-KEY: XXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1665996421845' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: 2a90cf0f52736c829698ba11bb6eeed2edea45a58b109a44f5616e9db02d0715' \
--header 'Content-Type: application/json' \
--data-raw '{}'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {},
    "retExtInfo": null,
    "time": 1665997272757
}
```

t(:delete_sub_api_key_para)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=desapikey>/user/v3/private/delete-sub-api</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#desapikey"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |

