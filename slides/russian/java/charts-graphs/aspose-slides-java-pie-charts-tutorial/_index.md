---
date: '2026-07-17'
description: Узнайте, как вращать круговую диаграмму, настраивать её цвета и экспортировать
  слайд в PDF с помощью Aspose.Slides for Java — полное руководство по визуализации
  данных.
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: Вращайте круговую диаграмму и настраивайте её цвета с помощью Aspose.Slides
  for Java. Узнайте, как экспортировать слайд в PDF и работать с листом данных диаграммы.
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: Вращение круговой диаграммы и настройка цветов в Java — руководство Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to rotate pie chart, customize pie chart colors, and export
    slide to PDF using Aspose.Slides for Java – a full data visualization guide.
  headline: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Request a free trial from the Aspose website, then purchase a permanent
      license. Load it at runtime as shown in the Common Issues table.
    question: How do I obtain an Aspose.Slides license for Java?
  - answer: The API requires JDK 16 or higher; older versions are not supported.
    question: Can I use this code with older JDK versions?
  - answer: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png",
      ImageFormat.Png);`.
    question: Is it possible to export the chart as an image instead of PPTX?
  - answer: Pie charts are designed for a single data series; for multiple series,
      consider using a doughnut chart.
    question: What if I need more than one series in a pie chart?
  - answer: Absolutely—Aspose.Slides for Java is platform‑independent and works on
      any OS with a compatible JDK.
    question: Does Aspose.Slides run on Linux servers?
  type: FAQPage
tags:
- rotate pie chart
- Aspose.Slides
- Java charting
- data visualization
title: Как вращать круговую диаграмму и настраивать цвета в Java с Aspose.Slides
url: /ru/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Создание круговых диаграмм с помощью Aspose.Slides для Java: Полное руководство

## Введение
В этом руководстве вы узнаете, как **rotate pie chart** элементы, настроить цвет каждого сегмента и экспортировать готовый слайд в PDF — всё с помощью Aspose.Slides для Java. Независимо от того, создаёте ли вы панель продаж, финансовый отчёт или любую презентацию, основанную на данных, освоив эти приёмы, вы сможете предоставлять чёткие, привлекающие внимание визуальные материалы без необходимости использовать Microsoft Office. Давайте подготовим инструменты и начнём.

## Быстрые ответы
- **Какой класс начинает новую презентацию?** `Presentation` из `com.aspose.slides`.
- **Какой вызов API добавляет круговую диаграмму?** `slide.addChart(ChartType.Pie, …)`.
- **Как задать каждому сегменту уникальный цвет?** Вызовите `series.setColorVaried(true)` и задайте сплошные заливки для каждой точки данных.
- **Какой метод вращает диаграмму?** `chart.setRotationAngle(double)` – используйте градусы от 0 до 360.
- **Можно ли экспортировать слайд в PDF?** Да, вызовите `presentation.save("output.pdf", SaveFormat.Pdf)`.

## Что означает «настройка цветов круговой диаграммы»?
Настройка цветов круговой диаграммы подразумевает назначение разных цветов заливки каждому сегменту, улучшая читаемость и визуальное восприятие. В Aspose.Slides это достигается включением разнообразных цветов и последующей установкой сплошных заливок для отдельных точек данных. Такой подход гарантирует, что каждый сегмент данных будет явно выделяться в презентации.

## Почему стоит использовать Aspose.Slides для Java при создании круговых диаграмм?
Aspose.Slides поддерживает **150+ типов диаграмм** и может отрисовать 300‑страничную презентацию менее чем за **5 секунд** на типичном сервере, без необходимости установки Microsoft Office. Библиотека работает на Windows, Linux и macOS, предоставляя кросс‑платформенную гибкость для любого проекта визуализации данных на Java.

## Требования
- **Aspose.Slides for Java** ≥ 25.4
- **JDK** 16 или новее
- IDE, например IntelliJ IDEA, Eclipse или NetBeans
- Базовые знания Java и знакомство с Maven или Gradle

## Настройка Aspose.Slides для Java
Добавьте библиотеку в конфигурацию сборки.

**Maven**  
Добавьте этот фрагмент в ваш файл `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Включите следующее в ваш файл `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download**  
Если вы предпочитаете ручной подход, скачайте последнюю JAR‑файл с [выпуски Aspose.Slides для Java](https://releases.aspose.com/slides/java/).

### Шаги получения лицензии
- **Бесплатная пробная версия** – изучите все функции бесплатно.  
- **Временная лицензия** – продлите ограничения пробной версии на короткий срок.  
- **Покупка** – получите постоянную лицензию для использования в продакшене.

**Базовая инициализация и настройка**  
Класс `Presentation` представляет файл PowerPoint в памяти и предоставляет методы для работы со слайдами.  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Руководство по реализации
Ниже представлена пошаговая инструкция, охватывающая всё от создания слайда до вращения готовой круговой диаграммы.

### Инициализация презентации и слайда
Создайте новый экземпляр `Presentation` и получите первый слайд, который будет служить холстом для диаграммы.  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Добавление круговой диаграммы на слайд
`addChart` добавляет форму диаграммы указанного типа на слайд в заданных координатах.  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Установка заголовка диаграммы
`setTitle` задаёт текстовый заголовок диаграммы и позиционирует его по центру.  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Настройка подписей данных для серии
`setShowValue(true)` включает отображение числовых значений на каждой точке данных серии.  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Подготовка листа данных диаграммы
`ChartDataWorkbook` хранит базовую таблицу данных, которая заполняет серии и категории диаграммы.  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Добавление категорий в диаграмму
`addCategory` создаёт новую метку категории для серии данных диаграммы.  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Добавление серии и заполнение точек данных
`addSeries` создаёт серию данных, а `addDataPointForBarSeries` вставляет числовые значения для каждой категории.  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Настройка цветов и границ серии
`setColorVaried(true)` включает индивидуальные цвета сегментов, а `setFillFormat` задаёт сплошную заливку каждой точке данных.  
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Настройка пользовательских подписей данных
`setDataLabelFormat` кастомизирует внешний вид, позицию и шрифт подписи для более ясных аннотаций диаграммы.  
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Установка угла вращения и сохранение презентации
`setRotationAngle` вращает всю круговую диаграмму, а `save` записывает презентацию в файл.  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Как вращать круговую диаграмму?
Загрузите объект диаграммы, вызовите `chart.setRotationAngle(45.0)` (или любое другое значение в градусах), затем сохраните презентацию. Вращение круговой диаграммы изменяет начальный угол, позволяя выделить определённый сегмент без изменения данных. Этот единственный вызов метода работает для любого экземпляра `Chart` в Aspose.Slides. Вы также можете комбинировать вращение с разнообразными цветами сегментов, чтобы привлечь внимание к наиболее важному пункту данных.

## Распространённые проблемы и решения
| Проблема | Причина | Решение |
|----------|---------|---------|
| **Все сегменты имеют одинаковый цвет** | `setColorVaried(true)` не вызван | Убедитесь, что включили разнообразные цвета для группы серии. |
| **Подписи данных не отображаются** | Флаг `showValue` отключён | Вызовите `setShowValue(true)` в формате подписи. |
| **Вращение не оказывает эффекта** | Используется более старая версия Aspose.Slides | Обновите до версии 25.4 или новее. |
| **Исключение лицензии во время выполнения** | Отсутствует или недействителен файл лицензии | Загрузите лицензию с помощью `License license = new License(); license.setLicense("Aspose.Slides.lic");` перед созданием `Presentation`. |

## Часто задаваемые вопросы

**В: Как получить лицензию Aspose.Slides для Java?**  
Ответ: Запросите бесплатную пробную версию на сайте Aspose, затем приобретите постоянную лицензию. Загрузите её во время выполнения, как показано в таблице «Распространённые проблемы и решения».

**В: Можно ли использовать этот код со старыми версиями JDK?**  
Ответ: API требует JDK 16 или выше; более старые версии не поддерживаются.

**В: Можно ли экспортировать диаграмму как изображение вместо PPTX?**  
Ответ: Да — после рендеринга вызовите `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`.

**В: Что делать, если нужен более чем один ряд в круговой диаграмме?**  
Ответ: Круговые диаграммы предназначены для одной серии данных; для нескольких рядов рассмотрите использование кольцевой диаграммы.

**В: Работает ли Aspose.Slides на Linux‑серверах?**  
Ответ: Абсолютно — Aspose.Slides для Java независим от платформы и работает на любой ОС с совместимым JDK.

---

**Последнее обновление:** 2026-07-17  
**Проверено с:** Aspose.Slides for Java 25.4 (JDK 16)  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Похожие руководства

- [Как создавать круговые диаграммы в Java‑презентациях с помощью Aspose.Slides: Полное руководство](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [Мастерство создания круговых диаграмм в Java с Aspose.Slides: Полное руководство](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [Вращение текста диаграмм в Java с Aspose.Slides: Полное руководство](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}