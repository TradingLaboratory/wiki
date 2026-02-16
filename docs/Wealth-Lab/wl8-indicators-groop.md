## Негруппированный список индикаторов:

WealthLab.Indicators
├── Abs
├── AccelerationBandsLower
├── AccelerationBandsUpper
├── AccumDist
├── ADX
├── ADXR
├── Alpha
├── AroonDown
├── AroonOscillator
├── AroonUp
├── ATHigh
├── ATLow
├── ATR
├── ATRBandLower
├── ATRBandUpper
├── ATRP
├── BarHistoryIndicatorWrapper
├── BarOfTheDay
├── BarsSince
├── BBLower
├── BBUpper
├── BBWidth
├── Beta
├── Camarilla
├── CCI
├── ChaikinOsc
├── Choppiness
├── CMF
├── CMO
├── ConsecCandle
├── ConsecDown
├── ConsecUp
├── Coppock
├── Corr
├── CrossOverBar
├── CrossoverIndValue
├── CrossUnderBar
├── CrossUnderValueBar
├── CSI
├── CutlersRSI
├── DayOfMth
├── DayOfWk
├── DayOfYr
├── Density
├── DILminus
├── DILplus
├── DIP
├── DirectionalMovement
├── DonchianMid
├── DSS
├── DX
├── DyMol
├── EMA
├── EMV
├── EnvelopeLower
├── EnvelopeUpper
├── ER
├── FastSMA
├── FIR
├── Fred
├── Fundamental
├── FundamentalRatio
├── Gap
├── GMA
├── Highest
├── HighestGranularClose
├── HiLoLimit
├── HourOfDay
├── Hurst
├── HV
├── IBS
├── IndicatorBase
├── IndicatorEventArgs
├── IndicatorFactory
├── IndOnInd
├── KaseCD_Oscillator
├── KasePeakOscillator
├── KDJ
├── KeltnLower
├── KeltnUpper
├── KST
├── KVO
├── LogReturn
├── Lowest
├── LowestGranularClose
├── LR
├── LRSlope
├── MACD
├── MACDClassic
├── MACDHist
├── MansfieldRelativeStrength
├── MarketState
├── MassIndex
├── MathIndOpInd
├── MathIndOpValue
├── MathOperation
├── MathOperationExtensions
├── MeanAbsDev
├── Median
├── MFI
├── MinerviniTrendRatio
├── MinOfDay
├── MnthOfYr
├── Mode
├── Momentum
├── NamedSeries
├── NegativeCloses
├── OBV
├── OffsetInd
├── PBFastOsc
├── PBSlowOsc
├── PctRank
├── PeakTrough
├── PeakTroughCalculator
├── PeakTroughReversalType
├── PeakTroughType
├── PercentOffATH
├── PMO
├── PositiveCloses
├── ProjectionBandLower
├── ProjectionBandUpper
├── PSAR
├── QStick
├── RealRelativeStrength
├── RisingFalling
├── RMI
├── ROC
├── ROC100
├── RSI
├── RsiWilliamsVixFix
├── RSquared
├── RVI
├── ScaledInd
├── SeriesAboveOrBelow
├── SeriesAboveOrBelowValue
├── SMA
├── SMI
├── SMMA
├── SmoothedInd
├── SpecialK
├── SplitReverse
├── Squeeze
├── StdDev
├── StdError
├── StochD
├── StochDSlow
├── StochK
├── StochKSlow
├── Stoch├── Sum
├── SwingHi
├── SwingHiLo
├── SwingLo
├── SymbolData
├── SymbolInd
├── TimeOfDay
├── TimeSeriesIndicatorWrapper
├── TR
├── TradingDaysLeft
├── TradingDaysSince
├── TransformerIndicatorBase
├── TrendLine
├── TrendMeter
├── TrendScore
├── TSF
├── TSI
├── Turnover
├── UltimateOsc
├── UpDown
├── UpDownVolume
├── USTYield
├── VChart
├── VKBandLower
├── VKBandUpper
├── VKWBandLower
├── VKWBandUpper
├── VolProHighNode
├── VolProLowNodeLower
├── VolProLowNodeUpper
├── VolumeProfileCacheInfo
├── VolumeProfileIndicator
├── VPT
├── VSI
├── WAP
├── WilderMA
├── WilderVolStop
├── WilliamsPctR
├── WMA
├── ZigZag
├── ZigZagHL
├── ZScore


## Сгруппированный список

Indicators/
├── MomentumIndicators/
│   ├── Oscillators/
│   │   ├── RSI.cs
│   │   ├── CutlersRSI.cs
│   │   ├── RsiWilliamsVixFix.cs
│   │   ├── Stoch.cs
│   │   ├── StochK.cs
│   │   ├── StochD.cs
│   │   ├── StochKSlow.cs
│   │   ├── StochDSlow.cs
│   │   ├── CCI.cs
│   │   ├── WilliamsPctR.cs
│   │   ├── MFI.cs
│   │   ├── UltimateOsc.cs
│   │   ├── CMO.cs
│   │   ├── KDJ.cs
│   │   ├── KaseCD_Oscillator.cs
│   │   ├── KasePeakOscillator.cs
│   │   ├── RVI.cs
│   │   ├── SMI.cs
│   │   ├── PMO.cs
│   │   ├── RMI.cs
│   │   ├── DSS.cs
│   │   ├── ChaikinOsc.cs
│   │   ├── IBS.cs
│   │   ├── ConsecUp.cs
│   │   ├── ConsecDown.cs
│   │   ├── ConsecCandle.cs
│   │   ├── Coppock.cs
│   │   ├── MassIndex.cs
│   │   ├── SpecialK.cs
│   │   ├── TSI.cs
│   │   └── VSI.cs
│   ├── UnboundedMomentum/
│   │   ├── MACD.cs
│   │   ├── MACDClassic.cs
│   │   ├── MACDHist.cs
│   │   ├── ROC.cs
│   │   ├── ROC100.cs
│   │   ├── Momentum.cs
│   │   ├── KVO.cs
│   │   ├── LR.cs
│   │   ├── LRSlope.cs
│   │   ├── TSF.cs
│   │   ├── PBFastOsc.cs
│   │   └── PBSlowOsc.cs
│   ├── TrendDirection/
│   │   ├── AroonUp.cs
│   │   ├── AroonDown.cs
│   │   ├── AroonOscillator.cs
│   │   ├── DILplus.cs
│   │   ├── DILminus.cs
│   │   ├── DIP.cs
│   │   ├── DirectionalMovement.cs
│   │   ├── UpDown.cs
│   │   └── RisingFalling.cs
│   └── TrendStrength/
│       ├── ADX.cs
│       ├── ADXR.cs
│       ├── DX.cs
│       ├── MinerviniTrendRatio.cs
│       ├── TrendMeter.cs
│       └── TrendScore.cs
├── OverlapStudies/
│   ├── MovingAverages/
│   │   ├── [SMA](SMA-wl8).cs
│   │   ├── FastSMA.cs
│   │   ├── EMA.cs
│   │   ├── WMA.cs
│   │   ├── SMMA.cs
│   │   ├── WilderMA.cs
│   │   ├── GMA.cs
│   │   └── FIR.cs
│   ├── BandsChannels/
│   │   ├── [BBLower](BBLower-wl8).cs
│   │   ├── [BBUpper](BBUpper-wl8).cs
│   │   ├── BBWidth.cs
│   │   ├── ATRBandLower.cs
│   │   ├── ATRBandUpper.cs
│   │   ├── AccelerationBandsLower.cs
│   │   ├── AccelerationBandsUpper.cs
│   │   ├── ProjectionBandLower.cs
│   │   ├── ProjectionBandUpper.cs
│   │   ├── VKBandLower.cs
│   │   ├── VKBandUpper.cs
│   │   ├── VKWBandLower.cs
│   │   ├── VKWBandUpper.cs
│   │   ├── EnvelopeLower.cs
│   │   ├── EnvelopeUpper.cs
│   │   ├── Camarilla.cs
│   │   ├── DonchianMid.cs
│   │   ├── HiLoLimit.cs
│   │   ├── KeltnLower.cs
│   │   └── KeltnUpper.cs
│   ├── TrendIndicators/
│   │   ├── PSAR.cs
│   │   ├── WilderVolStop.cs
│   │   ├── TrendLine.cs
│   │   ├── SwingHi.cs
│   │   ├── SwingLo.cs
│   │   ├── SwingHiLo.cs
│   │   ├── ZigZag.cs
│   │   └── ZigZagHL.cs
│   └── PriceLevels/
│       ├── Highest.cs
│       ├── HighestGranularClose.cs
│       ├── Lowest.cs
│       ├── LowestGranularClose.cs
│       ├── ATHigh.cs
│       ├── ATLow.cs
│       ├── PercentOffATH.cs
│       ├── MinOfDay.cs
│       ├── MnthOfYr.cs
│       ├── DayOfMth.cs
│       ├── DayOfWk.cs
│       ├── DayOfYr.cs
│       ├── HourOfDay.cs
│       └── TimeOfDay.cs
├── CycleIndicators/
│   ├── Hurst.cs
│   ├── PeakTrough.cs
│   └── PeakTroughCalculator.cs
├── VolumeIndicators/
│   ├── OBV.cs
│   ├── AccumDist.cs
│   ├── CMF.cs
│   ├── EMV.cs
│   ├── VPT.cs
│   ├── UpDownVolume.cs
│   ├── VolumeProfileIndicator.cs
│   ├── VChart.cs
│   ├── VolProHighNode.cs
│   ├── VolProLowNodeLower.cs
│   ├── VolProLowNodeUpper.cs
│   └── VolumeProfileCacheInfo.cs
├── VolatilityIndicators/
│   ├── ATR.cs
│   ├── ATRP.cs
│   ├── Choppiness.cs
│   ├── StdDev.cs
│   ├── StdError.cs
│   ├── HV.cs
│   ├── Squeeze.cs
│   ├── TR.cs
│   └── ER.cs
├── StatisticFunctions/
│   ├── Corr.cs
│   ├── RSquared.cs
│   ├── MeanAbsDev.cs
│   ├── Median.cs
│   ├── Mode.cs
│   ├── Density.cs
│   ├── PctRank.cs
│   ├── ZScore.cs
│   ├── DyMol.cs
│   ├── Fred.cs
│   ├── Fundamental.cs
│   ├── FundamentalRatio.cs
│   ├── MarketState.cs
│   └── USTYield.cs
├── MathOperators/
│   ├── Abs.cs
│   ├── Sum.cs
│   └── LogReturn.cs
├── PriceTransform/
│   ├── WAP.cs
│   ├── SymbolData.cs
│   ├── SymbolInd.cs
│   ├── NamedSeries.cs
│   ├── TimeSeriesIndicatorWrapper.cs
│   └── BarHistoryIndicatorWrapper.cs
├── IndicatorBaseClasses/
│   ├── IndicatorBase.cs
│   ├── IndicatorEventArgs.cs
│   ├── IndicatorFactory.cs
│   ├── IndOnInd.cs
│   ├── MathIndOpInd.cs
│   ├── MathIndOpValue.cs
│   ├── MathOperation.cs
│   ├── MathOperationExtensions.cs
│   ├── OffsetInd.cs
│   ├── ScaledInd.cs
│   ├── SeriesAboveOrBelow.cs
│   ├── SeriesAboveOrBelowValue.cs
│   ├── SplitReverse.cs
│   └── TransformerIndicatorBase.cs
└── OtherIndicators/
    ├── Alpha.cs
    ├── Beta.cs
    ├── BarOfTheDay.cs
    ├── BarsSince.cs
    ├── CrossOverBar.cs
    ├── CrossoverIndValue.cs
    ├── CrossUnderBar.cs
    ├── CrossUnderValueBar.cs
    ├── CSI.cs
    ├── Gap.cs
    ├── NegativeCloses.cs
    ├── PositiveCloses.cs
    ├── TradingDaysLeft.cs
    ├── TradingDaysSince.cs
    ├── Turnover.cs
    ├── MansfieldRelativeStrength.cs
    ├── RealRelativeStrength.cs
    ├── QStick.cs
    ├── KST.cs
    └── SmoothedInd.cs