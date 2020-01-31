# t(:rate_heading)
### t(:ip_rate_heading_understandin)
t(:ip_rate_para_understanding)

### t(:rate_heading_understandin)
t(:rate_para_understanding)

```
"rate_limit_status": 119,
"rate_limit_reset_ms": 1572114055663,
"rate_limit": 120
```

* `rate_limit_status` - t(:rate_text_limitStatus_understanding)
* `rate_limit` - t(:rate_text_limit_understanding)
* `rate_limit_reset_ms` - t(:rate_text_limitReset)


### t(:rate_heading_allEndpoints)
<table class="custom_table">
  <tr>
    <th>t(:row_comment_limit)</th>
    <th>t(:row_comment_path)</th>
    <th>t(:row_comment_consume)</th>
  </tr>
  <tr>
    <td rowspan="10">100/min</td>
    <td>open-api/order/create </td>
    <td>1 / request</td>
  </tr>
  <tr><td>open-api/order/cancel       </td><td>1 / request</td></tr>
  <tr><td>open-api/stop-order/create  </td><td>1 / request</td></tr>
  <tr><td>open-api/stop-order/cancel  </td><td>1 / request</td></tr>
  <tr><td>open-api/order/replace      </td><td>1 / request</td></tr>
  <tr><td>open-api/stop-order/replace </td><td>1 / request</td></tr>
  <tr><td>v2/private/order/create     </td><td>1 / request</td></tr>
  <tr><td>v2/private/order/cancel     </td><td>1 / request</td></tr>
  <tr><td>v2/private/order/cancelAll  </td><td>10 / request</td></tr>
  <tr><td>v2/private/stop-order/cancelAll </td><td>10 / request</td></tr>
  <tr>
    <td rowspan="3">600/min</td>
    <td>open-api/order/list </td>
    <td>1 / request</td>
  </tr>
  <tr><td>open-api/stop-order/list </td><td>1 / request</td></tr>
  <tr><td>v2/private/order </td><td>1 / request</td></tr>
  <tr>
    <td>120/min</td>
    <td>v2/private/execution/list</td>
    <td>1 / request</td>
  </tr>
  <tr>
    <td rowspan="3">75/min</td>
    <td>user/leverage/save  </td>
    <td>1 / request</td>
  </tr>
  <tr><td>position/change-position-margin </td><td>1 / request</td></tr>
  <tr><td>position/trading-stop           </td><td>1 / request</td></tr>
  <tr>
    <td rowspan="2">120/min</td>
    <td>position/list  </td>
    <td>1 / request</td>
  </tr>
  <tr><td>user/leverage</td><td>1 / request</td></tr>
  <tr>
    <td rowspan="3">120/min</td>
    <td>open-api/funding/prev-funding-rate  </td>
    <td>1 / request</td>
  </tr>
  <tr><td>open-api/funding/prev-funding      </td><td>1 / request</td></tr>
  <tr><td>open-api/funding/predicted-funding </td><td>1 / request</td></tr>
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

### t(:rate_heading_limits)
t(:rate_para_limits)

### t(:rate_heading_raise)
t(:rate_para_raise)

### t(:rate_heading_liquidity)
t(:rate_para_liquidity)

#### t(:rate_heading_threshold)
t(:rate_para_threshold)

##### t(:rate_heading_ratio)
t(:rate_para_ratio)

##### t(:rate_heading_ratioExample)


<pre class="center-column-nonindent">
t(:rate_pre_ratioExampleA)
</pre>

<pre class="center-column-nonindent">
t(:rate_pre_ratioExampleB)
</pre>


##### t(:rate_heading_minimum)
t(:rate_para_minimum)


#### t(:rate_heading_frequency)
t(:rate_para_frequency)


| t(:column_LCP) | t(:column_frequencyLimit) |
|  ----    | ----  |
| 20-100  | t(:row_frequencyLimit_800) |
| 10-20   | t(:row_frequencyLimit_600) |
| 5-10    | t(:row_frequencyLimit_400) |
| 2-5     | t(:row_frequencyLimit_200) |
| <2      | t(:row_frequencyLimit_100) |

##### t(:rate_heading_liquidityPoints)
t(:rate_para_liquidityPoints)

##### t(:rate_heading_explanation)
###### t(:rate_heading_priceRange)
t(:rate_para_priceRange)

###### t(:rate_heading_priceRangeExample)
<pre class="center-column-nonindent">
t(:rate_pre_priceRangeExample)
</pre>


###### t(:rate_heading_POU)
t(:rate_para_POU)

<pre class="center-column-nonindent">
t(:rate_pre_POUExample)
</pre>


###### t(:rate_heading_POA)
t(:rate_para_POA)

###### t(:rate_heading_POAExample)
t(:rate_para_POAExample)

<pre class="center-column-nonindent">
t(:rate_pre_POAExample)
</pre>

<aside class="notice">
t(:rate_aside_POAExample)
</aside>
