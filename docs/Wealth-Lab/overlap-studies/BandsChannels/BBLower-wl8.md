The lower Bollinger Band, calculated a specified number of standard deviations below a moving average, used to identify oversold conditions or volatility-based support. Recommended: Period = 20 · StdDev = 2.0

```C#

        public static BBLower Series(
	        TimeSeries source, 
	        int period, 
	        double stdDevs);
	        
        public static double Value(
	        int idx, 
	        TimeSeries source, 
	        int period, 
	        double stdDevs);
        
```