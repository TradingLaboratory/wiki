## 📊 Список методов для расчёта индикаторов в Wealth-Lab 8 Pro

В Wealth-Lab 8 все встроенные индикаторы находятся в пространстве имён **`WealthLab.Indicators`**. Большинство индикаторов предоставляют статический метод **`Calculate()`** (рекомендуемый в WL8) или **`Series()`** (устаревший, но совместимый с предыдущими версиями). Индикаторы возвращают объекты типа `TimeSeries` или специальные контейнеры с несколькими линиями (например, MACD).

---

### 🔗 Официальная документация
Полный справочник API: **https://www.wealth-lab.com/Support/ApiReference**  
Базовый класс индикаторов: **https://www.wealth-lab.com/Support/ApiReference/IndicatorBase**

---

### 📋 Список основных индикаторов

| № | Название индикатора | Класс / Метод | Сигнатура метода | Описание параметров |
|---|---------------------|---------------|------------------|---------------------|
| **1** | **Simple Moving Average (SMA)** | `SMA.Calculate()` | `TimeSeries SMA.Calculate(TimeSeries source, int period)` | `source` — исходный ряд (обычно `bars.Close`)<br>`period` — период усреднения (например, 20) |
| **2** | **Exponential Moving Average (EMA)** | `EMA.Calculate()` | `TimeSeries EMA.Calculate(TimeSeries source, int period)` | `source` — исходный ряд цен<br>`period` — период сглаживания |
| **3** | **Relative Strength Index (RSI)** | `RSI.Calculate()` | `TimeSeries RSI.Calculate(TimeSeries source, int period)` | `source` — ряд цен для расчёта<br>`period` — период (стандартно 14) |
| **4** | **MACD** | `MACD.Calculate()` | `MACDResult MACD.Calculate(TimeSeries source, int fastPeriod = 12, int slowPeriod = 26, int signalPeriod = 9)` | Возвращает объект `MACDResult` с тремя свойствами:<br>`MACD` — основная линия,<br>`Signal` — сигнальная линия,<br>`Histogram` — гистограмма |
| **5** | **Bollinger Bands** | `BollingerBands.Calculate()` | `BollingerBandsResult BollingerBands.Calculate(TimeSeries source, int period = 20, double stdDev = 2.0)` | Возвращает объект с тремя линиями:<br>`Upper` — верхняя граница,<br>`Middle` — средняя (SMA),<br>`Lower` — нижняя граница |
| **6** | **Average True Range (ATR)** | `ATR.Calculate()` | `TimeSeries ATR.Calculate(BarHistory bars, int period)` | `bars` — полная история баров (нужны High/Low/Close)<br>`period` — период расчёта |
| **7** | **Stochastic Oscillator** | `Stochastic.Calculate()` | `StochasticResult Stochastic.Calculate(BarHistory bars, int kPeriod = 14, int dPeriod = 3, int slowing = 3)` | Возвращает объект с двумя линиями:<br>`K` — быстрая линия %K,<br>`D` — медленная линия %D |
| **8** | **Average Directional Index (ADX)** | `ADX.Calculate()` | `ADXResult ADX.Calculate(BarHistory bars, int period = 14)` | Возвращает объект с тремя компонентами:<br>`ADX` — основной индекс,<br>`DIPlus` — +DI,<br>`DIMinus` — -DI |
| **9** | **Commodity Channel Index (CCI)** | `CCI.Calculate()` | `TimeSeries CCI.Calculate(BarHistory bars, int period = 14)` | `bars` — история с High/Low/Close<br>`period` — период расчёта |
| **10** | **Williams %R** | `WilliamsR.Calculate()` | `TimeSeries WilliamsR.Calculate(BarHistory bars, int period = 14)` | `bars` — история цен<br>`period` — lookback период |
| **11** | **Money Flow Index (MFI)** | `MFI.Calculate()` | `TimeSeries MFI.Calculate(BarHistory bars, int period = 14)` | Требует Volume в данных |
| **12** | **Rate of Change (ROC)** | `ROC.Calculate()` | `TimeSeries ROC.Calculate(TimeSeries source, int period)` | Измеряет процентное изменение цены за период |
| **13** | **Parabolic SAR** | `ParabolicSAR.Calculate()` | `TimeSeries ParabolicSAR.Calculate(BarHistory bars, double acceleration = 0.02, double max = 0.2)` | `acceleration` — шаг ускорения<br>`max` — максимальное значение ускорения |
| **14** | **Ichimoku Cloud** | `Ichimoku.Calculate()` | `IchimokuResult Ichimoku.Calculate(BarHistory bars, int conversionPeriod = 9, int basePeriod = 26, int spanPeriod = 52)` | Возвращает 5 компонентов облака Ишимоку |

---

### 💡 Пример использования в стратегии

```csharp
using WealthLab.Core;
using WealthLab.Indicators;

public class MyStrategy : UserStrategyBase
{
    private TimeSeries sma;
    private TimeSeries rsi;
    private MACDResult macd;

    public override void Initialize(BarHistory bars)
    {
        // SMA с периодом 20
        sma = SMA.Calculate(bars.Close, 20);
        
        // RSI с периодом 14
        rsi = RSI.Calculate(bars.Close, 14);
        
        // MACD со стандартными параметрами
        macd = MACD.Calculate(bars.Close, 12, 26, 9);
        
        // Устанавливаем точку старта (пропускаем бары без данных)
        StartIndex = 26 + 9; // max период из всех индикаторов
    }

    public override void Execute(BarHistory bars, int barNum)
    {
        double price = bars.Close[barNum];
        double currentSMA = sma[barNum];
        double currentRSI = rsi[barNum];
        double macdLine = macd.MACD[barNum];
        double signalLine = macd.Signal[barNum];
        
        // Пример условия: цена выше SMA И RSI в зоне перепроданности
        if (price > currentSMA && currentRSI < 30 && !HasPosition(bars))
        {
            PlaceTrade(bars, TransactionType.Buy, OrderType.Market);
        }
    }
}
```

---

### 🔍 Как найти документацию по конкретному индикатору

Официальные страницы API для каждого индикатора находятся по шаблону:  
**https://www.wealth-lab.com/Support/ApiReference/{ИмяКласса}**

Примеры:
- SMA: https://www.wealth-lab.com/Support/ApiReference/SMA
- RSI: https://www.wealth-lab.com/Support/ApiReference/RSI
- MACD: https://www.wealth-lab.com/Support/ApiReference/MACD
- BollingerBands: https://www.wealth-lab.com/Support/ApiReference/BollingerBands

> 💡 **Совет**: В редакторе кода WealthLab 8 нажмите `F1` при выделенном названии индикатора — откроется справка по этому методу.

---

### ⚠️ Важные замечания

1. **NaN значения**: Индикаторы возвращают `Double.NaN` для первых баров, пока не накопится достаточно данных (например, SMA(20) вернёт NaN для первых 19 баров) [[44]](https://www.wealth-lab.com/Support/ApiReference/IndicatorBase).

2. **StartIndex**: Всегда устанавливайте `StartIndex` в методе `Initialize()`, чтобы избежать обращения к несуществующим значениям:
   ```csharp
   StartIndex = System.Math.Max(smaPeriod, rsiPeriod);
   ```

3. **Доступ к значениям**: Получайте значение индикатора через индексатор:
   ```csharp
   double value = indicator[barNum]; // Текущее значение
   double prevValue = indicator[barNum - 1]; // Предыдущее значение
   ```

4. **Для индикаторов с несколькими линиями** (MACD, Bollinger Bands) используйте свойства возвращаемого объекта:
   ```csharp
   double upperBand = bb.Upper[barNum];
   double macdValue = macd.MACD[barNum];
   ```

---

### 📚 Дополнительные ресурсы

- Официальный форум (раздел Technical Indicators): https://www.wealth-lab.com/Forum/
- Примеры стратегий с индикаторами: https://www.wealth-lab.com/Discussions
- Видеоуроки по индикаторам: YouTube-канал WealthLab (поиск "WealthLab U. Lesson")

Этот список охватывает ~95% наиболее используемых индикаторов в алгоритмической торговле. Для специализированных индикаторов (например, из расширений TASC или Community) синтаксис аналогичен — проверяйте документацию конкретного расширения.