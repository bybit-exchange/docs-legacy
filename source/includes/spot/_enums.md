# t(:enums)
t(:ENUMs_para)

## Side (`side`)
* `Buy`
* `Sell`

## Time in force (`timeInForce`)
* `GTC` - Good Till Canceled
* `FOK` - Fill or Kill
* `IOC` - Immediate or Cancel

## Symbol (`symbol`)
* `BTCUSDT`
* `ETHUSDT`
* ...

t(:trading_symbol_comment)


## Order type (`type`/`orderTypes`)
* `LIMIT`
* `MARKET`
* `LIMIT_MAKER`


## Currency (`currency`/`coin`)
* `BTC`
* `ETH`
* `EOS`
* `XRP`
* `USDT`

The transfer API also includes:

* `DOT`
* `DOGE`
* `LTC`
* `XLM`
* `USD`


## Order status (`status`)
* `NEW`
* `PARTIALLY_FILLED`
* `FILLED`
* `CANCELED`
* `PENDING_CANCEL`
* `PENDING_NEW`
* `REJECTED`

## Quantity (`qty`)
t(:quantity)

## Price (`price`)
t(:price)

## Time in force (`time_in_force`)
* `GTC` t(:goodTillCancel)
* `IOC` t(:immediateOrCancel)
* `FOK` t(:fillOrKill)

## Kline interval (`interval`)
* `1m` t(:interval_1)
* `3m` t(:interval_3)
* `5m` t(:interval_5)
* `15m` t(:interval_15)
* `30m` t(:interval_30)
* `1h` t(:interval_60)
* `2h` t(:interval_120)
* `4h` t(:interval_240)
* `6h` t(:interval_360)
* `12h` t(:interval_720)
* `1d` t(:interval_D)
* `1w` t(:interval_W)
* `1M` t(:interval_M)

## LT status (`status`)
* `1` t(:etpStatus_1)
* `2` t(:etpStatus_2)
* `3` t(:etpStatus_3)
* `4` t(:etpStatus_4)

## LT order status (`orderStatus`)
* `1` t(:etpOrderStatus_1)
* `2` t(:etpOrderStatus_2)
* `3` t(:etpOrderStatus_3)

## LT order type (`orderType`)
* `1` t(:etpOrderType_1)
* `2` t(:etpOrderType_2)
