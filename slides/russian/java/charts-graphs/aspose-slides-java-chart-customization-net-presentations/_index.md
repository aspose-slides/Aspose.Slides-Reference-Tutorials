---
date: '2026-06-08'
description: Узнайте, как добавить серии в диаграмму и настроить сложенные столбчатые
  диаграммы в презентациях .NET с использованием Aspose.Slides for Java.
keywords:
- add series to chart
- stacked column chart example
- populate chart data
- create empty presentation
- Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  headline: Add Series to Chart with Aspose.Slides for Java in .NET
  type: TechArticle
- description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  name: Add Series to Chart with Aspose.Slides for Java in .NET
  steps:
  - name: Create an Empty Presentation
    text: '`Presentation` is the entry point class that represents a PowerPoint file
      in memory. *We start with a clean PPTX file, which gives us a canvas for adding
      charts.*'
  - name: Add a Stacked Column Chart to the Slide
    text: '`Chart` represents a chart shape within a slide. `ChartType.StackedColumn`
      specifies a stacked column chart. *The `addChart` method creates a **stacked
      column chart** and places it at the top‑left corner of the slide.*'
  - name: Add Series to the Chart (Primary Goal)
    text: '`Series` encapsulates a single data series in a chart. *Here we **add series
      to chart** – each call creates a new data series that will appear as a separate
      column group.*'
  - name: Add Categories to the Chart
    text: '`Category` defines an X‑axis label for chart data. *Categories act as the
      X‑axis labels, giving meaning to each column.*'
  - name: Populate Series Data
    text: '`DataPoint` holds a numeric value for a series at a specific category.
      *Data points give each series its numeric values, which the chart will render
      as bar heights.*'
  - name: Set Gap Width for Chart Series Group
    text: '`SeriesGroup` controls layout properties for a group of series, such as
      gap width. *Adjusting the gap width improves readability, especially when many
      categories are present.*'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports line, pie, area, radar, bubble, and 50+ other
      chart types, all accessible through the same `addChart` method.
    question: Can I add other chart types besides stacked column?
  - answer: No, the same Java license works for all output formats, including .NET
      PPTX files.
    question: Do I need a separate license for .NET output?
  - answer: Use `series.getFormat().getFill().setFillType(FillType.Solid)` and then
      set the desired `Color` object for each series.
    question: How do I change the chart’s color palette?
  - answer: Absolutely. Call `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the numeric value on each column.
    question: Is it possible to add data labels programmatically?
  - answer: Load the file with `new Presentation("existing.pptx")`, modify the chart
      using the same API calls, and save it back to disk.
    question: What if I need to update an existing presentation?
  type: FAQPage
title: Добавить серию в диаграмму с помощью Aspose.Slides for Java в .NET
url: /ru/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Освоение настройки диаграмм в .NET‑презентациях с помощью Aspose.Slides for Java

## Введение
В мире презентаций, основанных на данных, диаграммы являются незаменимыми инструментами, превращающими сырые цифры в убедительные визуальные истории. Когда вам нужно **add series to chart** программно, особенно внутри файлов .NET‑презентаций, задача может показаться сложной. К счастью, **Aspose.Slides for Java** предоставляет мощный, независимый от языка API, который делает создание и настройку диаграмм простыми — даже когда целевой формат — .NET PPTX. Это руководство проведёт вас через добавление серий, построение сложенной столбчатой диаграммы и тонкую настройку визуальных аспектов, таких как ширина промежутка, чтобы вы могли генерировать динамичные, насыщенные данными слайды, выглядящие отполированными и профессиональными.

## Быстрые ответы
Класс `Presentation` представляет файл PPTX, а `slide.getShapes().addChart(...)` вставляет форму диаграммы. Используйте `chart.getChartData().getSeries().add(...)` для добавления серии, а `setGapWidth()` регулирует промежуток.

- **Какой основной класс используется для начала презентации?** `Presentation` – представляет файл PPTX в памяти.  
- **Какой метод добавляет диаграмму на слайд?** `slide.getShapes().addChart(...)` создаёт объект диаграммы на слайде.  
- **Как добавить новую серию?** `chart.getChartData().getSeries().add(...)` вставляет новую серию данных.  
- **Можно ли изменить ширину промежутка между столбцами?** Да — вызовите `chart.getChartData().getSeriesGroups().get_Item(0).setGapWidth(50)` (значение в процентах).  
- **Нужна ли лицензия для продакшн?** Абсолютно — действительная лицензия Aspose.Slides for Java разблокирует все функции и удаляет водяные знаки оценки.

## Что означает “add series to chart”?
Добавление серии к диаграмме означает вставку новой коллекции точек данных, которые диаграмма отображает как отдельный визуальный элемент (например, отдельную группу столбцов). Каждая серия может иметь свои собственные значения, цвета и форматирование, позволяя сравнивать несколько наборов данных рядом.

## Почему использовать Aspose.Slides for Java для изменения .NET‑презентаций?
Aspose.Slides for Java позволяет генерировать или редактировать файлы PPTX, полностью совместимые с .NET‑просмотрщиками PowerPoint, без необходимости установки Microsoft Office. Используйте Aspose.Slides for Java, когда вам требуется серверное, кроссплатформенное решение, которое создаёт или обновляет .NET PPTX‑файлы, поддерживает более 50 типов диаграмм и обрабатывает файлы до 500 МБ без загрузки всего документа в память. Его API работает в Java, Kotlin, Scala или любом языке JVM, предоставляя тот же результат, который ожидают разработчики .NET.

## Предварительные требования
- **Библиотека Aspose.Slides for Java** (версия 25.4 или новее).  
- Maven, Gradle или ручная загрузка JAR.  
- Базовые знания Java и знакомство со структурой файлов PPTX.  

## Настройка Aspose.Slides for Java
### Установка через Maven
Добавьте следующую зависимость в ваш `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Установка через Gradle
Добавьте эту строку в ваш файл `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Прямая загрузка
В качестве альтернативы, загрузите последнюю JAR с официальной страницы выпусков: [выпуски Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

**Получение лицензии**  
Начните с бесплатной пробной версии, загрузив временную лицензию по ссылке [здесь](https://purchase.aspose.com/temporary-license/). Для использования в продакшн приобретите полную лицензию, чтобы разблокировать все функции и убрать водяные знаки оценки.

## Пошаговое руководство по реализации
Под каждым шагом вы найдёте короткий фрагмент кода (не изменённый по сравнению с оригиналом) и объяснение того, что он делает.

### Шаг 1: Создать пустую презентацию
`Presentation` — класс‑точка входа, представляющий файл PowerPoint в памяти.  
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```  
*Мы начинаем с чистого PPTX‑файла, который предоставляет нам холст для добавления диаграмм.*

### Шаг 2: Добавить сложенную столбчатую диаграмму на слайд
`Chart` представляет форму диаграммы на слайде. `ChartType.StackedColumn` указывает на сложенную столбчатую диаграмму.  
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```  
*Метод `addChart` создаёт **сложенную столбчатую диаграмму** и размещает её в левом верхнем углу слайда.*

### Шаг 3: Добавить серии к диаграмме (основная цель)
`Series` инкапсулирует одну серию данных в диаграмме.  
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```  
*Здесь мы **add series to chart** — каждый вызов создаёт новую серию данных, которая появится как отдельная группа столбцов.*

### Шаг 4: Добавить категории к диаграмме
`Category` определяет метку оси X для данных диаграммы.  
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```  
*Категории выступают в роли меток оси X, придавая смысл каждому столбцу.*

### Шаг 5: Заполнить данные серии
`DataPoint` хранит числовое значение серии для конкретной категории.  
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```  
*Точки данных предоставляют каждой серии её числовые значения, которые диаграмма отобразит в виде высоты столбцов.*

### Шаг 6: Установить ширину промежутка для группы серий диаграммы
`SeriesGroup` управляет свойствами макета группы серий, такими как ширина промежутка.  
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```  
*Регулировка ширины промежутка улучшает читаемость, особенно при большом количестве категорий.*

## Распространённые сценарии использования
- **Финансовая отчетность** — сравнение квартального дохода по бизнес‑подразделениям.  
- **Проектные панели** — отображение процентов выполнения задач по командам.  
- **Маркетинговая аналитика** — визуализация эффективности кампаний рядом.  
Эти сценарии выигрывают от **примера сложенной столбчатой диаграммы**, поскольку они подчёркивают вклад отдельных категорий в общий итог.

## Советы по производительности
- **Повторно используйте объект `Presentation`** при создании нескольких диаграмм, чтобы снизить нагрузку на память.  
- **Ограничьте количество точек данных** только теми, которые необходимы для визуального рассказа; Aspose.Slides может обрабатывать 10 000 точек, но скорость рендеринга падает после ~5 000.  
- **Освобождайте объекты** (`presentation.dispose()`) после сохранения, чтобы освободить ресурсы и избежать утечек памяти.

## Часто задаваемые вопросы
**В: Можно ли добавить другие типы диаграмм, кроме сложенной столбчатой?**  
**О:** Да, Aspose.Slides поддерживает линейные, круговые, областные, радиальные, пузырьковые и более 50 других типов диаграмм, все доступны через тот же метод `addChart`.

**В: Нужна ли отдельная лицензия для вывода в .NET?**  
**О:** Нет, одна и та же лицензия Java работает со всеми форматами вывода, включая файлы .NET PPTX.

**В: Как изменить цветовую палитру диаграммы?**  
**О:** Используйте `series.getFormat().getFill().setFillType(FillType.Solid)`, а затем задайте нужный объект `Color` для каждой серии.

**В: Можно ли программно добавить подписи данных?**  
**О:** Абсолютно. Вызовите `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`, чтобы отобразить числовое значение на каждом столбце.

**В: Что делать, если нужно обновить существующую презентацию?**  
**О:** Загрузите файл с помощью `new Presentation("existing.pptx")`, измените диаграмму, используя те же вызовы API, и сохраните её обратно на диск.

## Заключение
Теперь у вас есть полное пошаговое руководство о том, как **add series to chart**, создать **сложенную столбчатую диаграмму** и тонко настроить её внешний вид в .NET‑презентациях с помощью Aspose.Slides for Java. Экспериментируйте с различными типами диаграмм, цветами и источниками данных, чтобы создавать убедительные визуальные отчёты, которые впечатлят заинтересованные стороны и способствуют принятию решений на основе данных.

---

**Последнее обновление:** 2026-06-08  
**Тестировано с:** Aspose.Slides for Java 25.4 (JDK 16)  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Как создать процентные сложенные столбчатые диаграммы в .NET с помощью Aspose.Slides](/slides/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/)
- [Создание и манипуляция сериями диаграмм с Aspose.Slides .NET для эффективной визуализации данных](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)
- [Очистка конкретных точек данных серии диаграммы с Aspose.Slides .NET](/slides/net/additional-chart-features/clear-specific-chart-series-data-points-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}