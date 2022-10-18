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
> t(:auth_codequote_construct1a)

```python
param_str = "api_key=XXXXXXXXXXX&leverage=100&symbol=BTCUSDH21&timestamp=1542434791747"

# api_key=XXXXXXXXXXX&
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
GET /asset/v1/private/transfer/list?api_key=XXXXXXXXXXX&recvWindow=5000&timestamp=1623208423972&sign=b452640c21a2c9eaec30d24a9bce1a9660d1fb9d07ccc0d623a2a4fca0940095 HTTP/1.1
Host: api-testnet.bybit.com
```

> t(:auth_codequote_construct3)

```http
POST /asset/v1/private/transfer HTTP/1.1
Host: api-testnet.bybit.com
Content-Type: application/json

{
    "from_account_type": "SPOT",
    "to_account_type": "CONTRACT",
    "amount": "0.01",
    "coin": "USDT",
    "transfer_id": "11ff9b44-2d5d-4293-913d-4597c9ad2170",
    "sign": "{{signature}}",
    "timestamp": "{{timestamp}}",
    "api_key": "{{bybit-api-key}}",
    "recv_window": "50000"
}
