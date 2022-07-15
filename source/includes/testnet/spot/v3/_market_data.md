# t(:marketdata)
t(:market_para_auth)


### t(:spot_querysymbol)
> t(:codequote_curlExample)

```console
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=svSymbols>/spot/v1/symbols</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svSymbols"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>

| t(:column_parameter) |t(:column_type)|t(:column_comments)|
|:---------------------|:-----|----- |




### t(:orderbook)
> t(:codequote_curlExample)

```console
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=sqvDepth>/spot/quote/v1/depth</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvDepth"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |



<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:mergedOrderBook)

> t(:codequote_curlExample)

```console
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=sqvdMerged>/spot/quote/v1/depth/merged</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvdMerged"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b>|string|t(:spotSymbol)|



<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:publictradingrecords)
> t(:codequote_curlExample)

```console
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=sqvTrades>/spot/quote/v1/trades</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvTrades"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |



<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |



### t(:querykline)
> t(:codequote_curlExample)

```console
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=sqvKline>/spot/quote/v1/kline</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvKline"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<aside class="notice">
t(:spot_kline_latest_records)
</aside>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b>|string|t(:spotSymbol)|



<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |

<aside class="notice">
t(:spotKlineTimeRemark)
</aside>

### t(:spot_latestsymbolinfo)
> t(:codequote_curlExample)

```console
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=sqvt24hr>/spot/quote/v1/ticker/24hr</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvt24hr"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


<aside class="notice">
t(:spotTicker24hrRemark)
</aside>

### t(:lasttradedprice)
> t(:codequote_curlExample)

```console
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=sqvtPrice>/spot/quote/v1/ticker/price</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvtPrice"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |

<aside class="notice">
t(:spotTickerPriceRemark)
</aside>

### t(:bestbidask)
> t(:codequote_curlExample)

```console
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript

```


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=sqvtBook_ticker>/spot/quote/v1/ticker/book_ticker</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#sqvtBook_ticker"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
<aside class="notice">
t(:spotBookTickerRemark)
</aside>

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |

