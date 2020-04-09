# t(:ratelimits)
### t(:ipratelimits)
t(:ip_rate_para_understanding)

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
    <td rowspan="2">100/min</td>
    <td>/private/linear/order/create </td>
    <td>1 / request</td>
  </tr>
  <tr><td>/private/linear/order/cancel </td><td>1 / request</td></tr>
  <tr>
    <td rowspan="2">600/min</td>
    <td>/private/linear/order/list </td>
    <td>1 / request</td>
  </tr>
  <tr><td>/private/linear/order/search </td><td>1 / request</td></tr>
  <tr>
    <td rowspan="2">120/min</td>
    <td>open-api/wallet/fund/records  </td>
    <td>1 / request</td>
  </tr>
<tr><td>open-api/wallet/withdraw/list </td><td>1 / request</td></tr>
<tr>
    <td rowspan="1">600/min</td>
    <td>open-api/api-key  </td>
    <td>1 / request</td>
  </tr>
</table>

### t(:orderlimits)
t(:rate_para_limits)

### t(:raisemylimit)
t(:rate_para_raise)
