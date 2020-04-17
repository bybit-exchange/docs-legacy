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
    <td rowspan="6">100/min</td>
    <td>/private/linear/order/create </td>
    <td>1 / request</td>
  </tr>
  <tr><td>/private/linear/order/cancel </td><td>1 / request</td></tr>
  <tr><td>/private/linear/order/cancel-all </td><td>10 / request</td></tr>
  <tr><td>/private/linear/stop-order/create </td><td>1 / request</td></tr>
  <tr><td>/private/linear/stop-order/cancel </td><td>1 / request</td></tr>
  <tr><td>/private/linear/stop-order/cancel-all </td><td>10 / request</td></tr>
  <tr>
    <td rowspan="5">75/min</td>
    <td>/private/linear/position/set-leverage   </td>
    <td>1 / request</td>
  </tr>
  <tr><td>/private/linear/position/switch-isolated </td><td>1 / request</td></tr>
  <tr><td>/private/linear/position/set-auto-add-margin </td><td>1 / request</td></tr>
  <tr><td>/private/linear/position/trading-stop </td><td>1 / request</td></tr>
  <tr><td>/private/linear/position/add-margin </td><td>1 / request</td></tr>
    
  <tr>
    <td rowspan="3">120/min</td>
    <td>/private/linear/position/list  </td>
    <td>1 / request</td>
  </tr>
  <tr><td>/private/linear/trade/closed-pnl/list </td><td>1 / request</td></tr>
  <tr><td>/private/linear/trade/execution/list </td><td>1 / request</td></tr>
    
  <tr>
    <td rowspan="4">600/min</td>
    <td>/private/linear/order/list </td>
    <td>1 / request</td>
  </tr>
  <tr><td>/private/linear/order/search </td><td>1 / request</td></tr>
  <tr><td>/private/linear/stop-order/list </td><td>1 / request</td></tr>
  <tr><td>/private/linear/stop-order/search </td><td>1 / request</td></tr>
  
  <tr>
    <td rowspan="2">120/min</td>
    <td>/private/linear/funding/prev-funding  </td>
    <td>1 / request</td>
  </tr>
  <tr><td>/private/linear/funding/predicted-funding </td><td>1 / request</td></tr>
</table>

### t(:orderlimits)
t(:rate_para_limits)

### t(:raisemylimit)
t(:rate_para_raise)

### t(:liquidity)
t(:rate_para_liquidity)

#### t(:ofrthreshold)
t(:rate_para_threshold)

##### t(:ofrratio)
t(:rate_para_ratio)

##### t(:ofrratioExample)


<pre class="center-column-nonindent">
t(:rate_pre_ratioExampleA)
</pre>

<pre class="center-column-nonindent">
t(:rate_pre_ratioExampleB)
</pre>


##### t(:ofrminimum)
t(:rate_para_minimum)


#### t(:frequencylimit)
t(:rate_para_frequency)


| t(:column_LCP) | t(:column_frequencyLimit) |
|  ----    | ----  |
| 20-100  | t(:row_frequencyLimit_800) |
| 10-20   | t(:row_frequencyLimit_600) |
| 5-10    | t(:row_frequencyLimit_400) |
| 2-5     | t(:row_frequencyLimit_200) |
| <2      | t(:row_frequencyLimit_100) |

##### t(:liquidityPoints)
t(:rate_para_liquidityPoints)

##### t(:ratelimitsexplanation)

###### t(:pricerange)
t(:rate_para_priceRange)

###### t(:pricerangeExample)
<pre class="center-column-nonindent">
t(:rate_pre_priceRangeExample)
</pre>


###### t(:pou)
t(:rate_para_POU)

<pre class="center-column-nonindent">
t(:rate_pre_POUExample)
</pre>


###### t(:poa)
t(:rate_para_POA)

###### t(:poaExample)
t(:rate_para_POAExample)

<pre class="center-column-nonindent">
t(:rate_pre_POAExample)
</pre>

<aside class="notice">
t(:rate_aside_POAExample)
</aside>
