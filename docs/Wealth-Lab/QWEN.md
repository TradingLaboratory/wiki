# QWEN.md — Контекст директории Wealth-Lab

## 📋 Обзор директории

**Путь:** `C:\Users\vdv-v\source\repos\wiki\docs\Wealth-Lab\`

Эта директория содержит документацию по **Wealth-Lab 8 Pro** — платформе для разработки и тестирования торговых стратегий на рынке акций, фьючерсов и криптовалют. Документация является частью проекта **wiki** (MkDocs) и служит справочным материалом для разработчиков стратегий.

---

## 🏗️ Структура директории

### Корневые файлы

| Файл                         | Описание                                                                                           |
| ---------------------------- | -------------------------------------------------------------------------------------------------- |
| `wl8-references.md`          | Сборник ссылок: официальная документация, форум, Discord, YouTube-канал WealthLab                  |
| `wl8-indicators.md`          | Полный справочник индикаторов Wealth-Lab 8 с примерами кода и сигнатурами методов                  |
| `wl8-indicators-ungroop.md`  | Список всех доступных индикаторов в пространстве имён `WealthLab.Indicators` (алфавитный перечень) |
| `Indicators.wl8.statdart.md` | Структура каталога индикаторов по категориям (Momentum, Overlap, Volume, Volatility и т.д.)        |
| `Indicators.wl8.TASC.md`     | Маркер для индикаторов из журнала TASC (Technical Analysis of Stocks & Commodities)                |
| `MAMA-task.md`               | Документация по индикатору MAMA (MESA Adaptive Moving Average) от John Ehlers                      |
| `FAMA-task.md`               | Документация по индикатору FAMA (Following Adaptive Moving Average) от John Ehlers                 |

### Поддиректории (категории индикаторов)

```
Wealth-Lab/
├── IndicatorBaseClasses/       # Базовые классы индикаторов (IndicatorBase, IndicatorFactory и др.)
├── MathOperators/              # Математические операции над индикаторами
├── MomentumIndicators/         # Индикаторы момента
│   ├── Oscillators/            # Осцилляторы (RSI, Stochastic, CCI, Williams %R и др.)
│   ├── TrendDirection/         # Направление тренда (Aroon, ADX, DI+)
│   ├── TrendStrength/          # Сила тренда (ADX, TrendMeter, TrendScore)
│   └── UnboundedMomentum/      # Неограниченные осцилляторы (MACD, ROC, Momentum)
├── CycleIndicators/            # Циклические индикаторы (Hurst, PeakTrough)
├── OverlapStudies/             # Накладывающиеся индикаторы (скользящие средние, полосы, уровни)
├── VolumeIndicators/           # Объёмные индикаторы (OBV, AccumDist, CMF, Volume Profile)
├── VolatilityIndicators/       # Индикаторы волатильности (ATR, StdDev, Choppiness)
├── StatisticFunctions/         # Статистические функции (Corr, RSquared, ZScore)
├── PriceTransform/             # Преобразования цены (WAP, SymbolData, обёртки)
└── OtherIndicators/            # Прочие индикаторы (Alpha, Beta, CSI, Gap и др.)
```

---

## 📚 Ключевые темы документации

### 1. Базовые классы индикаторов

Все индикаторы Wealth-Lab 8 наследуются от `IndicatorBase` и используют паттерн Factory для создания экземпляров.

**Основные классы:**

- `IndicatorBase<T>` — базовый класс для всех индикаторов
- `IndicatorFactory` — фабрика для создания индикаторов
- `IndicatorEventArgs` — события индикаторов
- `IndOnInd` — индикатор на индикаторе
- `MathIndOpInd` — математические операции между индикаторами

### 2. Математические операции

Категория `MathOperators` предоставляет операции над индикаторами:

| Операция       | Описание                                       |
| -------------- | ---------------------------------------------- |
| `Abs`          | Модуль значения индикатора                     |
| `Sum`          | Суммирование значений за период                |
| `LogReturn`    | Логарифмическая доходность                     |
| `MathIndOpInd` | Операции между двумя индикаторами (+, -, *, /) |

### 3. Адаптивные индикаторы (TASC)

Индикаторы из журнала **Technical Analysis of Stocks & Commodities**:

- **MAMA** (MESA Adaptive Moving Average) — адаптивная скользящая средняя на основе спектрального анализа
- **FAMA** (Following Adaptive Moving Average) — следующая адаптивная средняя (всегда следует за MAMA)

**Параметры MAMA/FAMA:**

- `Fast Limit` (по умолчанию 0.5) — быстрый лимит адаптации
- `Slow Limit` (по умолчанию 0.05) — медленный лимит адаптации
- Период прогрева: 45 баров

**Пример использования:**

```csharp
using WealthLab.TASC;

var mama = MAMA.Series(bars.Close, 0.5, 0.05);
var fama = FAMA.Series(bars.Close, 0.5, 0.05);

// Сигнал: пересечение MAMA и FAMA
if (CrossOver(bar, mama, fama))
{
    // Покупка
}
```

### 4. Основные группы индикаторов

#### Momentum Indicators (Индикаторы момента)

| Подкатегория          | Индикаторы                                                                                                                    |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| **Oscillators**       | RSI, CutlersRSI, Stochastic, CCI, Williams %R, MFI, UltimateOsc, CMO, KDJ, RVI, SMI, PMO, RMI, DSS, ChaikinOsc, IBS, TSI, VSI |
| **UnboundedMomentum** | MACD, MACDClassic, MACDHist, ROC, ROC100, Momentum, KVO, LR, LRSlope, TSF                                                     |
| **TrendDirection**    | AroonUp/Down, AroonOscillator, DI+, DI-, DIP, DirectionalMovement, UpDown, RisingFalling                                      |
| **TrendStrength**     | ADX, ADXR, DX, MinerviniTrendRatio, TrendMeter, TrendScore                                                                    |

#### Overlap Studies (Накладывающиеся индикаторы)

| Подкатегория        | Индикаторы                                                                                                                   |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| **MovingAverages**  | SMA, FastSMA, EMA, WMA, SMMA, WilderMA, GMA, FIR                                                                             |
| **BandsChannels**   | Bollinger Bands (Lower/Upper/Width), ATR Bands, Acceleration Bands, Projection Bands, Donchian, Keltner, Envelope, Camarilla |
| **TrendIndicators** | Parabolic SAR, WilderVolStop, TrendLine, SwingHi/Lo, ZigZag                                                                  |
| **PriceLevels**     | Highest/Lowest, ATH/ATL, PercentOffATH, временные метки                                                                      |

#### Volume Indicators (Объёмные индикаторы)

OBV, AccumDist, CMF, EMV, VPT, UpDownVolume, VolumeProfileIndicator, VChart, VolPro (Volume Profile nodes)

#### Volatility Indicators (Индикаторы волатильности)

ATR, ATRP, Choppiness, StdDev, StdError, HV (Historical Volatility), Squeeze, TR, ER (Efficiency Ratio)

#### Cycle Indicators (Циклические индикаторы)

Hurst (индекс Хёрста), PeakTrough, PeakTroughCalculator

#### Statistic Functions (Статистические функции)

Corr (корреляция), RSquared, MeanAbsDev, Median, Mode, Density, PctRank, ZScore, DyMol, Fred, Fundamental, MarketState, USTYield

---

## 💻 Примеры кода

### Базовое использование индикатора

```csharp
using WealthLab.Core;
using WealthLab.Indicators;

public class MyStrategy : UserStrategyBase
{
    private TimeSeries sma;
    private TimeSeries rsi;

    public override void Initialize(BarHistory bars)
    {
        // SMA с периодом 20
        sma = SMA.Calculate(bars.Close, 20);

        // RSI с периодом 14
        rsi = RSI.Calculate(bars.Close, 14);

        // Установка StartIndex (пропуск баров без данных)
        StartIndex = 20;
    }

    public override void Execute(BarHistory bars, int barNum)
    {
        double currentSMA = sma[barNum];
        double currentRSI = rsi[barNum];
        double price = bars.Close[barNum];

        // Условие: цена выше SMA И RSI < 30 (перепроданность)
        if (price > currentSMA && currentRSI < 30 && !HasPosition(bars))
        {
            PlaceTrade(bars, TransactionType.Buy, OrderType.Market);
        }
    }
}
```

### Индикаторы с несколькими линиями

```csharp
// MACD
var macd = MACD.Calculate(bars.Close, 12, 26, 9);
double macdLine = macd.MACD[barNum];
double signalLine = macd.Signal[barNum];
double histogram = macd.Histogram[barNum];

// Bollinger Bands
var bb = BollingerBands.Calculate(bars.Close, 20, 2.0);
double upper = bb.Upper[barNum];
double middle = bb.Middle[barNum];
double lower = bb.Lower[barNum];

// ADX
var adx = ADX.Calculate(bars, 14);
double adxValue = adx.ADX[barNum];
double diPlus = adx.DIPlus[barNum];
double diMinus = adx.DIMinus[barNum];
```

### Математические операции над индикаторами

```csharp
// Разница между двумя индикаторами
var diff = new MathIndOpInd(indicator1, indicator2, MathOperation.Subtract);

// Модуль значения
var abs = Abs.Calculate(indicator);

// Сумма за период
var sum = Sum.Calculate(indicator, period);
```

---

## 🔗 Полезные ссылки

### Официальная документация

- **API Reference:** https://www.wealth-lab.com/Support/ApiReference
- **IndicatorBase:** https://www.wealth-lab.com/Support/ApiReference/IndicatorBase
- **F1 в редакторе:** Нажмите F1 на названии индикатора для открытия справки

### Сообщество и поддержка

- **Форум:** https://www.wealth-lab.com/Forum/
- **Discord:** https://discord.gg/sqFQESRaAW
- **YouTube:** https://www.youtube.com/@wealthlab

### Обучающие материалы

- **Lesson 1 (Charting & Navigation):** https://www.youtube.com/watch?v=hTl2gTUJrMY
- **Lesson 4 (Strategy Building Blocks):** https://www.youtube.com/watch?v=k_1gdo-KkzI

---

## ⚠️ Важные замечания

### 1. NaN значения

Индикаторы возвращают `Double.NaN` для первых баров, пока не накопится достаточно данных:

```csharp
// SMA(20) вернёт NaN для первых 19 баров
var sma = SMA.Calculate(bars.Close, 20);
// sma[0]...sma[18] = NaN
// sma[19] = первое значение
```

### 2. StartIndex

Всегда устанавливайте `StartIndex` в методе `Initialize()`:

```csharp
public override void Initialize(BarHistory bars)
{
    var sma20 = SMA.Calculate(bars.Close, 20);
    var rsi14 = RSI.Calculate(bars.Close, 14);

    // StartIndex = максимальный период прогрева
    StartIndex = 20;
}
```

### 3. Кэширование

Wealth-Lab автоматически кэширует индикаторы при использовании статических методов `Series()` или `Calculate()`:

```csharp
// Повторный вызов с теми же параметрами вернёт объект из кэша
var sma1 = SMA.Calculate(bars.Close, 20);
var sma2 = SMA.Calculate(bars.Close, 20);
// sma1 == sma2 (один и тот же объект)
```

### 4. Namespace для TASC индикаторов

Для индикаторов из журнала TASC требуется отдельный namespace:

```csharp
using WealthLab.TASC;  // Для MAMA, FAMA и других TASC-индикаторов
using WealthLab.Indicators;  // Для стандартных индикаторов
```

### 5. Доступ к значениям

Используйте индексатор для получения значений:

```csharp
// Текущее значение
double current = indicator[barNum];

// Предыдущее значение
double previous = indicator[barNum - 1];

// Проверка на NaN
if (!double.IsNaN(indicator[barNum]))
{
    // Корректное значение
}
```

---

## 📖 Связанные документы

- [[wl8-indicators]] — Полный список методов для расчёта индикаторов
- [[wl8-references]] — Сборник полезных ссылок по Wealth-Lab 8
- [[MAMA-task]] — Детальная документация по MAMA
- [[FAMA-task]] — Детальная документация по FAMA
- [[MathIndOpInd-wl8]] — Математические операции над индикаторами

---

## 🎯 Типовые сценарии использования

### 1. Добавление документации нового индикатора

```markdown
1. Создать файл в соответствующей поддиректории (например, MomentumIndicators/Oscillators/RSI-wl8.md)
2. Использовать шаблон:
   - Общая информация (таблица с параметрами)
   - HelpDescription (EN/RU)
   - Описание (логика работы)
   - Параметры (таблица)
   - Примеры кода
   - Важные замечания
3. Обновить Indicators.wl8.statdart.md (добавить в структуру)
```

### 2. Поиск индикатора по категории

```markdown
1. Открыть Indicators.wl8.statdart.md
2. Найти нужную категорию (например, MomentumIndicators/Oscillators)
3. Перейти в соответствующую поддиректорию
4. Найти файл с документацией (имя файла содержит название индикатора)
```

### 3. Создание стратегии с несколькими индикаторами

```csharp
// 1. Определить необходимые индикаторы
// 2. Рассчитать в Initialize()
// 3. Установить StartIndex = max(периоды индикаторов)
// 4. Использовать в Execute() для генерации сигналов
```

---

*Последнее обновление: 12 марта 2026 г.*
