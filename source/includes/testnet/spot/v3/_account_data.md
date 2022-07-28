# t(:accountdata)
t(:account_para)

### t(:getsymbols)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/spot/v3/public/symbols \
-H "Content-Type: application/x-www-form-urlencoded" \
-d 'api_key={api_key}&timestamp={timestamp}&sign={signature}'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "ok",
    "result": {
         "list":[
          {
            "name": "BTCUSDT",
            "alias": "BTCUSDT",
            "baseCurrency": "BTC",
            "quoteCurrency": "USDT",
            "basePrecision": "0.000001",
            "quotePrecision": "0.01",
            "minTradeQty": "0.0001",
            "minTradeAmt": "10",
            "minPricePrecision": "0.01",
            "maxTradeQty": "2",
            "maxTradeAmot": "200",
            "category": 1,
            "innovation": false,
            "showStatus": true
        },
        {
            "name": "ETHUSDT",
            "alias": "ETHUSDT",
            "baseCurrency": "ETH",
            "quoteCurrency": "USDT",
            "basePrecision": "0.0001",
            "quotePrecision": "0.01",
            "minTradeQty": "0.0001",
            "minTradeAmt": "10",
            "minPricePrecision": "0.01",
            "maxTradeQty": "2",
            "maxTradeAmt": "200",
            "category": "1",
            "innovation": "1",
            "showStatus": "1"
        }
    ]
  },
  "time":1234567
}
```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=svPostOrder>/spot/v3/public/symbols</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svPostOrder"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

| t(:column_parameter) | t(:column_required) | t(:column_type) | t(:column_comments) |
|:---------------------|:--------------------|:----------------|---------------------|

<p class="fake_header">t(:responseparameters)</p>

| t(:column_parameter) | t(:column_type) | t(:column_comments)       |
|:---------------------|:----------------|---------------------------|
| name                 | string          | t(:spotSymbol)            |
| alias                | string          | t(:spot_Alias)            |
| baseCoin             | string          | t(:spotBaseCurrency)      |
| quoteCoin            | string          | t(:spotQuoteCurrency)     |
| basePrecision        | string          | t(:spotBasePrecision)     |
| quotePrecision       | string          | t(:spotQuotePrecision)    |
| minTradeQty          | string          | t(:spotMinTradeQuantity)  |
| minTradeAmt          | string          | t(:spotMinTradeAmount)    |
| minPricePrecision    | string          | t(:spotMinPricePrecision) |
| maxTradeQty          | string          | t(:spotmaxTradeQuantity)  |
| maxTradeAmt          | string          | t(:spotmaxTradeAmount)    |
| category             | string          | t(:spotCategory)          |
| innovation           | string          | t(:spotInnovation)        |
| showStatus           | string          | t(:spotshowStatus)        |


### t(:placeactive)
> t(:codequote_curlExample)

```console
curl -X POST https://api-testnet.bybit.com/spot/v3/private/order \
-H "Content-Type: application/x-www-form-urlencoded" \
-d 'api_key={api_key}&timestamp={timestamp}&sign={signature}'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg":"OK",
    "result": {
        "accountId": "434792",
        "symbol": "BTCUSDT",
        "orderLinkId": "1655716296020435",
        "orderId": "1182628439163741184",
        "createTime": 1655716296035,
        "orderPrice": "0",
        "orderQty": "100",
        "execQty Qty": "0",
        "status": "NEW",
        "timeInForce": "GTC",
        "orderType": "MARKET",
        "side": "BUY"
    },
  "time":1234567
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=svPostOrder>/spot/v3/private/order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svPostOrder"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

| t(:column_parameter) | t(:column_required) | t(:column_type) | t(:column_comments)         |
|:---------------------|:--------------------|:----------------|-----------------------------|
| symbol               | true                | string          | t(:spotSymbol)              |
| orderQty             | true                | string          | t(:spotQtyPlaceOrder)       |
| side                 | true                | string          | t(:spotSide)                |
| orderType            | true                | string          | t(:spotOrderType)           |
| timeInForce          | false               | string          | t(:row_comment_timeInForce) |
| orderPrice           | false               | string          | t(:spotPostOrderPrice)      |
| orderLinkId          | false               | string          | t(:spotOrderLinkId)         |


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
| side                 | string          | t(:spotSide)                |
| status               | string          | t(:spotStatus)              |
| timeInForce          | string          | t(:row_comment_timeInForce) |
| accountId            | string          | t(:spotAccountId)           |
| execQty              | string          | t(:spotExecQty)             |


### t(:getactive)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/spot/v3/private/order \
-H "Content-Type: application/x-www-form-urlencoded" \
-d 'api_key={api_key}&timestamp={timestamp}&sign={signature}'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "ok",
    "result": {
        "accountId": "533287",
        "symbol": "DOGEUSDT",
        "orderLinkId": "spotDOGE0003",
        "orderId": "1180228509291857152",
        "orderPrice": "0",
        "orderQty": "15",
        "execQty": "25.4",
        "cummulativeQuoteQty": "14.9606",
        "avgPrice": "0.589",
        "status": "ORDER_NEW",
        "timeInForce": "GTC",
        "orderType": "MARKET",
        "side": "BUY",
        "stopPrice": "0.0",
        "icebergQty": "0.0",
        "createTime": 1655430202103,
        "updateTime": 1655430202331,
        "isWorking": "0",
        "locked": "0"
    },
     "time":1234567
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=svGetOrder>/spot/v3/private/order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svGetOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

| t(:column_parameter) | t(:column_required) | t(:column_type)  | t(:column_comments)                             |
|:---------------------|:--------------------|:-----------------|-------------------------------------------------|
| orderId              | false               | string           | t(:misc_row_comment_orderIdNotOrderLinkId_spot) |
| orderLinkId          | false               | string           | t(:misc_row_comment_orderLinkIdNotOrderId_spot) |

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
| cummulativeQuoteQty  | string          | t(:spotCummulativeQuoteQty) |
| avgPrice             | string          | t(:spotAvgPrice)            |
| status               | string          | t(:spotStatus)              |
| timeInForce          | string          | t(:row_comment_timeInForce) |
| orderType            | string          | t(:spotOrderType)           |
| side                 | string          | t(:spotSide)                |
| stopPrice            | string          | t(:spotStopPrice)           |
| icebergQty           | string          | t(:spotIcebergQty)          |
| createTime           | string          | t(:spotTime)                |
| updateTime           | string          | t(:spotUpdateTime)          |
| isWorking            | string          | t(:spotIsWorking)           |
| locked               | string          | t(:spotOrderLocked)         |


### t(:cancelactive)
> t(:codequote_curlExample)

```console
curl -X POST https://api-testnet.bybit.com/spot/v3/private/cancel-order \
-H "Content-Type: application/x-www-form-urlencoded" \
-d 'api_key={api_key}&timestamp={timestamp}&sign={signature}'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "",
    "result": {
        "accountId": "10054",
        "symbol": "ETHUSDT",
        "orderLinkId": "162081160171552",
        "orderId": "889826641228952064",
        "createTime": 1620811601728,
        "orderPrice": "20000",
        "orderQty": "10",
        "execQty": "0",
        "status": "CANCELED",
        "timeInForce": "GTC",
        "orderType": "LIMIT",
        "side": "BUY"
    },
    "time":1234567
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=svDeleteOrder>/spot/v3/private/cancel-order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svDeleteOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

| t(:column_parameter) | t(:column_required) | t(:column_type) | t(:column_comments)                             |
|:---------------------|:--------------------|:----------------|-------------------------------------------------|
| orderId              | false               | string          | t(:misc_row_comment_orderIdNotOrderLinkId_spot) |
| orderLinkId          | false               | string          | t(:misc_row_comment_orderLinkIdNotOrderId_spot) |

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
| side                  | string          | t(:spotSide)                |


### t(:batchcancelactiveorder)
> t(:codequote_curlExample)

```console
curl -X POST https://api-testnet.bybit.com/spot/v3/private/cancel-orders \
-H "Content-Type: application/x-www-form-urlencoded" \
-d 'api_key={api_key}&timestamp={timestamp}&sign={signature}'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "ok",
    "result": {
        "success": "0"
    },
    "time":1234567
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
| symbol                | true                | string          | t(:spotSymbol)      |
| side                  | false               | string          | t(:spotSide)        |
| orderTypes            | false               | string          | t(:spotOrderType)   |

<p class="fake_header">t(:responseparameters)</p>

| t(:column_parameter) | t(:column_type) | t(:column_comments)  |
|:---------------------|:----------------|----------------------|
| success              | string          | t(:spot_message)     |


### t(:batchcancelactiveorderbyids)
> t(:codequote_curlExample)

```console
curl -X POST https://api-testnet.bybit.com/spot/v3/private/cancel-orders-by-ids \
-H "Content-Type: application/x-www-form-urlencoded" \
-d 'api_key={api_key}&timestamp={timestamp}&sign={signature}'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
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
| orderIds              | true                | string          | t(:spotCancelOrderIds)      |

<p class="fake_header">t(:responseparameters)</p>

| t(:column_parameter)  | t(:column_type) | t(:column_comments) |
|:----------------------|:----------------|---------------------|
| orderId               | string          | t(:spotOrderId)     |
| code                  | string          | t(:errors)          |


### t(:openorders)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/spot/v3/private/open-orders \
-H "Content-Type: application/x-www-form-urlencoded" \
-d 'api_key={api_key}&timestamp={timestamp}&sign={signature}'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "ok",
    "result": {
        "list":[
        {
            "accountId": "3728885",
            "symbol": "BTCUSDT",
            "orderLinkId": "1231231211322",
            "orderId": "1204354919958703360",
            "orderPrice": "4940.83",
            "orderQty": "0.01",
            "status": "ORDER_NEW",
            "timeInForce": "GTC",
            "orderType": "LIMIT",
            "side": "BUY",
            "stopPrice": "0.0",
            "icebergQty": "0.0",
            "createTime": 1658306294375,
            "updateTime": 1658306294375,
            "isWorking": "1"
        }
    ]
  },
  "time":1234567
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
| cummulativeQuoteQty  | string          | t(:spotCummulativeQuoteQty) |
| avgPrice             | string          | t(:spotAvgPrice)            |
| status               | string          | t(:spotStatus)              |
| timeInForce          | string          | t(:row_comment_timeInForce) |
| orderType            | string          | t(:spotOrderType)           |
| side                 | string          | t(:spotSide)                |
| stopPrice            | string          | t(:spotStopPrice)           |
| icebergQty           | string          | t(:spotIcebergQty)          |
| createTime           | string          | t(:spotTime)                |
| updateTime           | string          | t(:spotUpdateTime)          |
| isWorking            | string          | t(:spotIsWorking)           |


### t(:orderhistory)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/spot/v3/private/history-orders \
-H "Content-Type: application/x-www-form-urlencoded" \
-d 'api_key={api_key}&timestamp={timestamp}&sign={signature}'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "ok",
    "result":{ 
           "list":[
        {
            "accountId": "10054",
            "symbol": "ETHUSDT",
            "orderLinkId": "1620615771764",
            "orderId": "888183901021893120",
            "orderPrice": "5000",
            "orderQty": "1",
            "execQty": "0",
            "cummulativeQuoteQty": "0",
            "avgPrice": "0",
            "status": "CANCELED",
            "timeInForce": "GTC",
            "orderType": "LIMIT",
            "side": "BUY",
            "stopPrice": "0.0",
            "icebergQty": "0.0",
            "createTime": 1620615771836,
            "updateTime": 1620617056334,
            "isWorking": "0"
        }
    ]
  },
  "time":1234567
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
| limit                | false               | string          | t(:spot_order_list_limit)  |
| startTime            | false               | int             | t(:spot_start_time)        |
| endTime              | false               | int             | t(:spot_end_time)          |


<p class="fake_header">t(:responseparameters)</p>

| t(:column_parameter) | t(:column_type) | t(:column_comments)         |
|:---------------------|:----------------|-----------------------------|
| accountId            | string          | t(:spotAccountId)           |
| symbol               | string          | t(:spotSymbol)              |
| orderLinkId          | string          | t(:spotOrderLinkId)         |
| orderId              | string          | t(:spotOrderId)             |
| orderPrice           | string          | t(:spotPrice)               |
| orderQty             | string          | t(:spotOriQty)              |
| execQty              | string          | t(:spotExecQty2)            |
| cummulativeQuoteQty  | string          | t(:spotCummulativeQuoteQty) |
| avgPrice             | string          | t(:spotAvgPrice)            |
| status               | string          | t(:spotStatus)              |
| timeInForce          | string          | t(:row_comment_timeInForce) |
| orderType            | string          | t(:spotOrderType)           |
| side                 | string          | t(:spotSide)                |
| stopPrice            | string          | t(:spotStopPrice)           |
| icebergQty           | string          | t(:spotIcebergQty)          |
| createTime           | string          | t(:spotTime)                |
| updateTime           | string          | t(:spotUpdateTime)          |
| isWorking            | string          | t(:spotIsWorking)           |


### t(:tradehistory)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/spot/v3/private/my-trades \
-H "Content-Type: application/x-www-form-urlencoded" \
-d 'api_key={api_key}&timestamp={timestamp}&sign={signature}'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
    "retCode": 0,
    "retMsg": "",
    "result": {
           "list":[
        {
            "id": "1178938734438029312",
            "symbol": "BTC3SUSDT",
            "orderId": "1178938734052153344",
            "ticketId": "2120000000000690997",
            "matchOrderId": "1178936255335987114",
            "orderPrice": "38.8404",
            "orderQty": "1",
            "execFee": "0.001",
            "feeTokenId": "BTC3S",
            "creatTime": 1655276448918,
            "isBuyer": "0",
            "isMaker": "0",
            "makerRebate": "0",
            "executionTime": 1655276448956
        }
    ]
  },
  "time":1234567
}
```

<aside class="notice">
t(:spotTradesHistoryTips)
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

| t(:column_parameter)  | t(:column_type) | t(:column_comments)     |
|:----------------------|:----------------|-------------------------|
| symbol                | string          | t(:spotSymbol)          |
| id                    | string          | t(:spotId)              |
| orderId               | string          | t(:spotTicketId)        |
| tradeId               | string          | t(:spotTradeId)         |
| orderPrice            | string          | t(:spotPrice)           |
| orderQty              | string          | t(:spotQty)             |
| execFee               | string          | t(:spot_fee)            |
| feeTokenId            | string          | t(:spotFeeTokenId)      |
| creatTime             | string          | t(:spotTime)            |
| isBuyer               | string          | t(:spotIsBuyer)         |
| isMaker               | string          | t(:spotIsMaker)         |
| matchOrderId          | string          | t(:spot_match_order_id) |
| makerRebate           | string          | t(:spotMakerRebate)     |
| executionTime         | int             | t(:spotExecutionTime)   |
