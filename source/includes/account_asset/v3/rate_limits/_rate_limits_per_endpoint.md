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
        <td rowspan="5">20/s</td>
        <tr><td>/asset/v3/private/transfer/inter-transfer </td>
        <tr><td>/asset/v3/private/transfer/sub-member-transfer </td>
        <tr><td>/asset/v3/private/transfer/transfer-sub-member-save </td>
        <tr><td>/asset/v3/private/transfer/universal-transfer </td>
    </tr>
    <tr>
        <td rowspan="8">60/s</td>
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
        <td rowspan="5">300/s</td>
        <tr><td>/asset/v3/public/deposit/allowed-deposit-list/query </td>
        <tr><td>/asset/v3/private/deposit/record/query </td>
        <tr><td>/asset/v3/private/withdraw/record/query </td>
        <tr><td>/asset/v3/private/deposit/address/query </td>
    </tr>
    <tr>
        <td rowspan="1">60/s</td>
        <td>/asset/v3/private/withdraw/cancel </td>
    </tr>
    <tr>
        <td rowspan="1">10/s</td>
        <td>/asset/v3/private/withdraw/create </td>
    </tr>
    <tr>
        <td rowspan="1">2/s</td>
        <td>/asset/v3/private/coin-info/query </td>
    </tr>
</table>
