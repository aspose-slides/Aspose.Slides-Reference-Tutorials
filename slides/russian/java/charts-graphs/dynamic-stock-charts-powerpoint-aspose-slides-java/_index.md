---
date: '2026-09-12'
description: Узнайте, как использовать Maven Aspose Slides для добавления и настройки
  динамических графиков акций в PowerPoint с Java. Включает настройку, добавление
  серий данных, форматирование линий и сохранение.
keywords:
- maven aspose slides
- add data series chart
- format chart lines
- customize chart java
lastmod: '2026-09-12'
og_description: Учебник Maven Aspose Slides показывает, как создавать и настраивать
  динамические графики акций в PowerPoint с использованием Java, охватывая серии данных,
  форматирование линий и сохранение.
og_image_alt: Illustration of a Java-generated stock chart in PowerPoint using Aspose.Slides
og_title: 'Руководство Maven Aspose Slides: создание динамических графиков акций в
  PowerPoint'
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to use Maven Aspose Slides to add and customize dynamic stock
    charts in PowerPoint with Java. Includes setup, adding data series, formatting
    lines, and saving.
  headline: 'Maven Aspose Slides: create dynamic stock charts in PowerPoint with Java'
  type: TechArticle
- questions:
  - answer: Yes. The library is pure Java, so you can run it in any servlet container
      or Spring Boot service.
    question: Can I use this code in a web application?
  - answer: Absolutely. It supports over 70 chart types, including Line, Bar, Pie,
      and Radar charts.
    question: Does Aspose.Slides support other chart types besides Stock?
  - answer: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`
      and then format the title as needed.
    question: How do I add a chart title programmatically?
  - answer: Practically, you can add tens of thousands of points; memory usage scales
      linearly, and the library streams data to keep the footprint low.
    question: Is there a limit to the number of data points per series?
  - answer: The latest version is always available under `com.aspose:aspose-slides:25.4`
      (or newer) on Maven Central.
    question: Which Maven coordinates should I use for the latest version?
  type: FAQPage
tags:
- maven aspose slides
- dynamic stock charts
- java charting
- aspose.slides
title: 'Maven Aspose Slides: создание динамических графиков акций в PowerPoint с Java'
url: /ru/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose Slides: создание динамических графиков акций в PowerPoint с помощью Java

## Введение

**Maven Aspose Slides** позволяет программно создавать сложные презентации PowerPoint из Java. В этом руководстве вы узнаете, как создавать динамические графики акций, добавлять и форматировать серии данных, настраивать линии графика и в конце сохранять файл. Независимо от того, финансовый аналитик, готовящий квартальные отчёты, или разработчик, создающий автоматические наборы слайдов, нижеописанные шаги предоставляют полное готовое к производству решение.

**Что вы узнаете**
- Как настроить Maven с Aspose.Slides для Java  
- Как добавить график акций и очистить данные по умолчанию  
- Как **добавить серию данных в график** и **форматировать линии графика**  
- Как **настроить специфические для Java визуальные элементы графика**  
- Как сохранить обновлённую презентацию

Готовы превратить сырые цифры в привлекающие внимание визуальные графики акций? Приступим!

## Быстрые ответы
- **Какой Maven‑артефакт нужен?** `aspose-slides` версия 25.4 (или новее).  
- **Можно ли запускать это на любой ОС?** Да — библиотека чисто Java и работает на Windows, macOS и Linux.  
- **Нужна ли лицензия для разработки?** Бесплатная временная лицензия подходит для тестирования; полная лицензия требуется для продакшн.  
- **Какие типы графиков поддерживаются?** Более 70 встроенных типов графиков, включая Stock, Line и Bar.  
- **Какой размер презентации можно обрабатывать?** Aspose.Slides может работать с файлами более 500 слайдов без загрузки всего файла в память.

## Что такое Maven Aspose Slides?

`Aspose.Slides for Java` — это Java API, позволяющее создавать, изменять и конвертировать файлы PowerPoint без Microsoft Office. Интеграция с Maven упрощает управление зависимостями, позволяя получать библиотеку напрямую из Maven Central.

## Почему использовать Maven Aspose Slides для графиков акций?

Aspose.Slides поддерживает **более 70 типов графиков** и может отрисовывать многосотстраничные презентации менее чем за секунду на типичном серверном оборудовании. Его функции **high‑low line** и **up/down bar** предоставляют точный контроль над финансовыми визуализациями, значительно превосходя возможности UI PowerPoint.

## Предварительные требования

- **Java Development Kit (JDK)** — версия 11 или выше.  
- **IDE** — IntelliJ IDEA, Eclipse или любой другой редактор по вашему выбору.  
- **Aspose.Slides for Java** — версия 25.4 (самая свежая на момент написания).  

### Настройка Aspose.Slides для Java

#### Maven
Чтобы интегрировать Aspose.Slides в ваш проект с помощью Maven, добавьте следующую зависимость в ваш `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle
Для пользователей Gradle включите следующее в ваш `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Прямая загрузка
В качестве альтернативы скачайте последнюю JAR‑файл с [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Получение лицензии** — начните с бесплатной пробной версии или запросите временную лицензию. Для коммерческого использования приобретите полную лицензию.

Для подробного справочника API см. [Aspose.Slides documentation](https://docs.aspose.com/slides/java/).

## Как создать динамический график акций шаг за шагом

Загрузите вашу презентацию, добавьте график акций, очистите данные по умолчанию, а затем вставьте свои серии и категории. Прямой ответ на основной вопрос:

> Загрузите существующий PPTX с помощью `new Presentation("template.pptx")`, добавьте `Chart` типа `ChartType.Stock`, очистите его серии и категории по умолчанию, затем заполните его своими точками данных и параметрами форматирования. В конце вызовите `presentation.save("output.pptx", SaveFormat.Pptx)`.

### Инициализация презентации
#### Обзор
Начните с загрузки существующего файла PowerPoint, чтобы изменить его на месте.

#### Пошагово
1. **Импортировать библиотеку** — класс `Presentation` является точкой входа для всех операций со слайдами.  

   ```java
   import com.aspose.slides.Presentation;
   ```

2. **Загрузить файл презентации** — укажите путь к вашему шаблону PPTX.  

   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Ready to perform operations on 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Добавить график акций на слайд
#### Обзор
Вставьте график Stock на первый слайд презентации.

Класс `Chart` представляет форму графика, которую можно добавить на слайд.

#### Прямой ответ
Вы добавляете график акций, вызывая `slide.getShapes().addChart(ChartType.Stock, x, y, width, height)`. Это создаёт объект графика, которым можно сразу управлять.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Очистить существующие серии данных и категории в графике
#### Обзор
Удалите любые предварительно заполненные серии или категории, чтобы начать с чистого набора данных.

Объект `ChartData` хранит серии и категории для графика.

#### Прямой ответ
Вызовите `chart.getChartData().getSeries().clear()` и `chart.getChartData().getCategories().clear()`, чтобы удалить содержимое по умолчанию перед добавлением своего.

   ```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Добавить категории в данные графика
#### Обзор
Определите категории оси X (например, даты), которые группируют ваши значения акций.

`ChartCategory` представляет метку оси X для графика.

#### Прямой ответ
Создайте новый `ChartCategory` для каждой метки, используя `chart.getChartData().getCategories().add(dataWorkbook.getCell(0, row, 0), "Jan")`, повторяя для каждого месяца или периода.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Add categories
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Добавить серии данных в график
#### Обзор
Добавьте четыре основные серии: Open, High, Low и Close.

`ChartSeries` хранит коллекцию точек данных для конкретной серии в графике.

#### Прямой ответ
Для каждой серии вызовите `chart.getChartData().getSeries().add(dataWorkbook.getCell(0, 0, colIndex), chart.getType())`. Это регистрирует серию в рабочей книге данных графика.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add series for 'Open', 'High', 'Low', and 'Close'
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Добавить точки данных в серию
#### Обзор
Заполните каждую серию числовыми значениями, представляющими цены акций.

`DataPoint` представляет отдельное значение в серии.

#### Прямой ответ
Пройдите по вашей коллекции данных и используйте `series.getDataPoints().addDataPointForBarSeries(dataWorkbook.getCell(0, row, col), value)` (или соответствующий метод для типа серии), чтобы вставить каждую точку.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add data points to 'Open' series
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Add data points to 'High' series
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Add data points to 'Low' series
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Add data points to 'Close' series
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Форматировать линии high‑low и бары up/down
#### Обзор
Отрегулируйте визуальный стиль соединителей high‑low и заливок баров up/down.

`Marker` определяет визуальный символ для точки данных.

#### Прямой ответ
Установите `chart.getChartData().getSeries().get(0).getMarker().setSize(10)` и настройте `chart.getChartData().getSeries().get(0).getFormat().getLine().setWidth(2)`, чтобы контролировать толщину и цвет линии.

   ```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Format high-low lines for 'Close' series
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

#### Показать up/down бары
Используйте метод `setShowUpDownBars(true)` графика, чтобы отобразить up/down бары.

   ```java
   // Display up/down bars for the stock chart series group
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### Настроить подписи данных на линиях high‑low
#### Обзор
Отображайте числовые значения непосредственно на линиях high‑low для быстрого доступа.

`DataLabel` управляет внешним видом подписей, привязанных к точкам данных.

#### Прямой ответ
Включите подписи данных с помощью `chart.getChartData().getSeries().get(0).getDataPoints().get(i).getLabel().setShowValue(true)` и при необходимости стилизуйте их.

   ```java
    // Show values on up/down bars for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### Установить цвет заливки up/down баров
#### Обзор
Залейте up-бары зелёным цветом, а down-бары красным, чтобы интуитивно передать движение рынка.

Объект `UpDownBars` предоставляет доступ к форматированию up и down баров.

#### Прямой ответ
Примените `chart.getUpDownBars().getUpBar().getFillFormat().setFillType(FillType.Solid)` и задайте сплошной цвет `Color.GREEN`; повторите для down-бара с `Color.RED`.

   ```java
    // Change the up/down bar colors for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // 'Open' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Up bars in cyan
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // 'High' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Down bars in dark sea green
        }
    }
    ```

### Сохранить файл PowerPoint
#### Обзор
Сохраните ваши изменения в новый файл PPTX.

Метод `save` записывает презентацию на диск в указанном формате.

#### Прямой ответ
Вызовите `presentation.save("DynamicStockChart.pptx", SaveFormat.Pptx)` — это сохраняет изменённую презентацию на диск в стандартном формате PowerPoint.

   ```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## Распространённые проблемы и их устранение

- **График не отображается** — убедитесь, что координаты X/Y и размеры графика находятся в пределах слайда.  
- **Отсутствуют точки данных** — проверьте, что индексы ячеек рабочей книги данных соответствуют серии/строке, которую вы хотите заполнить.  
- **Исключение лицензии** — временная пробная лицензия истекает через 30 дней; замените её постоянной лицензией для продакшн‑сборок.  
- **Замедление производительности на больших файлах** — используйте `Presentation.setCacheSize(0)`, чтобы отключить кэширование, если обрабатываете тысячи слайдов в пакете.

## Часто задаваемые вопросы

**В: Можно ли использовать этот код в веб‑приложении?**  
**О:** Да. Библиотека чисто Java, поэтому её можно запускать в любом servlet‑контейнере или сервисе Spring Boot.

**В: Поддерживает ли Aspose.Slides другие типы графиков, кроме Stock?**  
**О:** Абсолютно. Он поддерживает более 70 типов графиков, включая Line, Bar, Pie и Radar.

**В: Как программно добавить заголовок графика?**  
**О:** Используйте `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`, а затем при необходимости отформатируйте заголовок.

**В: Есть ли ограничение на количество точек данных в серии?**  
**О:** Практически можно добавить десятки тысяч точек; использование памяти растёт линейно, а библиотека потоково обрабатывает данные, чтобы сохранять небольшой объём памяти.

**В: Какие Maven‑координаты использовать для последней версии?**  
**О:** Последняя версия всегда доступна под `com.aspose:aspose-slides:25.4` (или новее) в Maven Central.

---

**Последнее обновление:** 2026-09-12  
**Тестировано с:** Aspose.Slides for Java 25.4  
**Автор:** Aspose

## Связанные руководства

- [aspose slides maven dependency: Добавление и настройка графиков в презентациях с помощью Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Создание графика PowerPoint Java – Сохранение презентаций с графиками с помощью Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [Создание и форматирование графиков PowerPoint Aspose Slides Java](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}