# t(:enums)
t(:ENUMs_para)

## AccountType (`type`/`accountType`)
* `AccountType_CONTRACT` (`期货账户`)
* `AccountType_SPOT`     (`现货账户`)
* `AccountType_INVESMENT`(`理财账户`)

## Currency (`currency`/`coin`)
* `BTC`
* `ETH`
* `EOS`
* `XRP`
* `USDT`
* `DOT`
* `DOGE`
* `LTC`
* `XLM`
* `USD`

## OperatorType
* `SYSTEM`
* `USER`
* `ADMIN`
* `AFFILIATE_USER`

## TransactionType (`业务场景`)
* `DEPOSIT` (`扫链入金`)
* `BALANCEADJJUST` (`内部加减钱`)
* `INTER_TRANSFER` (`账号内划转`)
* `WITHDRAW` (`出金`)
* `SUBMEMBER_TRANSFER` (`母子划转`)
* `RECONILIATION_DEPOSIT` (`法币入金`)
* `SUBMEMBER_TRANSFER` (`母子划转`)
* `EXTERNAL_TRANSFER` (`跨账号划转`)

## AccountTransferRecordStatus (`账户内部划转过程状态`)
* `INIT` (`划转前初始化状态`)
* `WITHDRAW_SUCCESS` (`出金成功`)
* `SUCCESS` (`划转完成`)
* `TERMINATED` (`业务终止`)
* `FAILED` (`划转异常，需人工处理`)

## TransferType
* `UNKNOWN`
* `IN` (`转入`)
* `OUT`(`转出`)
