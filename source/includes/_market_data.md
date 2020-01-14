# Market Data Endpoints
The following market data endpoints do not require authentication.

### Server Time
> Response Example

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {},
    "time_now": "1577444332.192859"
}
```

Get Bybit server time.

##### HTTP Request
GET
<code><span id=vpTime>/v2/public/time</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpTime"><img src="images/copy_to_clipboard.png" height=15 width=15></a></button>

##### Request Parameters
|parameter|required|type|comments|
|:----- |:-------|:-----|----- |


### Orderbook
> Response Example

```javascript
{
    "ret_code": 0,                              // return code
    "ret_msg": "OK",                            // error message
    "ext_code": "",                             // additional error code
    "ext_info": "",                             // additional error info
    "result": [
        {
            "symbol": "BTCUSD",                 // symbol
            "price": "9487",                    // price
            "size": 336241,                     // size (in USD contracts)
            "side": "Buy"                       // side
        },
        {
            "symbol": "BTCUSD",                 // symbol
            "price": "9487.5",                  // price
            "size": 522147,                     // size (in USD contracts)
            "side": "Sell"                      // side
        }
    ],
    "time_now": "1567108756.834357"             // UTC timestamp
}
```

Get the orderbook.

<aside class="notice">
The response is in the snapshot format.
</aside>

##### HTTP Request
GET
<code><span id=vpoL2>/v2/public/orderBook/L2</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoL2"><img src="images/copy_to_clipboard.png" height=15 width=15></a></button>

##### Request Parameters
|parameters|required|type|comments|
|:----- |:-------|:-----|----- |
|<a href="#enums-definitions-symbol-symbol">symbol</a> |true |string |Contract type |


### Latest Information for Symbol
> Response Example

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": [
        {
            "symbol": "BTCUSD",
            "bid_price": "7230",
            "ask_price": "7230.5",
            "last_price": "7230.00",
            "last_tick_direction": "ZeroMinusTick",
            "prev_price_24h": "7163.00",
            "price_24h_pcnt": "0.009353",
            "high_price_24h": "7267.50",
            "low_price_24h": "7067.00",
            "prev_price_1h": "7209.50",
            "price_1h_pcnt": "0.002843",
            "mark_price": "7230.31",
            "index_price": "7230.14",
            "open_interest": 117860186,
            "open_value": "16157.26",
            "total_turnover": "3412874.21",
            "turnover_24h": "10864.63",
            "total_volume": 28291403954,
            "volume_24h": 78053288,
            "funding_rate": "0.0001",
            "predicted_funding_rate": "0.0001",
            "next_funding_time": "2019-12-28T00:00:00Z",
            "countdown_hour": 2
        }
    ],
    "time_now": "1577484619.817968"
}
```

Get the latest information for symbol.

##### HTTP Request
GET
<code><span id=vpTickers>/v2/public/tickers</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpTickers"><img src="images/copy_to_clipboard.png" height=15 width=15></a></button>

##### Request Parameters
|parameters|required|type|comments|
|:----- |:-------|:-----|----- |
|<a href="#enums-definitions-symbol-symbol">symbol</a> |false |string |Contract type |


### Public Trading Records
> Response Example

```javascript
{
    "ret_code": 0,                                   // error code 0 means success
    "ret_msg": "OK",                                 // error message
    "ext_code": "",
    "ext_info": "",
    "result": [
        {
            "id": 7724919,                                   // ID
            "symbol": "BTCUSD",                             // contract type
            "price": 9499.5,                                // execution price
            "qty": 9500,                                    // execution quantity
            "side": "Buy",                                  // side
            "time": "2019-11-19T08:03:04.077Z"              // UTC time
        }
    ],
    "time_now": "1567109419.049271"
}
```

Get recent trades.

##### HTTP Request
GET
<code><span id=vpTradingRecords>/v2/public/trading-records</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpTradingRecords"><img src="images/copy_to_clipboard.png" height=15 width=15></a></button>

##### Request Parameters
|parameters|required|type|comments|
|:----- |:-------|:-----|----- |
|<a href="#enums-definitions-symbol-symbol">symbol</a> |true |string |Contract type |
|from |false |int |From ID. Default: return latest data|
|limit |false |int |Number of results. Default 500; max 1000|


### Get the Last Funding Rate
> Response Example

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": {
        "symbol": "BTCUSD",
        "funding_rate": "0.00010000",
        "funding_rate_timestamp": 1577433600
    },
    "ext_info": null,
    "time_now": "1577445586.446797",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1577445586454,
    "rate_limit": 120
}
```

The funding rate is generated every 8 hours at 00:00 UTC, 08:00 UTC and 16:00 UTC. For example, if a request is sent at 12:00 UTC, the funding rate generated earlier that day at 08:00 UTC will be sent.

##### HTTP Request
GET
<code><span id=oafPrevFundingRate>/open-api/funding/prev-funding-rate</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oafPrevFundingRate"><img src="images/copy_to_clipboard.png" height=15 width=15></a></button>

##### Request Parameters
|parameter|required|type|comments|
|:----- |:-------|:-----|----- |
|<a href="#enums-definitions-symbol-symbol">symbol</a> |true |string |Contract type    |


### Query Symbol
> Response Example

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {},
    "time_now": "1577444332.192859"
}
```

Get symbol info.

##### HTTP Request
GET
<code><span id=vpSymbols>/v2/public/symbols</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpSymbols"><img src="images/copy_to_clipboard.png" height=15 width=15></a></button>

##### Request Parameters
|parameter|required|type|comments|
|:----- |:-------|:-----|----- |
