# t(:lt)
### t(:ltInfo)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/spot/lt/v1/info \
-H "Content-Type: application/x-www-form-urlencoded" \
-d 'api_key={api_key}&ltCode={ltCode}&timestamp=1637669364000'
```

> t(:codequote_responseExample)

```javascript
{
  "ret_code": 0,
    "ret_msg": null,
    "result": {
      "ltCode": "BTC3L",
      "ltName": "3X Long",
      "maxPurchase": "300024.12345678",
      "minPurchase": "0.12345678",
      "maxPurchaseDaily": "500000.12345678",
      "maxRedeem": "1000.12345678",
      "minRedeem": "1.12345678",
      "maxRedeemDaily": "1000002.12345678",
      "purchaseFeeRate": "0.12345678",
      "redeemFeeRate": "0.12345678",
      "status": "1",
      "fundFee": "0.12345678",
      "fundFeeTime": 1620917160000,
      "manageFeeRate": "-0.12345678",
      "manageFeeTime": 1620917160000,
      "value": "1212432.12345678",
      "total": "200000000.12345678",
      "netValue": "10.12345678"
  },
  "ext_code": null,
  "ext_info": null
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=ltInfo>/spot/lt/v1/info</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ltInfo"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|ltCode|<b>true</b>|string|t(:spotLtCode)|
|timestamp|<b>false</b>|number|t(:spot_timestamp)|


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

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "",
    "ext_code": null,
    "ext_info": null,
    "result": {
        "ltCode": "BTC3L",
        "nav": "8.348543196938590649",
        "navTime": "1650259325443",
        "basket": "14.063000000262307568",
        "leverage": "3.451925561403627643",
        "circulation": "18969.901970158967556311"
    }
}
``` 

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=ltReference>/spot/lt/v1/reference</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ltReference"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|ltCode|<b>true</b>|string|t(:spotLtCode)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|ltCode|string|t(:spotResLtCode)|
|nav|string|t(:spotLtQuoteNav)|
|navTime|string|t(:spotLtQuoteNavTime)|
|basket|string|t(:spotTotalPositionValue)|
|leverage|string|t(:spotLeverage)|
|circulation|string|t(:spotResCirculation)|

### t(:ltPurchase)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/spot/lt/v1/purchase \
-H "Content-Type: application/x-www-form-urlencoded" \
-d 'api_key={api_key}&ltCode={ltCode}&ltAmount={ltAmount}&serialNo={serialNo}&timestamp=1637669364000'
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": null,
    "result": {
        "ltCode": "BTC3L",
        "orderStatus": "1",
        "orderQuantity": "12",
        "orderAmount": "123.12345678",
        "amount": "123.12345678",
        "timestamp": 1620917160000,
        "id": 1,
        "valueCoin": "USDT",
        "serialNo": "0a65e75f165543103539010011"
    },
    "ext_code": null,
    "ext_info": null
}
``` 

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=ltPurchase>/spot/lt/v1/purchase</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ltPurchase"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|ltCode|<b>true</b>|string|t(:spotLtCode)|
|ltAmount|<b>true</b>|number|t(:spotLtAmount)|
|timestamp|<b>true</b>|number|t(:spot_timestamp)|
|serialNo|<b>false</b>|string|t(:spotLtSerialNo)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|ltCode|string|t(:spotResLtCode)|
|t(:row_parameter_ltOrderStatus)|string|t(:spotResOrderStatus)|
|orderQuantity|string|t(:spotResPurchaseOrderQuantity)|
|orderAmount|string|t(:spotResPurchaseOrderAmount)|
|amount|string|t(:spotResPurchaseAmount)|
|timestamp|long|t(:spot_timestamp)|
|id|long|t(:spotResId)|
|valueCoin|string|t(:spotResValueCoin)|
|serialNo|string|t(:spotLtSerialNo)|


### t(:ltRedeem)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/spot/lt/v1/redeem \
-H "Content-Type: application/x-www-form-urlencoded" \
-d 'api_key={api_key}&ltCode={ltCode}&ltQuantity={ltQuantity}&serialNo={serialNo}&timestamp=1637669364000'
```

> t(:codequote_responseExample)

```javascript
{
  "ret_code": 0,
    "ret_msg": null,
    "result": {
      "ltCode": "BTC3L",
      "orderStatus": "1",
      "quantity": "12",
      "orderQuantity": "123.12345678",
      "orderAmount": "123.12345678",
      "timestamp": 1620917160000,
      "id": 1,
      "valueCoin": "USDT"
  },
  "ext_code": null, 
  "ext_info": null
}
``` 

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=ltRedeem>/spot/lt/v1/redeem</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ltRedeem"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|ltCode|<b>true</b>|string|t(:spotLtCode)|
|ltQuantity|<b>true</b>|number|t(:spotLtQuantity)|
|timestamp|<b>true</b>|number|t(:spot_timestamp)|
|serialNo|<b>false</b>|string|t(:spotLtSerialNo)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|ltCode|string|t(:spotResLtCode)|
|t(:row_parameter_ltOrderStatus)|string|t(:spotResOrderStatus)|
|t(:row_parameter_quantity) |string|t(:spotResRedeemQuantity)|
|orderQuantity|string|t(:spotResRedeemOrderQuantity)|
|orderAmount|string|t(:spotResRedeemOrderAmount)|
|timestamp|long|t(:spot_timestamp)|
|id|long|t(:spotResId)|
|valueCoin|string|t(:spotResValueCoin)|
|serialNo|string|t(:spotLtSerialNo)|


### t(:ltRecord)
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
            "ltCode": "BTC3L",
            "orderId": "1049",
            "orderType": 1,
            "orderTime": "1650253091000",
            "excTime": "1650253107000",
            "orderStatus": "1",
            "fee": "0",
            "amount": "9.44245991",
            "value": "85.50095708",
            "valueCoin": "USDT",
            "serialNo": "0a65e240165025309566610041"
        }
    ]
}
``` 

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=ltRecord>/spot/lt/v1/record</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ltRecord"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|ltCode|<b>false</b>|string|t(:spotLtCode)|
|orderId|<b>false</b>|long|t(:spotLtOrderId)|
|timestamp|<b>true</b>|long|t(:spot_timestamp)|
|startTime|<b>false</b>|long|t(:spotLtStartTime)|
|endTime|<b>false</b>|long|t(:spotLtEndTime)|
|limit|<b>false</b>|int|t(:row_comment_limit_100_500)|
|t(:row_parameter_ltOrderType)|<b>false</b>|int|t(:spotLtOrderType)|
|serialNo|<b>false</b>|string|t(:spotLtSerialNo)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|ltCode|string|t(:spotResLtCode)|
|orderId|string|t(:spotLtOrderId)|
|t(:row_parameter_ltOrderType)|int|t(:spotLtOrderType)|
|orderTime|string|t(:spotResOrderTime)|
|excTime|string|t(:spotResExcTime)|
|t(:row_parameter_ltOrderStatus)|string|t(:spotResOrderStatus)|
|fee|string|t(:spotResFee)|
|amount|string|t(:spotResOrderQuantity)|
|value|string|t(:spotResRecordValue)|
|valueCoin|string|t(:spotResValueCoin)|
|serialNo|string|t(:spotLtSerialNo)|
