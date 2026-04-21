# FAMA (Following Adaptive Moving Average)

## 📋 Общая информация

| Параметр                | Значение                                                  |
| ----------------------- | --------------------------------------------------------- |
| **Полное название**     | Following Adaptive Moving Average                         |
| **Аббревиатура**        | FAMA                                                      |
| **Автор**               | John Ehlers                                               |
| **Источник**            | Technical Analysis of Stocks & Commodities, Сентябрь 2001 |
| **Панель отображения**  | Price (ценовая)                                           |
| **Цвет по умолчанию**   | Синий (Blue)                                              |
| **Тип**                 | Сглаживающий индикатор (Smoother)                         |
| **Связанный индикатор** | MAMA (MESA Adaptive Moving Average)                       |
| **Период прогрева**     | 45 баров (PrefillNan)                                     |
| **Namespace**           | `WealthLab.TASC`                                          |
|                         |                                                           |

---

## 📖 HelpDescription

> **English:**  
> Following Adaptive Moving Average by John Ehlers from the September 2001 issue of Technical Analysis of Stocks & Commodities magazine
>
> **Русский:**  
> Адаптивная скользящая средняя следования от Джона Эрлерса из журнала Technical Analysis of Stocks & Commodities, выпуск за сентябрь 2001 года

---

## 🎯 Описание

**FAMA** — это адаптивная скользящая средняя, разработанная Джоном Эрлерсом. Индикатор автоматически подстраивается под волатильность рынка, используя два лимита (быстрый и медленный) для адаптации скорости реакции на изменения цены.

FAMA всегда следует за MAMA и используется в паре с ним для генерации торговых сигналов (пересечения MAMA и FAMA).

---

## ⚙️ Параметры

| № | Название | Тип | Значение по умолчанию | Описание |
|---|----------|-----|----------------------|----------|
| 1 | Source | TimeSeries | `PriceComponent.Close` | Источник данных (цена) |
| 2 | Fast Limit | Double | `0.5` | Быстрый лимит адаптации |
| 3 | Slow Limit | Double | `0.05` | Медленный лимит адаптации |

---

## 💻 Примеры использования

### Базовое создание индикатора

```csharp
using WealthLab.Indicators;
using WealthLab.TASC;

// Создание индикатора FAMA
var fama = FAMA.Series(Bars.Close, 0.5, 0.05);
```

### Использование в стратегии

```csharp
public class FamaStrategy : UserStrategyBase
{
    public override void Execute(Bar bar)
    {
        // Получаем значения MAMA и FAMA
        var mama = MAMA.Series(Bars.Close, 0.5, 0.05);
        var fama = FAMA.Series(Bars.Close, 0.5, 0.05);
        
        // Сигнал на покупку: MAMA пересекает FAMA снизу вверх
        if (CrossOver(bar, mama, fama))
        {
            BuyAtMarket(bar);
        }
        
        // Сигнал на продажу: MAMA пересекает FAMA сверху вниз
        if (CrossUnder(bar, mama, fama))
        {
            SellAtMarket(bar);
        }
    }
}
```

### Добавление на график

```csharp
// Добавление индикатора на ценовую панель
var fama = FAMA.Series(Bars.Close, 0.5, 0.05);
fama.DrawOnPane(PricePane);
```

---

## ⚠️ Важные замечания

1. **Период прогрева**: Индикатор требует минимум 45 баров для корректной работы (`PrefillNan(45)`). Первые 45 значений могут быть `NaN`.
2. **Кэширование**: Используется встроенное кэширование для оптимизации производительности. При повторном вызове с теми же параметрами возвращается объект из кэша.
3. **Парное использование**: Рекомендуется использовать вместе с MAMA для торговых сигналов. Сам по себе FAMA чаще выступает как фильтрующая линия.
4. **Параметры адаптации**: 
   - **Fast Limit** обычно в диапазоне 0.33–0.67
   - **Slow Limit** обычно в диапазоне 0.03–0.07
5. **Namespace**: Класс находится в пространстве имён `WealthLab.TASC`, убедитесь, что добавили соответствующую `using` директиву.