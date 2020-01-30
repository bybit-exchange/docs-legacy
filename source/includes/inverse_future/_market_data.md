# t(:market_heading)
t(:market_para_auth)

### t(:market_heading_time)
> t(:codequote_responseExample)

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

##### t(:heading_http_request)
GET
<code><span id=vpTime>/v2/public/time</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpTime"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |


### t(:market_heading_orderbook)
> t(:codequote_responseExample)

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

t(:market_para_orderbook)

<aside class="notice">
t(:market_aside_orderbook)
</aside>

##### t(:heading_http_request)
GET
<code><span id=vpoL2>/v2/public/orderBook/L2</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoL2"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |


### t(:market_heading_symbol)
> t(:codequote_responseExample)

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

##### t(:heading_http_request)
GET
<code><span id=vpTickers>/v2/public/tickers</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpTickers"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |false |string |t(:row_comment_symbol) |


### t(:market_heading_records)
> t(:codequote_responseExample)

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

t(:market_para_records)

##### t(:heading_http_request)
GET
<code><span id=vpTradingRecords>/v2/public/trading-records</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpTradingRecords"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
|from |false |int |t(:row_comment_from)|
|limit |false |int |Number of results. Default 500; max 1000|


### t(:market_heading_fundingRate)
> t(:codequote_responseExample)

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

t(:market_para_fundingRate)

##### t(:heading_http_request)
GET
<code><span id=oafPrevFundingRate>/open-api/funding/prev-funding-rate</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oafPrevFundingRate"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol)    |


### t(:market_heading_querySymbol)
> t(:codequote_responseExample)

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

t(:market_para_querySymbol)

##### t(:heading_http_request)
GET
<code><span id=vpSymbols>/v2/public/symbols</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpSymbols"><img src="/images/copy_to_clipboard.png" height=15 width=15></a></button>

##### t(:heading_request_parameters)
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
