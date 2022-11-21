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
> t(:auth_codequote_construct_asset_v3)

```python
param_str = "1660633147433XXXXXXXXX5000startTime=1659283200000&endTime=1660060800000&coin=USDT"

# timestamp: 1660633147433
# api_key: XXXXXXXXX
# recv_window: 5000
# startTime=1659283200000
# endTime=1660060800000
# coin=USDT
```

<aside class="notice">
t(:auth_para_cdn_request_id)
</aside>

t(:auth_para_dv3_construct1)
<div></div>

t(:auth_para_dv3_construct2)
> t(:auth_codequote_construct_asset_v3_1)

```http
GET https://api-testnet.bybit.com/asset/v3/private/withdraw/record/query?startTime=1659283200000&endTime=1660060800000&coin=USDT HTTP/1.1
Host: api-testnet.bybit.com
-H 'X-BAPI-SIGN-TYPE: 2' \
-H 'X-BAPI-SIGN: eb431d99a1a203a434a82ac3ea8e107b5f94a967e9aaf922c41e84fb3ec9df78' \
-H 'X-BAPI-API-KEY: {api key}' \
-H 'X-BAPI-TIMESTAMP: 1658384431891' \
-H 'X-BAPI-RECV-WINDOW: 5000'
```

> t(:auth_codequote_account_asset_v3_2)

```http
POST /asset/v3/private/withdraw/create HTTP/1.1
Host: api-testnet.bybit.com
-H 'X-BAPI-SIGN-TYPE: 2' \
-H 'X-BAPI-SIGN: c822337e76e30505e41b87a55af291e074f59f9496ba12ca2a57dc04fe65a178' \
-H 'X-BAPI-API-KEY: {api key}' \
-H 'X-BAPI-TIMESTAMP: 1658385589135' \
-H 'X-BAPI-RECV-WINDOW: 5000' \
-H 'Content-Type: application/json' \

{
    "coin": "USDT",
    "chain": "ETH",
    "address": "0x9ba58f56E420a00a23D3508Cf77fF268C8510A01",
    "tag": null,
    "amount": "20",
    "timestamp": 1660620515481
}
```
t(:auth_para_construct3_dv3)

<aside class="notice">
t(:auth_aside_signature)
</aside>
