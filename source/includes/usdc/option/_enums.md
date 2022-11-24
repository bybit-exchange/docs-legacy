# t(:enums)
t(:ENUMs_para)

## Side (`side`)
* `Buy`
* `Sell`

## Time in force (`timeInForce`)
* `GoodTillCancel`
* `ImmediateOrCancel`
* `FillOrKill`
* `PostOnly`

## Symbol (`symbol`)
t(:usdc_trading_symbol_comment)


## Order type (`orderType`)
* `Limit`
* `Market`


## Currency (`currency`/`coin`)
* `USDC`


## Order status (`orderStatus`)
* `New`
* `PartiallyFilled`
* `Filled`
* `Cancelled`
* `Rejected`

## Quantity (`orderQty`/`qty`)
t(:usdcQuantity)

## Price (`price`)
t(:usdcPriceRule)


## Transaction type (`type`)
* `TRANSFER_IN` t(:transfer_in)
* `TRANSFER_OUT` t(:transfer_out)
* `TRADE` t(:trade)
* `SETTLEMENT` t(:settlement)
* `DELIVERY` t(:delivery)
* `LIQUIDATION` t(:liquidation)


## Margin Mode (`marginMode`)
* `REGULAR_MARGIN`
* `PORTFOLIO_MARGIN`

## Exec Type (`execType`)
* `TRADE`

## Stop Order Type (`stopOrderType`)
* `Stop`
* `TakeProfit`
* `StopLoss`
* `TrailingStop`
* `TrailingProfit`
* `PartialTakeProfit`
* `PartialStopLoss`


## Cancel Type (`cancelType`)
* `CancelByUser`
* `CancelAllBeforeLiq`
* `CancelAllBeforeAdl`
* `CancelByReduceOnly`
* `CancelBySettle`
* `CancelByCannotAffordOrderCost`
* `CancelByPmTrialMmOverEquity`
* `CancelByAccountBlocking`
* `CancelByDelivery`
* `CancelByMmpTriggered`
* `CancelByCrossSelfMuch`
* `CancelByCrossReachMaxTradeNum`

## LastLiquidityInd (`LastLiquidityInd`)
* `TAKER`
* `MAKER`

## Base Coin (`baseCoin`)
* `BTC`
* `ETH`
* `SOL`

## Period (`period`)

BTC & ETH
`7`
`14`
`21`
`30`
`60`
`90`
`180`
`270`days

SOL
`7`
`14`
`21`
`30`
`60`
`90`days

## Symbol status (`status`)
* `WAITING_ONLINE` t(:waiting_online)
* `ONLINE` t(:online)
* `DELIVERING` t(:delivering)
* `OFFLINE` t(:offline)
