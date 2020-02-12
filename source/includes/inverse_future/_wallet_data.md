# t(:wallet_heading)
t(:wallet_para)


### t(:wallet_heading_walletBalance)
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
    "time_now": "1578284274.816029"
}
```

t(:wallet_para_walletBalance)

<aside class="notice">
t(:wallet_aside_walletBalance)
</aside>

##### t(:heading_http_request)
GET
<code><span id=oawfRecords>/v2/private/wallet/balance</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawfRecords"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#t-enums_header-currency-currency-coin">coin</a> |true |string |t(:row_comment_coin) |


### t(:wallet_heading_walletRecords)
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

##### t(:heading_http_request)
GET
<code><span id=oawfRecords>/open-api/wallet/fund/records</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawfRecords"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|start_date |false |string |t(:row_comment_startDate) |
|end_date |false |string |t(:row_comment_endDate) |
|<a href="#t-enums_header-currency-currency-coin">currency</a> |false |string |t(:row_comment_currency) |
|<a href="#t-enums_header-currency-currency-coin">coin</a> |false |string |t(:row_comment_coin) |
|<a href="#t-enums_header-wallet-fund-type-wallet_fund_type">wallet_fund_type</a> |false |string |t(:row_comment_walletFundType) |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:row_comment_limit) |


### t(:wallet_heading_withdrawRecords)
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
          "coin": "XRP",  //t(:enum_coin)                                    
          "status": "Pending" //t(:enum_withdraw_status)
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

##### t(:heading_http_request)
GET
<code><span id=oawwList>/open-api/wallet/withdraw/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawwList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|start_date |false |string |t(:row_comment_startDate) |
|end_date |false |string |t(:row_comment_endDate) |
|<a href="#t-enums_header-currency-currency-coin">coin</a> |false |string |t(:row_comment_currency) |
|<a href="#t-enums_header-withdraw-status-status">status</a> |false |string |t(:row_comment_withdrawStatus) |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:row_comment_limit) |


### t(:wallet_heading_tradeRecords)
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
                "exec_type": "Trade", //t(:enum_exec_type)
                "exec_value": "0.00012227",
                "fee_rate": "0.00075",
                "last_liquidity_ind": "RemovedLiquidity", //t(:enum_Liquidity_type)
                "leaves_qty": 0,
                "nth_fill": 2,
                "order_id": "7ad50cb1-9ad0-4f74-804b-d82a516e1029",
                "order_link_id": "",
                "order_price": "8178",
                "order_qty": 1,
                "order_type": "Market", //t(:enum_order_type)
                "side": "Buy", //t(:enum_side)
                "symbol": "BTCUSD", //t(:enum_symbol)
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

##### t(:heading_http_request)
GET
<code><span id=vpeList>/v2/private/execution/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpeList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|order_id |false |string |t(:wallet_row_comment_orderId) |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |false |string |t(:misc_row_comment_symbolNotOrderId) |
|start_time |false |int |t(:row_comment_startTime) |
|page |false |integer |t(:row_comment_page) |
|limit |false |integer |t(:row_comment_limit) |


## t(:wallet_heading_getRisk)
> t(:codequote_responseExample)

```javascript
{
  "ret_code": 0,
  "ret_msg": "ok",
  "ext_code": "",
  "result": [
    {
      "id": 1,
      "coin": "BTC",
      "limit": 150,
      "maintain_margin": "0.50",
      "starting_margin": "1.00",
      "section": [
        "1",
        "2",
        "3",
        "5",
        "10",
        "25",
        "50",
        "100"
      ],
      "is_lowest_risk": 1,
      "created_at": "2018-11-09T13:53:04.000Z",
      "updated_at": "2018-11-09T13:53:04.000Z"
    },
    {
      "id": 11,
      "coin": "ETH",
      "limit": 3000,
      "maintain_margin": "1.00",
      "starting_margin": "2.00",
      "section": [
        "1",
        "2",
        "3",
        "5",
        "15",
        "30",
        "40",
        "50"
      ],
      "is_lowest_risk": 1,
      "created_at": "2019-01-25T08:31:54.000Z",
      "updated_at": "2019-01-25T08:31:54.000Z"
    }
  ],
  "ext_info": null,
  "time_now": "1577587907.157396",
  "rate_limit_status": 599,
  "rate_limit_reset_ms": 1577587907162,
  "rate_limit": 600
}
```

t(:wallet_para_getRisk)

<aside class="notice">
t(:wallet_aside_getRisk)
</aside>

##### t(:heading_http_request)
GET
<code><span id=oawrlList>/open-api/wallet/risk-limit/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawrlList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |


## t(:wallet_heading_setRisk)
> t(:codequote_responseExample)

```javascript
{
  "ret_code": 0,
  "ret_msg": "ok",
  "ext_code": "",
  "result": {
    "position": {
      "id": 1,
      "user_id": 1,
      "symbol": "BTCUSD",
      "side": "None",
      "size": 0,
      "position_value": 0,
      "entry_price": 0,
      "risk_id": 2,
      "auto_add_margin": 0,
      "leverage": 1,
      "position_margin": 0,
      "liq_price": 0,
      "bust_price": 0,
      "occ_closing_fee": 0,
      "occ_funding_fee": 0,
      "take_profit": 0,
      "stop_loss": 0,
      "trailing_stop": 0,
      "position_status": "Normal",
      "deleverage_indicator": 0,
      "oc_calc_data": "{\"blq\":1,\"blv\":\"0.000125\",\"slq\":0,\"bmp\":8000,\"smp\":0,\"fc\":-0.00012529,\"bv2c\":1.00225,\"sv2c\":1.0007575}",
      "order_margin": 0.00012529,
      "wallet_balance": 1000,
      "realised_pnl": 0,
      "cum_realised_pnl": 0,
      "cum_commission": 0,
      "cross_seq": 4376,
      "position_seq": 13689,
      "created_at": "2019-08-13T06:51:29.000Z",
      "updated_at": "2019-12-29T03:11:08.000Z",
      "ext_fields": {
        "v": 4
      }
    },
    "risk": {
      "id": 2,
      "coin": "BTC",
      "limit": 300,
      "maintain_margin": "1.00",
      "starting_margin": "1.50",
      "section": "[\"1\",\"2\",\"3\",\"5\",\"10\",\"25\",\"50\",\"66\"]",
      "is_lowest_risk": 0,
      "created_at": "2019-06-26T05:46:45.000Z",
      "updated_at": "2019-06-26T05:46:55.000Z"
    }
  },
  "ext_info": null,
  "time_now": "1577589068.435439",
  "rate_limit_status": 71,
  "rate_limit_reset_ms": 1577589068546,
  "rate_limit": "75"
}
```

t(:wallet_para_setRisk)

<aside class="notice">
t(:wallet_aside_getRisk)
</aside>

##### t(:heading_http_request)
GET
<code><span id=oawRiskLimit>/open-api/wallet/risk-limit</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawRiskLimit"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

##### t(:heading_request_parameters)
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#t-enums_header-symbol-symbol">symbol</a> |true |string |t(:row_comment_symbol) |
|risk_id |true |integer |t(:row_comment_riskId) |
