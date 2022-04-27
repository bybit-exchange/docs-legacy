# t(:spotCrossMarginTrading)
### t(:spotEnableCrossMarginTrading)
> t(:codequote_curlExample)

```console
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "",
    "ext_code": null,
    "ext_info": null,
    "result": 438
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=crossMarginLoan>/spot/v1/cross-margin/loan</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#crossMarginLoan"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|currency|<b>true</b>|string|t(:spotCurrency)|
|qty|<b>true</b>|string|t(:spotBorrowQty)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|result|number|t(:spotResult)|


### t(:spotRepayMarginLoan)
> t(:codequote_curlExample)

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "",
    "ext_code": null,
    "ext_info": null,
    "result": 307
}
``` 

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=crossMarginRepay>/spot/v1/cross-margin/repay</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#crossMarginRepay"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|currency|<b>true</b>|string|t(:spotCurrency)|
|qty|<b>true</b>|string|t(:spotRepayQty)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|result|number|t(:spotResult)|

### t(:spotQueryBorrowingInfo)
> t(:codequote_curlExample)

```console

```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "",
    "ext_code": null,
    "ext_info": null,
    "result": [
        {
            "id": "0",
            "accountId": "290120",
            "currency": "USDT",
            "loanAmount": "500",
            "loanBalance": "0.005",
            "interestAmount": "0.005",
            "interestBalance": "0",
            "createdTime": "1650946211000",
            "type": 2,
            "status": 1
        }
    ]
}
``` 

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=queryBorrowingInfo>/spot/v1/cross-margin/order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#queryBorrowingInfo"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|startTime|false|long|t(:spot_orders_start_time)|
|endTime|false|long|t(:spot_orders_end_time)|
|currency|false|string|t(:spotCurrency)|
|status|false|int|t(:spotCrossMarginOrderStatus)|
|limit|false|int|t(:spotCrossMarginLimit)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id|long|t(:spotBorrowingId)|
|accountId|string|t(:spotAccountId)|
|currency|string|t(:spotCurrency)|
|loanAmount|string|t(:spotLoanAmount)|
|loanBalance|string|t(:spotLoanBalance)|
|interestAmount|string|t(:spotInterestAmount)|
|interestBalance|string|t(:spotInterestBalance)|
|createdTime|long|t(:spotCrossMarginCreatedTime)|
|type|int|t(:spotCrossMarginType)|
|status|int|t(:spotCrossMarginOrderStatus)|


### t(:spotQueryAccountInfo)
> t(:codequote_curlExample)

```console
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "",
    "ext_code": null,
    "ext_info": null,
    "result": {
        "status": "1",
        "riskRate": "0",
        "acctBalanceSum": "17.544271415503388734",
        "debtBalanceSum": "0.000000125952475464",
        "loanAccountList": [
            {
                "tokenId": "BTC",
                "total": "9.02798765888",
                "locked": "0",
                "loan": "0",
                "interest": "0",
                "free": "9.02798765888"
            },
            {
                "tokenId": "XRP",
                "total": "5074.35554",
                "locked": "0",
                "loan": "0",
                "interest": "0",
                "free": "5074.35554"
            },
            {
                "tokenId": "ETH",
                "total": "73.52299564",
                "locked": "0",
                "loan": "0",
                "interest": "0",
                "free": "73.52299564"
            },
            {
                "tokenId": "USDT",
                "total": "116360.2045351043476",
                "locked": "0",
                "loan": "0.005",
                "interest": "0.0001",
                "free": "116360.2045351043476"
            },
            {
                "tokenId": "BIT",
                "total": "6.78291",
                "locked": "0",
                "loan": "0",
                "interest": "0",
                "free": "6.78291"
            }
        ]
    }
}
``` 

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=queryAccountInfo>/spot/v1/cross-margin/accounts/balance</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#queryAccountInfo"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|status|string|t(:spotCrossMarginAccountStatus)|
|riskRate|string|t(:spotResOrderStatus)|
|acctBalanceSum|string|t(:spotAcctBalanceSum)|
|debtBalanceSum|string|t(:spotDebtBalanceSum)|
|loanAccountList|List|Object|
|tokenId|string|t(:spotTokenId)|
|total|string|t(:spotTotal)|
|free|string|t(:spotFree)|
|locked|string|t(:spotLocked)|
|loan|string|t(:spotLiability)|
|interest|string|t(:spotInterest)|

### t(:spotQueryInterestQuota)
> t(:codequote_curlExample)


> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "",
    "ext_code": null,
    "ext_info": null,
    "result": {
        "currency": "USDT",
        "interestRate": "0.00011",
        "maxLoanAmount": "15000",
        "loanAbleAmount": "1414762.97401717124312"
    }
}
``` 

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=queryInterestQuota>/spot/v1/cross-margin/loan-info</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#queryInterestQuota"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|currency|<b>true</b>|string|t(:spotCurrency)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|currency|string|t(:spotCurrency)|
|interestRate|string|t(:spotInterestRate)|
|maxLoanAmount|int|t(:spotMaxLoanAmount)|
|loanAbleAmount|string|t(:spotLoanableAmount)|


### t(:spotQueryRepaymentHistory)
> t(:codequote_curlExample)


> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "",
    "ext_code": null,
    "ext_info": null,
    "result": [
        {
            "repayMarginOrderId": "1142655714041531904",
            "repayId": "307",
            "accountId": "290120",
            "currency": "USDT",
            "repaidAmount": "500",
            "repayTime": "1650951176000",
            "transactIds": [
                {
                    "transactId": "438",
                    "repaidSerialNumber": "1142614062270779136",
                    "repaidAmount": "500",
                    "repaidPrincipal": "499.995",
                    "repaidInterest": "0.005"
                }
            ]
        }
    ]
}
``` 

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=queryRepaymentHistory>/spot/v1/cross-margin/repay/history</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#queryRepaymentHistory"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|startTime|false|long|t(:spot_orders_start_time)|
|endTime|false|long|t(:spot_orders_end_time)|
|currency|false|string|t(:spotCurrency)|
|limit|false|int|t(:spotCrossMarginLimit)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|repayMarginOrderId|string|t(:spotRepayMarginOrderId)|
|repayId|string|t(:spotRepayId)|
|repayTime|string|t(:spotRepayTime)|
|accountId|string|t(:spotAccountId)|
|currency|string|t(:spotCurrency)|
|repaidAmount|string|t(:spotRepaidAmount)|
|transactIds|List|Object|
|repaidSerialNumber|string|t(:spotRepaidSerialNumber)|
|transactId|string|t(:spotTransactId)|
|repaidAmount|string|t(:spotRepaidAmount)|
|repaidPrincipal|string|t(:spotRepaidPrincipal)|
|repaidInterest|string|t(:spotRepaidInterest)|
