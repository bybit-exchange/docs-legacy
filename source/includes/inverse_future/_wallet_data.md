# t(:wallet)
t(:wallet_para)


### t(:balance)
> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "BTC": {
            "equity": 1002,                         //equity = wallet_balance + unrealised_pnl
            "available_balance": 999.99987471,      //available_balance
            //In Isolated Margin Mode:
            // available_balance = wallet_balance - (position_margin + occ_closing_fee + occ_funding_fee + order_margin)
            //In Cross Margin Mode:
              //if unrealised_pnl > 0:
              //available_balance = wallet_balance - (position_margin + occ_closing_fee + occ_funding_fee + order_margin)；
              //if unrealised_pnl < 0:
              //available_balance = wallet_balance - (position_margin + occ_closing_fee + occ_funding_fee + order_margin) + unrealised_pnl
            "used_margin": 0.00012529,              //used_margin = wallet_balance - available_balance
            "order_margin": 0.00012529,             //Used margin by order
            "position_margin": 0,                   //position margin
            "occ_closing_fee": 0,                   //position closing fee
            "occ_funding_fee": 0,                   //funding fee
            "wallet_balance": 1000,                 //wallet balance. When in Cross Margin mod, the number minus your unclosed loss is your real wallet balance.
            "realised_pnl": 0,                      //daily realized profit and loss
            "unrealised_pnl": 2,                    //unrealised profit and loss
                //when side is sell:
                // unrealised_pnl = size * (1.0 / mark_price -  1.0 / entry_price）
                //when side is buy:
                // unrealised_pnl = size * (1.0 / entry_price -  1.0 / mark_price）
            "cum_realised_pnl": 0,                  //total relised profit and loss
            "given_cash": 0,                        //given_cash
            "service_cash": 0                       //service_cash
        }
    },
    "time_now": "1578284274.816029",
    "rate_limit_status": 98,
    "rate_limit_reset_ms": 1580885703683,
    "rate_limit": 100
}
```

t(:wallet_para_walletBalance)

<aside class="notice">
t(:wallet_aside_walletBalance)
</aside>

#### t(:httprequest1)
GET
<code><span id=vpwBalance>/v2/private/wallet/balance</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpwBalance"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters1)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#currency-currency-coin">coin</a> |true |string |t(:row_comment_coin) |


### t(:walletrecords)
> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": {
        "data": [
            {
                "id": 235853,
                "user_id": 1,
                "coin": "BTC",
                "wallet_id": 27913,
                "type": "Realized P&L",
                "amount": "0.00000023",
                "tx_id": "",
                "address": "BTCUSD",
                "wallet_balance": "0.03000353",
                "exec_time": "2019-12-10T00:00:29.000Z",
                "cross_seq": 0
            },
            {
                "id": 234467,
                "user_id": 1,
                "coin": "BTC",
                "wallet_id": 27913,
                "type": "Realized P&L",
                "amount": "-0.00000006",
                "tx_id": "",
                "address": "BTCUSD",
                "wallet_balance": "0.03000330",
                "exec_time": "2019-12-09T00:00:25.000Z",
                "cross_seq": 0
            }
        ]
    },
    "ext_info": null,
    "time_now": "1577481867.115552",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1577481867122,
    "rate_limit": 120
}
```

t(:wallet_para_walletRecords)

<aside class="notice">
t(:wallet_aside_walletRecords)
</aside>

#### t(:httprequest1)
GET
<code><span id=oawfRecords>/open-api/wallet/fund/records</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawfRecords"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters1)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|start_date |false |string |t(:row_comment_startDate) |
|end_date |false |string |t(:row_comment_endDate) |
|<a href="#currency-currency-coin">currency</a> |false |string |t(:row_comment_currency) |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:row_comment_coin) |
|<a href="#wallet-fund-type-wallet_fund_type">wallet_fund_type</a> |false |string |t(:row_comment_walletFundType) |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:row_comment_limit) |


### t(:withdrawrecords)
> t(:codequote_responseExample)

```javascript
{
  "ret_code": 0,
  "ret_msg": "ok",
  "ext_code": "",
  "result": {
      "data": [{
          "id": 137,                                        
          "user_id": 1,                                     
          "coin": "XRP",  //t(:enum_coin_link)                                    
          "status": "Pending" //t(:enum_withdraw_status_link)
          "amount": "20.00000000",
          "fee": "0.25000000",
          "address": "rH7H595XYEVTEHU2FySYsWnmfACBnZS9zM",
          "tx_id": "",
          "submited_at": "2019-06-11T02:20:24.000Z",
          "updated_at": "2019-06-11T02:20:24.000Z"
      }]
      "current_page": 1,
      "last_page": 1
  },
  "ext_info": null,
  "time_now": "1577482295.125488",
  "rate_limit_status": 119,
  "rate_limit_reset_ms": 1577482295132,
  "rate_limit": 120
}
```

t(:wallet_para_withdrawRecords)

<aside class="notice">
t(:wallet_aside_withdrawRecords)
</aside>

#### t(:httprequest1)
GET
<code><span id=oawwList>/open-api/wallet/withdraw/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawwList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters1)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|start_date |false |string |t(:row_comment_startDate) |
|end_date |false |string |t(:row_comment_endDate) |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:row_comment_currency) |
|<a href="#withdraw-status-status">status</a> |false |string |t(:row_comment_withdrawStatus) |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:row_comment_limit) |


### t(:usertraderecords)
> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "order_id": "t(:comment_abandoned)", // t(:comment_abandoned)
        "trade_list": [
            {
                "closed_size": 0,
                "cross_seq": 277136382,
                "exec_fee": "0.0000001",
                "exec_id": "256e5ef8-abfe-5772-971b-f944e15e0d68",
                "exec_price": "8178.5",
                "exec_qty": 1,
                "exec_time": "1571676941.70682",
                "exec_type": "Trade", //t(:enum_exec_type_link)
                "exec_value": "0.00012227",
                "fee_rate": "0.00075",
                "last_liquidity_ind": "RemovedLiquidity", //t(:enum_Liquidity_type_link)
                "leaves_qty": 0,
                "nth_fill": 2,
                "order_id": "7ad50cb1-9ad0-4f74-804b-d82a516e1029",
                "order_link_id": "",
                "order_price": "8178",
                "order_qty": 1,
                "order_type": "Market", //t(:enum_order_type_link)
                "side": "Buy", //t(:enum_side_link)
                "symbol": "BTCUSD", //t(:enum_symbol_link)
                "user_id": 1
            }
        ]
    },
    "time_now": "1577483699.281488",
    "rate_limit_status": 118,
    "rate_limit_reset_ms": 1577483699244737,
    "rate_limit": 120
}
```

t(:wallet_para_tradeRecords)

<aside class="notice">
t(:wallet_aside_tradeRecords)
</aside>

#### t(:httprequest1)
GET
<code><span id=vpeList>/v2/private/execution/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpeList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

#### t(:requestparameters1)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |false |string |t(:wallet_row_comment_orderId) |
|<a href="#symbol-symbol">symbol</a> |false |string |t(:misc_row_comment_symbolNotOrderId) |
|start_time |false |int |t(:row_comment_startTime) |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:row_comment_limit) |