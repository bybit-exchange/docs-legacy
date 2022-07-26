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

| t(:column_parameter) | t(:column_type) | t(:column_comments)              |
|:---------------------|:----------------|----------------------------------|
| name                 | string          | 币对名称                             |
| alias                | string          | 币对别名                             |
| baseCoin             | string          | base币种                           |
| quoteCoin            | string          | quote币种                          |
| basePrecision        | string          | base币种精度                         |
| quotePrecision       | string          | quote币种精度                        |
| minTradeQty          | string          | 最小订单数量(对市价买单无效)                  |
| minTradeAmt          | string          | 最小订单额(只对市价买单有效)                  |
| minPricePrecision    | string          | 最小价格精度                           |
| maxTradeQty          | string          | 最大成交量（当您下订单类型为LIMIT_MAKER 时将被忽略） |
| maxTradeAmt          | string          | 最大成交额（当您下订单类型为LIMIT_MAKER 时将被忽略） |
| category             | string          | symbol 所在分区:1主类别                 |
| innovation           | string          | 0=创新区，这个币种价格波动比较大 1=非创新区         |
| showStatus           | string          | 0=开放交易，1=未开放交易                   |


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
        "side": "BUY",
        "orderCategory": 0
    },
  "time":1234567
}
```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=svPostOrder>/spot/v3/private/order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svPostOrder"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

| t(:column_parameter) | t(:column_required) | t(:column_type) | t(:column_comments)                                                                                            |
|:---------------------|:--------------------|:----------------|----------------------------------------------------------------------------------------------------------------|
| symbol               | true                | string          | 交易对                                                                                                            |
| orderQty             | true                | string          | 交易数量（市价买单即type=Market且side=Buy时orderQty指的是quote currency；比如BTCUSDT的orderQty指的是USDT的数量, 而非市价买单时orderQty指向都是BTC） |
| side                 | true                | string          | 方向（BUY/SELL）                                                                                                   |
| orderType            | true                | string          | 订单类型（LIMIT/MARKET/LIMIT_MAKER）                                                                                 |
| timeInForce          | false               | string          | 执行策略                                                                                                           |
| orderPrice           | false               | string          | 订单价格（type字段为MARKET时，orderPrice字段为非必须；type字段为LIMIT、LIMIT_MAKER时，orderPrice字段为必须）                                |
| orderLinkId          | false               | string          | 特殊订单ID，用户自己生成                                                                                                  |
| orderCategory        | false               | int             | 订单种类（0=普通订单，1=止盈止损），默认0                                                                                        |
| triggerPrice         | false               | string          | 触发价格，当orderCategory=1时必传                                                                                       |

<p class="fake_header">t(:responseparameters)</p>

| t(:column_parameter) | t(:column_type) | t(:column_comments)                                                                                                                                                                                                 |
|:---------------------|:----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| orderId              | string          | 订单ID                                                                                                                                                                                                                |
| orderLinkId          | string          | 特殊订单ID，用户自己生成                                                                                                                                                                                                       |
| symbol               | string          | 交易对                                                                                                                                                                                                                 |
| createTime           | string          | 订单创建时间                                                                                                                                                                                                              |
| orderPrice           | string          | 订单价格                                                                                                                                                                                                                |
| orderQty             | string          | 交易数量                                                                                                                                                                                                                |
| orderType            | string          | 订单类型                                                                                                                                                                                                                |
| side                 | string          | 方向（BUY/SELL）                                                                                                                                                                                                        |
| status               | string          | 订单状态。订单种类为普通订单时，可能出现的值为NEW（新订单，无成交）、PARTIALLY_FILLED（部分成交）、FILLED（全部成交）、CANCELED（已取消）、REJECTED（被拒绝）；订单种类为止盈止损时，可能出现的值为ORDER_NEW（新订单）、ORDER_FILLED（已触发订单）、ORDER_CANCELED（已取消）、ORDER_REJECTED（被拒绝）、ORDER_FAILED（触发失败） |
| timeInForce          | string          | 执行策略                                                                                                                                                                                                                |
| accountId            | string          | 账户ID                                                                                                                                                                                                                |
| execQty              | string          | 忽略                                                                                                                                                                                                                  |
| orderCategory        | string          | 订单种类（0=普通订单，1=止盈止损）                                                                                                                                                                                                 |
| triggerPrice         | string          | 触发价格                                                                                                                                                                                                                |


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
        "locked": "0",
        "executedOrderId": 1204354919958703361,
        "triggerPrice": "4940.83",
        "orderCategory": 1
    },
     "time":1234567
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=svGetOrder>/spot/v3/private/order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svGetOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

| t(:column_parameter) | t(:column_required) | t(:column_type)  | t(:column_comments)     |
|:---------------------|:--------------------|:-----------------|-------------------------|
| orderId              | false               | string           | 如果不传orderLinkId，则为必传    |
| orderLinkId          | false               | string           | 如果不传orderLinkId，则为必传    |
| orderCategory        | false               | int              | 订单种类（0=普通订单，1=止盈止损），默认0 |

<p class="fake_header">t(:responseparameters)</p>

| t(:column_parameter) | t(:column_type) | t(:column_comments)                                                                                                                                                                                                 |
|:---------------------|:----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| accountId            | string          | 账户ID                                                                                                                                                                                                                |
| symbol               | string          | 交易对                                                                                                                                                                                                                 |
| orderLinkId          | string          | 特殊订单ID，用户自己生成                                                                                                                                                                                                       |
| orderId              | string          | 订单ID                                                                                                                                                                                                                |
| orderPrice           | string          | 订单价格                                                                                                                                                                                                                |
| orderQty             | string          | 交易数量                                                                                                                                                                                                                |
| execQty              | string          | 成交数量                                                                                                                                                                                                                |
| cummulativeQuoteQty  | string          | 对于某些历史数据cummulativeQuoteQty<0,说明数据当前不可用                                                                                                                                                                             |
| avgPrice             | string          | 平均成交价                                                                                                                                                                                                               |
| status               | string          | 订单状态。订单种类为普通订单时，可能出现的值为NEW（新订单，无成交）、PARTIALLY_FILLED（部分成交）、FILLED（全部成交）、CANCELED（已取消）、REJECTED（被拒绝）；订单种类为止盈止损时，可能出现的值为ORDER_NEW（新订单）、ORDER_FILLED（已触发订单）、ORDER_CANCELED（已取消）、ORDER_REJECTED（被拒绝）、ORDER_FAILED（触发失败） |
| timeInForce          | string          | 执行策略                                                                                                                                                                                                                |
| orderType            | string          | 订单类型                                                                                                                                                                                                                |
| side                 | string          | 方向（BUY/SELL）                                                                                                                                                                                                        |
| stopPrice            | string          | 停止价                                                                                                                                                                                                                 |
| icebergQty           | string          | 忽略                                                                                                                                                                                                                  |
| createTime           | string          | 撮合引擎中的创建时间                                                                                                                                                                                                          |
| updateTime           | string          | 更新时间                                                                                                                                                                                                                |
| isWorking            | string          | 是否生效（0=未生效，1=已生效）                                                                                                                                                                                                   |
| locked               | string          | 锁定数量（如果为0，则说明该笔订单的资金已完成结算）                                                                                                                                                                                          |
| orderCategory        | string          | 订单种类（0=普通订单，1=止盈止损）                                                                                                                                                                                                 |
| triggerPrice         | string          | 触发价格                                                                                                                                                                                                                |
| executedOrderId      | string          | 触发订单编号                                                                                                                                                                                                              |


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

| t(:column_parameter) | t(:column_required) | t(:column_type) | t(:column_comments)     |
|:---------------------|:--------------------|:----------------|-------------------------|
| orderId              | false               | string          | 如果不传orderLinkId，则为必传    |
| orderLinkId          | false               | string          | 如果不传orderLinkId，则为必传    |
| orderCategory        | false               | int             | 订单种类（0=普通订单，1=止盈止损），默认0 |

<p class="fake_header">t(:responseparameters)</p>

| t(:column_parameter)  | t(:column_type) | t(:column_comments)                                                                                                                                                                                                 |
|:----------------------|:----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| orderId               | string          | 订单ID                                                                                                                                                                                                                |
| orderLinkId           | string          | 特殊订单ID，用户自己生成                                                                                                                                                                                                       |
| symbol                | string          | 交易对                                                                                                                                                                                                                 |
| status                | string          | 订单状态。订单种类为普通订单时，可能出现的值为NEW（新订单，无成交）、PARTIALLY_FILLED（部分成交）、FILLED（全部成交）、CANCELED（已取消）、REJECTED（被拒绝）；订单种类为止盈止损时，可能出现的值为ORDER_NEW（新订单）、ORDER_FILLED（已触发订单）、ORDER_CANCELED（已取消）、ORDER_REJECTED（被拒绝）、ORDER_FAILED（触发失败） |
| accountId             | string          | 账户ID                                                                                                                                                                                                                |
| orderPrice            | string          | 订单创建时间                                                                                                                                                                                                              |
| createTime            | string          | 订单价格                                                                                                                                                                                                                |
| orderQty              | string          | 交易数量                                                                                                                                                                                                                |
| execQty               | string          | 成交数量                                                                                                                                                                                                                |
| timeInForce           | string          | 执行策略                                                                                                                                                                                                                |
| orderType             | string          | 订单类型                                                                                                                                                                                                                |
| side                  | string          | 方向（BUY/SELL）                                                                                                                                                                                                        |
| orderCategory         | string          | 订单种类（0=普通订单，1=止盈止损）                                                                                                                                                                                                 |
| triggerPrice          | string          | 触发价格                                                                                                                                                                                                                |


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

| t(:column_parameter)  | t(:column_required) | t(:column_type) | t(:column_comments)                               |
|:----------------------|:--------------------|:----------------|---------------------------------------------------|
| symbol                | true                | string          | 交易对                                               |
| side                  | false               | string          | 订单方向（BUY/SELL）                                    |
| orderTypes            | false               | string          | 订单类型。多个订单类型使用英文逗号分隔，例如LIMIT,LIMIT_MAKER.默认真：LIMIT |
| orderCategory         | false               | int             | 订单种类（0=普通订单，1=止盈止损），默认0                           |

<p class="fake_header">t(:responseparameters)</p>

| t(:column_parameter) | t(:column_type) | t(:column_comments) |
|:---------------------|:----------------|---------------------|
| success              | string          | 是否成功(0=不成功、1=成功)    |


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

| t(:column_parameter)  | t(:column_required) | t(:column_type) | t(:column_comments)        |
|:----------------------|:--------------------|:----------------|----------------------------|
| orderIds              | true                | string          | 订单号，可用英文逗号拼接表示多个订单，不超过100个 |
| orderCategory         | false               | int             | 订单种类（0=普通订单，1=止盈止损），默认0    |

<p class="fake_header">t(:responseparameters)</p>

| t(:column_parameter)  | t(:column_type) | t(:column_comments) |
|:----------------------|:----------------|---------------------|
| orderId               | string          | 订单ID                |
| code                  | string          | 错误码                 |


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
            "isWorking": "1",
            "executedOrderId": "1204354919958703361",
            "triggerPrice": "4940.83",
            "orderCategory": 1
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

| t(:column_parameter) | t(:column_required) | t(:column_type) | t(:column_comments)                |
|:---------------------|:--------------------|:----------------|------------------------------------|
| symbol               | false               | string          | 交易对                                |
| orderId              | false               | string          | 通过指定orderId返回比这个orderId小的订单，可以用来分页 |
| limit                | false               | string          | 默认500，最大500                        |
| orderCategory        | false               | int             | 订单种类（0=普通订单，1=止盈止损），默认0            |


<p class="fake_header">t(:responseparameters)</p>

| t(:column_parameter) | t(:column_type) | t(:column_comments)                                                                                                                                                                                                  |
|:---------------------|:----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| accountId            | string          | 账户ID                                                                                                                                                                                                                 |
| symbol               | string          | 交易对                                                                                                                                                                                                                  |
| orderLinkId          | string          | 特殊订单ID，用户自己生成                                                                                                                                                                                                        |
| orderId              | string          | 订单ID                                                                                                                                                                                                                 |
| orderPrice           | string          | 订单价格                                                                                                                                                                                                                 |
| orderQty             | string          | 交易数量                                                                                                                                                                                                                 |
| execQty              | string          | 成交数量                                                                                                                                                                                                                 |
| cummulativeQuoteQty  | string          | 对于某些历史数据cummulativeQuoteQty<0,说明数据当前不可用                                                                                                                                                                              |
| avgPrice             | string          | 平均成交价                                                                                                                                                                                                                |
| status               | string          | 订单状态。订单种类为普通订单时，可能出现的值为NEW（新订单，无成交）、PARTIALLY_FILLED（部分成交）、FILLED（全部成交）、CANCELED（已取消）、REJECTED（被拒绝）；订单种类为止盈止损时，可能出现的值为ORDER_NEW（新订单）、ORDER_FILLED（已触发订单）、ORDER_CANCELED（已取消）、ORDER_REJECTED（被拒绝）、ORDER_FAILED（触发失败）  |
| timeInForce          | string          | 执行策略                                                                                                                                                                                                                 |
| orderType            | string          | 订单类型                                                                                                                                                                                                                 |
| side                 | string          | 方向（BUY/SELL）                                                                                                                                                                                                         |
| stopPrice            | string          | 停止价                                                                                                                                                                                                                  |
| icebergQty           | string          | 忽略                                                                                                                                                                                                                   |
| createTime           | string          | 撮合引擎中的创建时间                                                                                                                                                                                                           |
| updateTime           | string          | 更新时间                                                                                                                                                                                                                 |
| isWorking            | string          | 是否生效（0=未生效，1=已生效）                                                                                                                                                                                                    |
| orderCategory        | string          | 订单种类（0=普通订单，1=止盈止损）                                                                                                                                                                                                  |
| triggerPrice         | string          | 触发价格                                                                                                                                                                                                                 |
| executedOrderId      | string          | 触发订单编号                                                                                                                                                                                                               |


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

| t(:column_parameter) | t(:column_required) | t(:column_type) | t(:column_comments)                |
|:---------------------|:--------------------|:----------------|------------------------------------|
| symbol               | false               | string          | 交易对                                |
| orderId              | false               | string          | 通过指定orderId返回比这个orderId小的订单，可以用来分页 |
| limit                | false               | string          | 默认500，最大500                        |
| startTime            | false               | int             | 开始时间                               |
| endTime              | false               | int             | 开始时间                               |
| orderCategory        | false               | int             | 订单种类（0=普通订单，1=止盈止损），默认0            |


<p class="fake_header">t(:responseparameters)</p>

| t(:column_parameter) | t(:column_type) | t(:column_comments)                                                                                                                                                                                                 |
|:---------------------|:----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| accountId            | string          | 账户ID                                                                                                                                                                                                                |
| symbol               | string          | 交易对                                                                                                                                                                                                                 |
| orderLinkId          | string          | 特殊订单ID，用户自己生成                                                                                                                                                                                                       |
| orderId              | string          | 订单ID                                                                                                                                                                                                                |
| orderPrice           | string          | 订单价格                                                                                                                                                                                                                |
| orderQty             | string          | 交易数量                                                                                                                                                                                                                |
| execQty              | string          | 成交数量                                                                                                                                                                                                                |
| cummulativeQuoteQty  | string          | 对于某些历史数据cummulativeQuoteQty<0,说明数据当前不可用                                                                                                                                                                             |
| avgPrice             | string          | 平均成交价                                                                                                                                                                                                               |
| status               | string          | 订单状态。订单种类为普通订单时，可能出现的值为NEW（新订单，无成交）、PARTIALLY_FILLED（部分成交）、FILLED（全部成交）、CANCELED（已取消）、REJECTED（被拒绝）；订单种类为止盈止损时，可能出现的值为ORDER_NEW（新订单）、ORDER_FILLED（已触发订单）、ORDER_CANCELED（已取消）、ORDER_REJECTED（被拒绝）、ORDER_FAILED（触发失败） |
| timeInForce          | string          | 执行策略                                                                                                                                                                                                                |
| orderType            | string          | 订单类型                                                                                                                                                                                                                |
| side                 | string          | 方向（BUY/SELL）                                                                                                                                                                                                        |
| stopPrice            | string          | 停止价                                                                                                                                                                                                                 |
| icebergQty           | string          | 忽略                                                                                                                                                                                                                  |
| createTime           | string          | 撮合引擎中的创建时间                                                                                                                                                                                                          |
| updateTime           | string          | 更新时间                                                                                                                                                                                                                |
| isWorking            | string          | 是否生效（0=未生效，1=已生效）                                                                                                                                                                                                   |
| orderCategory        | string          | 订单种类（0=普通订单，1=止盈止损）                                                                                                                                                                                                 |
| triggerPrice         | string          | 触发价格                                                                                                                                                                                                                |
| executedOrderId      | string          | 触发订单编号                                                                                                                                                                                                              |


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

| t(:column_parameter) | t(:column_required) | t(:column_type) | t(:column_comments)                     |
|:---------------------|:--------------------|:----------------|-----------------------------------------|
| symbol               | false               | string          | 交易对                                     |
| orderId              | false               | string          | 通过指定orderId返回比这个orderId小的订单，可以用来分页      |
| limit                | false               | string          | 默认50，最大50                               |
| startTime            | false               | int             | 开始时间                                    |
| endTime              | false               | int             | 开始时间                                    |
| fromTradeId          | false               | string          | 从大于此trade ID开始查询（fromTicketId<trade ID） |
| toTradeId            | false               | string          | 从小于次trade ID为终点（trade ID<toTicketId）    |

<p class="fake_header">t(:responseparameters)</p>

| t(:column_parameter)  | t(:column_type) | t(:column_comments)                                                                                                                                                                                                 |
|:----------------------|:----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| symbol                | string          | 交易对                                                                                                                                                                                                                 |
| id                    | string          | 账户ID                                                                                                                                                                                                                |
| orderId               | string          | 订单ID                                                                                                                                                                                                                |
| tradeId               | string          | 订单ID                                                                                                                                                                                                                |
| orderPrice            | string          | 订单价格                                                                                                                                                                                                                |
| orderQty              | string          | 交易数量                                                                                                                                                                                                                |
| execFee               | string          | 成交数量                                                                                                                                                                                                                |
| feeTokenId            | string          | 对于某些历史数据cummulativeQuoteQty<0,说明数据当前不可用                                                                                                                                                                             |
| creatTime             | string          | 平均成交价                                                                                                                                                                                                               |
| isBuyer               | string          | 订单状态。订单种类为普通订单时，可能出现的值为NEW（新订单，无成交）、PARTIALLY_FILLED（部分成交）、FILLED（全部成交）、CANCELED（已取消）、REJECTED（被拒绝）；订单种类为止盈止损时，可能出现的值为ORDER_NEW（新订单）、ORDER_FILLED（已触发订单）、ORDER_CANCELED（已取消）、ORDER_REJECTED（被拒绝）、ORDER_FAILED（触发失败） |
| isMaker               | string          | 执行策略                                                                                                                                                                                                                |
| matchOrderId          | string          | 订单类型                                                                                                                                                                                                                |
| makerRebate           | string          | 方向（BUY/SELL）                                                                                                                                                                                                        |
| executionTime         | int             | 停止价                                                                                                                                                                                                                 |
