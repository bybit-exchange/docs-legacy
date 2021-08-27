# t(:transfer_api)
t(:transfer_para)


### t(:transfer_action)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/asset/v1/private/transfer' \
--header 'Content-Type: application/json' \
--data-raw '{
    "fromAccountType": "SPOT",
    "toAccountType": "CONTRACT",
    "amount": "0.1",
    "coin": "BTC",
    "transferId": "b668ce35-db92-4db4-9f81-0b5da57d4df6",
    "api_key": "YtcjswsO9WjAmQVUx7",
    "sign": "{{sign}}",
    "timestamp": "{{timestamp}}",
    "recv_window": "{{recvWindow}}"
}'
```

```python
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

t(:trigger_transfer_action)

<aside class="notice">
t(:transfer_api_notice)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oawwListNew>/asset/v1/private/transfer</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawwListNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|transfer_id |true |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |true |string |t(:row_comment_currency) |
|amount |true |string |t(:row_comment_to_amount) |
|<a href="#accounttype-type-accounttype">from_account_type</a> |true |string |t(:row_comment_accounttype) |
|<a href="#accounttype-type-accounttype">to_account_type</a> |true |string |t(:row_comment_accounttype) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transfer_id |string |t(:row_comment_transfer_id) |





### t(:subMember_transfer_action)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/asset/v1/private/sub-member/transfer' \
--header 'Content-Type: application/json' \
--data-raw '{
    "transferId": "5f95de18-b10f-43be-9746-7b95c4a37d97",
    "amount": "0.1",
    "coin": "BTC",
    "subUserId":"251711",
    "type": "IN",
    "api_key": "YtcjswsO9WjAmQVUx7",
    "sign": "{{sign}}",
    "timestamp": "{{timestamp}}",
    "recv_window": "{{recvWindow}}"
}'
```

```python
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

t(:subMember_trigger_transfer_action)

<aside class="notice">
t(:subMember_transfer_api_notice)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oawwListNew>/asset/v1/private/sub-member/transfer</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawwListNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|transfer_id |true |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |true |string |t(:row_comment_currency) |
|amount |true |string |t(:row_comment_to_amount) |
|sub_user_id |true |string |t(:row_comment_to_subUserId) |
|<a href="#transfertype">type</a> |true |string |t(:row_comment_transfertype) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transfer_id |string |t(:row_comment_transfer_id) |




### t(:query_transfer_list)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v1/private/transfer/list'
```

```python
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
<code><span id=oawwListNew>/asset/v1/private/transfer/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawwListNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|transfer_id |false |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:row_comment_currency) |
|<a href="#transferstatus">status</a> |false |string |t(:row_comment_transferstatus) |
|start_time |false |integer |t(:row_comment_startTime_ms) |
|end_time |false |integer |t(:row_comment_endTime_ms) |
|<a href="#pageaction-turn-page">direction</a> |false |string |t(:row_comment_pageaction) |
|limit |false |integer |t(:row_comment_to_limit) |
|cursor |false |string |t(:row_comment_to_cursor)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transfer_id |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |string |t(:row_comment_currency) |
|amount |string |t(:row_comment_to_amount) |
|<a href="#accounttype-type-accounttype">from_account_type</a> |string |t(:row_comment_accounttype) |
|<a href="#accounttype-type-accounttype">to_account_type</a> |string |t(:row_comment_accounttype) |
|timestamp |integer |t(:row_comment_to_timestamp) |
|<a href="#transferstatus">status</a> |string |t(:row_comment_transferstatus) |
|cursor |string |t(:row_comment_to_cursor)|






### t(:query_subMember_transfer_list)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v1/private/sub-member/transfer/list'
```

```python
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
<code><span id=oawwListNew>/asset/v1/private/sub-member/transfer/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawwListNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|transfer_id |false |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:row_comment_currency) |
|<a href="#transferstatus">status</a> |false |string |t(:row_comment_transferstatus) |
|start_time |false |integer |t(:row_comment_startTime_ms) |
|end_time |false |integer |t(:row_comment_endTime_ms) |
|<a href="#pageaction-turn-page">direction</a> |false |string |t(:row_comment_pageaction) |
|limit |false |integer |t(:row_comment_to_limit) |
|cursor |false |string |t(:row_comment_to_cursor)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transfer_id |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |string |t(:row_comment_currency) |
|amount |string |t(:row_comment_to_amount) |
|user_id |integer |t(:row_comment_to_subUserId) |
|sub_user_id |integer|t(:row_comment_to_subUserId) |
|timestamp |integer |t(:row_comment_to_timestamp) |
|<a href="#transferstatus">status</a> |string |t(:row_comment_transferstatus) |
|<a href="#transfertype">type</a> |string |t(:row_comment_transfertype) |
|cursor |string |t(:row_comment_to_cursor)|






### t(:query_subMember_id_list)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/asset/v1/private/sub-member/member-ids'
```

```python
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
