---
date: '2026-01-14'
description: Узнайте, как создать сгруппированную столбчатую диаграмму на Java с помощью
  Aspose.Slides. Пошаговое руководство, охватывающее создание пустой презентации,
  добавление диаграммы в презентацию и управление сериями.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: Как создать сгруппированную столбчатую диаграмму в Java с Aspose.Slides
url: /ru/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Освоение создания диаграмм в Java с Aspose.Slides

## Как создавать и управлять диаграммами с помощью Aspose.Slides для Java

### Введение
Создание динамических презентаций часто подразумевает визуализацию данных с помощью диаграмм. С **Aspose.Slides for Java** вы можете без усилий **создать сгруппированную столбчатую диаграмму** и управлять различными типами диаграмм, повышая как ясность, так и воздействие. Это руководство проведёт вас через создание пустой презентации, добавление сгруппированной столбчатой диаграммы, управление сериями и условное инвертирование отрицательных точек данных — всё с использованием Aspose.Slides for Java.

**Что вы узнаете:**
- Как настроить Aspose.Slides для Java.
- Шаги для **создания пустой презентации** и добавления диаграммы в презентацию.
- Техники эффективного управления сериями диаграмм и точками данных.
- Методы условного инвертирования отрицательных точек данных для лучшей визуализации.
- Как безопасно сохранить презентацию.

Давайте перейдём к предварительным требованиям перед началом.

## Быстрые ответы
- **Какой основной класс для начала?** `Presentation` из `com.aspose.slides`.
- **Какой тип диаграммы создаёт сгруппированную столбчатую диаграмму?** `ChartType.ClusteredColumn`.
- **Как добавить диаграмму на слайд?** Используйте `addChart()` в коллекции фигур слайда.
- **Можно ли инвертировать отрицательные значения?** Да, с помощью `invertIfNegative(true)` для точки данных.
- **Какая версия требуется?** Aspose.Slides for Java 25.4 или новее.

## Что такое сгруппированная столбчатая диаграмма?
Сгруппированная столбчатая диаграмма отображает несколько серий данных рядом друг с другом для каждой категории, что делает её идеальной для сравнения значений между группами. Aspose.Slides позволяет генерировать эту диаграмму программно без открытия PowerPoint.

## Почему стоит использовать Aspose.Slides для Java, чтобы добавить диаграмму в презентацию?
- **Полный контроль** над данными диаграммы, её внешним видом и расположением.
- **Не требуется установка Office** на сервере.
- **Поддерживает все основные типы диаграмм**, включая сгруппированные столбчатые диаграммы.
- **Лёгкая интеграция** с Maven/Gradle сборками.

## Предварительные требования

1. **Необходимые библиотеки:**
   - Aspose.Slides for Java (версия 25.4 или новее).

2. **Требования к настройке окружения:**
   - Совместимая версия JDK (например, JDK 16).
   - Установленные Maven или Gradle, если вы предпочитаете управление зависимостями.

3. **Требования к знаниям:**
   - Базовое понимание программирования на Java.
   - Знакомство с управлением зависимостями в вашей среде разработки.

## Настройка Aspose.Slides для Java
Чтобы начать использовать Aspose.Slides, выполните следующие шаги:

**Установка через Maven:**  
Добавьте следующую зависимость в ваш файл `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Установка через Gradle:**  
Добавьте следующую строку в ваш `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Прямое скачивание:**  
В качестве альтернативы, загрузите последнюю версию с [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Приобретение лицензии
- **Бесплатная пробная версия:** Вы можете начать с бесплатной пробной версии, чтобы изучить функции.  
- **Временная лицензия:** Получите временную лицензию для полного доступа в течение периода оценки.  
- **Покупка:** Рассмотрите возможность покупки, если она соответствует вашим долгосрочным потребностям.

### Базовая инициализация
Ниже приведён минимальный код, необходимый для создания нового экземпляра презентации:

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Руководство по реализации
Теперь разберём каждую функцию на управляемые шаги.

### Создание презентации со сгруппированной столбчатой диаграммой
#### Обзор
В этом разделе показано, как **создать пустую презентацию**, добавить **сгруппированную столбчатую диаграмму** и разместить её на первом слайде.

**Шаги:**
1. **Инициализировать объект Presentation** – создать новый `Presentation`.
2. **Добавить сгруппированную столбчатую диаграмму** – вызвать `addChart()` с соответствующим типом и размерами.

**Пример кода:**
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Управление сериями диаграммы
#### Обзор
Узнайте, как очистить любые серии по умолчанию, добавить новую серию и заполнить её как положительными, так и отрицательными значениями.

**Шаги:**
1. **Очистить существующие серии** – удалить любые предварительно заполненные данные.
2. **Добавить новую серию** – использовать ячейку рабочей книги в качестве имени серии.
3. **Вставить точки данных** – добавить значения, включая отрицательные, чтобы позже продемонстрировать инверсию.

**Пример кода:**
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Инвертирование точек данных серии в зависимости от условий
#### Обзор
По умолчанию Aspose.Slides может инвертировать отрицательные значения. Вы можете управлять этим поведением глобально и для каждой точки данных.

**Шаги:**
1. **Установить глобальную инверсию** – отключить автоматическую инверсию для всей серии.
2. **Применить условную инверсию** – включить инверсию только для конкретных отрицательных точек.

**Пример кода:**
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

### Распространённые проблемы и решения
| Проблема | Решение |
|----------|---------|
| Диаграмма отображается пустой | Убедитесь, что индекс слайда (`0`) существует и размеры диаграммы находятся в пределах слайда. |
| Отрицательные значения не инвертируются | Проверьте, что для серии установлен `invertIfNegative(false)`, а для конкретной точки данных — `invertIfNegative(true)`. |
| Исключение лицензии | Примените действующую лицензию Aspose перед созданием объекта `Presentation`. |

## Часто задаваемые вопросы

**В: Могу ли я добавить другие типы диаграмм, кроме сгруппированной столбчатой?**  
О: Да, Aspose.Slides поддерживает линейные, круговые, столбчатые, областные и многие другие типы диаграмм.

**В: Нужна ли лицензия для разработки?**  
О: Бесплатная пробная версия подходит для оценки, но для использования в продакшене требуется коммерческая лицензия.

**В: Как экспортировать диаграмму как изображение?**  
О: Используйте `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` после рендеринга.

**В: Можно ли стилизовать диаграмму (цвета, шрифты)?**  
О: Конечно. Каждый `IChartSeries` и `IChartDataPoint` предоставляет свойства стилей.

**В: Что если я хочу добавить диаграмму в существующий файл PPTX?**  
О: Загрузите файл с помощью `new Presentation("existing.pptx")`, затем добавьте диаграмму на нужный слайд.

## Заключение
В этом руководстве вы узнали, как **создавать сгруппированную столбчатую диаграмму** в Java, управлять сериями и условно инвертировать отрицательные точки данных с помощью Aspose.Slides. Обладая этими методами, вы можете программно создавать убедительные, основанные на данных презентации.

**Следующие шаги:**
- Поэкспериментировать с другими типами диаграмм, предлагаемыми Aspose.Slides для Java.  
- Погрузиться в расширенные параметры стилизации, такие как пользовательские цвета, подписи данных и форматирование осей.  
- Интегрировать генерацию диаграмм в ваши конвейеры отчетности или аналитики.

---

**Последнее обновление:** 2026-01-14  
**Тестировано с:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}