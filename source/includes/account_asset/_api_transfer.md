# t(:transfer_api)
t(:transfer_para)


### t(:transfer)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api.bybit.com/asset/v1/private/transfer' \
--header 'Content-Type: application/json' \
--data-raw '{
    "fromAccountType": "SPOT",
    "toAccountType": "CONTRACT",
    "amount": "0.1",
    "coin": "BTC",
    "transferId": "11ff9b44-2d5d-4293-913d-4597c5ad2117",
    "api_key": "{{api_key}}",
    "sign": "{{sign}}",
    "timestamp": "{{timestamp}}",
    "recv_window": "{{recvWindow}}"
}'
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Wallet.Wallet_getBalance(coin="BTC").result())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 38001,
    "ret_msg": "available balance running low",
    "ext_code": "",
    "result": null,
    "ext_info": null,
    "time_now": 1629880449841,
    "rate_limit_status": 19,
    "rate_limit_reset_ms": 1629880449841,
    "rate_limit": 1
}
`

t(:wallet_para_withdrawRecords)

<aside class="notice">
t(:wallet_aside_withdrawRecords)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oawwListNew>/v2/private/wallet/withdraw/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawwListNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#date-start_date-end_date">start_date</a> |false |string |t(:row_comment_startDate) |
|<a href="#date-start_date-end_date">end_date</a> |false |string |t(:row_comment_endDate) |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:row_comment_currency) |
|<a href="#withdraw-status-status">status</a> |false |string |t(:enum_withdraw_status_link) |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:row_comment_limit) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |number |t(:row_comment_userID)  |
|coin |string |t(:row_comment_coin_type)  |
|status |string |t(:enum_withdraw_status_link)  |
|amount |string |t(:row_comment_fund_amount)  |
|fee |string |t(:row_comment_fee_rate)  |
|address |string |t(:row_comment_address)  |
|tx_id |string |t(:row_comment_tx_id)  |
|submited_at |string |t(:row_comment_submited_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
