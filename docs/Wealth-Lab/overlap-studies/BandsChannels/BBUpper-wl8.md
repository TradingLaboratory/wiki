The upper Bollinger Band, calculated a specified number of standard deviations above a moving average, used to identify overbought conditions or volatility-based resistance. Recommended: Period = 20 · StdDev = 2.0

```C#
        public static BBUpper Series(
	        TimeSeries source, 
	        int period, 
	        double stdDevs);
	        
        public static double Value(
	        int idx, 
	        TimeSeries source, 
	        int period, 
	        double stdDevs);
```


Код метода:

```C#
#region Assembly WealthLab.Core, Version=8.0.1.0, Culture=neutral, PublicKeyToken=null
// C:\Program Files\Quantacula, LLC\WealthLab 8\WealthLab.Core.dll
#endregion

using System.Collections.Generic;
using WealthLab.Core;

namespace WealthLab.Indicators
{
    public class BBUpper : IndicatorBase
    {
        public BBUpper();
        public BBUpper(TimeSeries source, int period, double stdDevs);

        public override string Name { get; }
        public override string Abbreviation { get; }
        public override string HelpDescription { get; }
        public override string PaneTag { get; }
        public override WLColor DefaultColor { get; }
        public override PlotStyle DefaultPlotStyle { get; }
        public override List<string> Companions { get; }

        public static BBUpper Series(TimeSeries source, int period, double stdDevs);
        public static double Value(int idx, TimeSeries source, int period, double stdDevs);
        public override void Populate();
        protected override void GenerateParameters();
    }
}

```