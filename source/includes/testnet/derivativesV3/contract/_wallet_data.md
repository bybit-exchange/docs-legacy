# t(:contract_account)
t(:contract_accountPara)


### t(:balance)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/contract/v3/private/account/wallet/balance?coin=BTC' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: f8f516355e0c59b28d429b13b4ea6a350d02f9c96e2f9fd1be235863e8c1834c' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1658736635286' \
--header 'X-BAPI-RECV-WINDOW: 5000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "list": [
            {
                "coin": "BTC",
                "equity": "0.80319649",
                "walletBalance": "0.80319649",
                "positionMargin": "0",
                "availableBalance": "0.80319649",
                "orderMargin": "0",
                "occClosingFee": "0",
                "occFundingFee": "0",
                "unrealisedPnl": "0",
                "cumRealisedPnl": "0.00120039",
                "givenCash": "0",
                "serviceCash": "0"
            }
        ]
    },
    "retExtInfo": {},
    "time": 1658736635763
}
```

t(:wallet_para_walletBalance)

<aside class="notice">
t(:wallet_aside_walletBalance)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpwBalance>/contract/v3/private/account/wallet/balance</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpwBalance"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:contract_accountCoin) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> coin |string |t(:contract_accountCoin_resp)  |
|list> equity |string |t(:row_comment_equity)  |
|list> walletBalance |string |t(:row_comment_wallet_balance)  |
|list> positionMargin |string |t(:row_comment_position_margin)  |
|list> availableBalance |string |t(:row_comment_http_available_balance)  |
|list> orderMargin|string |t(:row_comment_order_margin)    |
|list> occClosingFee |string |t(:row_comment_occ_closing_fee)  |
|list> occFundingFee |string |t(:row_comment_occ_funding_fee)  |
|list> unrealisedPnl |string |t(:row_comment_unrealised_pnl)  |
|list> cumRealisedPnl|string |t(:row_comment_cum_realised_pnl)  |
|list> givenCash |string |t(:row_response_comment_given_cash)  |
|list> serviceCash |string |t(:row_response_comment_service_cash)  |


### t(:tradingFeeRate)
t(:contract_tradingFeeRate_para)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/contract/v3/private/account/fee-rate?symbol=ETHUSDT' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: e65aad8dd5459774ad21aaca77420947332fdbfe433bef959c6507ce2379999f' \
--header 'X-BAPI-API-KEY: T0d98KyVamQ62YBzN8' \
--header 'X-BAPI-TIMESTAMP: 1658739026859' \
--header 'X-BAPI-RECV-WINDOW: 5000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "list": [
            {
                "symbol": "ETHUSDT",
                "takerFeeRate": "0.0006",
                "makerFeeRate": "0.0001"
            }
        ]
    },
    "retExtInfo": {},
    "time": 1658739027301
}
```

<aside class="warning">
t(:contract_feeRate_warning)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=tradingFeeRate>/contract/v3/private/account/fee-rate</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#tradingFeeRate"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol |false |string |t(:row_comment_symbol) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> symbol |string |t(:row_comment_symbol)  |
|list> takerFeeRate |string |t(:contract_accountTakerFeeRate)  |
|list> makerFeeRate |string |t(:contract_accountMakerFeeRate)  |


### t(:walletrecords)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/contract/v3/private/account/wallet/fund-records?coin=USDT&walletFundType=AccountTransfer&limit=1' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-SIGN: 591a44021fff458a6dfbba517755e1105066864d94c38a0ce84619ae51cf2313' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1658737208933' \
--header 'X-BAPI-RECV-WINDOW: 5000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "list": [
            {
                "coin": "USDT",
                "type": "AccountTransfer",
                "amount": "500",
                "walletBalance": "2731.63599033",
                "execTime": "1658215763731"
            }
        ],
        "nextPageCursor": "elZpeUVCSCtFRk5pZjMrMU9reDdMdkpJS2VZdEpqczNHaExPUU5CazA0Yz0="
    },
    "retExtInfo": {},
    "time": 1658737209400
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
<code><span id=oawfRecordsNew>/contract/v3/private/account/wallet/fund-records</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawfRecordsNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|startTime |false |string |t(:contract_accountStatTime) |
|endTime |false |string |t(:contract_accountEndTime) |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:contract_accountCoin_resp) |
|<a href="#wallet-fund-type-wallet_fund_type-type">walletFundType</a> |false |string |t(:row_comment_walletFundType) |
|limit |false |string |t(:row_comment_limit) |
|cursor |false |string |t(:contract_accountCursor) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> coin |string |t(:row_comment_coin_type)  |
|list> type |string |t(:row_comment_fund_type)  |
|list> amount |string |t(:row_comment_fund_amount)  |
|list> wallet_balance |string |t(:row_comment_wallet_balance)  |
|list> exec_time |string |t(:row_comment_exec_timestamp)  |
|nextPageCursor |string |t(:contract_accountNextPageCursor)  |
