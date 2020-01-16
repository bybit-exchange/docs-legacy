# Authentication
<aside class="notice">
To generate an API key please go <a href="https://testnet.bybit.com/app/user/api-management">here for the <b>testnet</b></a> or <a href="https://www.bybit.com/app/user/api-management">here for the <b>mainnet</b></a>.
</aside>

Domains:
<ul>
  <li>
    <span id=testnet><a href="https://api-testnet.bybit.com">https://api-testnet.bybit.com</a></span>
    <button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#testnet"><img src="images/copy_to_clipboard.png" height=15 width=15></a></button>
  </li>
  <li>
    <span id=mainnet><a href="https://api.bybit.com">https://api.bybit.com</a></span>
    <button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#mainnet"><img src="images/copy_to_clipboard.png" height=15 width=15></a></button>
  </li>
</ul>


All requests made to **private** endpoints must be authenticated. Requests made to **public** endpoints do not require the additional parameters needed for authentication.

## Parameters for Authenticated Endpoints
The following parameters must be used for authentication:
<ul>
  <li>`api_key`</li>
  <li>`timestamp` - UTC timestamp in **milliseconds**</li>
  <li>`sign` - a signature derived from the request's parameters</li>
</ul>

<aside class="warning">
Make sure to conform to the timestamp rule of verification or your request will be rejected! Timestamp rule of verification: timestamp < server_time + 1000
</aside>

Additionally, we offer the `recv_window`, which indicates for how long an HTTP request is valid. This should be sent in milliseconds. Default value: 5000. This is used to prevent replay attacks.

## Constructing the Request
> An example for adjusting leverage

```python
param_str = "api_key=B2Rou0PLPpGqcU0Vu2&leverage=100&symbol=BTCUSD&timestamp=1542434791747"

# api_key=B2Rou0PLPpGqcU0Vu2&
# leverage=100&
# symbol=BTCUSD&
# timestamp=1542434791747
```

> Note how the parameters are ordered in <b>ascending</b> order, with api_key first followed by leverage, then symbol, then timestamp.

<p>1. Concatenate all the public parameters in the <a href="https://en.wikipedia.org/wiki/Query_string">query string</a> format. The parameters must be ordered in <b>ascending</b> order. This will be used to generate the <code>sign</code>.</p>
<div></div>

<p>2. Sign the parameters string.</p>
> Different requests need different message formats.
> Possible message formats for **GET** requests:

```http
GET /user/leverage?api_key=B2Rou0PLPpGqcU0Vu2&timestamp=1542434791000&sign=670e3e4aa32b243f2dedf1dafcec2fd17a440e71b05681550416507de591d908 HTTP/1.1
Host: api-testnet.bybit.com
```

```http
GET /user/leverage HTTP/1.1
Host: api-testnet.bybit.com
Content-Type: application/json

{
    "api_key": "B2Rou0PLPpGqcU0Vu2",
    "timestamp": 1542434791000,
    "sign": "670e3e4aa32b243f2dedf1dafcec2fd17a440e71b05681550416507de591d908"
}
```

> Message format for **POST** requests:

```http
POST /user/leverage/save HTTP/1.1
Host: api-testnet.bybit.com
Content-Type: application/json

{
    "api_key": "B2Rou0PLPpGqcU0Vu2",
    "leverage": 100,
    "symbol": "BTCUSD",
    "timestamp": 1542434791000,
    "sign": "670e3e4aa32b243f2dedf1dafcec2fd17a440e71b05681550416507de591d908"
}
```

<p>3. Append the signature at the end of the parameters string, and send the HTTP request. Please note that the format for messages is different depending on whether you are sending a GET or POST request.</p>

<aside class="notice">
Example signature algorithms can be found <a href="https://github.com/bybit-exchange/bybit-official-api-docs/tree/master/en/example">here</a>.
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
