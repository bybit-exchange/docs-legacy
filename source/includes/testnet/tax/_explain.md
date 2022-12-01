## t(:dataExplanation)
### t(:tradeHistoryType)
#### t(:spotTradeHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|OrderID |string |t(:taxOrderId) |
|TradeID |string |t(:taxTradeId) |
|Symbol |string |t(:taxSymbol) |
|Side |string |t(:taxSide) |
|QuoteCoin |string |t(:taxQuoteCoin) |
|BaseCoin |string |t(:taxBaseCoin) |
|ExecPrice |string |t(:taxExecPrice) |
|ExecValue |string |t(:taxExecValue) |
|TradingFee |string |t(:taxTradingFee) |
|FeeToken |string |t(:taxFeeToken) |
|TradeTime |string |t(:taxTradeTime) |

#### t(:contractTradeHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|OrderID |string |t(:taxOrderId) |
|TradeID |string |t(:taxTradeId) |
|ContractType |string |t(:taxContractType) |
|Symbol |string |t(:taxSymbol) |
|Side |string |t(:taxSide) |
|QuoteCoin |string |t(:taxQuoteCoin) |
|BaseCoin |string |t(:taxBaseCoin) |
|ExecPrice |string |t(:taxExecPrice) |
|ExecQty |string |t(:taxExecQty) |
|ExecType |string |t(:taxExecType) |
|ExecValue |string |t(:taxExecValue) |
|FeeRate |string |t(:taxFeeRate) |
|FeeToken |string |t(:taxFeeToken) |
|TradingFee |string |t(:taxTradingFee) |
|TradeTime |string |t(:taxTradeTime) |

#### t(:usdcOptionTradeHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|OrderID |string |t(:taxOrderId) |
|TradeID |string |t(:taxTradeId) |
|ContractType |string |t(:taxContractType) |
|Symbol |string |t(:taxSymbol) |
|ExecQty |string |t(:taxExecQty) |
|Side |string |t(:taxSide) |
|QuoteCoin |string |t(:taxQuoteCoin) |
|BaseCoin |string |t(:taxBaseCoin) |
|ExecPrice |string |t(:taxExecPrice) |
|ExecQty |string |t(:taxExecQty) |
|ExecType |string |t(:taxExecType) |
|ExecValue |string |t(:taxExecValue) |
|FeeRate |string |t(:taxFeeRate) |
|FeeToken |string |t(:taxFeeToken) |
|TradingFee |string |t(:taxTradingFee) |
|TradeTime |string |t(:taxTradeTime) |

#### t(:nftTradeHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|OrderID |string |t(:taxOrderId) |
|Network |string |t(:taxNetwork) |
|Side |string |t(:taxSide) |
|NftId |string |t(:taxNftId) |
|ExecValue |string |t(:taxExecValue) |
|BaseCoin |string |t(:taxBaseCoin) |
|PlatformFee |string |t(:taxPlatformFee) |
|ShareFee |string |t(:taxShareFee) |
|TradeTime |string |t(:taxTradeTime) |

### t(:PNLHistoryType)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|OrderID |string |t(:taxOrderId) |
|ContractType |string |t(:taxContractType) |
|Symbol |string |t(:taxSymbol) |
|Side |string |t(:taxSide) |
|ClosedSize |string |t(:taxClosedSize) |
|CumEntryValue |string |t(:taxCumEntryValue) |
|AvgEntryPrice |string |t(:taxAvgEntryPrice) |
|CumExitValue |string |t(:taxCumExitValue) |
|AvgExitPrice |string |t(:taxAvgExitPrice) |
|SettleCoin |string |t(:taxSettleCoin) |
|ClosedPNL |string |t(:taxClosedPNL) |
|FillCount |string |t(:taxFillCount) |
|TradeTime |string |t(:taxTradeTime) |

### t(:earnHistoryType)
#### t(:savingsYieldHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|AssetStakedCoin |string |t(:taxAssetStakedCoin) |
|StakingType |string |t(:taxStakingType) |
|AssetEarnedCoin |string |t(:taxAssetEarnedCoin) |
|EffectiveStakingAmount |string |t(:taxEffectiveStakingAmount) |
|Yield |string |t(:taxYield) |
|TradeTime |string |t(:taxTradeTime) |

#### t(:liquidityMiningLiquidityHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|OrderID |string |t(:taxOrderId) |
|Symbol |string |t(:taxSymbol) |
|OrderType |string |t(:taxOrderType) |
|EntryPrice |string |t(:taxEntryPrice) |
|Leverage |string |t(:taxLeverage) |
|Slippage |string |t(:taxSlippage) |
|Liquidity |string |t(:taxLiquidity) |
|TradeTime |string |t(:taxTradeTime) |

#### t(:liquidityMiningYieldHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|AssetEarnedCoin |string |t(:taxAssetEarnedCoin) |
|Yield |string |t(:taxYield) |
|TradeTime |string |t(:taxTradeTime) |

#### t(:liquidityMiningSwapHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|OrderId |string |t(:taxOrderID) |
|InitialCoin |string |t(:taxInitialCoin) |
|DepositAmount |string |t(:taxDepositAmount) |
|SwapCoin |string |t(:taxSwapCoin) |
|SwapAmount |string |t(:taxSwapAmount) |
|SwapFeeToken |string |t(:taxSwapFeeToken) |
|SwapFee |string |t(:taxSwapFee) |
|Slippage |string |t(:taxSlippage) |
|TradeTime |string |t(:taxTradeTime) |

#### t(:dualAssetSwapHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|OrderId |string |t(:taxOrderID) |
|InitialCoin |string |t(:taxInitialCoin) |
|DepositAmount |string |t(:taxDepositAmount) |
|SwapCoin |string |t(:taxSwapCoin) |
|SwapAmount |string |t(:taxSwapAmount) |
|OrderTime |int |t(:taxOrderTime) |
|TradeTime |int |t(:taxTradeTime) |

#### t(:defiMiningYieldHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|OrderId |string |t(:taxOrderID) |
|AssetStakedCoin |string |t(:taxAssetStakedCoin) |
|Yield |string |t(:taxYield) |
|OrderTime |int |t(:taxOrderTime) |
|TradeTime |int |t(:taxTradeTime) |

#### t(:lauchpoolYieldHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|AssetEarnedCoin |string |t(:taxAssetEarnedCoin) |
|EffectiveStakingAmount |string |t(:taxEffectiveStakingAmount) |
|Yield |string |t(:taxYield) |
|TradeTime |int |t(:taxTradeTime) |

#### t(:sharkfinYieldHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|AssetEarnedCoin |string |t(:taxAssetEarnedCoin) |
|Yield |string |t(:taxYield) |
|TradeTime |int |t(:taxTradeTime) |

### t(:depositNWithdrawHistoryType)
#### t(:cryptoDepositHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|Txid |string |t(:taxTxid) |
|DepositType |string |t(:taxDepositType) |
|ChainType |string |t(:taxChainType) |
|Symbol |string |t(:taxSymbol) |
|FinalAmount |string |t(:taxFinalAmount) |
|OrderTime |int |t(:taxOrderTime) |
|CompletedTime |int |t(:taxCompletedTime) |

#### t(:p2pDepositHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|OrderID |string |t(:taxOrderID) |
|OrderType |string |t(:taxOrderType) |
|P2pSide |string |t(:taxP2PSide) |
|Fiat |string |t(:taxFiat) |
|FiatAmount |string |t(:taxFiatAmount) |
|Coin |string |t(:taxCoin) |
|CoinPrice |string |t(:taxCoinPrice) |
|CoinAmount |string |t(:taxCoinAmount) |
|OrderTime |int |t(:taxOrderTime) |
|CompletedTime |int |t(:taxCompletedTime) |

#### t(:fiatDepositWithdrawHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|OrderID |string |t(:taxOrderID) |
|Type |string |t(:taxType) |
|Fiat |string |t(:taxFiat) |
|DepositAmount |string |t(:taxDepositAmount) |
|FinalAmount |string |t(:taxFinalAmount) |
|Fee |string |t(:taxFee) |
|PaymentMethods |string |t(:taxPaymentMethods) |
|OrderTime |int |t(:taxOrderTime) |
|CompletedTime |int |t(:taxCompletedTime) |

#### t(:expressOrderDepositHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|OrderID |string |t(:taxOrderID) |
|Side |string |t(:taxExpressOrderDepositSide) |
|Fiat |string |t(:taxFiat) |
|DepositAmount |string |t(:taxExpressOrderDepositAmount) |
|DestinationCoin |string |t(:taxDestinationCoin) |
|CoinPrice |string |t(:taxCoinPrice) |
|FinalAmount |string |t(:taxFinalAmount) |
|Fee |string |t(:taxExpressOrderDepositFee) |
|OrderTime |int |t(:taxOrderTime) |
|CompletedTime |int |t(:taxCompletedTime) |

#### t(:thirdPartyDepositHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|OrderID |string |t(:taxOrderID) |
|Txid |string |t(:taxTxid) |
|Platform |string |t(:taxPlatform) |
|Fiat |string |t(:taxFiat) |
|DepositAmount |string |t(:taxDepositAmount) |
|DestinationCoin |string |t(:taxDestinationCoin) |
|CoinPrice |string |t(:taxCoinPrice) |
|FinalAmount |string |t(:taxFinalAmount) |
|OrderTime |int |t(:taxOrderTime) |
|CompletedTime |int |t(:taxCompletedTime) |

#### t(:cryptoWithdrawHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|Txid |string |t(:taxTxid) |
|ChainType |string |t(:taxChainType) |
|Coin |string |t(:taxCoin) |
|FinalAmount |string |t(:taxFinalAmount) |
|Fee |string |t(:taxCryptoWithdrawFee) |
|OrderTime |int |t(:taxOrderTime) |
|CompletedTime |int |t(:taxCompletedTime) |

#### t(:nftDepositWithdrawalHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|OrderId |string |t(:taxOrderID) |
|TxHash |string |t(:taxTxHash) |
|TokenId |string |t(:taxTokenId) |
|TransferType |string |t(:taxTransferType) |
|Network |string |t(:taxNetwork) |
|FeeToken |string |t(:taxFeeToken) |
|Fee |string |t(:taxTradingNftFee) |
|OrderTime |int |t(:taxOrderTime) |
|CompletedTime |int |t(:taxCompletedTime) |

### t(:bonusHistoryType)
<aside class="notice">
t(:taxBonusAndCoupon)
</aside>

#### t(:couponHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|Coin |string |t(:taxCouponCoin) |
|FinalAmount |string |t(:taxCouponFinalAmount) |
|CompletedTime |int |t(:taxCompletedTime) |

#### t(:bonusHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|Coin |string |t(:taxBonusCoin) |
|FinalAmount |string |t(:taxBonusFinalAmount) |
|CompletedTime |int |t(:taxCompletedTime) |


### t(:airdropHistoryType)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|Coin |string |t(:taxAirdropCoin) |
|FinalAmount |string |t(:taxAirdropFinalAmount) |
|TransferType |string |t(:taxAirdropTransferType) |
|TransferDescription |string |t(:taxTransferDescription) |
|CompletedTime |int |t(:taxCompletedTime) |
