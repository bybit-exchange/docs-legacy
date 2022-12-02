# t(:enums)
t(:ENUMs_para)

## ReportType (`reportType`)
* `TRADE` - TradeHistory
* `P&L` - P&L History
* `EARN` - Earn History
* `DEPOSIT&WITHDRAWAL` - Deposit and Withdrawal History
* `BONUS` - Bonus History
* `AIRDROP` - Airdrop History

## ReportNumber (`reportNumber`)
ReportType = "TRADE"

* `1` - Get Spot Trade History
* `2` - Get Contract Trade History
* `3` - Get USDC Options Trade History
* `4` - Get NFT Trade History

ReportType = "P&L"

* `1` - Get Contract Closed P&L History

ReportType = "EARN"

* `1` - Get BybitSavings Yield History
* `2` - Get LiquidityMining Liquidity History
* `3` - Get LiquidityMining Yield History
* `4` - Get LiquidityMining Swap History
* `5` -Get DualAsset Swap History
* `6` - Get DeFiMining Yield History
* `7` - Get Launchpool Yield History
* `8` - Get Sharkfin Yield History

ReportType = "DEPOSIT&WITHDRAWAL"

* `1` - Get Crypto Deposit History
* `2` - Get P2P Deposit History
* `3` - Get Fiat Deposit and Withdraw History
* `4` - Get Express Order Deposit History
* `5` -Get Third Party Deposit History
* `6` - Get Crypto Withdraw History
* `7` - Get NFT Deposit and Withdrawal History

ReportType = "BONUS"

* `1` - Get Coupon History
* `2` - Get Bonus History

ReportType = "AIRDROP"

* `1` - Get Airdrop History
