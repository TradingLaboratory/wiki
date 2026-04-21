# MAMA (MESA Adaptive Moving Average)

## Общая информация

| Поле | Значение |
|------|----------|
| **Название** | MESA Adaptive Moving Average |
| **Аббревиатура** | MAMA |
| **Автор** | John Ehlers |
| **Источник** | Technical Analysis of Stocks & Commodities, September 2001 |
| **Панель** | Price |
| **Цвет по умолчанию** | Красный (WLColor.Red) |
| **Тип** | Сглаживающий индикатор (Smoother) |
| **Namespace** | WealthLab.TASC |
| **Период прогрева** | 45 баров |
| **Связанные индикаторы** | FAMA |

---

## HelpDescription

### EN
MESA Adaptive Moving Average by John Ehlers from the September 2001 issue of Technical Analysis of Stocks & Commodities magazine

### RU
Адаптивная скользящая средняя MESA от Джона Эрлерса из сентябрьского выпуска 2001 года журнала Technical Analysis of Stocks & Commodities

---

## Описание

**MAMA (MESA Adaptive Moving Average)** — это адаптивный индикатор тренда, разработанный Джоном Эрлерсом на основе цикла MESA (Maximum Entropy Spectral Analysis). 

### Логика работы:
- Индикатор адаптируется к изменениям рыночного цикла
- Использует два лимита (быстрый и медленный) для контроля скорости адаптации
- Вычисляется с помощью вспомогательного класса `MamaFamaCalculator`
- Реализует механизм кэширования для оптимизации производительности
- Требует 45 периодов для прогрева перед выдачей значимых значений

### Особенности:
- Автоматически подстраивается под волатильность рынка
- Меньше запаздывает по сравнению с традиционными скользящими средними
- Работает в паре с индикатором FAMA (Following Adaptive Moving Average)

---

## Параметры

| Параметр | Тип | Значение по умолчанию | Описание |
|----------|-----|----------------------|----------|
| **Source** | TimeSeries | Close | Источник данных для расчёта |
| **Fast Limit** | Double | 0.5 | Верхний предел адаптации (быстрый) |
| **Slow Limit** | Double | 0.05 | Нижний предел адаптации (медленный) |

---

## Примеры

### Базовое использование
```csharp
using WealthLab.TASC;
using WealthLab.Core;

// Создание индикатора MAMA с параметрами по умолчанию
var mama = MAMA.Series(barSeries.Close, 0.5, 0.05);

// Добавление на график
PlotSeries(PricePane, mama, 2, WLColor.Red);
```

### Использование с другими параметрами
```csharp
// MAMA с изменёнными лимитами
var mamaFast = MAMA.Series(barSeries.Close, 0.7, 0.1);
var mamaSlow = MAMA.Series(barSeries.Close, 0.3, 0.03);

// Получение значения на текущем баре
double currentValue = mama[barSeries.Count - 1];
```

### Совместное использование с FAMA
```csharp
// MAMA и FAMA для торговых сигналов
var mama = MAMA.Series(barSeries.Close);
var fama = FAMA.Series(barSeries.Close);

// Сигнал на покупку: MAMA пересекает FAMA снизу вверх
if (CrossOver(bar, mama, fama))
{
    // Логика покупки
}
```

---

## Важные замечания

### Кэширование
- Индикатор использует встроенный механизм кэширования WealthLab
- Ключ кэша формируется на основе параметров Fast Limit и Slow Limit
- Повторные вызовы с теми же параметрами возвращают кэшированный объект

### Ограничения
- Требуется минимум 45 баров для корректной работы (PrefillNan(45))
- Первые 45 значений будут равны NaN
- Зависит от внешнего класса `MamaFamaCalculator` для вычислений

### Рекомендации
- Fast Limit должен быть больше Slow Limit
- Типичные значения: Fast Limit = 0.5, Slow Limit = 0.05
- Для более агрессивной адаптации увеличьте Fast Limit
- Для более плавной линии уменьшите Fast Limit и увеличьте Slow Limit

### Производительность
- Кэширование снижает нагрузку при многократном использовании
- Избегайте создания новых экземпляров в циклах без необходимости
- Используйте статический метод `Series()` для автоматического кэширования