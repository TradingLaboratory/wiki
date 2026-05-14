Returns the lowest value of a price series over a specified lookback period, commonly used to identify support levels, breakdowns, and trailing reference points. Recommended: Period = 20 (short-term) · 50 (medium-term) · 200 (long-term)

```C#
        public static Lowest Series(TimeSeries source, int lookback);
        public static double Value(int idx, TimeSeries source, int lookback);
```