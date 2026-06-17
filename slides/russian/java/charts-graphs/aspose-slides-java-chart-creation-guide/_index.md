---
date: '2026-06-03'
description: Узнайте, как создать сгруппированную столбчатую диаграмму в Java с использованием
  Aspose.Slides. Это руководство охватывает зависимость Maven, шаги создания диаграммы
  и работу с данными.
keywords:
- create clustered column chart
- how to create chart
- maven dependency aspose slides
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  headline: Create Clustered Column Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  name: Create Clustered Column Chart in Java with Aspose.Slides
  steps:
  - name: Create a Presentation and Add a Clustered Column Chart
    text: '`Presentation` class represents a PowerPoint document and allows creating
      slides.'
  - name: Manage Chart Series
    text: Now we’ll clear any default series, add a new one, and populate it with
      both positive and negative values.
  - name: Invert Negative Data Points Conditionally
    text: '`invertIfNegative` method enables inversion of negative values in a chart
      series.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library is used?
  - answer: Clustered column chart.
    question: Which chart type is demonstrated?
  - answer: Yes, using `invertIfNegative`.
    question: Can I invert negative values?
  - answer: JDK 16 or later.
    question: What Java version is required?
  - answer: Yes, a valid Aspose license.
    question: Is a license needed for production?
  type: FAQPage
title: Создание сгруппированной столбчатой диаграммы в Java с Aspose.Slides
url: /ru/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Создать сгруппированную столбчатую диаграмму в Java с Aspose.Slides

## Как создать диаграмму в Java: Введение
Создание динамических презентаций часто включает визуализацию данных с помощью диаграмм. С **Aspose.Slides for Java** вы можете без усилий **создавать объекты сгруппированных столбчатых диаграмм**, повышать ясность и оказывать более сильное влияние на вашу аудиторию. Этот учебник проведёт вас через настройку библиотеки, добавление сгруппированной столбчатой диаграммы, управление сериями и условное инвертирование отрицательных точек данных.

**Что вы узнаете**
- Как настроить Aspose.Slides for Java.  
- Шаги по **созданию сгруппированной столбчатой диаграммы** в вашей презентации.  
- Техники управления сериями диаграммы и точками данных.  
- Методы условного инвертирования отрицательных точек данных для лучшей визуализации.  
- Как безопасно сохранить презентацию.

## Быстрые ответы
- **Какая библиотека используется?** Aspose.Slides for Java.  
- **Какой тип диаграммы демонстрируется?** Сгруппированная столбчатая диаграмма.  
- **Можно ли инвертировать отрицательные значения?** Да, используя `invertIfNegative`.  
- **Какая версия Java требуется?** JDK 16 или новее.  
- **Нужна ли лицензия для продакшна?** Да, действующая лицензия Aspose.

## Что такое сгруппированная столбчатая диаграмма?
Сгруппированная столбчатая диаграмма — это визуальное представление, которое размещает несколько серий данных рядом друг с другом для каждой категории, позволяя быстро сравнивать группы. Она идеальна для финансовых отчётов, панелей продаж и любых сценариев, где необходимо сравнить несколько метрик одновременно.

## Почему использовать Aspose.Slides для создания диаграмм?
Aspose.Slides позволяет генерировать и полностью настраивать диаграммы программно, исключая необходимость ручного редактирования PowerPoint. Она поддерживает **более 70 форматов ввода и вывода** и может обрабатывать презентации с **до 10 000 слайдов** без загрузки всего файла в память, обеспечивая высокую производительность для масштабных отчётов.

## Предварительные требования
1. **Необходимые библиотеки**  
   - Aspose.Slides for Java (версия 25.4 или новее).  

2. **Среда**  
   - JDK 16 или новее.  
   - Maven или Gradle для управления зависимостями.  

3. **Знания**  
   - Базовое программирование на Java.  
   - Знакомство с инструментами сборки (Maven/Gradle).  

## Настройка Aspose.Slides для Java
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
Альтернативно, загрузите последнюю версию с [релизы Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

### Приобретение лицензии
- **Бесплатная пробная версия:** Исследуйте возможности без лицензии.  
- **Временная лицензия:** Используйте во время оценки.  
- **Полная лицензия:** Приобретите для продакшн‑развёртываний.

### Базовая инициализация
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Как добавить сгруппированную столбчатую диаграмму на слайд?
`Presentation` — основной класс, представляющий файл PowerPoint. Загрузите новый `Presentation`, добавьте слайд и вызовите `slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400)`. Этот один вызов создаёт полностью функциональную сгруппированную столбчатую диаграмму, размещённую по указанным координатам. Затем вы можете получить объект диаграммы для изменения серий, точек данных и визуальных стилей.

## Пошаговое руководство

### Шаг 1: Создать презентацию и добавить сгруппированную столбчатую диаграмму
Класс `Presentation` представляет документ PowerPoint и позволяет создавать слайды.  
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
Теперь мы очистим любые стандартные серии, добавим новую и заполним её как положительными, так и отрицательными значениями.  
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

### Шаг 3: Условно инвертировать отрицательные точки данных
Метод `invertIfNegative` позволяет инвертировать отрицательные значения в серии диаграммы.  
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

## Распространённые ошибки и советы
- **Забыли вызвать `dispose` у объекта `Presentation`?** Всегда вызывайте `dispose()` в блоке `finally`, чтобы освободить нативные ресурсы.  
- **Отрицательные значения не отображаются инвертированными?** Убедитесь, что вызываете `invertIfNegative(true)` **после** добавления точки данных.  
- **Проблемы с размером диаграммы:** Координаты (X, Y) и размеры (ширина, высота) указаны в пунктах; скорректируйте их под макет вашего слайда.  

## Часто задаваемые вопросы

**Q:** Могу ли я создавать другие типы диаграмм тем же подходом?  
A: Да, просто замените `ChartType.ClusteredColumn` на любое другое значение перечисления `ChartType` (например, `Line`, `Pie`).  

**Q:** Нужна ли лицензия для сборок разработки?  
A: Требуется временная или оценочная лицензия для полного доступа к функциям; иначе библиотека работает в пробном режиме с ограничениями водяного знака.  

**Q:** Как экспортировать презентацию в PDF после добавления диаграмм?  
`SaveFormat.Pdf` указывает PDF как формат вывода при сохранении презентации. Используйте `pres.save("output.pdf", SaveFormat.Pdf);` после завершения работы с диаграммами.  

**Q:** Можно ли стилизовать отдельные столбцы (цвет, граница)?  
`IChartDataPoint` представляет отдельную точку данных в диаграмме и позволяет её форматировать. Каждый `IChartDataPoint` предоставляет опции, такие как `getFillFormat().setFillType(FillType.Solid)` и `getLineFormat()`.  

**Q:** Что делать, если нужно обновить данные диаграммы после сохранения презентации?  
A: Загрузите презентацию снова с помощью `new Presentation("file.pptx")`, измените данные диаграммы и сохраните её повторно.  

---

**Последнее обновление:** 2026-06-03  
**Тестировано с:** Aspose.Slides for Java 25.4 (JDK 16)  
**Автор:** Aspose

## Связанные руководства

- [Как создать сложенную столбчатую диаграмму в Java с Aspose.Slides – Полное руководство](/slides/java/charts-graphs/aspose-slides-java-stacked-column-charts/)
- [Как создать диаграмму в Java с Aspose.Slides – Мастерство создания и валидации диаграмм](/slides/java/charts-graphs/aspose-slides-chart-creation-validation-java/)
- [Создание и форматирование диаграмм в Java с помощью Aspose.Slides: Полное руководство](/slides/java/charts-graphs/create-format-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}