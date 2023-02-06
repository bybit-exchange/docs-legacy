## t(:understandingratelimits)
t(:rate_para_understanding_v3)

<aside class="notice">
t(:assetRateLimitNotice)
</aside>

### t(:perendpointtransfer)
<table class="custom_table">
    <tr>
        <th>t(:row_comment_rate_limit)</th>
        <th>t(:row_comment_path)</th>
    </tr>
    <tr>
        <td rowspan="5">20/min</td>
        <tr><td>/asset/v3/private/transfer/inter-transfer </td>
        <tr><td>/asset/v3/private/transfer/sub-member-transfer </td>
        <tr><td>/asset/v3/private/transfer/transfer-sub-member-save </td>
        <tr><td>/asset/v3/private/transfer/universal-transfer </td>
    </tr>
    <tr>
        <td rowspan="8">60/min</td>
        <tr><td>/asset/v3/private/transfer/inter-transfer/list/query </td>
        <tr><td>/asset/v3/private/transfer/sub-member-transfer/list/query </td>
        <tr><td>/asset/v3/private/transfer/transfer-coin/list/query </td>
        <tr><td>/asset/v3/private/transfer/sub-member/list/query </td>
        <tr><td>/asset/v3/private/transfer/universal-transfer/list/query </td>
        <tr><td>/asset/v3/private/transfer/account-coin/balance/query </td>
        <tr><td>/asset/v3/private/transfer/asset-info/query </td>
    </tr>
</table>

### t(:perendpointDepositWithdraw)
<table class="custom_table">
    <tr>
        <th>t(:row_comment_rate_limit)</th>
        <th>t(:row_comment_path)</th>
    </tr>
    <tr>
        <td rowspan="6">300/min</td>
        <tr><td>/asset/v3/private/deposit/sub-member-record/query </td>
        <tr><td>/asset/v3/private/deposit/record/query </td>
        <tr><td>/asset/v3/private/withdraw/record/query </td>
        <tr><td>/asset/v3/private/deposit/address/query </td>
        <tr><td>/asset/v3/private/deposit/sub-member-address/query </td>
    </tr>
    <tr>
        <td rowspan="1">60/min</td>
        <td>/asset/v3/private/withdraw/cancel </td>
    </tr>
    <tr>
        <td rowspan="1">10/min</td>
        <td>/asset/v3/private/withdraw/create </td>
    </tr>
    <tr>
        <td rowspan="1">2/s</td>
        <td>/asset/v3/private/coin-info/query </td>
    </tr>
</table>

### t(:userApikeyEndpoints)
<table class="custom_table">
    <tr>
        <th>t(:row_comment_rate_limit)</th>
        <th>t(:row_comment_path)</th>
    </tr>
    <tr>
        <td rowspan="8">5/s</td>
        <tr><td>/user/v3/private/create-sub-member </td>
        <tr><td>/user/v3/private/create-sub-api </td>
        <tr><td>/user/v3/private/frozen-sub-member </td>
        <tr><td>/user/v3/private/update-api </td>
        <tr><td>/user/v3/private/delete-api </td>
        <tr><td>/user/v3/private/update-sub-api </td>
        <tr><td>/user/v3/private/delete-sub-api </td>
    </tr>
    <tr>
        <td rowspan="3">10/s</td>
        <tr><td>/user/v3/private/query-sub-members </td>
        <tr><td>/user/v3/private/query-api </td>
    </tr>
</table>
