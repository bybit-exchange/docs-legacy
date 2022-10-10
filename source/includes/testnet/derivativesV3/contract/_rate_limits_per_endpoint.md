### t(:understandingratelimits)
t(:rate_para_understanding_v3)

```
// Response header

Content-Type: application/json; charset=utf-8
Content-Length: 957
X-Bapi-Limit: 120
X-Bapi-Limit-Status: 118
X-Bapi-Limit-Reset-Timestamp: 1665397625986
```

* `X-Bapi-Limit-Status` - t(:rate_text_limitStatus_understanding)
* `X-Bapi-Limit` - t(:rate_text_limit_understanding)
* `X-Bapi-Limit-Reset-Timestamp` - t(:rate_text_limitReset)

### t(:perendpoint)
<table class="custom_table">
  <tr>
    <th>t(:row_comment_rate_limit)</th>
    <th>t(:row_comment_path)</th>
    <th>t(:row_comment_consume)</th>
  </tr>
  <tr>
    <td rowspan="5">100/min</td>  
  </tr>
  <tr><td>/contract/v3/private/order/create  </td><td>1 / request</td></tr>
  <tr><td>/contract/v3/private/order/cancel  </td><td>1 / request</td></tr>
  <tr><td>/contract/v3/private/order/replace </td><td>1 / request</td></tr>
  <tr><td>/contract/v3/private/order/cancel-all  </td><td>10 / request</td></tr>
  <tr>
    <td rowspan="3">600/min</td>
  </tr>
  <tr><td>/contract/v3/private/order/list </td><td>1 / request</td></tr>
  <tr><td>/contract/v3/private/order/unfilled-orders </td><td>1 / request</td></tr>
  <tr>
    <td rowspan="4">120/min</td>
  </tr>
  <tr><td>/contract/v3/private/execution/list</td><td>1 / request</td></tr>
  <tr><td>/contract/v3/private/position/list</td><td>1 / request</td></tr>
  <tr><td>/contract/v3/private/position/closed-pnl</td><td>1 / request</td></tr>
  <tr>
    <td rowspan="2">120/min</td>
    <tr><td>/contract/v3/private/position/limit-info</td>
    <td>12 / request</td>
  </tr>
  <tr>
    <td rowspan="5">75/min</td>
    <td>/contract/v3/private/position/set-leverage </td>
    <td>1 / request</td>
  </tr>
  <tr><td>/contract/v3/private/position/switch-isolated</td><td>1 / request</td></tr>
  <tr><td>/contract/v3/private/position/trading-stop</td><td>1 / request</td></tr>
  <tr><td>/contract/v3/private/position/switch-mode</td><td>1 / request</td></tr>
  <tr><td>/contract/v3/private/account/fee-rate</td><td>1 / request</td></tr>
  <tr>
    <td rowspan="3">120/min</td>
  </tr>
  <tr><td>/contract/v3/private/account/wallet/balance</td><td>1 / request</td></tr>
    <tr><td>/contract/v3/private/account/wallet/fund-records</td><td>1 / request</td></tr>
  <tr>
    <td rowspan="4">120/min</td>
    <tr><td>/v2/private/funding/prev-funding-rate</td>
    <td>1 / request</td>
  </tr>
  <tr><td>/v2/private/funding/prev-funding</td><td>1 / request</td></tr>
  <tr><td>/v2/private/funding/predicted-funding</td><td>1 / request</td></tr>
  <tr>
    <td rowspan="3">120/min</td>
    <tr><td>/v2/private/wallet/fund/records</td>
    <td>1 / request</td>
  </tr>
<tr><td>/v2/private/wallet/withdraw/list</td><td>1 / request</td></tr>
<tr>
    <td rowspan="2">600/min</td>
    <tr><td>/v2/private/account/api-key</td>
    <td>1 / request</td>
  </tr>
</table>
