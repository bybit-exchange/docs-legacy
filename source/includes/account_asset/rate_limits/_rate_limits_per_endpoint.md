<aside class="notice">
t(:assetRateLimitIntro)
</aside>

### t(:perendpointtransfer)
<table class="custom_table">
    <tr>
        <th>t(:row_comment_rate_limit)</th>
        <th>t(:row_comment_path)</th>
        <th>t(:row_comment_consume)</th>
    </tr>
    <tr>
        <td rowspan="1">20/min</td>
        <td>/asset/v1/private/transfer </td>
        <td>1 / request</td>
    </tr>
    <tr>
        <td rowspan="1">20/min</td>
        <td>/asset/v1/private/sub-member/transfer </td>
        <td>1 / request</td>
    </tr>
    <tr>
        <td rowspan="1">60/min</td>
        <td>/asset/v1/private/sub-member/member-ids </td>
        <td>1 / request</td>
    </tr>
    <tr>
        <td rowspan="1">60/min</td>
        <td>/asset/v1/private/transfer/list </td>
        <td>1 / request</td>
    </tr>
    <tr>
        <td rowspan="1">60/min</td>
        <td>/asset/v1/private/sub-member/transfer/list </td>
        <td>1 / request</td>
    </tr>
</table>

### t(:perendpointDepositWithdraw)
<table class="custom_table">
    <tr>
        <th>t(:row_comment_rate_limit)</th>
        <th>t(:row_comment_path)</th>
        <th>t(:row_comment_consume)</th>
    </tr>
    <tr>
        <td rowspan="1">3/min</td>
        <td>/asset/v1/private/withdraw </td>
        <td>1 / request</td>
    </tr>
    <tr>
        <td rowspan="1">10/min</td>
        <td>/asset/v1/private/withdraw/cancel </td>
        <td>1 / request</td>
    </tr>
    <tr>
        <td rowspan="1">30/min</td>
        <td>/asset/v1/private/deposit/address </td>
        <td>1 / request</td>
    </tr>
    <tr>
        <td rowspan="2">60/min</td>
        <td>/asset/v1/private/asset-info/query </td>
        <td>1 / request</td>
    </tr>
    <tr>
        <td>/asset/v1/private/deposit/record/query </td>
        <td>1 / request</td>
    </tr>
    <tr>
        <td rowspan="2">120/min</td>
        <td>/asset/v1/private/withdraw/record/query </td>
        <td>1 / request</td>
    </tr>
    <tr>
        <td>/asset/v1/private/coin-info/query </td>
        <td>1 / request</td>
    </tr>
</table>
