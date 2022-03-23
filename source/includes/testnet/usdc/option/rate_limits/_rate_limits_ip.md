# t(:ratelimits)
### t(:ipratelimits)
t(:usdc_ip_rate_para_understanding)


### t(:perendpoint)
<table class="custom_table">
  <tr>
    <th>t(:row_comment_rate_limit)</th>
    <th>t(:row_comment_path)</th>
  </tr>
  <tr>
    <td rowspan="1">20 requests/second</td>
    <td>/option/usdc/openapi/private/v1/cancel-order </td>
  </tr>
  <tr>
    <td rowspan="1">20 requests/second</td>
    <td>/option/usdc/openapi/private/v1/batch-cancel-orders </td>
  </tr>
  <tr>
    <td rowspan="1">2 requests/second</td>
    <td>/option/usdc/openapi/private/v1/cancel-all </td>
  </tr>
  <tr>
    <td rowspan="1">5 requests/second</td>
    <td>All other private endpoints</td>
  </tr>
</table>
