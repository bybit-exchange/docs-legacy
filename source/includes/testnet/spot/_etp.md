# t(:lt)
<aside class="notice">
t(:lt_notice)
</aside>

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
      "ltCode": "btc3l",
      "ltName": "BTC*3",
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
<code><span id=vpoCreate>/spot/lt/v1/info</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

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
|status|string|t(:spotResLtStatus)|
|fundFee|string|t(:spotResFundFee)|
|fundFeeTime|long|t(:spotResFundFeeTime)|
|manageFeeRate|string|t(:spotResManageFee)|
|manageFeeTime|string|t(:spotResManageFeeTime)|
|value|string|t(:spotResValue)|
|total|string|t(:spotResTotal)|
|netValue|string|t(:spotResNetValue)|

<aside class="notice">
t(:lt_para)
</aside>

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
        "valueCoin": "usdt"
    },
    "ext_code": null,
    "ext_info": null
}
``` 

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/spot/lt/v1/purchase</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

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
|orderStatus|string|t(:spotResOrderStatus)|
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
      "etpCode": "BTC3L",
      "orderStatus": "1",
      "quantity": "12",
      "orderQuantity": "123.12345678",
      "orderAmount": "123.12345678",
      "timestamp": 1620917160000,
      "id": 1,
      "valueCoin": "usdt"
  },
  "ext_code": null, 
  "ext_info": null
}
``` 

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/spot/lt/v1/redeem</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

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
|orderStatus|string|t(:spotResOrderStatus)|
|quantity|string|t(:spotResRedeemQuantity)|
|orderQuantity|string|t(:spotResRedeemOrderQuantity)|
|orderAmount|string|t(:spotResRedeemOrderAmount)|
|timestamp|long|t(:spot_timestamp)|
|id|long|t(:spotResId)|
|valueCoin|string|t(:spotResValueCoin)|
|serialNo|string|t(:spotEtpSerialNo)|


### t(:etpRecord)
> t(:codequote_curlExample)


> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": null,
    "result":
    [
      {
        "etpCode": "btc3l",
        "orderId": 1,
        "orderType": 1,
        "orderTime": 1620917160000,
        "excTime": 1620917160000,
        "orderStatus": "1",
        "fee": "0.12345678",
        "amount": "12.12345678",
        "value": "12.12345678",
        "valueCoin": "usdt"
      }
    ],
    "ext_code": null,
    "ext_info": null
}
``` 

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpoCreate>/spot/etp/v1/record</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|etpCode|<b>false</b>|string|t(:spotEtpCode)|
|orderId|<b>false</b>|long|t(:spotEtpOrderId)|
|timestamp|<b>true</b>|long|t(:spot_timestamp)|
|startTime|<b>false</b>|long|t(:spotEtpStartTime)|
|endTime|<b>false</b>|long|t(:spotEtpEndTime)|
|limit|<b>false</b>|int|t(:row_comment_limit_100_500)|
|orderType|<b>false</b>|int|t(:spotEtpOrderType)|
|serialNo|<b>false</b>|string|t(:spotEtpSerialNo)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|etpCode|string|t(:spotResEtpCode)|
|orderId|string|t(:spotEtpOrderId)|
|orderType|int|t(:spotEtpOrderType)|
|orderTime|long|t(:spotResOrderTime)|
|excTime|long|t(:spotResExcTime)|
|orderStatus|string|t(:spotResStatus)|
|fee|string|t(:spotResFee)|
|amount|string|t(:spotResAmount)|
|value|string|t(:spotResRecordValue)|
|valueCoin|string|t(:spotResValueCoin)|
|serialNo|string|t(:spotEtpSerialNo)|


### t(:etpQuoteReference)
> t(:codequote_curlExample)

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": null,
    "result": {
      "etpCode": "btc3lusdtnav",
      "nav": "12.12345678",
      "navTime": 1620917160000,
      "leverage": "2.12345678",
      "basket": "122222.12345678"
  },
  "ext_code": null,
  "ext_info": null
}
``` 

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpoCreate>/spot/etp/v1/reference</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|etpCode|<b>true</b>|string|t(:spotEtpCode)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|etpCode|string|t(:spotResEtpCode)|
|nav|string|t(:spotEtpQuoteNav)|
|navTime|long|t(:spotEtpQuoteNavTime)|
|basket|string|t(:spotEtpQuoteBasket)|
|leverage|string|t(:spotLeverage)|
