# t(:etp)
t(:etp_para)

### t(:etpInfo)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/spot/etp/v1/info \
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
      "purchaseFeeRate": "0.12345678",
      "redeemFeeRate": "0.12345678",
      "etpStatus": "1",
      "fundFeeRate": "0.12345678",
      "fundFeeTime": 1620917160000,
      "manageFeeRate": "-0.12345678",
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
<code><span id=sevInfo>/spot/etp/v1/info</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sevInfo"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|etpCode|<b>true</b>|string|t(:spotEtpCode)|


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
|purchaseFeeRate|string|t(:spotResPurchaseFee)|
|redeemFeeRate|string|t(:spotResRedeemFee)|
|t(:row_parameter_etpStatus)|int|t(:spotResEtpStatus)|
|fundFeeRate|string|t(:spotResFundFee)|
|fundFeeTime|long|t(:spotResFundFeeTime)|
|manageFeeRate|string|t(:spotResManageFee)|
|manageFeeTime|string|t(:spotResManageFeeTime)|
|circulation|string|t(:spotResCirculation)|
|value|string|t(:spotResValue)|
|total|string|t(:spotResTotal)|
|netValue|string|t(:spotResNetValue)|

### t(:etpPurchase)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/spot/etp/v1/purchase \
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
<code><span id=sevPurchase>/spot/etp/v1/purchase</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sevPurchase"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|etpCode|<b>true</b>|string|t(:spotEtpCode)|
|etpAmount|<b>true</b>|number|t(:spotEtpAmount)|
|serialNo|<b>true</b>|string|t(:spotEtpSerialNo)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|etpCode|string|t(:spotResEtpCode)|
|t(:row_parameter_etpOrderStatus)|int|t(:spotResOrderStatus)|
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
curl https://api-testnet.bybit.com/spot/etp/v1/redeem \
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
<code><span id=sevRedeem>/spot/etp/v1/redeem</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sevRedeem"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|etpCode|<b>true</b>|string|t(:spotEtpCode)|
|etpQuantity|<b>true</b>|number|t(:spotEtpQuantity)|
|serialNo|<b>true</b>|string|t(:spotEtpSerialNo)|


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|etpCode|string|t(:spotResEtpCode)|
|t(:row_parameter_etpOrderStatus)|int|t(:spotResOrderStatus)|
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
<code><span id=sevRecord>/spot/etp/v1/record</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sevRecord"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|etpCode|false|string|t(:spotEtpCode)|
|orderId|false|long|t(:spotEtpOrderId)|
|startTime|false|long|t(:spotEtpStartTime)|
|endTime|false|long|t(:spotEtpEndTime)|
|limit|false|int|t(:row_comment_limit_100_500)|
|t(:row_parameter_etpOrderType)|false|int|t(:spotEtpOrderType)|
|serialNo|false|string|t(:spotEtpSerialNo)|

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|etpCode|string|t(:spotResEtpCode)|
|orderId|string|t(:spotEtpOrderId)|
|t(:row_parameter_etpOrderType)|int|t(:spotEtpOrderType)|
|orderTime|long|t(:spotResOrderTime)|
|excTime|long|t(:spotResExcTime)|
|t(:row_parameter_etpOrderStatus)|int|t(:spotResStatus)|
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

t(:etpQuoteReference_para)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=sevReference>/spot/etp/v1/reference</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sevReference"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

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
