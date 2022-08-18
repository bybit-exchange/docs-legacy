## t(:understandingratelimits)
t(:rate_para_understanding)

```
"rate_limit_status": 119,
"rate_limit_reset_ms": 1572114055663,
"rate_limit": 120
```

* `rate_limit_status` - t(:rate_text_limitStatus_understanding)
* `rate_limit` - t(:rate_text_limit_understanding)
* `rate_limit_reset_ms` - t(:rate_text_limitReset)

### t(:perendpoint)
<table class="custom_table">
  <tr>
    <th>t(:row_comment_rate_limit)</th>
    <th>t(:row_comment_path)</th>
    <th>t(:row_comment_consume)</th>
  </tr>
  <tr>
    <td rowspan="10">100/min</td>  
  </tr>
  <tr><td>/v2/private/order/cancel       </td><td>1 / request</td></tr>
  <tr><td>/v2/private/stop-order/create  </td><td>1 / request</td></tr>
  <tr><td>/v2/private/stop-order/cancel  </td><td>1 / request</td></tr>
  <tr><td>/v2/private/order/replace      </td><td>1 / request</td></tr>
  <tr><td>/v2/private/stop-order/replace </td><td>1 / request</td></tr>
  <tr><td>/v2/private/order/create     </td><td>1 / request</td></tr>
  <tr><td>/v2/private/order/cancel     </td><td>1 / request</td></tr>
  <tr><td>/v2/private/order/cancelAll  </td><td>10 / request</td></tr>
  <tr><td>/v2/private/stop-order/cancelAll </td><td>10 / request</td></tr>
  <tr>
    <td rowspan="3">600/min</td>
    <td>/v2/private/order/list </td>
    <td>1 / request</td>
  </tr>
  <tr><td>/v2/private/stop-order/list </td><td>1 / request</td></tr>
  <tr><td>/v2/private/order </td><td>1 / request</td></tr>
  <tr>
    <td>120/min</td>
    <td>/v2/private/execution/list</td>
    <td>1 / request</td>
  </tr>
  <tr>
    <td rowspan="5">75/min</td>
    <td>/v2/private/position/leverage/save </td>
    <td>1 / request</td>
  </tr>
  <tr><td>/v2/private/position/change-position-margin</td><td>1 / request</td></tr>
  <tr><td>/v2/private/position/trading-stop</td><td>1 / request</td></tr>
  <tr><td>/v2/private/tpsl/switch-mode</td><td>1 / request</td></tr>
  <tr><td>/v2/private/position/fee-rate</td><td>1 / request</td></tr>
  <tr>
    <td rowspan="3">120/min</td>
  </tr>
  <tr><td>/v2/private/position/list</td><td>1 / request</td></tr>
    <tr><td>/v2/private/wallet/balance</td><td>1 / request</td></tr>
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
