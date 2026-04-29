---
date: '2026-02-12'
description: Узнайте, как создавать диаграммы и управлять ими с помощью Aspose.Slides
  для Java. Этот учебник показывает, как создать сгруппированную столбчатую диаграмму,
  работать с сериями данных и настраивать визуализацию.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: 'Как создать диаграмму в Java с Aspose.Slides: Полное руководство'
url: /ru/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-container >}}

{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как создать диаграмму в Java с помощью Aspose.Slides

## Как создать диаграмму в Java: Введение
Создание динамических презентаций часто включает визуализацию данных с помощью диаграмм. С **Aspose.Slides for Java** вы можете без труда **how to create chart** объекты, улучшать ясность и оказывать более сильное воздействие на вашу аудиторию. Этот учебник проведет вас через настройку библиотеки, добавление **create clustered column chart**, управление сериями и условное инвертирование отрицательных точек данных.

**Что вы узнаете**
- Как настроить Aspose.Slides for Java.
- Шаги для **create clustered column chart** в вашей презентации.
- Техники управления сериями диаграммы и точками данных.
- Методы условного инвертирования отрицательных точек данных для лучшей визуализации.
- Как безопасно сохранить презентацию.

### Быстрые ответы
- **Какая библиотека используется?** Aspose.Slides for Java.
- **Какой тип диаграммы демонстрируется?** Clustered column chart.
- **Могу ли я инвертировать отрицательные значения?** Да, используя `invertIfNegative`.
- **Какая версия Java требуется?** JDK 16 или новее.
- **Нужна ли лицензия для продакшн?** Да, действующая лицензия Aspose.

## Что такое Clustered Column Chart?
Clustered column chart отображает несколько серий данных рядом друг с другом для каждой категории, что упрощает сравнение значений между группами. Он идеален для финансовых отчетов, панелей продаж и любых сценариев, где необходимо сопоставлять несколько метрик.

## Почему использовать Aspose.Slides для создания диаграмм?
- **Полный контроль** над внешним видом диаграммы без зависимости от пользовательского интерфейса PowerPoint.
- **Программная генерация** позволяет создавать автоматизированные конвейеры отчетности.
- **Кросс‑платформенная** поддержка гарантирует, что ваш код работает на любой системе, совместимой с Java.
- **Богатый API** для тонкой настройки (цвета, подписи данных, инверсия и т.д.).

## Предварительные требования
1. **Необходимые библиотеки**
   - Aspose.Slides for Java (версия 25.4 или новее).

2. **Среда**
   - JDK 16 или новее.
   - Maven или Gradle для управления зависимостями.

3. **Знания**
   - Базовое программирование на Java.
   - Знакомство с инструментами сборки (Maven/Gradle).

## Настройка Aspose.Slides for Java
### Установка через Maven
Добавьте следующую зависимость в ваш файл `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Установка через Gradle
Добавьте следующую строку в ваш файл `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Прямое скачивание
В качестве альтернативы загрузите последнюю версию с [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Приобретение лицензии
- **Free Trial:** Исследуйте возможности без лицензии.
- **Temporary License:** Используйте во время оценки.
- **Full License:** Приобретите для продакшн-развертываний.

### Базовая инициализация
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Пошаговое руководство

### Шаг 1: Создать презентацию и добавить Clustered Column Chart
На этом шаге мы **how to create chart** объекты и размещаем **create clustered column chart** на первом слайде.

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

### Шаг 2: Управление сериями диаграммы
Теперь мы очистим любые серии по умолчанию, добавим новую и заполним её как положительными, так и отрицательными значениями.

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

### Шаг 3: Условное инвертирование отрицательных точек данных
По умолчанию Aspose.Slides не инвертирует отрицательные значения. Мы включим инверсию только для тех точек, которым это необходимо.

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

### Распространённые ошибки и советы
- **Забыли вызвать `dispose()` у объекта `Presentation`?** Всегда вызывайте `dispose()` в блоке `finally`, чтобы освободить нативные ресурсы.
- **Отрицательные значения не отображаются как инвертированные?** Убедитесь, что вы вызываете `invertIfNegative(true)` **после** добавления точки данных.
- **Проблемы с размером диаграммы:** Координаты (X, Y) и размеры (width, height) указаны в пунктах; скорректируйте их под макет слайда.

## Часто задаваемые вопросы

**В: Могу ли я создавать другие типы диаграмм тем же подходом?**  
**О:** Да, просто замените `ChartType.ClusteredColumn` на любое другое значение перечисления `ChartType` (например, `Line`, `Pie`).

**В: Нужна ли лицензия для сборок разработки?**  
**О:** Требуется временная или оценочная лицензия для полного доступа к функциям; иначе библиотека работает в пробном режиме с ограничениями водяного знака.

**В: Как экспортировать презентацию в PDF после добавления диаграмм?**  
**О:** Используйте `pres.save("output.pdf", SaveFormat.Pdf);` после завершения работы с диаграммами.

**В: Можно ли стилизовать отдельные столбцы (цвет, граница)?**  
**О:** Да, каждый `IChartDataPoint` предоставляет параметры форматирования, такие как `getFillFormat().setFillType(FillType.Solid)` и `getLineFormat()`.

**В: Что делать, если нужно обновить данные диаграммы после сохранения презентации?**  
**О:** Загрузите презентацию снова с помощью `new Presentation("file.pptx")`, измените данные диаграммы и сохраните заново.

---

**Последнее обновление:** 2026-02-12  
**Тестировано с:** Aspose.Slides for Java 25.4 (JDK 16)  
**Автор:** Aspose  

{{< /blocks/products/pf/main-wrap-class >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}