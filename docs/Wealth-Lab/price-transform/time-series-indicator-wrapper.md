# TimeSeriesIndicatorWrapper

## Описание из Wealth-Lab



## код индикатора

```csharp
#region Assembly WealthLab.Core, Version=8.0.1.0, Culture=neutral, PublicKeyToken=null
// C:\Program Files\Quantacula, LLC\WealthLab 8\WealthLab.Core.dll
#endregion

using WealthLab.Core;

namespace WealthLab.Indicators
{
    public class TimeSeriesIndicatorWrapper : IndicatorBase
    {
        public TimeSeriesIndicatorWrapper();
        public TimeSeriesIndicatorWrapper(TimeSeries series);
        public TimeSeriesIndicatorWrapper(TimeSeries series, string description, string paneTag);

        public override string Name { get; }
        public override string Abbreviation { get; }
        public override string HelpDescription { get; }
        public override string PaneTag { get; }
        public override bool IsPrivate { get; }

        public override void Populate();
    }
}
```