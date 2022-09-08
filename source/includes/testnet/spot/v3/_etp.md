# t(:lt)

### t(:ltInfos)
> t(:codequote_curlExample)

```console
https://api.bybit.com/spot/v3/public/infos?ltCode=BTC3S \
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "success",
    "result": {
        "list": [
            {
                "fundFee": "-77.80535586",
                "fundFeeTime": 1662566400000,
                "ltCode": "BTC3SUSDT",
                "ltName": "3X Short",
                "manageFeeRate": "0.00005",
                "manageFeeTime": 1662598800000,
                "maxPurchase": "10000",
                "maxPurchaseDaily": "200000",
                "maxRedeem": "1000",
                "maxRedeemDaily": "60000",
                "minPurchase": "100",
                "minRedeem": "5",
                "netValue": "27.86850988224310062",
                "purchaseFeeRate": "0.0005",
                "redeemFeeRate": "0.0005",
                "status": "1",
                "total": "5000000",
                "value": "503990989.499587242974184768"
            }
        ]
    },
    "retExtInfo": null,
    "time": 1662545667108
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=ltInfos>/spot/v3/public/infos</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ltInfos"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|ltCode|false|string|t(:spotLtCode)|


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|ltCode|string|t(:spotResLtCode)|
|ltName|string|t(:spotResLtName)|
|maxPurchase|string|t(:spotResMaxPurchase)|
|minPurchase|string|t(:spotResMinPurchase)|
|maxPurchaseDaily|string|t(:spotResMaxPurchaseDaily)|
|maxRedeem|string|t(:spotResMaxRedeem)|
|minRedeem|string|t(:spotResMinRedeem)|
|maxRedeemDaily|string|t(:spotResMaxRedeemDaily)|
|purchaseFeeRate|string|t(:spotResPurchaseFee)|
|redeemFeeRate|string|t(:spotResRedeemFee)|
|t(:row_parameter_ltStatus)|string|t(:spotResLtStatus)|
|fundFee|string|t(:spotResFundFee)|
|fundFeeTime|long|t(:spotResFundFeeTime)|
|manageFeeRate|string|t(:spotResManageFee)|
|manageFeeTime|long|t(:spotResManageFeeTime)|
|value|string|t(:spotResValue)|
|total|string|t(:spotResTotal)|
|netValue|string|t(:spotResNetValue)|


<aside class="notice">
t(:lt_para)
</aside>

### t(:ltQuoteReference)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api.bybit.com/spot/v3/private/reference?ltCode=BTC3S' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-API-KEY: XXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1662549197919' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: c9a7c916aece021143c891fa3c87bc1469087a3927847ef757e50ff0e783282c'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "success",
    "result": {
        "basket": "-111.537000043436201394",
        "circulation": "26876.652597034302633009",
        "leverage": "-2.797206317443581498",
        "ltCode": "BTC3S",
        "nav": "27.833235232732847932",
        "navTime": 1662546552568
    },
    "retExtInfo": null,
    "time": 1662546552602
}
``` 

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=ltReference>/spot/v3/private/reference</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ltReference"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|ltCode|<b>true</b>|string|t(:spotLtCode)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|basket|string|t(:spotTotalPositionValue)|
|circulation|string|t(:spotResCirculation)|
|leverage|string|t(:spotLeverage)|
|ltCode|string|t(:spotResLtCode)|
|nav|string|t(:spotLtQuoteNav)|
|navTime|long|t(:spotLtQuoteNavTime)|

### t(:ltPurchase)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/spot/v3/private/purchase' \
--header 'Content-Type: application/json' \
--header 'X-BAPI-API-KEY: XXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1662549845240' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: 9f787f824122ea1ef6d368a4a24c775e7853128decd9651cab91824162261b21' \
--data-raw '{
    "ltCode": "DOT3LUSDT",
    "ltAmount": "100",
    "serialNo": "x005"
}'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "success",
    "result": {
        "amount": "100",
        "id": "2085",
        "ltCode": "DOT3LUSDT",
        "orderAmount": "",
        "orderQuantity": "",
        "orderStatus": "2",
        "serialNo": "x005",
        "timestamp": 1662549845373,
        "valueCoin": "USDT"
    },
    "retExtInfo": null,
    "time": 1662549845453
}
``` 

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=ltPurchase>/spot/v3/private/purchase</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ltPurchase"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|ltCode|<b>true</b>|string|t(:spotLtCode)|
|ltAmount|<b>true</b>|number|t(:spotLtAmount)|
|serialNo|false|string|t(:spotLtSerialNo)|


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|amount|string|t(:spotResPurchaseAmount)|
|id|string|t(:spotResId)|
|ltCode|string|t(:spotResLtCode)|
|orderAmount|string|t(:spotResPurchaseOrderAmount)|
|orderQuantity|string|t(:spotResPurchaseOrderQuantity)|
|t(:row_parameter_ltOrderStatus)|string|t(:spotResOrderStatus)|
|serialNo|string|t(:spotLtSerialNo)|
|timestamp|long|t(:spot_timestamp)|
|valueCoin|string|t(:spotResValueCoin)|


### t(:ltRedeem)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/spot/v3/private/redeem' \
--header 'Content-Type: application/json' \
--header 'X-BAPI-API-KEY: XXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1662605726010' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: c6a4d178988d07045c06528b7038842f4d75dde8be840cc8c538ca434f6fc617' \
--data-raw '{
    "ltCode": "DOT3LUSDT",
    "ltQuantity": "50",
    "serialNo": "r001"
}'
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "success",
    "result": {
        "id": "2087",
        "ltCode": "DOT3LUSDT",
        "orderAmount": "",
        "orderQuantity": "50",
        "orderStatus": "2",
        "quantity": "",
        "serialNo": "r001",
        "timestamp": 1662605726326,
        "valueCoin": "DOT3L"
    },
    "retExtInfo": null,
    "time": 1662605727987
}
``` 

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=ltRedeem>/spot/v3/private/redeem</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ltRedeem"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|ltCode|<b>true</b>|string|t(:spotLtCode)|
|ltQuantity|<b>true</b>|number|t(:spotLtQuantity)|
|serialNo|false|string|t(:spotLtSerialNo)|


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id|long|t(:spotResId)|
|ltCode|string|t(:spotResLtCode)|
|orderAmount|string|t(:spotV3ResRedeemOrderAmount)|
|orderQuantity|string|t(:spotResRedeemOrderQuantity)|
|t(:row_parameter_ltOrderStatus)|string|t(:spotResOrderStatus)|
|<a href="#quantity-qty">quantity</a> |string|t(:spotV3ResRedeemQuantity)|
|serialNo|string|t(:spotLtSerialNo)|
|timestamp|long|t(:spot_timestamp)|
|valueCoin|string|t(:spotResValueCoin)|


### t(:ltRecord)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/private/record?ltCode=DOT3L&startTime=1662548400000&endTime=1662549840000' \
--header 'X-BAPI-SIGN-TYPE: 2' \
--header 'X-BAPI-API-KEY: XXXXXXXXX' \
--header 'X-BAPI-TIMESTAMP: 1662608374151' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: 6f864a0df2989ba8b58a7ee0cb5c76434728acca2cd60d76d9aba456b60b59ad'
```


> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "success",
    "result": {
        "list": [
            {
                "amount": "",
                "excTime": 1662549752000,
                "fee": "",
                "ltCode": "DOT3L",
                "orderId": "2083",
                "orderStatus": "3",
                "orderTime": 1662549752000,
                "orderType": 1,
                "serialNo": "x003",
                "value": "",
                "valueCoin": "USDT"
            },
            {
                "amount": "",
                "excTime": 1662549702000,
                "fee": "",
                "ltCode": "DOT3L",
                "orderId": "2082",
                "orderStatus": "3",
                "orderTime": 1662549702000,
                "orderType": 1,
                "serialNo": "x002",
                "value": "",
                "valueCoin": "USDT"
            }
        ]
    },
    "retExtInfo": null,
    "time": 1662608374640
}
``` 

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=ltRecord>/spot/v3/private/record</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ltRecord"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|ltCode|false|string|t(:spotLtCode)|
|orderId|false|string|t(:spotLtOrderId)|
|startTime|false|long|t(:spot_start_time)|
|endTime|false|long|t(:spot_end_time)|
|limit|false|int|t(:row_comment_limit_100_500)|
|t(:row_parameter_ltOrderType)|false|int|t(:spotLtOrderType)|
|serialNo|false|string|t(:spotLtSerialNo)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|amount|string|t(:spotResOrderQuantity)|
|excTime|long|t(:spotResExcTime)|
|fee|string|t(:spotResFee)|
|ltCode|string|t(:spotResLtCode)|
|orderId|string|t(:spotLtOrderId)|
|t(:row_parameter_ltOrderStatus)|string|t(:spotResOrderStatus)|
|orderTime|long|t(:spotResOrderTime)|
|t(:row_parameter_ltOrderType)|int|t(:spotLtOrderType)|
|serialNo|string|t(:spotLtSerialNo)|
|value|string|t(:spotResRecordValue)|
|valueCoin|string|t(:spotResValueCoin)|
