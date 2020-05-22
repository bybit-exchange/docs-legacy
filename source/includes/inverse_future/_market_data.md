# t(:marketdata)
t(:market_para_auth)

### t(:orderbook)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/v2/public/orderBook/L2?symbol=BTCUSD
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

### t(:querykline)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/v2/public/kline/list?symbol=BTCUSD&interval=1&limit=2&from=1581231260
```

> t(:codequote_responseExample)

```javascript
{
	"ret_code": 0,
	"ret_msg": "OK",
	"ext_code": "",
	"ext_info": "",
	"result": [{
		"symbol": "BTCUSD",
		"interval": "1",
		"open_time": 1581231300,
		"open": "10112.5",
		"high": "10112.5",
		"low": "10112",
		"close": "10112",
		"volume": "75981",
		"turnover": "7.51394369"
	}, {
		"symbol": "BTCUSD",
		"interval": "1",
		"open_time": 1581231360,
		"open": "10112",
		"high": "10112.5",
		"low": "10112",
		"close": "10112",
		"volume": "24616",
		"turnover": "2.4343353100000003"
	}],
	"time_now": "1581928016.558522"
}
```

t(:market_para_querykline)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpkList>/v2/public/kline/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpkList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
|interval |true |string |t(:row_comment_interval) |
|from |true |integer |t(:row_comment_from_timestamp) |
|limit |false |integer |t(:row_comment_limit_200) |

### t(:latestsymbolinfo)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/v2/public/tickers
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


### t(:publictradingrecords)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/v2/public/trading-records?symbol=BTCUSD
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

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpTradingRecords>/v2/public/trading-records</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpTradingRecords"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
|from |false |int |t(:row_comment_from)|
|limit |false |int |Number of results. Default 500; max 1000|


### t(:querysymbol)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/v2/public/symbols
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
      "name": "BTCUSD",
      "base_currency": "BTC",
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
        "min_trading_qty": 1,
        "qty_step": 1
      }
    },
    {
      "name": "ETHUSD",
      "base_currency": "ETH",
      "quote_currency": "USD",
      "price_scale": 2,
      "taker_fee": "0.00075",
      "maker_fee": "-0.00025",
      "leverage_filter": {
        "min_leverage": 1,
        "max_leverage": 50,
        "leverage_step": "0.01"
      },
      "price_filter": {
        "min_price": "0.05",
        "max_price": "99999.95",
        "tick_size": "0.05"
      },
      "lot_size_filter": {
        "max_trading_qty": 1000000,
        "min_trading_qty": 1,
        "qty_step": 1
      }
    },
    {
      "name": "EOSUSD",
      "base_currency": "EOS",
      "quote_currency": "USD",
      "price_scale": 3,
      "taker_fee": "0.00075",
      "maker_fee": "-0.00025",
      "leverage_filter": {
        "min_leverage": 1,
        "max_leverage": 50,
        "leverage_step": "0.01"
      },
      "price_filter": {
        "min_price": "0.001",
        "max_price": "1999.999",
        "tick_size": "0.001"
      },
      "lot_size_filter": {
        "max_trading_qty": 1000000,
        "min_trading_qty": 1,
        "qty_step": 1
      }
    },
    {
      "name": "XRPUSD",
      "base_currency": "XRP",
      "quote_currency": "USD",
      "price_scale": 4,
      "taker_fee": "0.00075",
      "maker_fee": "-0.00025",
      "leverage_filter": {
        "min_leverage": 1,
        "max_leverage": 50,
        "leverage_step": "0.01"
      },
      "price_filter": {
        "min_price": "0.0001",
        "max_price": "199.9999",
        "tick_size": "0.0001"
      },
      "lot_size_filter": {
        "max_trading_qty": 1000000,
        "min_trading_qty": 1,
        "qty_step": 1
      }
    }
  ],
  "time_now": "1581411225.414179"
}
```

t(:market_para_querySymbol)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpSymbols>/v2/public/symbols</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpSymbols"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |


### t(:query_liqrecords)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/v2/public/liq-records?symbol=BTCUSD&limit=1&start_time=1589979415000
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code":0,
    "ret_msg":"OK",
    "ext_code":"",
    "ext_info":"",
    "result":[
        {
            "id":2369683,
            "qty":155,
            "side":"Buy",
            "time":1590030126798,
            "symbol":"BTCUSD",
            "price":9444
        }
    ],
    "time_now":"1590068362.493540"
}
```
t(:market_para_query_liqrecords)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpkLiq>/v2/public/liq-records</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpkLiq"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
|from |false |integer |t(:row_comment_from) |
|limit |false |integer |t(:row_comment_limit_liq) |
|start_time |false |integer |t(:row_comment_startTime_ms) |
|end_time |false |integer |t(:row_comment_endTime_ms) |
