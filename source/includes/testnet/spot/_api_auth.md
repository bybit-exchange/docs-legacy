# t(:authentication)
<aside class="notice">
t(:auth_aside_key)
</aside>

<aside class="notice">
t(:spot_auth_aside_env)
</aside>

t(:auth_para_privatepublic)

## t(:authenticationparameters)

t(:auth_para_params)

t(:spot_auth_para_recv)

<aside class="warning">
t(:spot_auth_aside_timestamp)
</aside>

## t(:constructingtherequest)
> t(:auth_codequote_construct1a)

```python
param_str = "api_key=B2Rou0PLPpGqcU0Vu2&leverage=100&symbol=BTCUSDH21&timestamp=1542434791747"

# api_key=B2Rou0PLPpGqcU0Vu2&
# leverage=100&
# symbol=BTCUSDH21&
# timestamp=1542434791747
```

> t(:auth_codequote_construct1b)

t(:auth_para_construct1)
<div></div>

t(:auth_para_construct2)
> t(:auth_codequote_construct2)

```http
GET /spot/v1/order?api_key=q1ksyOX2T0G2SkK8nu&qty=100&recvWindow=999999999&side=BUY&symbol=BTCUSDT&timestamp=1623208423972&type=MARKET&sign=b452640c21a2c9eaec30d24a9bce1a9660d1fb9d07ccc0d623a2a4fca0940095 HTTP/1.1
Host: api-testnet.bybit.com
```

> t(:auth_codequote_construct3)

```http
POST /spot/v1/order HTTP/1.1
Host: api-testnet.bybit.com
Content-Type: application/x-www-form-unlencoded

api_key:q1ksyOX2T0G2SkK8nu
qty:100
recvWindow:999999999
side:BUY
symbol:BTCUSDT
timestamp:1623208423972
type:MARKET
sign:b452640c21a2c9eaec30d24a9bce1a9660d1fb9d07ccc0d623a2a4fca0940095

```

t(:auth_para_construct3)

<aside class="notice">
t(:spot_auth_aside_signature)
</aside>

<!--
### Examples of the Signature Algorithm

* [C#](https://github.com/bybit-exchange/bybit-official-api-docs/blob/master/en/example/Encryption.cs)
* [Python](https://github.com/bybit-exchange/bybit-official-api-docs/blob/master/en/example/Encryption.py)
* [C++](https://github.com/bybit-exchange/bybit-official-api-docs/blob/master/en/example/Encryption.cpp)
* [Go](https://github.com/bybit-exchange/bybit-official-api-docs/blob/master/en/example/Encryption.go)
* [PHP](https://github.com/bybit-exchange/bybit-official-api-docs/blob/master/en/example/Encryption.php)
-->


<script>
function copyStringToClipboard (endpoint) {
  var str = document.getElementById(endpoint).innerText;
  // remove whitespace
  var str = str.replace(/ /g,"");
  // Create new element
  var el = document.createElement("textarea");
  // Set value (string to be copied)
  el.value = str;
  // Set non-editable to avoid focus and move outside of view
  el.setAttribute("readonly", "");
  el.style = {position: "absolute", left: "-9999px"};
  document.body.appendChild(el);
  // Select text inside element
  el.select();
  // Copy text to clipboard
  document.execCommand("copy");
  // Remove temporary element
  document.body.removeChild(el);
}
</script>
