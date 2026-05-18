---
date: '2026-02-22'
description: Узнайте, как создать сложенную столбчатую диаграмму в Java с использованием
  Aspose.Slides. В этом руководстве рассматриваются зависимость Aspose Slides Maven,
  добавление процентной сложенной диаграммы, форматирование подписей данных диаграммы
  и сохранение презентации в формате PPTX.
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: Как создать слоистую столбчатую диаграмму в Java с помощью Aspose.Slides –
  Полное руководство
url: /ru/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как создать сложенную столбчатую диаграмму в Java с Aspose.Slides – Полное руководство

## Introduction

Поднимите уровень ваших презентаций, добавив информативные визуализации данных с помощью Aspose.Slides for Java. В этом руководстве вы **создадите слайды со сложенной столбчатой диаграммой**, которые будут выглядеть профессионально, будь то бизнес‑отчёты или демонстрация статистики проекта. К концу урока вы сможете:

- Настроить окружение с зависимостью Aspose Slides Maven
- Создать презентацию с нуля
- **Добавить процентную сложенную диаграмму** и настроить её внешний вид
- **Отформатировать подписи данных диаграммы** и **изменить формат вертикальной оси**
- **Сохранить презентацию как PPTX** одной строкой кода

Давайте пройдём каждый шаг, чтобы вы сразу начали создавать убедительные презентации.

## Quick Answers
- **What library do I need?** `aspose-slides` Maven/Gradle dependency (see “aspose slides maven dependency” below)  
- **Which chart type is used?** `ChartType.PercentsStackedColumn` for a percentage‑stacked column chart  
- **How do I change the axis number format?** Use `IAxis.setNumberFormat()` and disable linking to source  
- **Can I customize data labels?** Yes – iterate through `IChartDataPoint` objects and set a custom `ITextFrame`  
- **How do I save the file?** Call `presentation.save("output.pptx", SaveFormat.Pptx)`

## What is a stacked column chart?
Сложенная столбчатая диаграмма визуализирует несколько рядов данных, наложенных друг на друга в вертикальных столбцах. При использовании **процентного** варианта каждый столбец всегда суммируется до 100 %, что упрощает сравнение пропорционального вклада по категориям.

## Why use Aspose.Slides for Java?
Aspose.Slides предоставляет чистый Java‑API, работающий на любой платформе без установленного Microsoft Office. Он обеспечивает тонкий контроль над объектами диаграмм, поддерживает широкий набор форматов и позволяет программно генерировать презентации — идеально для автоматизированных отчётов или серверной генерации документов.

## Prerequisites
- **Java Development Kit (JDK):** 8 или выше  
- **IDE:** IntelliJ IDEA, Eclipse или любой совместимый редактор Java  
- **Build Tool:** Maven или Gradle (опционально, но рекомендуется)  
- **Basic Java knowledge** – вы должны быть уверены в работе с классами и методами  

## Setting Up Aspose.Slides for Java
Чтобы начать, добавьте библиотеку Aspose.Slides в ваш проект.

### Aspose Slides Maven Dependency
Добавьте следующее в ваш `pom.xml` (это **aspose slides maven dependency**, которая вам понадобится):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Alternative
Если вы предпочитаете Gradle, включите эту строку в `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
Либо скачайте последнюю JAR‑файл с [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### License Acquisition
Вы можете начать с бесплатной пробной версии, чтобы изучить возможности Aspose.Slides. Чтобы убрать ограничения оценки, рассмотрите возможность получения временной или полной лицензии.

- **Free Trial:** Доступ к ограниченному набору функций без немедленных расходов.  
- **Temporary License:** Запросите через [сайт Aspose](https://purchase.aspose.com/temporary-license/).  
- **Purchase:** Перейдите на страницу покупки для полного доступа.

### Basic Initialization
Ниже минимальный фрагмент кода, показывающий, как создать объект `Presentation`:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Implementation Guide

### Creating a Presentation and Adding a Slide
**Overview:**  
Сначала мы создадим пустую презентацию и проверим, что слайд существует.

#### Step 1: Initialize Presentation Object
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Step 2: Save the Presentation
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Adding Percentage Stacked Column Chart to a Slide
**Overview:**  
Теперь разместим **процентную сложенную диаграмму** на первом слайде.

#### Step 1: Initialize and Access Slide
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### Step 2: Add Chart to Slide
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Customizing Chart Axis Number Format
**Overview:**  
Для лучшей читаемости мы **изменим формат вертикальной оси**, чтобы отображать проценты.

#### Step 1: Add and Access Chart
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Step 2: Set Custom Number Format
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Adding Series and Data Points to Chart
**Overview:**  
Мы заполним диаграмму примерными рядами данных.

#### Step 1: Initialize Presentation and Chart
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Step 2: Add Data Series
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Formatting Series Fill Color
**Overview:**  
Присвоим каждому ряду отдельный цвет, чтобы диаграмма была легче воспринимаема.

#### Step 1: Initialize and Access Chart
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Step 2: Set Fill Colors
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Formatting Data Labels
**Overview:**  
Теперь мы **отформатируем подписи данных диаграммы**, чтобы они отображали пользовательский текст.

#### Step 1: Access Chart Series and Data Points
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Step 2: Customize Data Labels
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Common Issues and Solutions
- **Chart appears empty:** Ensure you have added at least one data series and data point before saving.  
- **Axis numbers not showing percentages:** Remember to set `verticalAxis.setNumberFormatLinkedToSource(false)`; otherwise the custom format is ignored.  
- **License evaluation message:** Apply a valid license file before creating the `Presentation` object to suppress the evaluation banner.

## Frequently Asked Questions

**Q: Can I use this code with Java 11 or newer?**  
A: Yes. The library supports JDK 8+; just use the appropriate classifier (e.g., `jdk16` for JDK 16 or later).

**Q: How do I export the chart as an image instead of a PPTX?**  
A: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding the chart to the slide.

**Q: Is it possible to add a legend to the stacked column chart?**  
A: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My Chart");` and configure `chart.getLegend()` as needed.

**Q: What if I need to update data after the presentation is generated?**  
A: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();` to reflect changes.

**Q: Does Aspose.Slides work on Linux servers?**  
A: Yes. The library is pure Java and runs on any OS with a compatible JRE.

## Conclusion
Следуя этому руководству, вы научились **создавать презентации со сложенной столбчатой диаграммой** с помощью Aspose.Slides for Java, от настройки окружения до тонкой визуальной стилизации. Экспериментируйте с различными наборами данных, цветами и форматами подписей, чтобы ваши отчёты действительно выделялись.

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.Slides 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}