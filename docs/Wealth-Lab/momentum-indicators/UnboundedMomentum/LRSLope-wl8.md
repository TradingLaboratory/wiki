Measures the slope of the linear regression line over a lookback period, quantifying trend direction and strength. Recommended: Period = 20 · Positive values indicate uptrends; negative values indicate downtrends

```C#

public static LRSlope Series(TimeSeries source, int period, bool logScale = false);
public static double Value(int idx, TimeSeries source, int period);

```