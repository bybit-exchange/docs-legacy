# t(:authentication)
<aside class="notice">
t(:auth_aside_key)
</aside>

<aside class="notice">
t(:auth_aside_env)
</aside>

t(:auth_para_privatepublic)

## t(:authenticationparameters)

t(:auth_para_params)

t(:auth_para_recv)

<aside class="warning">
t(:auth_aside_timestamp)
</aside>

## t(:constructingtherequest)

<aside class="notice">
t(:auth_para_cdn_request_id)
</aside>

t(:usdc_auth_para_construct1)
t(:auth_para_construct2)

An example how to place an order:

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
url = "https://api-testnet.bybit.com/derivatives/v3/copytrading/order/create"

payload = json.dumps({"side":"Sell","symbol":"BTCUSDT","order_type":"Market","qty":"0.01","price":"1"})

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
