## t(:dataExplanation)
### t(:tradeHistoryType)
#### t(:spotTradeHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderID |string |t(:taxOrderId) |
|tradeID |string |t(:taxTradeId) |
|symbol |string |t(:taxSymbol) |
|side |string |t(:taxSide) |
|quoteCoin |string |t(:taxQuoteCoin) |
|baseCoin |string |t(:taxBaseCoin) |
|execValue |string |t(:taxExecValue) |
|tradingFee |string |t(:taxTradingFee) |
|feeToken |string |t(:taxFeeToken) |
|tradeTime |string |t(:taxTradeTime) |

#### t(:contractTradeHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderID |string |t(:taxOrderId) |
|tradeID |string |t(:taxTradeId) |
|contractType |string |t(:taxContractType) |
|symbol |string |t(:taxSymbol) |
|side |string |t(:taxSide) |
|quoteCoin |string |t(:taxQuoteCoin) |
|baseCoin |string |t(:taxBaseCoin) |
|execPrice |string |t(:taxExecPrice) |
|execQty |string |t(:taxExecQty) |
|execType |string |t(:taxExecType) |
|execValue |string |t(:taxExecValue) |
|feeRate |string |t(:taxFeeRate) |
|feeToken |string |t(:taxFeeToken) |
|tradingFee |string |t(:taxTradingFee) |
|tradeTime |string |t(:taxTradeTime) |

#### t(:usdcOptionTradeHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderID |string |t(:taxOrderId) |
|tradeID |string |t(:taxTradeId) |
|contractType |string |t(:taxContractType) |
|symbol |string |t(:taxSymbol) |
|execQty |string |t(:taxExecQty) |
|side |string |t(:taxSide) |
|quoteCoin |string |t(:taxQuoteCoin) |
|baseCoin |string |t(:taxBaseCoin) |
|execPrice |string |t(:taxExecPrice) |
|execQty |string |t(:taxExecQty) |
|execType |string |t(:taxExecType) |
|execValue |string |t(:taxExecValue) |
|feeRate |string |t(:taxFeeRate) |
|feeToken |string |t(:taxFeeToken) |
|tradingFee |string |t(:taxTradingFee) |
|tradeTime |string |t(:taxTradeTime) |

#### t(:nftTradeHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderID |string |t(:taxOrderId) |
|network |string |t(:taxNetwork) |
|side |string |t(:taxSide) |
|nftId |string |t(:taxNftId) |
|execValue |string |t(:taxExecValue) |
|baseCoin |string |t(:taxBaseCoin) |
|platformFee |string |t(:taxPlatformFee) |
|shareFee |string |t(:taxShareFee) |
|tradeTime |string |t(:taxTradeTime) |

### t(:PNLHistoryType)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderID |string |t(:taxOrderId) |
|contractType |string |t(:taxContractType) |
|symbol |string |t(:taxSymbol) |
|side |string |t(:taxSide) |
|closedSize |string |t(:taxClosedSize) |
|cumEntryValue |string |t(:taxCumEntryValue) |
|avgEntryPrice |string |t(:taxAvgEntryPrice) |
|cumExitValue |string |t(:taxCumExitValue) |
|avgExitPrice |string |t(:taxAvgExitPrice) |
|closedPNL |string |t(:taxClosedPNL) |
|fillCount |string |t(:taxFillCount) |
|tradeTime |string |t(:taxTradeTime) |

### t(:earnHistoryType)
#### t(:savingsYieldHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|assetStakedCoin |string |t(:taxAssetStakedCoin) |
|stakingType |string |t(:taxStakingType) |
|assetEarnedCoin |string |t(:taxAssetEarnedCoin) |
|effectiveStakingAmount |string |t(:taxEffectiveStakingAmount) |
|yield |string |t(:taxYield) |
|tradeTime |string |t(:taxTradeTime) |

#### t(:liquidityMiningLiquidityHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderID |string |t(:taxOrderId) |
|symbol |string |t(:taxSymbol) |
|orderType |string |t(:taxOrderType) |
|entryPrice |string |t(:taxEntryPrice) |
|leverage |string |t(:taxLeverage) |
|slippage |string |t(:taxSlippage) |
|liquidity |string |t(:taxLiquidity) |
|tradeTime |string |t(:taxTradeTime) |

#### t(:liquidityMiningYieldHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|assetEarnedCoin |string |t(:taxAssetEarnedCoin) |
|yield |string |t(:taxYield) |
|tradeTime |string |t(:taxTradeTime) |

#### t(:liquidityMiningSwapHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId |string |t(:taxOrderID) |
|initialCoin |string |t(:taxInitialCoin) |
|depositAmount |string |t(:taxDepositAmount) |
|swapCoin |string |t(:taxSwapCoin) |
|swapAmount |string |t(:taxSwapAmount) |
|swapFeeToken |string |t(:taxSwapFeeToken) |
|swapFee |string |t(:taxSwapFee) |
|slippage |string |t(:taxSlippage) |
|tradeTime |string |t(:taxTradeTime) |

#### t(:dualAssetSwapHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId |string |t(:taxOrderID) |
|initialCoin |string |t(:taxInitialCoin) |
|depositAmount |string |t(:taxDepositAmount) |
|swapCoin |string |t(:taxSwapCoin) |
|swapAmount |string |t(:taxSwapAmount) |
|orderTime |int |t(:taxOrderTime) |
|tradeTime |int |t(:taxTradeTime) |

#### t(:defiMiningYieldHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId |string |t(:taxOrderID) |
|assetStakedCoin |string |t(:taxAssetStakedCoin) |
|yield |string |t(:taxYield) |
|orderTime |int |t(:taxOrderTime) |
|tradeTime |int |t(:taxTradeTime) |

#### t(:lauchpoolYieldHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|assetEarnedCoin |string |t(:taxAssetEarnedCoin) |
|effectiveStakingAmount |string |t(:taxEffectiveStakingAmount) |
|yield |string |t(:taxYield) |
|tradeTime |int |t(:taxTradeTime) |

#### t(:sharkfinYieldHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|assetEarnedCoin |string |t(:taxAssetEarnedCoin) |
|yield |string |t(:taxYield) |
|tradeTime |int |t(:taxTradeTime) |

### t(:depositNWithdrawHistoryType)
#### t(:cryptoDepositHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|txid |string |t(:taxTxid) |
|depositType |string |t(:taxDepositType) |
|chainType |string |t(:taxChainType) |
|symbol |string |t(:taxSymbol) |
|finalAmount |string |t(:taxFinalAmount) |
|orderTime |int |t(:taxOrderTime) |
|completedTime |int |t(:taxCompletedTime) |

#### t(:p2pDepositHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderID |string |t(:taxOrderID) |
|orderType |string |t(:taxOrderType) |
|p2pSide |string |t(:taxP2PSide) |
|fiat |string |t(:taxFiat) |
|fiatAmount |string |t(:taxFiatAmount) |
|coin |string |t(:taxCoin) |
|coinPrice |string |t(:taxCoinPrice) |
|coinAmount |string |t(:taxCoinAmount) |
|orderTime |int |t(:taxOrderTime) |
|completedTime |int |t(:taxCompletedTime) |

#### t(:fiatDepositWithdrawHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderID |string |t(:taxOrderID) |
|type |string |t(:taxType) |
|fiat |string |t(:taxFiat) |
|depositAmount |string |t(:taxDepositAmount) |
|finalAmount |string |t(:taxFinalAmount) |
|fee |string |t(:taxFee) |
|paymentMethods |string |t(:taxPaymentMethods) |
|orderTime |int |t(:taxOrderTime) |
|completedTime |int |t(:taxCompletedTime) |

#### t(:expressOrderDepositHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderID |string |t(:taxOrderID) |
|side |string |t(:taxExpressOrderDepositSide) |
|fiat |string |t(:taxFiat) |
|depositAmount |string |t(:taxExpressOrderDepositAmount) |
|destinationCoin |string |t(:taxDestinationCoin) |
|coinPrice |string |t(:taxCoinPrice) |
|finalAmount |string |t(:taxFinalAmount) |
|fee |string |t(:taxExpressOrderDepositFee) |
|orderTime |int |t(:taxOrderTime) |
|completedTime |int |t(:taxCompletedTime) |

#### t(:thirdPartyDepositHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderID |string |t(:taxOrderID) |
|txid |string |t(:taxTxid) |
|platform |string |t(:taxPlatform) |
|fiat |string |t(:taxFiat) |
|depositAmount |string |t(:taxDepositAmount) |
|destinationCoin |string |t(:taxDestinationCoin) |
|coinPrice |string |t(:taxCoinPrice) |
|finalAmount |string |t(:taxFinalAmount) |
|orderTime |int |t(:taxOrderTime) |
|completedTime |int |t(:taxCompletedTime) |

#### t(:cryptoWithdrawHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|txid |string |t(:taxTxid) |
|chainType |string |t(:taxChainType) |
|coin |string |t(:taxCoin) |
|finalAmount |string |t(:taxFinalAmount) |
|fee |string |t(:taxCryptoWithdrawFee) |
|orderTime |int |t(:taxOrderTime) |
|completedTime |int |t(:taxCompletedTime) |

#### t(:nftDepositWithdrawalHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId |string |t(:taxOrderID) |
|TxHash |string |t(:taxTxHash) |
|tokenId |string |t(:taxTokenId) |
|transferType |string |t(:taxTransferType) |
|network |string |t(:taxNetwork) |
|feeToken |string |t(:taxFeeToken) |
|tradingFee |string |t(:taxTradingNftFee) |
|orderTime |int |t(:taxOrderTime) |
|completedTime |int |t(:taxCompletedTime) |

### t(:bonusHistoryType)
#### t(:couponHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|coin |string |t(:taxCouponCoin) |
|finalAmount |string |t(:taxCouponFinalAmount) |
|completedTime |int |t(:taxCompletedTime) |

#### t(:bonusHistory)
<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|coin |string |t(:taxBonusCoin) |
|finalAmount |string |t(:taxBonusFinalAmount) |
|completedTime |int |t(:taxCompletedTime) |


### t(:airdropHistoryType)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|coin |string |t(:taxAirdropCoin) |
|finalAmount |string |t(:taxAirdropFinalAmount) |
|transferType |string |t(:taxAirdropTransferType) |
|transferDescription |string |t(:taxTransferDescription) |
|completedTime |int |t(:taxCompletedTime) |
