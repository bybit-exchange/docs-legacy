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

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|respExample |string | |


### t(:bonusHistoryType)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|respExample |string | |


### t(:airdropHistoryType)

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|respExample |string | |
