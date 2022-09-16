# t(:accountdata)
t(:account_para)


### t(:placeactive)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/spot/v3/private/order' \
--header 'X-BAPI-SIGN: cc63fb44be4a87f4b7bbd42db012ddacc1c935c3d3ae3e01c3b4be393522c213' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1659067662307' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'X-BAPI-SIGN: cc63fb44be4a87f4b7bbd42db012ddacc1c935c3d3ae3e01c3b4be393522c213' \
--header 'Content-Type: application/json' \
--data-raw '{
    "symbol": "BTCUSDT",
    "orderQty":"0.01",
    "side": "Buy",
    "orderType": "LIMIT",
    "timeInForce": "GTC",
    "orderPrice": "21300",
    "orderLinkId": "spotx006",
    "orderCategory": 1,
    "triggerPrice": "21700"
}'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "orderId": "1230969397479298560",
        "orderLinkId": "spotx006",
        "symbol": "BTCUSDT",
        "createTime": "1661478987332",
        "orderPrice": "21300",
        "orderQty": "0.01",
        "orderType": "LIMIT",
        "side": "BUY",
        "status": "ORDER_NEW",
        "timeInForce": "GTC",
        "accountId": "554118",
        "orderCategory": 1,
        "triggerPrice": "21700"
    },
    "retExtMap": {},
    "retExtInfo": null,
    "time": 1661478987364
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=svPlaceOrder>/spot/v3/private/order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svPlaceOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
| t(:column_parameter) | t(:column_required) | t(:column_type) | t(:column_comments)         |
|:---------------------|:--------------------|:----------------|-----------------------------|
| symbol               | <b>true</b>         | string          | t(:spotSymbol)              |
| orderQty             | <b>true</b>         | string          | t(:spotQtyPlaceOrder)       |
| side                 | <b>true</b>         | string          | t(:spotV3_comment_side)     |
| orderType            | <b>true</b>         | string          | t(:spotOrderType)           |
| <a href="#time-in-force-time_in_force">timeInForce</a>| false               | string          | t(:row_comment_timeInForce) |
| orderPrice           | false               | string          | t(:spotPostOrderPrice)      |
| orderLinkId          | false               | string          | t(:spotOrderLinkId)         |
| orderCategory        | false               | int             | t(:spotv3_orderCategory)         |
| triggerPrice         | false               | string          | t(:spotv3_triggerPrice)         |


<p class="fake_header">t(:responseparameters)</p>
| t(:column_parameter) | t(:column_type) | t(:column_comments)         |
|:---------------------|:----------------|-----------------------------|
| orderId              | string          | t(:spotOrderId)             |
| orderLinkId          | string          | t(:spotOrderLinkId)         |
| symbol               | string          | t(:spotSymbol)              |
| createTime           | string          | t(:spotTransactTime)        |
| orderPrice           | string          | t(:spotPrice)               |
| orderQty             | string          | t(:spotOriQty)              |
| orderType            | string          | t(:spotOrderType)           |
| side                 | string          | t(:spotV3_comment_side)     |
| status               | string          | t(:spotStatus)              |
| timeInForce          | string          | t(:row_comment_timeInForce) |
| accountId            | string          | t(:spotAccountId)           |
| execQty              | string          | t(:spotExecQty)             |
| orderCategory        | int             | t(:spotv3_orderCategory)    |
| triggerPrice         | string          | t(:spotv3_triggerPrice)     |


### t(:getactive)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/private/order?orderLinkId=spotA0010' \
--header 'X-BAPI-SIGN: 828571067751622ed4191e7e8ee913defccd1f099b9dfb8332a6a05edf799eaf' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1659076396894' \
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
        "accountId": "533287",
        "symbol": "BTCUSDT",
        "orderLinkId": "spotA0010",
        "orderId": "1210810256551063296",
        "orderPrice": "23500",
        "orderQty": "0.01",
        "execQty": "0",
        "cummulativeQuoteQty": "0",
        "avgPrice": "0",
        "status": "NEW",
        "timeInForce": "GTC",
        "orderType": "LIMIT",
        "side": "SELL",
        "stopPrice": "0.0",
        "icebergQty": "0.0",
        "createTime": "1659075830464",
        "updateTime": "1659075830497",
        "isWorking": "1",
        "locked": "0.01"
    },
    "retExtMap": {},
    "retExtInfo": {},
    "time": 1659076397365
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=svGetOrder>/spot/v3/private/order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svGetOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

| t(:column_parameter) | t(:column_required) | t(:column_type)  | t(:column_comments)                             |
|:---------------------|:--------------------|:-----------------|-------------------------------------------------|
| orderId              | false               | string           | t(:spotV3_comment_orderId) |
| orderLinkId          | false               | string           | t(:spotV3_comment_orderLinkId) |

<p class="fake_header">t(:responseparameters)</p>

| t(:column_parameter) | t(:column_type) | t(:column_comments)         |
|:---------------------|:----------------|-----------------------------|
| accountId            | string          | t(:spotAccountId)           |
| symbol               | string          | t(:spotSymbol)              |
| orderLinkId          | string          | t(:spotOrderLinkId)         |
| orderId              | string          | t(:spotOrderId)             |
| orderPrice           | string          | t(:spotOPrice)              |
| orderQty             | string          | t(:spotOriQty)              |
| execQty              | string          | t(:spotExecQty2)            |
| cummulativeQuoteQty  | string          | t(:spotV3_comment_cummulativeQuoteQty) |
| avgPrice             | string          | t(:spotAvgPrice)            |
| status               | string          | t(:spotStatus)              |
| timeInForce          | string          | t(:row_comment_timeInForce) |
| orderType            | string          | t(:spotOrderType)           |
| side                 | string          | t(:spotSide)                |
| stopPrice            | string          | t(:spotStopPrice)           |
| icebergQty           | string          | t(:spotIcebergQty)          |
| createTime           | string          | t(:spotTime)                |
| updateTime           | string          | t(:spotUpdateTime)          |
| isWorking            | string          | t(:spotV3_comment_isWorking)|
| locked               | string          | t(:spotOrderLocked)         |


### t(:cancelactive)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/spot/v3/private/cancel-order' \
--header 'X-BAPI-SIGN: 2cdc75a6be90f2a3d70875595c289b6342ff55021a26d9fecf988a8f78266ccc' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1659078017415' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "orderId": "1210810256551063296",
    "orderLinkId": null
}'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "orderId": "1210810256551063296",
        "orderLinkId": "spotA0010",
        "symbol": "BTCUSDT",
        "status": "CANCELED",
        "accountId": "533287",
        "createTime": "1659075830464",
        "orderPrice": "23500",
        "orderQty": "0.01",
        "execQty": "0",
        "timeInForce": "GTC",
        "orderType": "LIMIT",
        "side": "SELL"
    },
    "retExtMap": {},
    "retExtInfo": {},
    "time": 1659078151226
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=svDeleteOrder>/spot/v3/private/cancel-order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svDeleteOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
| t(:column_parameter) | t(:column_required) | t(:column_type) | t(:column_comments) |
|:---------------------|:--------------------|:----------------|--------------------------  |
| orderId              | false               | string          | t(:spotV3_comment_orderId) |
| orderLinkId          | false               | string          | t(:spotV3_comment_orderLinkId) |

<p class="fake_header">t(:responseparameters)</p>
| t(:column_parameter)  | t(:column_type) | t(:column_comments)         |
|:----------------------|:----------------|-----------------------------|
| orderId               | string          | t(:spotOrderId)             |
| orderLinkId           | string          | t(:spotOrderLinkId)         |
| symbol                | string          | t(:spotSymbol)              |
| status                | string          | t(:spotStatus)              |
| accountId             | string          | t(:spotAccountId)           |
| orderPrice            | string          | t(:spotOPrice)              |
| createTime            | string          | t(:spotTransactTime)        |
| orderQty              | string          | t(:spotOriQty)              |
| execQty               | string          | t(:spotExecQty2)            |
| timeInForce           | string          | t(:row_comment_timeInForce) |
| orderType             | string          | t(:spotOrderType)           |
| side                  | string          | t(:spotV3_comment_side)     |


### t(:batchcancelactiveorder)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/spot/v3/private/cancel-orders' \
--header 'X-BAPI-SIGN: bd24c37216d90bd76214a7e22638e6a0bc9d8f7ec74218e79c3f6f90e8c56b8e' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1659078150737' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "symbol": "BTCUSDT",
    "side": "Buy",
    "orderTypes": "LIMIT,LIMIT_MAKER"
}'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "success": "1"
    },
    "retExtInfo": {},
    "time": 1659080154042
}
```

[//]: # (<aside class="notice">)

[//]: # (t&#40;:spotCancelTips&#41;)

[//]: # (</aside>)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=soBatchCancel>/spot/v3/private/cancel-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#soBatchCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
| t(:column_parameter)  | t(:column_required) | t(:column_type) | t(:column_comments) |
|:----------------------|:--------------------|:----------------|---------------------|
| symbol                | <b>true</b>         | string          | t(:spotSymbol)      |
| side                  | false               | string          | t(:spotV3_comment_side) |
| orderTypes            | false               | string          | t(:spotV3_comment_orderTypes) |

<p class="fake_header">t(:responseparameters)</p>
| t(:column_parameter) | t(:column_type) | t(:column_comments)  |
|:---------------------|:----------------|----------------------|
| success              | string          | t(:spotV3_comment_success)     |


### t(:batchcancelactiveorderbyids)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api-testnet.bybit.com/spot/v3/private/cancel-orders-by-ids' \
--header 'X-BAPI-SIGN: 84cc9b260300c2fd8b378e8acd1254902b341e4c3ea3a462c7440265245a52e8' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1659080877551' \
--header 'X-BAPI-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "orderIds": "1210851823244553984,1210852013162639104"
}'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "OK",
    "result": {
        "list": []
    },
    "retExtInfo": {},
    "time": 1659080815222
}

// Response for failing to cancel 1 or more orders

{
    "retCode": 0,
    "retMsg": "",
    "result": {
          "list":[
        {
          "orderId": "889208273689997824",
          "code": "1139"
        }
    ]
  },
  "time":1234567
}
```

[//]: # (<aside class="notice">)

[//]: # (t&#40;:spotNormalCancelTips&#41;)

[//]: # (</aside>)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=soBatchCancelIds>/spot/v3/private/cancel-orders-by-ids</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#soBatchCancelIds"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

| t(:column_parameter)  | t(:column_required) | t(:column_type) | t(:column_comments)         |
|:----------------------|:--------------------|:----------------|-----------------------------|
| orderIds              | <b>true</b>         | string          | t(:spotCancelOrderIds)      |

<p class="fake_header">t(:responseparameters)</p>

| t(:column_parameter) | t(:column_type) | t(:column_comments) |
|:---------------------|:----------------|---------------------|
| list> orderId        | string          | t(:spotOrderId)     |
| list> code           | string          | t(:errors)          |


### t(:openorders)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/private/open-orders?symbol=BTCUSDT' \
--header 'X-BAPI-SIGN: e28768ea749013bbd0eb38edf78e1cac187d3018e4807859a84a37cf52feb5c0' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1659081676022' \
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
                "accountId": "533287",
                "symbol": "BTCUSDT",
                "orderLinkId": "spotx004",
                "orderId": "1210858291884732160",
                "orderPrice": "23500",
                "orderQty": "0.02",
                "execQty": "0",
                "cummulativeQuoteQty": "0",
                "avgPrice": "0",
                "status": "NEW",
                "timeInForce": "GTC",
                "orderType": "LIMIT_MAKER",
                "side": "SELL",
                "stopPrice": "0.0",
                "icebergQty": "0.0",
                "createTime": 1659081556722,
                "updateTime": 1659081556740,
                "isWorking": "1"
            }
        ]
    },
    "retExtInfo": {},
    "time": 1659081570356
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=svOpenOrders>/spot/v3/private/open-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svOpenOrders"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
| t(:column_parameter) | t(:column_required) | t(:column_type) | t(:column_comments)          |
|:---------------------|:--------------------|:----------------|------------------------------|
| symbol               | false               | string          | t(:spotSymbol)               |
| orderId              | false               | string          | t(:spotOrderId4Pagination)   |
| limit                | false               | string          | t(:spot_order_list_limit)    |


<p class="fake_header">t(:responseparameters)</p>
| t(:column_parameter) | t(:column_type) | t(:column_comments)         |
|:---------------------|:----------------|-----------------------------|
| accountId            | string          | t(:spotAccountId)           |
| symbol               | string          | t(:spotSymbol)              |
| orderLinkId          | string          | t(:spotOrderLinkId)         |
| orderId              | string          | t(:spotOrderId)             |
| orderPrice           | string          | t(:spotOPrice)              |
| orderQty             | string          | t(:spotOriQty)              |
| execQty              | string          | t(:spotExecQty2)            |
| cummulativeQuoteQty  | string          | t(:spotV3_comment_cummulativeQuoteQty) |
| avgPrice             | string          | t(:spotAvgPrice)            |
| status               | string          | t(:spotStatus)              |
| timeInForce          | string          | t(:row_comment_timeInForce) |
| orderType            | string          | t(:spotOrderType)           |
| side                 | string          | t(:spotV3_comment_side)     
| stopPrice            | string          | t(:spotStopPrice)           |
| icebergQty           | string          | t(:spotIcebergQty)          |
| createTime           | string          | t(:spotTime)                |
| updateTime           | string          | t(:spotUpdateTime)          |
| isWorking            | string          | t(:spotV3_comment_isWorking)|


### t(:orderhistory)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/private/history-orders?symbol=BTCUSDT&limit=2&startTime=1658246400000&endTime=1659110400000' \
--header 'X-BAPI-SIGN: 1e18efe3e2c96df191c84d86b8a4d695184ea5fe64aa21062fa15e8464caeca0' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1659082629976' \
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
                "accountId": "533287",
                "symbol": "BTCUSDT",
                "orderLinkId": "spotx003",
                "orderId": "1210856408331857664",
                "orderPrice": "23800",
                "orderQty": "0.02",
                "execQty": "0",
                "cummulativeQuoteQty": "0",
                "avgPrice": "0",
                "status": "REJECTED",
                "timeInForce": "GTC",
                "orderType": "LIMIT_MAKER",
                "side": "BUY",
                "stopPrice": "0.0",
                "icebergQty": "0.0",
                "createTime": 1659081332185,
                "updateTime": 1659081332225,
                "isWorking": "1"
            },
            {
                "accountId": "533287",
                "symbol": "BTCUSDT",
                "orderLinkId": "spotx002",
                "orderId": "1210852013162639104",
                "orderPrice": "23800",
                "orderQty": "0.05",
                "execQty": "0",
                "cummulativeQuoteQty": "0",
                "avgPrice": "0",
                "status": "CANCELED",
                "timeInForce": "GTC",
                "orderType": "LIMIT_MAKER",
                "side": "SELL",
                "stopPrice": "0.0",
                "icebergQty": "0.0",
                "createTime": 1659080808240,
                "updateTime": 1659080815265,
                "isWorking": "1"
            }
        ]
    },
    "retExtInfo": {},
    "time": 1659082630638
}
```

<aside class="notice">
t(:spotOrdersHistoryTips)
</aside>
<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=svHistoryOrders>/spot/v3/private/history-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svHistoryOrders"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
| t(:column_parameter) | t(:column_required) | t(:column_type) | t(:column_comments)        |
|:---------------------|:--------------------|:----------------|----------------------------|
| symbol               | false               | string          | t(:spotSymbol)             |
| orderId              | false               | string          | t(:spotOrderId4Pagination) |
| limit                | false               | integer          | t(:spot_historyOrder_limit)  |
| startTime            | false               | long             | t(:spot_start_time)        |
| endTime              | false               | long             | t(:spot_end_time)          |


<p class="fake_header">t(:responseparameters)</p>
| t(:column_parameter) | t(:column_type) | t(:column_comments)          |
|:---------------------|:----------------|------------------------------|
| accountId            | string          | t(:spotAccountId)            |
| symbol               | string          | t(:spotSymbol)               |
| orderLinkId          | string          | t(:spotOrderLinkId)          |
| orderId              | string          | t(:spotOrderId)              |
| orderPrice           | string          | t(:spotPrice)                |
| orderQty             | string          | t(:spotOriQty)               |
| execQty              | string          | t(:spotExecQty2)             |
| cummulativeQuoteQty  | string          | t(:spotCummulativeQuoteQty)  |
| avgPrice             | string          | t(:spotAvgPrice)             |
| status               | string          | t(:spotStatus)               |
| timeInForce          | string          | t(:row_comment_timeInForce)  |
| orderType            | string          | t(:spotOrderType)            |
| side                 | string          | t(:spotV3_comment_side)      |
| stopPrice            | string          | t(:spotStopPrice)            |
| icebergQty           | string          | t(:spotIcebergQty)           |
| createTime           | string          | t(:spotTime)                 |
| updateTime           | string          | t(:spotUpdateTime)           |
| isWorking            | string          | t(:spotV3_comment_isWorking) |


### t(:tradehistory)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api-testnet.bybit.com/spot/v3/private/my-trades?symbol=BTCUSDT' \
--header 'X-BAPI-SIGN: 9f1c84cfd13cb470d4f0ffb2463f30bf19fe2c0079d0ee5e42c7ca9d0441876d' \
--header 'X-BAPI-API-KEY: {api key}' \
--header 'X-BAPI-TIMESTAMP: 1659084253772' \
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
                "symbol": "BTCUSDT",
                "id": "1210346127973428992",
                "orderId": "1210073515485572864",
                "tradeId": "2100000000001769786",
                "orderPrice": "20500",
                "orderQty": "0.02",
                "execFee": "0.00002",
                "feeTokenId": "BTC",
                "creatTime": "1659020488738",
                "isBuyer": "0",
                "isMaker": "0",
                "matchOrderId": "1210346015893229312",
                "makerRebate": "0",
                "executionTime": "1659020502026"
            },
            {
                "symbol": "BTCUSDT",
                "id": "1208702504949264128",
                "orderId": "1208702504731160320",
                "tradeId": "2100000000001753197",
                "orderPrice": "20240",
                "orderQty": "0.009881",
                "execFee": "0.000009881",
                "feeTokenId": "BTC",
                "creatTime": "1658824566874",
                "isBuyer": "0",
                "isMaker": "1",
                "matchOrderId": "1208677465155702529",
                "makerRebate": "0",
                "executionTime": "1658824566893"
            }
        ]
    },
    "retExtMap": {},
    "retExtInfo": {},
    "time": 1659084254366
}
```

<aside class="notice">
t(:spotTradesHistoryTips)
</aside>

<aside class="notice">
t(:spotTradesHisotryTips_order)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=svMyTrades>/spot/v3/private/my-trades</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svMyTrades"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
| t(:column_parameter) | t(:column_required) | t(:column_type) | t(:column_comments)           |
|:---------------------|:--------------------|:----------------|-------------------------------|
| symbol               | false               | string          | t(:spotSymbol)                |
| orderId              | false               | string          | t(:spotOrderId)               |
| limit                | false               | string          | t(:spot_trades_history_limit) |
| startTime            | false               | int             | t(:spot_start_time)           |
| endTime              | false               | int             | t(:spot_end_time)             |
| fromTradeId          | false               | string          | t(:spot_from_id)              |
| toTradeId            | false               | string          | t(:spot_to_id)                |


<p class="fake_header">t(:responseparameters)</p>
| t(:column_parameter)  | t(:column_type) | t(:column_comments)   |
|:----------------------|:----------------|-----------------------|
| symbol                | string          | t(:spotSymbol)        |
| id                    | string          | t(:spotId)            |
| orderId               | string          | t(:spotOrderId)      |
| tradeId               | string          | t(:spotTradeId)       |
| orderPrice            | string          | t(:spotPrice)         |
| orderQty              | string          | t(:spotQty)           |
| execFee               | string          | t(:spot_fee)          |
| feeTokenId            | string          | t(:spotFeeTokenId)    |
| creatTime             | string          | t(:spotTime)          |
| isBuyer               | string          | t(:spotV3_comment_isBuyer)|
| isMaker               | string          | t(:spotV3_comment_isMaker)|
| matchOrderId          | string          | t(:spot_match_order_id) |
| makerRebate           | string          | t(:spotMakerRebate)   |
| executionTime         | string          | t(:spotExecutionTime) |
