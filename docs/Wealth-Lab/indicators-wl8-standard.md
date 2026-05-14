# Indicators.wl8.standard

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
│   │   ├── [IBS](IBS-wl8.md)
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
│   │   ├── [LRSlope](LRSLope-wl8.md)
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
│   │   ├── [SMA](SMA-wl8.md)
│   │   ├── [FastSMA](FastSMA-wl8.md)
│   │   ├── EMA.cs
│   │   ├── WMA.cs
│   │   ├── SMMA.cs
│   │   ├── WilderMA.cs
│   │   ├── GMA.cs
│   │   └── FIR.cs
│   ├── BandsChannels/
│   │   ├── [BBLower](BBLower-wl8.md).cs
│   │   ├── [BBUpper](BBUpper-wl8.md).cs
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
│       ├── [Lowest](Lowest-wl8.md)
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
│   ├── [[atr]].cs
│   ├── [[raw/documentation/wiki-indicators/docs/wealth-lab/volatility-indicators/atrp]]
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
│   ├── [MathIndOpInd](MathIndOpInd-wl8.md)
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