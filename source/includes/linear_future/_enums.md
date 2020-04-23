# t(:enums)
t(:ENUMs_para)

## Side (`side`)
* `Buy`
* `Sell`

## Symbol (`symbol`)
* `BTCUSDT`

## Currency (`currency`/`coin`)
* `USDT`


## Wallet fund type (`wallet_fund_type`)
* `Deposit` t(:deposit)
* `Withdraw` t(:withdraw)
* `RealisedPNL` t(:realisedpnl)
* `Commission` t(:commission)
* `Refund` t(:refund)
* `Prize` t(:prize)
* `ExchangeOrderWithdraw` t(:exchangeOrderWithdraw)
* `ExchangeOrderDeposit` t(:exchangeOrderDeposit)

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

## Order status (`order_status`)
t(:para_orderStatusGet)

* `Created` t(:created1)
* `Rejected` t(:rejected)
* `New` t(:new1)
* `PartiallyFilled` t(:partiallyFilled1)
* `Filled` t(:filled1)
* `Cancelled` t(:cancelled1)
* `PendingCancel` t(:pendingCancel1)

<!--
## Stop order status (`stop_order_status`)
* `Active` t(:active)
* `Untriggered` t(:untriggered)
* `Triggered` t(:triggered)
* `Cancelled` t(:cancelled)
* `Rejected` t(:rejected)
* `Deactivated` t(:deactivated1)
-->

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
* `CreateByTrailingStop`
* `CreateByLiq` - Created by partial liquidation
* `CreateByAdl_PassThrough` - Created by ADL
* `CreateByTakeOver_PassThrough` - Created by liquidation takeover

## Exec type (`exec_type`)
* `Trade` t(:exec_trade)
* `AdlTrade` t(:exec_adlTrade)
* `Funding` t(:exec_funding)
* `BustTrade` t(:exec_bustTrade)

## Liquidity type (`last_liquidity_ind`)
* `AddedLiquidity` t(:addedLiquidity)
* `RemovedLiquidity` t(:removedLiquidity)