# t(:otcLoan)
<aside class="notice">
t(:otcLoanNotice)
</aside>

### t(:marginProductInfo)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/public/margin-product-infos?productId=70'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "marginProductInfo": [
            {
                "productId": "70",
                "leverage": "5.00000000",
                "supportSpot": 1,
                "supportContract": 1,
                "withdrawLine": "0.5",
                "transferLine": "0.6",
                "spotBuyLine": "0.7",
                "spotSellLine": "0.8",
                "contractOpenLine": "0.9",
                "liquidationLine": "0.95",
                "stopLiquidationLine": "0.40000000",
                "contractLeverage": "",
                "transferRatio": "",
                "spotSymbols": [
                    "DYDXQQTEST001"
                ],
                "contractSymbols": [
                    "RAYUSDT",
                    "API3USDT"
                ]
            }
        ]
    },
    "retExtInfo": {},
    "time": 1669362961705
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=maproinf>/spot/v3/public/margin-product-infos</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#maproinf"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|productId|false|string|t(:otcLoan_req_productId)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|marginProductInfo |array |Object |
|> productId |string |t(:otcLoan_productId) |
|> leverage |string |t(:otcLoan_leverage) |
|> supportSpot |integer |t(:otcLoan_supportSpot) |
|> supportContract |integer |t(:otcLoan_supportContract) |
|> withdrawLine |string |t(:otcLoan_withdrawLine) |
|> transferLine |string |t(:otcLoan_transferLine) |
|> spotBuyLine |string |t(:otcLoan_spotBuyLine) |
|> spotSellLine |string |t(:otcLoan_spotSellLine) |
|> contractOpenLine |string |t(:otcLoan_contractOpenLine) |
|> liquidationLine |string |t(:otcLoan_liquidationLine) |
|> stopLiquidationLine |string |t(:otcLoan_stopLiquidationLine) |
|> contractLeverage |string |t(:otcLoan_contractLeverage) |
|> transferRatio |string |t(:otcLoan_transferRatio) |
|> spotSymbols |array |t(:otcLoan_spotSymbols) |
|> contractSymbols |array |t(:otcLoan_contractSymbols) |


### t(:marginCoinInfo)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/spot/v3/public/margin-ensure-tokens?productId=70'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "marginToken": [
            {
                "productId": "70",
                "spotToken": [
                    {
                        "token": "BTC",
                        "convertRatio": "1.00000000"
                    },
                    {
                        "token": "ETH",
                        "convertRatio": "1.00000000"
                    },
                    {
                        "token": "USDT",
                        "convertRatio": "1"
                    }
                ],
                "contractToken": [
                    {
                        "token": "USDT",
                        "convertRatio": "1"
                    }
                ]
            }
        ]
    },
    "retExtInfo": {},
    "time": 1669363954802
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=marginToken>/spot/v3/public/margin-ensure-tokens</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#marginToken"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|productId|false|string|t(:marginCoinInfo_req_productId)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|marginToken |array |Object |
|> productId |string |t(:otcLoan_productId) |
|> spotToken |array |t(:otcLoan_spotToken) |
|>> token |string |t(:token) |
|>> convertRatio |string |t(:convertRatio) |
|> contractToken |array |t(:otcLoan_contractToken) |
|>> token |string |t(:token) |
|>> convertRatio |string |t(:convertRatio) |


### t(:loanInfo)
t(:loanInfo_para)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/private/margin-loan-infos' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-API-KEY: XXXXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1669364798602' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: 41b41006bdc50d0ad6d83c712804a490ef3dae079b9cd3202103022cd813bb00'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "loanInfo": [
            {
                "orderId": "1244781478207029504",
                "orderProductId": "34",
                "parentUid": "999805",
                "loanTime": "1663126149000",
                "loanCoin": "USDT",
                "loanAmount": "500000",
                "unpaidAmount": "6351.49614274",
                "unpaidInterest": "264.0137162",
                "repaidAmount": "493648.50385726",
                "repaidInterest": "0",
                "interestRate": "0.00027397",
                "status": 1,
                "leverage": "20",
                "supportSpot": 1,
                "supportContract": 1,
                "withdrawLine": "0.5",
                "transferLine": "0.6",
                "spotBuyLine": "0.7",
                "spotSellLine": "0.8",
                "contractOpenLine": "0.9",
                "liquidationLine": "0.95",
                "stopLiquidationLine": "0.20000000",
                "contractLeverage": "3",
                "transferRatio": "0.1",
                "spotSymbols": [
                    "DYDXQQTEST001",
                    "DYDXNEO",
                    "PMTEST16USDT"
                ],
                "contractSymbols": [
                    "RAYUSDT",
                    "API3USDT",
                    "SUSHIUSDT"
                ]
            }
        ]
    },
    "retExtInfo": {},
    "time": 1669364798924
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=marloainf>/spot/v3/private/margin-loan-infos</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#marloainf"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|orderId|false|string|t(:loanInfo_req_orderId)|
|startTime|false|long|t(:spot_orders_start_time)|
|endTime|false|long|t(:spot_orders_end_time)|
|limit|false|int|t(:loanInfo_limit)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|loanInfo |array |Object |
|> orderId |string |t(:otcLoan_orderId) |
|> orderProductId |string |t(:otcLoan_productId) |
|> parentUid |string |t(:otcLoan_parentUid) |
|> loanTime |string |t(:otcLoan_loanTime) |
|> loanCoin |string |t(:otcLoan_loanCoin) |
|> loanAmount |string |t(:otcLoan_loanAmount) |
|> unpaidAmount |string |t(:otcLoan_unpaidAmount) |
|> unpaidInterest |string |t(:otcLoan_unpaidInterest) |
|> repaidAmount |string |t(:otcLoan_repaidAmount) |
|> repaidInterest |string |t(:otcLoan_repaidInterest) |
|> interestRate |string |t(:otcLoan_interestRate) |
|> status |string |t(:otcLoan_status) |
|> leverage |string |t(:otcLoan_leverage) |
|> supportSpot |intger |t(:otcLoan_supportSpot) |
|> supportContract |integer |t(:otcLoan_supportContract) |
|> withdrawLine |string |t(:otcLoan_withdrawLine) |
|> transferLine |string |t(:otcLoan_transferLine) |
|> spotBuyLine |string |t(:otcLoan_spotBuyLine) |
|> spotSellLine |string |t(:otcLoan_spotSellLine) |
|> contractOpenLine |string |t(:otcLoan_contractOpenLine) |
|> liquidationLine |string |t(:otcLoan_liquidationLine) |
|> stopLiquidationLine |string |t(:otcLoan_stopLiquidationLine) |
|> contractLeverage |string |t(:otcLoan_contractLeverage) |
|> transferRatio |string |t(:otcLoan_transferRatio) |
|> spotSymbols |array |t(:otcLoan_spotSymbols) |
|> contractSymbols |array |t(:otcLoan_contractSymbols) |


### t(:repayInfo)
t(:repayInfo_para)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/private/margin-repaid-infos?startTime=1663126392000&endTime=1663126394000' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-API-KEY: XXXXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1669366647851' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: 4a2d54488d29cde341e51ce9eae0dcb685ac485953b659ba8852bd28077529c4'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "repayInfo": [
            {
                "repayOrderId": "8189",
                "repaidTime": "1663126393000",
                "token": "USDT",
                "quantity": "30000",
                "interest": "0",
                "businessType": "1",
                "status": "1"
            }
        ]
    },
    "retExtInfo": {},
    "time": 1669366648366
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=marrepinf>/spot/v3/private/margin-repaid-infos</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#marrepinf"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|startTime|false|long|t(:spot_orders_start_time)|
|endTime|false|long|t(:spot_orders_end_time)|
|limit|false|int|t(:loanInfo_limit)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|repayInfo |array |Object |
|> repayOrderId |string |t(:otcLoan_repayOrderId) |
|> repaidTime |string |t(:otcLoan_repaidTime) |
|> token |string |t(:otcLoan_token) |
|> quantity |string |t(:otcLoan_quantity) |
|> interest |string |t(:otcLoan_interest) |
|> businessType |string |t(:otcLoan_businessType) |
|> status |string |t(:otcLoan_status) |


### t(:ltv)
t(:ltv_para)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/private/margin-ltv' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-API-KEY: XXXXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1669367335035' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: 75d8c29b293635f3501c6dc8770892681a05a2788aa3c467dd136e7dabf173a9'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "ltvInfo": [
            {
                "ltv": "0.1147",
                "parentUid": "999805",
                "subAccountUids": [
                    "999805"
                ],
                "unpaidAmount": "",
                "unpaidInfo": [
                    {
                        "token": "USDT",
                        "unpaidQty": "6351.49614274",
                        "unpaidInterest": "264.0137162"
                    }
                ],
                "balance": "57626.875915433333333332400000000",
                "spotBalanceInfo": [
                    {
                        "token": "BTC",
                        "price": "16375.621333333333333332",
                        "qty": "0.2"
                    },
                    ....
                    {
                        "token": "XRP",
                        "price": "0.409517",
                        "qty": "10000"
                    }
                ],
                "contractInfo": [
                    {
                        "token": "USDT",
                        "price": "1",
                        "qty": "0"
                    }
                ]
            }
        ]
    },
    "retExtInfo": {},
    "time": 1669367335608
}
```

<aside class="notice">
t(:ltv_notice)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=ltv>/spot/v3/private/margin-ltv</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ltv"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|ltvInfo |array |Object |
|> ltv |string |t(:otcLoan_ltv) |
|> parentUid |string |t(:otcLoan_ltv_parentUid) |
|> subAccountUids |array |t(:otcLoan_subAccountUids) |
|> unpaidAmount |string |t(:otcLoan_ltv_unpaidAmount) |
|> unpaidInfo |array |t(:otcLoan_unpaidInfo) |
|>> token |string |t(:otcLoan_ltv_token) |
|>> unpaidQty |string |t(:otcLoan_unpaidQty) |
|>> unpaidInterest |string |t(:otcLoan_Interest) |
|> balance |string |t(:otcLoan_balance) |
|> spotBalanceInfo |array |t(:otcLoan_spotBalanceInfo) |
|>> token |string |t(:otcLoan_ltv_spot_token) |
|>> price |string |t(:otcLoan_ltv_spot_price) |
|>> qty |string |t(:otcLoan_ltv_spot_qty) |
|> contractInfo |array |t(:otcLoan_contractInfo) |
|>> token |string |t(:otcLoan_ltv_contract_token) |
|>> price |string |t(:otcLoan_ltv_contract_price) |
|>> qty |string |t(:otcLoan_ltv_contract_qty) |
