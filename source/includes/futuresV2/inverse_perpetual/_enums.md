# t(:enums)
t(:ENUMs_para)

## Side (`side`)
* `Buy`
* `Sell`

## Symbol (`symbol`)
* `BTCUSD`
* `ETHUSD`
* `EOSUSD`
* `XRPUSD`
* `DOTUSD`

t(:trading_symbol_comment)

## Currency (`currency`/`coin`)
* `BTC`
* `ETH`
* `EOS`
* `XRP`
* `DOT`
* `USDT`

## Contract Type(`contract_type`)
* `InversePerpetual`
* `LinearPerpetual`
* `InverseFutures`

## Contract Status(`status`)
* `Trading`
* `Settling`
* `Closed`



## Wallet fund type (`wallet_fund_type` / `type`)
* `Deposit` t(:deposit)
* `Withdraw` t(:withdraw)
* `RealisedPNL` t(:realisedpnl)
* `Commission` t(:commission)
* `Refund` t(:refund)
* `Prize` t(:prize)
* `ExchangeOrderWithdraw` t(:exchangeOrderWithdraw)
* `ExchangeOrderDeposit` t(:exchangeOrderDeposit)
* `ReturnServiceCash` t(:returnServiceCash)
* `Insurance` t(:insurance)
* `SubMember` t(:subMember)
* `Coupon` t(:coupon)
* `AccountTransfer` t(:accountTransfer)
* `CashBack` t(:cashBack)


## Withdraw status (`status`)
* `ToBeConfirmed` t(:toBeConfirmed)
* `UnderReview` t(:underReview)
* `Pending` t(:pending)
* `Success` t(:success)
* `CancelByUser` t(:cancelByUser)
* `Reject` t(:reject)
* `Expire` t(:expire)


## Order type (`order_type`)
* `Limit` t(:limit)
* `Market` t(:market)

## Quantity (`qty`)
t(:quantity)

## Price (`price`)
t(:price)

## Time in force (`time_in_force`)
* `GoodTillCancel` t(:goodTillCancel)
* `ImmediateOrCancel` t(:immediateOrCancel)
* `FillOrKill` t(:fillOrKill)
* `PostOnly` t(:postOnly)

## Trigger price type (`trigger_by`)
* `LastPrice` t(:lastPrice)
* `IndexPrice` t(:indexPrice)
* `MarkPrice` t(:markPrice)

## Order (`order`)
t(:para_order)

* `desc` t(:desc)
* `asc` t(:asc)

## Order status (`order_status`/`stop_order_status`)
t(:para_orderStatusGet)

* `Created` t(:created1)
* `New` t(:new1)
* `Rejected` t(:rejected1)
* `PartiallyFilled` t(:partiallyFilled1)
* `Filled` t(:filled1)
* `PendingCancel` t(:pendingCancel1)
* `Cancelled` t(:cancelled1)

Only for conditional orders:

* `Untriggered` t(:untriggered)
* `Deactivated` t(:deactivated1)
* `Triggered` t(:triggered)
* `Active` t(:active)


## Cancel type (`cancel_type`)
* `CancelByUser` t(:cancelByUser)
* `CancelByReduceOnly` t(:cancelByReduceOnly)
* `CancelByPrepareLiq`,`CancelAllBeforeLiq` t(:cancelByPrepareLiq)
* `CancelByPrepareAdl`,`CancelAllBeforeAdl` t(:cancelByPrepareAdl)
* `CancelByAdmin` t(:cancelByAdmin)
* `CancelByTpSlTsClear` t(:cancelByTpSlTsClear)
* `CancelByPzSideCh` t(:cancelByPzSideCh)

## Create type (`create_type`)
* `CreateByUser`
* `CreateByClosing`
* `CreateByAdminClosing`
* `CreateByStopOrder`
* `CreateByTakeProfit`
* `CreateByStopLoss`
* `CreateByPartialTakeProfit`
* `CreateByPartialStopLoss`
* `CreateByTrailingStop`
* `CreateByLiq` - Created by partial liquidation
* `CreateByAdl_PassThrough` - Created by ADL
* `CreateByTakeOver_PassThrough` - Created by liquidation takeover

## Exec type (`exec_type`)
* `Trade` t(:exec_trade)
* `AdlTrade` t(:exec_adlTrade)
* `Funding` t(:exec_funding)
* `BustTrade` t(:exec_bustTrade)
* `Settle` t(:exec_settle)

## Liquidity type (`last_liquidity_ind`)
* `AddedLiquidity` t(:addedLiquidity)
* `RemovedLiquidity` t(:removedLiquidity)


## Tick direction type (`tick_direction`)
t(:tick_direction)

* `PlusTick` t(:plusTick)
* `ZeroPlusTick` t(:zeroPlusTick)
* `MinusTick` t(:minusTick)
* `ZeroMinusTick` t(:zeroMinusTick)

## TP/SL mode (`tp_sl_mode`)
t(:tp_sl_mode)

* `Full` t(:Full)
* `Partial` t(:Partial)

## Kline interval (`interval`)
* `1` t(:interval_1)
* `3` t(:interval_3)
* `5` t(:interval_5)
* `15` t(:interval_15)
* `30` t(:interval_30)
* `60` t(:interval_60)
* `120` t(:interval_120)
* `240` t(:interval_240)
* `360` t(:interval_360)
* `720` t(:interval_720)
* `D` t(:interval_D)
* `W` t(:interval_W)
* `M` t(:interval_M)

## Date (`start_date`/`end_date`)
t(:date)

## Stop order type (`stop_order_type`)
* `TakeProfit`
* `StopLoss`
* `TrailingStop`
* `Stop`
