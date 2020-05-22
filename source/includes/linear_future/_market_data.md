# t(:marketdata)
t(:market_para_auth)

### t(:orderbook)
<a href="/docs/inverse#t-orderbook">t(:shared_endpoint_desc)</a>

### t(:querykline)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/public/linear/kline?symbol=BTCUSDT&interval=1&limit=2&from=1581231260
```

> t(:codequote_responseExample)

```javascript
{
	"ret_code": 0,
	"ret_msg": "OK",
	"ext_code": "",
	"ext_info": "",
	"result": [{
	    "id": 3866948,
        "symbol": "BTCUSDT",
        "period": "1",
        "start_at": 1577836800,
        "volume": 1451.59,
        "open": 7700,
        "high": 999999,
        "low": 0.5,
        "close": 6000
	},
	{
	    "id": 3866948,
        "symbol": "BTCUSDT",
        "period": "1",
        "start_at": 1577836800, // t(:comment_abandoned)
        "volume": 1451.59,
        "open": 7700,           // t(:comment_abandoned)
        "high": 999999,
        "low": 0.5,
        "close": 6000,
        "interval": 1,
        "open_time": 1577836800,
        "turnover": 2.4343353100000003,
	}],
	"time_now": "1581928016.558522"
}
```

t(:linear_market_para_querykline)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpSymbols>/public/linear/kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpSymbols"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
|interval |true |string |t(:row_comment_interval) |
|from |true |integer |t(:row_comment_from_timestamp) |
|limit |false |integer |t(:linear_kline_row_comment_limit_200) |






### t(:latestsymbolinfo)
<a href="/docs/inverse#t-latestsymbolinfo">t(:shared_endpoint_desc)</a>






### t(:publictradingrecords)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/public/linear/recent-trading-records?symbol=BTCUSDT&limit=500
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,                                   // error code 0 means success
    "ret_msg": "OK",                                 // error message
    "ext_code": "",
    "ext_info": "",
    "result": [
        {
            "id": "18368131384",                            // ID, string type, all ids are in descending order globally
            "symbol": "BTCUSDT",                            // contract type
            "price": 9499.5,                                // execution price
            "qty": 9500,                                    // execution quantity
            "side": "Buy",                                  // side
            "time": "2019-11-19T08:03:04.077Z",             // t(:comment_abandoned)
            "trade_time_ms":1587638305175
        }
    ],
    "time_now": "1567109419.049271"
}
```

t(:market_para_records)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpRecentTradingRecords>/public/linear/recent-trading-records</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpRecentTradingRecords"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
|limit |false |int |t(:linear_row_comment_recent_trading_records_limit)|




### t(:querysymbol)
<a href="/docs/inverse#t-querysymbol">t(:shared_endpoint_desc)</a>

### t(:query_liqrecords)
<a href="/docs/inverse#t-query_liqrecords">t(:shared_endpoint_desc)</a>

### t(:fundingrate)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/public/linear/funding/prev-funding-rate?symbol=BTCUSDT
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code":0,
    "ret_msg":"OK",
    "ext_code":"",
    "ext_info":"",
    "result":{
        "symbol":"BTCUSDT",
        "funding_rate":-0.00005965,
        "funding_rate_timestamp":"2020-04-07T08:00:00.000Z"
    },
    "time_now":"1586251109.454281"
}
```

t(:market_para_fundingRate)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpPreFundingRate>/public/linear/funding/prev-funding-rate</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpPreFundingRate"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |













### t(:markpricekline)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/public/linear/mark-price-kline?symbol=BTCUSDT&interval=1&limit=2&from=1581231260
```

> t(:codequote_responseExample)

```javascript
{
	"ret_code": 0,
	"ret_msg": "OK",
	"ext_code": "",
	"ext_info": "",
	"result": [{
	    "id": 3866948,
        "symbol": "BTCUSDT",
        "period": "1",
        "start_at": 1577836800,
        "volume": 1451.59,
        "open": 7700,
        "high": 999999,
        "low": 0.5,
        "close": 6000
	},
	{
	    "id": 3866948,
        "symbol": "BTCUSDT",
        "period": "1",
        "start_at": 1577836800,
        "volume": 1451.59,
        "open": 7700,
        "high": 999999,
        "low": 0.5,
        "close": 6000
	}],
	"time_now": "1581928016.558522"
}
```

t(:linear_query_mark_price_kline)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=plmpk>/public/linear/mark-price-kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#plmpk"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
|interval |true |string |t(:row_comment_interval) |
|from |true |integer |t(:row_comment_from_timestamp) |
|limit |false |integer |t(:linear_kline_row_comment_limit_200) |
















<!--
### t(:orderbook)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/public/orderBook/L2?symbol=BTCUSD
```

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

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpoL2>/v2/public/orderBook/L2</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoL2"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |



























### t(:latestsymbolinfo)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/public/tickers
```

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

t(:market_para_symbol)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpTickers>/v2/public/tickers</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpTickers"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |false |string |t(:row_comment_symbol) |
-->











<!--
### t(:querysymbol)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/public/linear/symbols
```

> t(:codequote_responseExample)

```javascript
{
"ret_code": 0,
"ret_msg": "OK",
"ext_code": "",
"ext_info": "",
"result": [
    {
        "name": "BTCUSDT",
        "base_currency": "USDT",
        "quote_currency": "USD",
        "price_scale": 2,
        "taker_fee": "0.00075",
        "maker_fee": "-0.00025",
        "leverage_filter": {
            "min_leverage": 1,
            "max_leverage": 100,
            "leverage_step": "0.01"
        },
        "price_filter": {
            "min_price": "0.5",
            "max_price": "999999.5",
            "tick_size": "0.5"
        },
        "lot_size_filter": {
            "max_trading_qty": 1000000,
            "min_trading_qty": 0.001,
            "qty_step": 0.001
        }
    }
],
"time_now": "1586780484.438405"
}
```

t(:market_para_querySymbol)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpSymbols>/public/linear/symbols</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpSymbols"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
-->
