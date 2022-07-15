# t(:accountdata)
t(:account_para)

### t(:placeactive)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/spot/v1/order \
-H "Content-Type: application/x-www-form-urlencoded" \
-d 'api_key={api_key}&side=Buy&symbol=ETHUSDT&type=MARKET&qty=10&timeInForce=GTC&timestamp={timestamp}&sign={signature}'
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript

```


<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=svPostOrder>/spot/v1/order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svPostOrder"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |



<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |

### t(:getactive)
> t(:codequote_curlExample)

```console
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript

```

t(:getactive)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=svGetOrder>/spot/v1/order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svGetOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:cancelactive)
> t(:codequote_curlExample)

```console
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript

```


<p class="fake_header">t(:httprequest)</p>
DELETE
<code><span id=svDeleteOrder>/spot/v1/order</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svDeleteOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |



### t(:fastcancelactiveorder)
> t(:codequote_curlExample)

```console
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
```


<aside class="notice">
t(:spotNormalCancelTips)
</aside>

<p class="fake_header">t(:httprequest)</p>
DELETE
<code><span id=svoFast>/spot/v1/order/fast</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svoFast"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |

### t(:batchcancelactiveorder)
> t(:codequote_curlExample)

```console

```

```python--pybit
```

> t(:codequote_responseExample)

```javascript

```

<aside class="notice">
t(:spotCancelTips)
</aside>

<p class="fake_header">t(:httprequest)</p>
DELETE
<code><span id=soBatchCancel>/spot/order/batch-cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#soBatchCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |



### t(:batchfastcancelactiveorder)
> t(:codequote_curlExample)

```console

```

```python--pybit
```

> t(:codequote_responseExample)

```javascript

```

<aside class="notice">
t(:spotFastCancelTips)
</aside>


<p class="fake_header">t(:httprequest)</p>
DELETE
<code><span id=soBatchFastCancel>/spot/order/batch-fast-cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#soBatchFastCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |



### t(:batchcancelactiveorderbyids)
> t(:codequote_curlExample)

```console

```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
```

<aside class="notice">
t(:spotNormalCancelTips)
</aside>

<p class="fake_header">t(:httprequest)</p>
DELETE
<code><span id=soBatchCancelIds>/spot/order/batch-cancel-by-ids</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#soBatchCancelIds"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |




### t(:openorders)
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
<code><span id=svOpenOrders>/spot/v1/open-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svOpenOrders"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |


<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:orderhistory)
> t(:codequote_curlExample)

```console

```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
{
   
}
```

<aside class="notice">
t(:spotOrdersHistoryTips)
</aside>
<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=svHistoryOrders>/spot/v1/history-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svHistoryOrders"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:tradehistory)
> t(:codequote_curlExample)

```console
```

```python--pybit
```

> t(:codequote_responseExample)

```javascript
```

<aside class="notice">
t(:spotTradesHistoryTips)
</aside>
<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=svMyTrades>/spot/v1/myTrades</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#svMyTrades"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |

<p class="fake_header">fee object</p>

|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
