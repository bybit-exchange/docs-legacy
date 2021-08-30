# t(:ratelimits)
### t(:ipratelimits)
t(:ip_rate_para_understanding)

### t(:spot_understandingratelimits)
t(:spot_rate_para_understanding)

### t(:perendpointtransfer)
<table class="custom_table">
    <tr>
        <th>t(:row_comment_rate_limit)</th>
        <th>t(:row_comment_path)</th>
        <th>t(:row_comment_consume)</th>
    </tr>
    <tr>
        <td rowspan="2">20/min</td>
        <td>/asset/v1/private/transfer </td>
        <td>1 / request</td>
    </tr>
    <tr>
        <td>/asset/v1/private/sub-member/transfer </td>
        <td>1 / request</td>
    </tr>
    <tr>
        <td rowspan="3">60/min</td>
        <td>/asset/v1/private/sub-member/member-ids </td>
        <td>1 / request</td>
    </tr>
    <tr>
        <td>/asset/v1/private/transfer/list </td>
        <td>1 / request</td>
    </tr>
    <tr>
        <td>/asset/v1/private/sub-member/transfer/list </td>
        <td>1 / request</td>
    </tr>
</table>
