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
* `TRANSFER_IN`
* `TRANSFER_OUT`
* `TRADE`
* `SETTLEMENT`
* `DELIVERY`
* `LIQUIDATION`

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

## LastLiquidityInd (`LastLiquidityInd`)
* `TAKER`
* `MAKER`
