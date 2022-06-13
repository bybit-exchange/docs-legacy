# t(:wallet)
t(:wallet_para)


### t(:balance)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/wallet/balance?api_key={api_key}&coin=BTC&timestamp={timestamp}&sign={sign}"
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Wallet.Wallet_getBalance(coin="BTC").result())
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.get_wallet_balance(coin="BTC"))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "BTC": {
            "equity": 1002,
            "available_balance": 999.99987471,
            "used_margin": 0.00012529,
            "order_margin": 0.00012529,
            "position_margin": 0,
            "occ_closing_fee": 0,
            "occ_funding_fee": 0,
            "wallet_balance": 1000,
            "realised_pnl": 0,
            "unrealised_pnl": 2,
            "cum_realised_pnl": 0,
            "given_cash": 0,
            "service_cash": 0
        }
    },
    "time_now": "1578284274.816029",
    "rate_limit_status": 98,
    "rate_limit_reset_ms": 1580885703683,
    "rate_limit": 100
}
```

t(:wallet_para_walletBalance)

<aside class="notice">
t(:wallet_aside_walletBalance)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpwBalance>/v2/private/wallet/balance</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpwBalance"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:row_comment_coin_false) |



<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|equity |number |t(:row_comment_equity)  |
|available_balance |number |t(:row_comment_http_available_balance)  |
|used_margin |number |t(:row_comment_used_margin)    |
|order_margin|number |t(:row_comment_order_margin)    |
|position_margin |number |t(:row_comment_position_margin)  |
|occ_closing_fee |number |t(:row_comment_occ_closing_fee)  |
|occ_funding_fee |number |t(:row_comment_occ_funding_fee)  |
|wallet_balance |number |t(:row_comment_wallet_balance)  |
|realised_pnl |number |t(:row_comment_realised_pnl)  |
|unrealised_pnl |number |t(:row_comment_unrealised_pnl)  |
|cum_realised_pnl|number |t(:row_comment_cum_realised_pnl)  |
|given_cash |number |t(:row_response_comment_given_cash)  |
|service_cash |number |t(:row_response_comment_service_cash)  |


### t(:walletrecords)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/wallet/fund/records?api_key={api_key}&timestamp={timestamp}&sign={sign}"
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Wallet.Wallet_getRecords().result())
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.wallet_fund_records())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": {
        "data": [
            {
                "id": 235853,
                "user_id": 1,
                "coin": "BTC",
                "wallet_id": 27913,
                "type": "Realized P&L",
                "amount": "0.00000023",
                "tx_id": "",
                "address": "BTCUSD",
                "wallet_balance": "0.03000353",
                "exec_time": "2019-12-10T00:00:29.000Z",
                "cross_seq": 0
            },
            {
                "id": 234467,
                "user_id": 1,
                "coin": "BTC",
                "wallet_id": 27913,
                "type": "Realized P&L",
                "amount": "-0.00000006",
                "tx_id": "",
                "address": "BTCUSD",
                "wallet_balance": "0.03000330",
                "exec_time": "2019-12-09T00:00:25.000Z",
                "cross_seq": 0
            }
        ]
    },
    "ext_info": null,
    "time_now": "1577481867.115552",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1577481867122,
    "rate_limit": 120
}
```

t(:wallet_para_walletRecords)

<aside class="notice">
t(:wallet_aside_walletRecords)
</aside>

<aside class="notice">
t(:wallet_aside_walletRecords1)
</aside>

<aside class="warning">
t(:wallet_aside_walletRecords2)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oawfRecordsNew>/v2/private/wallet/fund/records</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawfRecordsNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#date-start_date-end_date">start_date</a> |false |string |t(:row_comment_startDate) |
|<a href="#date-start_date-end_date">end_date</a> |false |string |t(:row_comment_endDate) |
|<a href="#currency-currency-coin">currency</a> |false |string |t(:row_comment_currency) |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:row_comment_coin) |
|<a href="#wallet-fund-type-wallet_fund_type-type">wallet_fund_type</a> |false |string |t(:row_comment_walletFundType) |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:row_comment_limit) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |number |t(:row_comment_userID)  |
|coin |string |t(:row_comment_coin_type)  |
|type |string |t(:row_comment_fund_type)  |
|amount |string |t(:row_comment_fund_amount)  |
|tx_id |string |t(:row_comment_tx_id)  |
|address |string |t(:row_comment_address)  |
|wallet_balance |string |t(:row_comment_wallet_balance)  |
|exec_time |string |t(:row_comment_exec_timestamp)  |
|cross_seq |number |t(:row_comment_cross_seq)  |


### t(:withdrawrecords)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/wallet/withdraw/list?api_key={api_key}&timestamp={timestamp}&sign={sign}"
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Wallet.Wallet_withdraw().result())
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.withdraw_records())
```

> t(:codequote_responseExample)

```javascript
{
  "ret_code": 0,
  "ret_msg": "ok",
  "ext_code": "",
  "result": {
      "data": [{
          "id": 137,                                        
          "user_id": 1,                                     
          "coin": "XRP",
          "status": "Pending"
          "amount": "20.00000000",
          "fee": "0.25000000",
          "address": "rH7H595XYEVTEHU2FySYsWnmfACBnZS9zM",
          "tx_id": "",
          "submited_at": "2019-06-11T02:20:24.000Z",
          "updated_at": "2019-06-11T02:20:24.000Z"
      }]
      "current_page": 1,
      "last_page": 1
  },
  "ext_info": null,
  "time_now": "1577482295.125488",
  "rate_limit_status": 119,
  "rate_limit_reset_ms": 1577482295132,
  "rate_limit": 120
}
```

t(:wallet_para_withdrawRecords)

<aside class="warning">
t(:wallet_aside_walletRecords2)
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
|t(:row_parameter_withdraw_status) |false |string |t(:row_comment_withdrawStatus) |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:row_comment_limit) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |number |t(:row_comment_userID)  |
|coin |string |t(:row_comment_coin_type)  |
|t(:row_parameter_withdraw_status) |string |t(:row_comment_withdrawStatus)  |
|amount |string |t(:row_comment_fund_amount)  |
|fee |string |t(:row_comment_fee_rate)  |
|address |string |t(:row_comment_address)  |
|tx_id |string |t(:row_comment_tx_id)  |
|submited_at |string |t(:row_comment_submited_at)  |
|updated_at |string |t(:row_comment_updated_at)  |

### t(:assetexchangerecords)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/exchange-order/list?api_key={api_key}&timestamp={timestamp}&sign={sign}"
```

```python--pybit
from pybit import inverse_perpetual
session_auth = inverse_perpetual.HTTP(
    endpoint="https://api-testnet.bybit.com",
    api_key="your api key",
    api_secret="your api secret"
)
print(session_auth.asset_exchange_records())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": [
        {
            "id": 31,
            "exchange_rate": 40.57202774,
            "from_coin": "BTC",
            "to_coin": "ETH",
            "to_amount": 4.05720277,
            "from_fee": 0.0005,
            "from_amount": 0.1,
            "created_at": "2020-06-15 03:32:52"
        },
        {
            "id": 30,
            "exchange_rate": 39.92359901,
            "from_coin": "BTC",
            "to_coin": "ETH",
            "to_amount": 39.923599,
            "from_fee": 0.0005,
            "from_amount": 1,
            "created_at": "2020-06-12 08:27:51"
        }
    ],
    "time_now": "1592554785.486414",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1592554785484,
    "rate_limit": 120
}

```

t(:wallet_para_assetexchangerecords)


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpeOrder>/v2/private/exchange-order/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpeOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|limit |false |integer |t(:row_comment_limit) |
|from |false |integer |t(:row_comment_from_id) |
|direction |false |string |t(:row_comment_direction) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|from_coin |string |t(:row_comment_from_coin) |
|from_amount |number |t(:row_comment_from_amount)  |
|to_coin|string |t(:row_comment_to_coin)    |
|to_amount |number |t(:row_comment_to_amount)  |
|exchange_rate |number |t(:row_comment_exchange_rate) |
|from_fee |number |t(:row_comment_from_fee)  |
|created_at |string |t(:row_comment_created_at_in_exchange)  |
