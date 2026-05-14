# ATR - wl8 (standard)

## Описание ATR из программы:

```csharp
ATR(BarHistory source, int period);
```

Measures market volatility by averaging the true range over a specified period, without regard to price direction. Recommended: Period = 14 · Used for position sizing and stop placement

## Класс ATR из wl8

```csharp

#region Assembly WealthLab.Core, Version=8.0.1.0, Culture=neutral, PublicKeyToken=null
// C:\Program Files\Quantacula, LLC\WealthLab 8\WealthLab.Core.dll
#endregion

using WealthLab.Core;

namespace WealthLab.Indicators
{
    public class ATR : IndicatorBase
    {
        public ATR();
        public ATR(BarHistory source, int period);

        public override string Name { get; }
        public override string Abbreviation { get; }
        public override string HelpDescription { get; }
        public override string PaneTag { get; }
        public override WLColor DefaultColor { get; }

        public static ATR Series(BarHistory source, int period);
        public override bool CalculatePartialValue();
        public override void Populate();
        protected override void GenerateParameters();
    }
}

```

