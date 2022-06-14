# t(:authentication)
<aside class="notice">
t(:auth_aside_key)
</aside>

<aside class="notice">
t(:spot_auth_aside_env)
</aside>

t(:auth_para_privatepublic)

## t(:authenticationparameters)


t(:spot_auth_para_recv)

<aside class="warning">
t(:spot_auth_aside_timestamp)
</aside>

## t(:constructingtherequest)

t(:usdc_auth_para_construct1)
t(:auth_para_construct2)

<aside class="notice">
t(:auth_aside_signature)
</aside>
> t(:auth_codequote_construct3)

```console
POST 'https://api.bybit.com/option/usdc/openapi/private/v1/place-order'
X-BAPI-API-KEY: your api key
X-BAPI-SIGN: 6c864f0f0d332133b79de911387c6408ae0d189609c485b9a132fd5ec3beb2ee'
X-BAPI-SIGN-TYPE: 2
X-BAPI-TIMESTAMP: 1655197818844
X-BAPI-RECV-WINDOW: 5000
Content-Type: application/json

{
    "side": "Buy",
    "symbol": "BTC-14JUN22-24500-C",
    "orderType": "Market",
    "orderQty": "0.5",
    "orderPrice": "500",
    "orderLinkId": "option10005",
    "reduce_only": false
}
```

```python
import requests
import json
import time
import hashlib
import hmac

api_key='API-KEY'
secret_key='SECRET-KEY'
time_stamp=str(int(time.time() * 10 ** 3))
recv_window=str(5000)
url = "https://api-testnet.bybit.com/perpetual/usdc/openapi/private/v1/place-order"

payload = json.dumps({"side":"Buy","orderFilter":"Order","orderType":"Limit","orderQty":"5","orderPrice":"40780","timeInForce":"ImmediateOrCancel","symbol":"BTCPERP"})

param_str= str(time_stamp) + api_key + recv_window + payload
hash = hmac.new(bytes(secret_key, "utf-8"), param_str.encode("utf-8"),hashlib.sha256)
signature = hash.hexdigest()

headers = {
  'X-BAPI-API-KEY': api_key,
  'X-BAPI-SIGN': signature,
  'X-BAPI-SIGN-TYPE': '2',
  'X-BAPI-TIMESTAMP': time_stamp,
  'X-BAPI-RECV-WINDOW': recv_window,
  'Content-Type': 'application/json'
}
response = requests.request("POST", url, headers=headers, data=payload)
print(response.text)

```


t(:auth_para_construct3)


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
