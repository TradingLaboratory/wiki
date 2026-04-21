# AngleBetweenInd (PowerPack)
Measures the directional alignment between two data series by calculating the angle between their recent values over a rolling lookback period. Smaller angles indicate stronger directional agreement, while larger angles indicate divergence or opposition. Recommended: Period = 20 · Values below ~30° suggest alignment; above ~120° suggest strong divergence


```C#

  public static AngleBetweenInd Series(BarHistory source, TimeSeries ts1, TimeSeries ts2, int period)
  
  public static double Value(int idx, TimeSeries ts1, TimeSeries ts2, int period)

```
