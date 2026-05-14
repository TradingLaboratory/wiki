A computationally optimized Simple Moving Average that produces the same values as an SMA while updating more efficiently, making it suitable for strategies with many symbols or indicators. Recommended: Periods = 20 (short), 50 (medium), 200 (long)

```C#

        public static FastSMA Series(TimeSeries source, int period);
        public static double Value(int bar, TimeSeries ds, int period);

```