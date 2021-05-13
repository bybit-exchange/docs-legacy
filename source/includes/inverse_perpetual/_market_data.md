# t(:marketdata)
t(:market_para_auth)

### t(:orderbook)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/v2/public/orderBook/L2?symbol=BTCUSD
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Market.Market_orderbook(symbol="BTCUSD").result())
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
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_symbol) |string |t(:row_comment_symbol) |
| price |string |t(:row_comment_resp_price) |
| size |integer |t(:row_comment_resp_size) |
|t(:row_parameter_side) |string |t(:row_comment_side)  |


### t(:querykline)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/v2/public/kline/list?symbol=BTCUSD&interval=1&limit=2&from=1581231260
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Kline.Kline_get(symbol="BTCUSD", interval="m", **{'from':1581231260}).result())
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
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|interval |<b>true</b> |string |t(:row_comment_interval) |
|from |<b>true</b> |integer |t(:row_comment_from_timestamp) |
|limit |false |integer |t(:row_comment_limit_200) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| t(:row_parameter_symbol) |string |t(:row_comment_symbol) |
| interval |string |t(:row_comment_interval) |
| open_time |integer |t(:row_comment_resp_open_time) |
| open |string |t(:row_comment_open) |
| high |string |t(:row_comment_high) |
| low |string |t(:row_comment_low) |
| close |string |t(:row_comment_close) |
| volume |string |t(:row_comment_resp_volume) |
| turnover |string |t(:row_comment_resp_turnover) |

### t(:latestsymbolinfo)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/v2/public/tickers
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Market.Market_symbolInfo().result())
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
            "countdown_hour": 2,
            "delivery_fee_rate": "0",
            "predicted_delivery_price": "0.00",
            "delivery_time": ""
        },
        {
            "symbol": "BTCUSDM21",
            "bid_price": "67895",
            "ask_price": "67895.5",
            "last_price": "67895.50",
            "last_tick_direction": "ZeroPlusTick",
            "prev_price_24h": "68073.00",
            "price_24h_pcnt": "-0.002607",
            "high_price_24h": "69286.50",
            "low_price_24h": "66156.00",
            "prev_price_1h": "68028.50",
            "price_1h_pcnt": "-0.001955",
            "mark_price": "67883.88",
            "index_price": "62687.89",
            "open_interest": 531821673,
            "open_value": "0.00",
            "total_turnover": "85713.36",
            "turnover_24h": "2371.47",
            "total_volume": 5352251354,
            "volume_24h": 160716002,
            "funding_rate": "0",
            "predicted_funding_rate": "0",
            "next_funding_time": "",
            "countdown_hour": 0,
            "delivery_fee_rate": "0.0005",
            "predicted_delivery_price": "0.00",
            "delivery_time": "2021-06-25T08:00:00Z"
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
|t(:row_parameter_symbol) |false |string |t(:row_comment_symbol) |



<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol |string |t(:row_comment_symbol) |
| bid_price |string |t(:row_comment_resp_bid_price) |
| ask_price |string |t(:row_comment_resp_ask_price) |
| last_price |string |t(:row_comment_resp_last_price) |
| last_tick_direction |string |t(:enum_tick_direction) |
| prev_price_24h |string |t(:row_comment_resp_prev_price_24h) |
| price_24h_pcnt |string |t(:row_comment_resp_price_24h_pcnt) |
| high_price_24h |string |t(:row_comment_resp_high_price_24h) |
| low_price_24h |string |t(:row_comment_resp_low_price_24h) |
| prev_price_1h |string |t(:row_comment_resp_prev_price_1h) |
| price_1h_pcnt |string |t(:row_comment_resp_price_1h_pcnt) |
| mark_price |string |t(:row_comment_resp_mark_price) |
| index_price |string |t(:row_comment_resp_index_price) |
| open_interest |number |t(:row_comment_resp_open_interest) |
| open_value |string |t(:row_comment_resp_open_value) |
| total_turnover |string |t(:row_comment_resp_total_turnover) |
| turnover_24h |string |t(:row_comment_resp_turnover_24h) |
| total_volume |number |t(:row_comment_resp_total_volume) |
| volume_24h |number |t(:row_comment_resp_volume_24h) |
| funding_rate |string |t(:row_comment_resp_funding_rate) |
| predicted_funding_rate |string |t(:row_comment_resp_predicted_funding_rate) |
| next_funding_time |string |t(:row_comment_resp_next_funding_time) |
| countdown_hour |number |t(:row_comment_resp_countdown_hour) |
| delivery_fee_rate |string |t(:row_comment_resp_delivery_fee_rate) |
| predicted_delivery_price |string |t(:row_comment_resp_predicted_delivery_price) |
| delivery_time |string |t(:row_comment_resp_delivery_time) |
### t(:publictradingrecords)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/v2/public/trading-records?symbol=BTCUSD
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Market.Market_tradingRecords(symbol="BTCUSD").result())
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
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|from |false |int |t(:row_comment_from)|
|limit |false |int |t(:row_comment_limit_liq)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |number |t(:row_response_comment_id)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|price |number |t(:row_response_comment_execprice)  |
|t(:row_parameter_quantity) |number |t(:row_response_comment_execqty)  |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|time |string |t(:row_response_comment_time)  |


### t(:querysymbol)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/v2/public/symbols
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Symbol.Symbol_get().result())
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
            "name":"BTCUSD",
            "alias":"BTCUSD",
            "status":"Trading",
            "base_currency":"BTC",
            "quote_currency":"USD",
            "price_scale":2,
            "taker_fee":"0.00075",
            "maker_fee":"-0.00025",
            "leverage_filter":{
                "min_leverage":1,
                "max_leverage":100,
                "leverage_step":"0.01"
            },
            "price_filter":{
                "min_price":"0.5",
                "max_price":"999999.5",
                "tick_size":"0.5"
            },
            "lot_size_filter":{
                "max_trading_qty":1000000,
                "min_trading_qty":1,
                "qty_step":1
            }
        },
        {
            "name":"EOSUSD",
            "alias":"EOSUSD",
            "status":"Trading",
            "base_currency":"EOS",
            "quote_currency":"USD",
            "price_scale":3,
            "taker_fee":"0.00075",
            "maker_fee":"-0.00025",
            "leverage_filter":{
                "min_leverage":1,
                "max_leverage":50,
                "leverage_step":"0.01"
            },
            "price_filter":{
                "min_price":"0.001",
                "max_price":"1999.999",
                "tick_size":"0.001"
            },
            "lot_size_filter":{
                "max_trading_qty":1000000,
                "min_trading_qty":1,
                "qty_step":1
            }
        },
        {
            "name":"BTCUSDT",
            "alias":"BTCUSDT",
            "status":"Trading",
            "base_currency":"BTC",
            "quote_currency":"USDT",
            "price_scale":2,
            "taker_fee":"0.00075",
            "maker_fee":"-0.00025",
            "leverage_filter":{
                "min_leverage":1,
                "max_leverage":100,
                "leverage_step":"0.01"
            },
            "price_filter":{
                "min_price":"0.5",
                "max_price":"999999.5",
                "tick_size":"0.5"
            },
            "lot_size_filter":{
                "max_trading_qty":100,
                "min_trading_qty":0.001,
                "qty_step":0.001
            }
        },
        {
            "name":"BTCUSDM21",
            "alias":"BTCUSD0625",
            "status":"Trading",
            "base_currency":"BTC",
            "quote_currency":"USD",
            "price_scale":2,
            "taker_fee":"0.00075",
            "maker_fee":"-0.00025",
            "leverage_filter":{
                "min_leverage":1,
                "max_leverage":100,
                "leverage_step":"0.01"
            },
            "price_filter":{
                "min_price":"0.5",
                "max_price":"999999.5",
                "tick_size":"0.5"
            },
            "lot_size_filter":{
                "max_trading_qty":1000000,
                "min_trading_qty":1,
                "qty_step":1
            }
        }
    ],
    "time_now":"1615801223.589808"
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

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|name |string |t(:row_response_comment_name)    |
|alias |string |t(:row_response_comment_name)    |
|status |string |t(:row_response_comment_status)    |
|base_currency |string |t(:row_response_comment_base_currency)    |
|quote_currency |string |t(:row_response_comment_quote_currency)    |
|price_scale |number |t(:row_response_comment_price_scale)    |
|taker_fee |string |t(:row_response_comment_taker_fee)    |
|maker_fee |string |t(:row_response_comment_maker_fee)    |
|leverage_filter > min_leverage |number |t(:row_response_comment_min_leverage)    |
|leverage_filter > max_leverage |number |t(:row_response_comment_max_leverage)    |
|leverage_filter > leverage_step |string |t(:row_response_comment_leverage_step)    |
|price_filter > min_price |string |t(:row_response_comment_min_price)    |
|price_filter > max_price |string |t(:row_response_comment_max_price)    |
|price_filter > tick_size |string |t(:row_response_comment_tick_size)    |
|lot_size_filter > max_trading_qty |number |t(:row_response_comment_max_trading_qty)    |
|lot_size_filter > min_trading_qty |number |t(:row_response_comment_min_trading_qty)    |
|lot_size_filter > qty_step |number |t(:row_response_comment_qty_step)    |


### t(:query_liqrecords)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/v2/public/liq-records?symbol=BTCUSD
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Market.Market_liqRecords(symbol="BTCUSD").result())
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
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|from |false |integer |t(:row_comment_from) |
|limit |false |integer |t(:row_comment_limit_liq) |
|start_time |false |integer |t(:row_comment_startTime_ms) |
|end_time |false |integer |t(:row_comment_endTime_ms) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |number |t(:row_response_comment_id)  |
|t(:row_parameter_quantity) |number |t(:row_response_comment_execqty)  |
|t(:row_parameter_side) |string |t(:row_response_liq_record_side)  |
|time |number |t(:row_response_comment_nill_time)  |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|price |number |t(:row_response_comment_execprice)  |


### t(:markpricekline)
> t(:codequote_curlExample)

```console
curl "https://api.bybit.com/v2/public/mark-price-kline?symbol=BTCUSD&interval=1&limit=2&from=1581231260"
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Kline.Kline_markPrice(symbol="BTCUSD", interval="30",limit=200, **{'from':1600544880}).result())
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
            "id":2,
            "symbol":"BTCUSD",
            "period":"1",
            "start_at":1582231260,
            "open":100,
            "high":120,
            "low":88,
            "close":115
        }
    ],
    "time_now":"1591263582.601795"
}
```

t(:linear_query_mark_price_kline)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=plmpk>/v2/public/mark-price-kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#plmpk"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |<b>true</b> |string |t(:row_comment_symbol) |
|interval |<b>true</b> |string |t(:row_comment_interval) |
|from |<b>true</b> |integer |t(:row_comment_from_timestamp) |
|limit |false |integer |t(:linear_kline_row_comment_limit_200) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol |string |t(:row_comment_symbol) |
| period |string |t(:row_comment_period) |
| start_at |integer |t(:row_comment_startTime) |
| open |integer |t(:row_comment_open) |
| high |integer |t(:row_comment_high) |
| low |integer |t(:row_comment_low) |
| close |integer |t(:row_comment_close) |

### t(:queryindexpricekline)
> t(:codequote_curlExample)

```console
curl "https://api.bybit.com/v2/public/index-price-kline?symbol=BTCUSD&interval=1&limit=2&from=1581231260"
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Kline.Kline_indexPrice(symbol="BTCUSD", interval="1", **{'from':1615067084}).result())
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
            "symbol":"BTCUSD",
            "period":"1",
            "open_time":1582231260,
            "open":"10106.09",
            "high":"10108.75",
            "low":"10104.66",
            "close":"10108.73"
        }
    ],
    "time_now":"1591263582.601795"
}
```
t(:inverse_query_index_price_kline)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=v2pIndexPriceKline>/v2/public/index-price-kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#v2pIndexPriceKline"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
|interval |true |string |t(:row_comment_interval) |
|from |true |integer |t(:row_comment_from_timestamp) |
|limit |false |integer |t(:linear_kline_row_comment_limit_200) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| <a href="#symbol-symbol">symbol</a> |string |t(:row_comment_symbol) |
| period |string |t(:row_comment_period) |
| open_time |integer |t(:row_comment_startTime) |
| open |string |t(:row_comment_open) |
| high |string |t(:row_comment_high) |
| low |string |t(:row_comment_low) |
| close |string |t(:row_comment_close) |



### t(:querypremiumindexkline)
> t(:codequote_curlExample)

```console
curl "https://api.bybit.com/v2/public/premium-index-kline?symbol=BTCUSD&interval=1&limit=2&from=1581231260"
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Kline.Kline_premiumIndexPrice(symbol="BTCUSD", interval="1", **{'from':1615067084}).result())
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
            "symbol":"BTCUSD",
            "period":"1",
            "open_time":1582231260,
            "open":"0.000588",
            "high":"0.000618",
            "low":"0.000588",
            "close":"0.000618"
        }
  ],
    "time_now":"1591263582.601795"
}
```
t(:inverse_query_premium_indices_kline)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpPremiumIndexKline>/v2/public/premium-index-kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpPremiumIndexKline"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
|interval |true |string |t(:row_comment_interval) |
|from |true |integer |t(:row_comment_from_timestamp) |
|limit |false |integer |t(:linear_kline_row_comment_limit_200) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| <a href="#symbol-symbol">symbol</a> |string |t(:row_comment_symbol) |
| period |string |t(:row_comment_period) |
| open_time |integer |t(:row_comment_startTime) |
| open |string |t(:row_comment_open) |
| high |string |t(:row_comment_high) |
| low |string |t(:row_comment_low) |
| close |string |t(:row_comment_close) |


## t(:advanceddata)
### t(:marketopeninterest)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/v2/public/open-interest?symbol=BTCUSD&period=5min
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Market.Market_openInterest(symbol="BTCUSD", limit=2, period="5min").result())
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
            "open_interest":371491978,
            "timestamp":1597658100,
            "symbol":"BTCUSD"
        },
        {
            "open_interest":370696076,
            "timestamp":1597657800,
            "symbol":"BTCUSD"
        }
    ],
    "time_now":"1597658304.938839"
}
```

t(:market_para_marketopeninterest)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpMarketOpenInterest>/v2/public/open-interest</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpMarketOpenInterest"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|period |<b>true</b> |string |t(:row_comment_period)|
|limit |false |int |t(:row_comment_limit_50_200)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| open_interest |number |t(:row_comment_open_interest) |
| timestamp |number |t(:row_comment_time_stamp) |
| symbol |string |t(:row_comment_symbol) |


### t(:marketbigdeal)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/v2/public/big-deal?symbol=BTCUSD
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Market.Market_bigDeal(symbol="BTCUSD", limit=2).result())
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
            "symbol":"BTCUSD",
            "side":"Sell",
            "timestamp":1597623362,
            "value":1242368
        },
        {
            "symbol":"BTCUSD",
            "side":"Buy",
            "timestamp":1597623363,
            "value":1242368
        }
    ],
    "time_now":"1597658434.219859"
}
```

t(:market_para_marketbigdeal)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpMarketBigDeal>/v2/public/big-deal</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpMarketBigDeal"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|limit |false |int |t(:row_comment_limit_500_1000)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol |string |t(:row_comment_symbol) |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
| timestamp |number |t(:row_comment_time_stamp) |
| value |number |t(:row_comment_value) |




### t(:marketaccountratio)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/v2/public/account-ratio?symbol=BTCUSD&period=5min
```

```python
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Market.Market_accountRatio(symbol="BTCUSD", limit=2, period="5min").result())
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
            "symbol":"BTCUSD",
            "buy_ratio":0.6538,
            "sell_ratio":0.3462,
            "timestamp":1597659000
        },
        {
            "symbol":"BTCUSD",
            "buy_ratio":0.6533,
            "sell_ratio":0.3467,
            "timestamp":1597658700
        }
    ],
    "time_now":"1597659230.743313"
}
```

t(:market_para_marketaccountratio)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpMarketAccountRatio>/v2/public/account-ratio</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpMarketAccountRatio"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|period |<b>true</b> |string |t(:row_comment_period)|
|limit |false |int |t(:row_comment_limit_50_500)|

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| symbol |string |t(:row_comment_symbol) |
| buy_ratio |number |t(:row_comment_buy_ratio) |
| sell_ratio |number |t(:row_comment_sell_ratio) |
| timestamp |number |t(:row_comment_time_stamp) |


<!--
### t(:marketfundingrate)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/v2/public/funding-rate?symbol=BTCUSD&limit=100
```
```javascript
{
    "ret_code":0,
    "ret_msg":"OK",
    "ext_code":"",
    "ext_info":"",
    "result":[
        {
            "symbol":"BTCUSD",
            "funding_rate":0.00375,
            "timestamp":1590998277
                }
    ],
    "time_now":"1590068362.493540"
}
```

t(:market_para_marketfundingrate)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpMarketFundingRate>/v2/public/funding-rate</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpMarketFundingRate"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|limit |false |int |t(:row_comment_limit_100)|


### t(:marketeliteratio)
> t(:codequote_curlExample)

```console
curl https://api.bybit.com/v2/public/elite-ratio?symbol=BTCUSD&period=5min
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
            "symbol":"BTCUSD",
            "buy_ratio":0.4288,
            "sell_ratio":0.5712,
            "timestamp":1591165240
        },
        {
            "symbol":"XRPUSD",
            "buy_ratio":0.3288,
            "sell_ratio":0.6712,
            "timestamp":1591165240
        }
    ],
    "time_now":"1591597368.673697"
}
```

t(:market_para_marketeliteratio)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpMarketEliteRatio>/v2/public/elite-ratio</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpMarketEliteRatio"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|period |<b>true</b> |string |t(:row_comment_period)|
-->
