### t(:understandingratelimits)
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
  <tr><td>/futures/private/order/cancel       </td><td>1 / request</td></tr>
  <tr><td>/futures/private/stop-order/create  </td><td>1 / request</td></tr>
  <tr><td>/futures/private/stop-order/cancel  </td><td>1 / request</td></tr>
  <tr><td>/futures/private/order/replace      </td><td>1 / request</td></tr>
  <tr><td>/futures/private/stop-order/replace </td><td>1 / request</td></tr>
  <tr><td>/futures/private/order/create     </td><td>1 / request</td></tr>
  <tr><td>/futures/private/order/cancel     </td><td>1 / request</td></tr>
  <tr><td>/futures/private/order/cancelAll  </td><td>10 / request</td></tr>
  <tr><td>/futures/private/stop-order/cancelAll </td><td>10 / request</td></tr>
  <tr>
    <td rowspan="4">600/min</td>
    <td>/futures/private/order/list </td>
    <td>1 / request</td>
  </tr>
  <tr><td>/futures/private/stop-order/list </td><td>1 / request</td></tr>
  <tr><td>/futures/private/order </td><td>1 / request</td></tr>
  <tr><td>/futures/private/stop-order </td><td>1 / request</td></tr>
  <tr>
    <td>120/min</td>
    <td>/futures/private/execution/list</td>
    <td>1 / request</td>
  </tr>
  <tr>
    <td rowspan="6">75/min</td>
    <td>/futures/private/position/leverage/save </td>
    <td>1 / request</td>
  </tr>
  <tr><td>/futures/private/position/change-position-margin</td><td>1 / request</td></tr>
  <tr><td>/futures/private/position/trading-stop</td><td>1 / request</td></tr>
  <tr><td>/futures/private/position/switch-mode</td><td>1 / request</td></tr>
  <tr><td>/futures/private/position/switch-isolated</td><td>1 / request</td></tr>
  <tr><td>/futures/private/tpsl/switch-mode</td><td>1 / request</td></tr>
  <tr>
    <td rowspan="3">120/min</td>
  </tr>
  <tr><td>/futures/private/position/list</td><td>1 / request</td></tr>
</table>
