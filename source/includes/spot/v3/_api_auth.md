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
> t(:spot_auth_codequote_construct1a)

```console
GET
rule: timestamp + api_key + recv_window + queryString

param_str = "1659072951686T0d98KyVamQ62YBzN85000symbol=BTCUSDT"

POST
rule: timestamp + api_key + recv_window + raw_request_body

param_str =
   "1659073093578T0d98KyVamQ62YBzN85000{
    "symbol": "BTCUSDT",
    "orderQty":"0.05",
    "side": "Sell",
    "orderType": "LIMITT",
    "timeInForce": "GTC",
    "orderPrice": "24500",
    "orderLinkId": "spotA0008"
  }"
```
```python

```

<aside class="notice">
t(:auth_para_cdn_request_id)
</aside>

t(:auth_para_dv3_construct1)
<div></div>

t(:auth_para_dv3_construct2)
> t(:spotV3_auth_codequote_construct)

```http
GET /spot/v3/private/open-orders?symbol=BTCUSDT HTTP/1.1
Host: api-testnet.bybit.com
-H 'X-BAPI-SIGN-TYPE: 2' \
-H 'X-BAPI-SIGN: eb431d99a1a203a434a82ac3ea8e107b5f94a967e9aaf922c41e84fb3ec9df78' \
-H 'X-BAPI-API-KEY: {api key}' \
-H 'X-BAPI-TIMESTAMP: 1658384431891' \
-H 'X-BAPI-RECV-WINDOW: 5000'
```

> t(:auth_codequote_construct3)

```http
POST /spot/v3/private/order HTTP/1.1
Host: api-testnet.bybit.com
-H 'X-BAPI-SIGN-TYPE: 2' \
-H 'X-BAPI-SIGN: c822337e76e30505e41b87a55af291e074f59f9496ba12ca2a57dc04fe65a178' \
-H 'X-BAPI-API-KEY: {api key}' \
-H 'X-BAPI-TIMESTAMP: 1658385589135' \
-H 'X-BAPI-RECV-WINDOW: 5000' \
-H 'Content-Type: application/json' \
-d '{
    "symbol": "BTCUSDT",
    "orderQty":"0.05",
    "side": "Sell",
    "orderType": "LIMITT",
    "timeInForce": "GTC",
    "orderPrice": "24500",
    "orderLinkId": "spotA0008"
}'
```

t(:auth_para_construct3_dv3)

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
