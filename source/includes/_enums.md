# ENUMs Definitions
This is a list of valid options (and rules) for the different parameters when sending a request to the API.

## Side (`side`)
* `Buy`
* `Sell`

## Symbol (`symbol`)
* `BTCUSD`
* `ETHUSD`
* `EOSUSD`
* `XRPUSD`

## Currency (`currency`/`coin`)
* `BTC`
* `ETH`
* `EOS`
* `XRP`


## Wallet fund type (`wallet_fund_type`)
* `Deposit`
* `Withdraw`
* `RealisedPNL`
* `Commission`
* `Refund`
* `Prize`
* `ExchangeOrderWithdraw`
* `ExchangeOrderDeposit`

## Withdraw status (`status`)
* `ToBeConfirmed`
* `UnderReview`
* `Pending` - Pending transfer
* `Success`
* `CancelByUser`
* `Reject`
* `Expire`


## Order type (`order_type`)
* `Limit`
* `Market`

## Quantity (`qty`)
* Maximum quantity of 1 million (`1000000`)
* Must be an integer - no decimals, only a whole number of USD contracts
  * `40` - allowed
  * `30.5` - illegal

## Price (`price`)
* Active order
  * Must be an increment of that market's `tick_size`
    * Current symbol information (like tick sizes) can be found with the <a href="#">Query Symbol endpoint</a>.
    * Use modulo (`%`) to calculate whether or not a price will be accepted, like so:
      <pre class="center-column">
      IF price % tick_size = 0
          // send request
      ELSE
          // do not send request as the price will not be accepted by the system
      </pre>
  * Must be less than 1 million (`1000000`)
  * If the user has no open position then the price must be greater than 10% of the market price
    * For example, if the current market price (last price) is `10314`, then the absolute minimum the price may be is `1031.5`. It may not be `1031` or below.
    * In pseudocode (assuming the price is an increment of 0.5):
      <pre class="center-column">
      IF price > (last_price * 0.1)
          // send request
      ELSE
          // do not send request as the price will not be accepted by the system
      </pre>
  * If the user holds a position, the order price must be better than the liquidation price.
    * For example, if the liquidation price of an open long position is `5176.5` then the price may be a minimum of `5177`. In the case of a short position the price must be less than the liquidation price.
* Conditional order
  * Must be equal to order greater than `1`

## Time in force (`time_in_force`)
* `GoodTillCancel`
* `ImmediateOrCancel`
* `FillOrKill`
* `PostOnly`
* `""` - if and only if you are placing a market order

## Trigger price type (`trigger_by`)
* `LastPrice`
* `IndexPrice`
* `MarkPrice`

## Order status (`order_status`) (creation)
<aside class="notice">
These are the possible values for <code>order_status</code> as included in the response of an <b>Order Creation</b> request. To see the options for <code>order_status</code> in the response for a Get Active/Conditional request, see <a href="#enums-definitions-order-status-order_status-get">here</a>.
</aside>

* `Created`
* `New`
* `PartiallyFilled`
* `Filled`
* `Cancelled`
* `Rejected` - order rejected by the system.

## Order (`order`)
This is for sorting the orders by creation date.

* `desc` (default)
* `asc`

## Order status (`order_status`) (get)
<aside class="notice">
These are the possible values for <code>order_status</code> as included in the response of a <b>Get Order</b> request. To see the options for <code>order_status</code> in the response for a Create Active/Conditional request, see <a href="#enums-definitions-order-status-order_status-creation">here</a>.
</aside>

Filter fetched orders by their order statuses
To filter by multiple statuses, separate with a comma like so: `Filled,New`

* `Created`
* `Rejected`
* `New`
* `PartiallyFilled`
* `Filled`
* `Cancelled`
* `PendingCancel` - The matching engine has received the cancellation but there is no guarantee that it will be successful
* `Deactivated` - The conditional order was cancelled before triggering

## Stop order status (`stop_order_status`)
* `Active` - order is triggered and placed successfully
* `Untriggered` - order waits to be triggered
* `Triggered` - order is triggered
* `Cancelled` - order is cancelled
* `Rejected` - order is triggered but fail to be placed


## Cancel type (`cancel_type`)
* `CancelByUser`
* `CancelByReduceOnly`
* `CancelByPrepareLiq`,`CancelAllBeforeLiq` - Cancelled by force liquidation
* `CancelByPrepareAdl`,`CancelAllBeforeAdl` - Cancelled by ADL
* `CancelByAdmin`
* `CancelByTpSlTsClear` - This is a cancelled TP/SL/TS order
* `CancelByPzSideCh` - This order is cancelled after TP/SL/TS

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
