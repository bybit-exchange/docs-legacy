# t(:CrossMarginTrading)
<aside class="notice">
t(:spotCrossMarginTradingDesc)
</aside>

### t(:borrowmarginloan)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/spot/v3/private/cross-margin-loan' \
--header 'Content-Type: application/json' \
--header 'X-BAPI-API-KEY: XXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1662617848755' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: 03529daeca45ccf5c491a8e6569ff3dff39d1e984171e7aedca0dc2624d0c416' \
--data-raw '{
    "coin": "USDT",
    "qty": "200"
}'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "success",
    "result": {
        "transactId": "14143"
    },
    "retExtInfo": null,
    "time": 1662617848970
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=crossMarginLoan>/spot/v3/private/cross-margin-loan</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#crossMarginLoan"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#currency-currency-coin">currency</a>|<b>true</b>|string|t(:spotCurrency)|
|qty|<b>true</b>|string|t(:spotBorrowQty)|


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transactId|string|t(:spotResult)|


### t(:RepayMarginLoan)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/spot/v3/private/cross-margin-repay' \
--header 'Content-Type: application/json' \
--header 'X-BAPI-API-KEY: XXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1662618298354' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: 29e4463832bf753b770853c5559b00dd3be376ae3d42f5d7043ff39be1d7891b' \
--data-raw '{
    "coin": "USDT",
    "qty": "150"
}'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "success",
    "result": {
        "repayId": "12128"
    },
    "retExtInfo": null,
    "time": 1662618298452
}
```

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=crossMarginRepay>/spot/v3/private/cross-margin-repay</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#crossMarginRepay"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#currency-currency-coin">currency</a>|<b>true</b>|string|t(:spotCurrency)|
|qty|<b>true</b>|string|t(:spotRepayQty)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|repayId|string|t(:spotV3RepayId)|

### t(:QueryBorrowingInfo)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/private/cross-margin-orders?startTime=1662508800000&endTime=1662552000000&coin=USDT&status=1' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-API-KEY: XXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1662619080929' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: 00f707bf08f8b91a8d6b7e6a1a4f3f551033482f29a78254debf63515415e637'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "success",
    "result": {
        "list": [
            {
                "accountId": "533287",
                "coin": "USDT",
                "createdTime": 1662617849000,
                "id": "14143",
                "interestAmount": "0.001668",
                "interestBalance": "0",
                "loanAmount": "200",
                "loanBalance": "50.001668",
                "status": 1,
                "type": 2
            }
        ]
    },
    "retExtInfo": null,
    "time": 1662618592344
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=queryBorrowingInfo>/spot/v3/private/cross-margin-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#queryBorrowingInfo"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|startTime|false|long|t(:spot_orders_start_time)|
|endTime|false|long|t(:spot_orders_end_time)|
|<a href="#currency-currency-coin">currency</a>|false|string|t(:spotCurrency)|
|status|false|int|t(:spotCrossMarginOrderStatus)|
|limit|false|int|t(:spotCrossMarginLimit)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list|array|Object|
|accountId|string|t(:spotAccountId)|
|coin|string|t(:spotCurrency)|
|createdTime|long|t(:spotCrossMarginCreatedTime)|
|id|long|t(:spotBorrowingId)|
|interestAmount|string|t(:spotInterestAmount)|
|interestBalance|string|t(:spotInterestBalance)|
|loanAmount|string|t(:spotLoanAmount)|
|loanBalance|string|t(:spotLoanBalance)|
|status|int|t(:spotCrossMarginOrderStatus)|
|type|int|t(:spotCrossMarginType)|


### t(:QueryAccountInfo)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/private/cross-margin-account' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-API-KEY: XXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1662619341689' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: a583c6f9bd6d2f272868ab4552cc8fb194faf7f9b2323b299411eef5d4cce4c8'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "success",
    "result": {
        "acctBalanceSum": "0.062912223136001122",
        "debtBalanceSum": "0.002588651523215288",
        "loanAccountList": [
            {
                "free": "0.95449",
                "interest": "0",
                "loan": "0",
                "locked": "0",
                "tokenId": "ETH",
                "total": "0.95449"
            },
            {
                "free": "219.32838547",
                "interest": "0",
                "loan": "50.001668",
                "locked": "0",
                "tokenId": "USDT",
                "total": "219.32838547"
            },
            {
                "free": "86.186045",
                "interest": "0",
                "loan": "0",
                "locked": "0",
                "tokenId": "USDC",
                "total": "86.186045"
            }
        ],
        "riskRate": "0.0411",
        "status": 1
    },
    "retExtInfo": null,
    "time": 1662619341782
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=queryAccountInfo>/spot/v3/private/cross-margin-account</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#queryAccountInfo"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|acctBalanceSum|string|t(:spotAcctBalanceSum)|
|debtBalanceSum|string|t(:spotDebtBalanceSum)|
|loanAccountList|array|Object|
|free|string|t(:spotFree)|
|interest|string|t(:spotInterest)|
|loan|string|t(:spotLiability)|
|locked|string|t(:spotLocked)|
|tokenId|string|t(:spotTokenId)|
|total|string|t(:spotTotal)|
|riskRate|string|t(:spotResRiskRate)|
|status|string|t(:spotCrossMarginAccountStatus)|

### t(:QueryInterestQuota)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/private/cross-margin-loan-info?coin=USDT' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-API-KEY: XXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1662619710952' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: 565094ad6f947b0f7d5d2022dbd7f48a4abf110740e71f2c1fc0304ed6ec725a'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "success",
    "result": {
        "coin": "USDT",
        "interestRate": "0.000200000000",
        "loanAbleAmount": "4610.7712066900784",
        "maxLoanAmount": "100000"
    },
    "retExtInfo": null,
    "time": 1662619711090
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=queryInterestQuota>/spot/v3/private/cross-margin-loan-info</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#queryInterestQuota"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#currency-currency-coin">currency</a>|<b>true</b>|string|t(:spotCurrency)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|coin|string|t(:spotCurrency)|
|interestRate|string|t(:spotInterestRate)|
|loanAbleAmount|string|t(:spotLoanableAmount)|
|maxLoanAmount|string|t(:spotMaxLoanAmount)|


### t(:QueryRepaymentHistory)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/private/cross-margin-repay-history?coin=USDT&startTime=1662480000000&endTime=1662552000000' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-API-KEY: XXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1662622151668' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: 48db29501c9e20aff22ec80f2bf201022314fe97d6ea11b89025dd6f59b386da'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "success",
    "result": {
        "list": [
            {
                "accountId": "533287",
                "coin": "USDT",
                "repaidAmount": "150",
                "repayId": "12128",
                "repayMarginOrderId": "1240526631777624064",
                "repayTime": "1662618298000",
                "transactIds": [
                    {
                        "repaidAmount": "150",
                        "repaidInterest": "0.001668",
                        "repaidPrincipal": "149.998332",
                        "repaidSerialNumber": "1240522860586622976",
                        "transactId": "14143"
                    }
                ]
            }
        ]
    },
    "retExtInfo": null,
    "time": 1662622151872
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=queryRepaymentHistory>/spot/v3/private/cross-margin-repay-history</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#queryRepaymentHistory"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|startTime|false|long|t(:spot_orders_start_time)|
|endTime|false|long|t(:spot_orders_end_time)|
|coin|false|string|t(:spotCurrency)|
|limit|false|int|t(:spotCrossMarginLimit)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|accountId|string|t(:spotAccountId)|
|coin|string|t(:spotCurrency)|
|repaidAmount|string|t(:spotRepaidAmount)|
|repayId|string|t(:spotRepayId)|
|repayMarginOrderId|string|t(:spotRepayMarginOrderId)|
|repayTime|string|t(:spotRepayTime)|
|transactIds|array|Object|
|repaidAmount|string|t(:spotRepaidAmount)|
|repaidInterest|string|t(:spotRepaidInterest)|
|repaidPrincipal|string|t(:spotRepaidPrincipal)|
|repaidSerialNumber|string|t(:spotRepaidSerialNumber)|
|transactId|string|t(:spotTransactId)|
