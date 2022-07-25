# t(:errors)

t(:errors_intro)



HTTP Code | t(:errorcode_meaning)
---------- | -------
200 | t(:spot_http_200)
403 | t(:spot_http_403)
404 | t(:spot_http_404)

Return Code | t(:errorcode_meaning)
---------- | -------
0        |  Success
10001    |  Error - request failed processed. Please try again.
10002    |  Request not authorized - an API key is required and should be included in all requests.
10003    |  Too many requests - please use WebSocket for live updates. Current limit is %s requests per minute.
10004    |  invalid sign
10005    |  permission denied for current apikey
10006    |  System not responding. Request status unknown. Please contact live support.
10007    |  Response timeout from backend server. Delivery and request status unknown.
10016	   |   System error. Please try again later.
3100102  |  Contract name cannot be empty.
3100103  |  Invalid order direction.
3100104  |	Please enter the order quantity.
3100105  |	Only Standard and Advanced versions supported.
3100106  |	Please enter the order price.
3100107  |	Order type must be price or implied volatility.
3100108  |	Implied volatility must be greater than zero.
3100109  |	Invalid order type.
3100110  |	Invalid time in force.
3100113  |	Order price cannot be lower than {{key0}}.
3100114  |	Order price cannot be higher than {{key0}}.
3100115  |	The min. tick size should be {{key0}}.
3100116  |	Order quantity below the lower limit.
3100117  |	Order qty exceeds the upper limit.
3100118  |	The min. order size increment is {{key0}}.
3100119  |	Order ID cannot be empty.
3100122  |	Only modification to implied volatility, order price, or order quantity supported.
3100123  |	outRequestId cannot be empty.
3100126  |	Settlement in progress! {{key0}} not available for trades.
3100127  |	{{key0}} not yet available for trades.
3100128  |	{{key0}} no longer available for trades.
3100129  |	Repeated Request
3100136  |	Order does not exist. (the order does not exist or the order has been completed to the final state (Canceled, Filled))
3100141  |	Failed to place new order(s)! Position is being liquidated.
3100143  |	Failed to cancel! The order has already been filled.
3100191  |	Failed! The order has already been canceled.
3100192  |	Failed to edit! The order has already been filled.
3100193  |	Failed to edit! The order has already been canceled.
3100144  |	Failed to edit!
3100145  |	Up to {{key0}} active orders supported for Options.
3200300	 |   Insufficient margin balance.
3200304	 |   The number of active orders exceeds the upper limit.
3200200	 |   Insufficient margin balance.
3303001	 |   No corresponding command execution authority.
3303004	 |   Instruction execution exception.
3303005	 |   Repeat signature verification.
3303006	 |   Sign verification failed.
3303007	 |   Single connection execution command frequency overrun.
3303008	 |   The number of websocket connections established by a single uid exceeds the limit.
3400001  |   Please ensure that there are no positions in your USDC account, including USDC perpetual and options
3400002  |   Please ensure that there are no active orders in your USDC account, including Limit, Market and Conditional orders
3400005  |   Set margin mode failed
3400015	 |   System error. Please try again later.
3400045	 |   Set margin mode failed. The error will be triggerd when your account is in the upgrade of unified margin account, then you request set margin mode endpoint in the mean time.
3500001	 |   System error. Please try again later.
3500040	 |   System error. Please try again later.

