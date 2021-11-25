# t(:etp)
t(:etp_para)

### t(:etpInfo)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/spot/v1/etp/info \
-H "Content-Type: application/x-www-form-urlencoded" \
-d 'api_key={api_key}&etpCode={etpCode}&timestamp=1637669364000'
```

> t(:codequote_responseExample)

```javascript
{
  "ret_code": 0,
    "ret_msg": null,
    "result": {
      "etpCode": "btc3l",
      "etpName": "BTC*3",
      "maxPurchase": "300024.12345678",
      "minPurchase": "0.12345678",
      "maxPurchaseDaily": "500000.12345678",
      "maxRedeem": "1000.12345678",
      "minRedeem": "1.12345678",
      "maxRedeemDaily": "1000002.12345678",
      "purchaseFee": "0.12345678",
      "redeemFee": "0.12345678",
      "etpStatus": "1",
      "fundFee": "0.12345678",
      "fundFeeTime": 1620917160000,
      "manageFee": "-0.12345678",
      "manageFeeTime": 1620917160000,
      "circulation": "3124234233.12345678",
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
<code><span id=vpoCreate>/spot/v1/etp/info</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|etpCode|<b>true</b>|string|t(:spotEtpCode)|
|timestamp|<b>false</b>|number|t(:spot_timestamp)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|etpCode|string|t(:spotResEtpCode)|
|etpName|string|t(:spotResEtpName)|
|maxPurchase|string|t(:spotResMaxPurchase)|
|minPurchase|string|t(:spotResMinPurchase)|
|maxPurchaseDaily|string|t(:spotResMaxPurchaseDaily)|
|maxRedeem|string|t(:spotResMaxRedeem)|
|minRedeem|string|t(:spotResMinRedeem)|
|maxRedeemDaily|string|t(:spotResMaxRedeemDaily)|
|purchaseFee|string|t(:spotResPurchaseFee)|
|redeemFee|string|t(:spotResRedeemFee)|
|etpStatus|int|t(:spotResEtpStatus)|
|fundFee|string|t(:spotResFundFee)|
|fundFeeTime|long|t(:spotResFundFeeTime)|
|manageFee|string|t(:spotResManageFee)|
|manageFeeTime|string|t(:spotResManageFeeTime)|
|circulation|string|t(:spotResCirculation)|
|value|string|t(:spotResValue)|
|total|string|t(:spotResTotal)|
|netValue|string|t(:spotResNetValue)|

### t(:etpPurchase)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/spot/v1/etp/purchase \
-H "Content-Type: application/x-www-form-urlencoded" \
-d 'api_key={api_key}&etpCode={etpCode}&etpAmount={etpAmount}&serialNo={serialNo}&timestamp=1637669364000'
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": null,
    "result": {
        "etpCode": "btc3l",
        "orderStatus": 1,
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
<code><span id=vpoCreate>/spot/v1/etp/purchase</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|etpCode|<b>true</b>|string|t(:spotEtpCode)|
|etpAmount|<b>true</b>|number|t(:spotEtpAmount)|
|timestamp|<b>true</b>|number|t(:spot_timestamp)|
|serialNo|<b>true</b>|string|t(:spotEtpSerialNo)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|etpCode|string|t(:spotResEtpCode)|
|orderStatus|int|t(:spotResOrderStatus)|
|orderQuantity|string|t(:spotResOrderQuantity)|
|orderAmount|string|t(:spotResOrderAmount)|
|amount|string|t(:spotResAmount)|
|timestamp|long|t(:spot_timestamp)|
|id|long|t(:spotResId)|
|valueCoin|string|t(:spotResValueCoin)|
|serialNo|string|t(:spotEtpSerialNo)|


### t(:etpRedeem)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/spot/v1/etp/redeem \
-H "Content-Type: application/x-www-form-urlencoded" \
-d 'api_key={api_key}&etpCode={etpCode}&etpQuantity={etpQuantity}&serialNo={serialNo}&timestamp=1637669364000'
```

> t(:codequote_responseExample)

```javascript
{
  "ret_code": 0,
    "ret_msg": null,
    "result": {
      "etpCode": "btc3l",
      "orderStatus": 1,
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
<code><span id=vpoCreate>/spot/v1/etp/redeem</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|etpCode|<b>true</b>|string|t(:spotEtpCode)|
|etpQuantity|<b>true</b>|number|t(:spotEtpQuantity)|
|timestamp|<b>true</b>|number|t(:spot_timestamp)|
|serialNo|<b>true</b>|string|t(:spotEtpSerialNo)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|etpCode|string|t(:spotResEtpCode)|
|orderStatus|int|t(:spotResOrderStatus)|
|quantity|string|t(:spotEtpQuantity)|
|orderQuantity|string|t(:spotResOrderQuantity)|
|orderAmount|string|t(:spotResOrderAmount)|
|amount|string|t(:spotResAmount)|
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
        "status": 1,
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
<code><span id=vpoCreate>/spot/v1/etp/record</span></code>
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
|status|int|t(:spotResStatus)|
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
    "symbol": "btc3lusdtnav",
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
<code><span id=vpoCreate>/spot/quote/v1/etp/reference</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol|<b>true</b>|string|t(:spotSymbol)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|symbol|string|t(:spotSymbol)|
|nav|string|t(:spotEtpQuoteNav)|
|navTime|long|t(:spotEtpQuoteNavTime)|
|basket|string|t(:spotEtpQuoteBasket)|
|leverage|string|t(:spotLeverage)|
