---
title: "How to Create Chart: Stacked Column with Aspose.Slides Java"
description: "Learn how to create chart using Aspose.Slides for Java, including percentage stacked column setup, axis formatting, and data label customization."
date: "2026-01-24"
weight: 1
url: "/java/charts-graphs/aspose-slides-java-stacked-column-charts/"
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Master Stacked Column Charts in Java with Aspose.Slides: A Comprehensive Guide

## Introduction

Elevate your presentations by incorporating insightful data visualizations with the power of Aspose.Slides for Java. In this tutorial you’ll learn **how to create chart**‑driven slides that turn raw numbers into clear stories—whether you’re preparing business reports, project dashboards, or marketing decks.  

We’ll walk through setting up your environment, adding a **percentage stacked column** chart, and customizing axes, series, and data labels so the final deck looks polished and professional.

Let’s dive into creating presentations that captivate your audience.

## Quick Answers
- **What is the primary library?** Aspose.Slides for Java
- **Which Maven artifact adds the library?** `com.aspose:aspose-slides` (see *aspose slides maven* section)
- **How to add a percentage stacked column chart?** Use `ChartType.PercentsStackedColumn` when calling `addChart`
- **Can I format chart axis numbers?** Yes – set `verticalAxis.setNumberFormat("0.00%")`
- **How to customize data label text?** Override each point’s `ITextFrame` via `point.getLabel().getTextFrameForOverriding()`

## What is a Stacked Column Chart?
A stacked column chart groups multiple data series in a single column, letting you compare the total size while still seeing each component’s contribution. The **percentage stacked column** variant normalizes each column to 100 %, making it ideal for showing proportional data across categories.

## Why Use Aspose.Slides for Java?
- **No Office installation required** – generate PPTX files on any server.
- **Full‑featured chart API** – supports all chart types, including the percentage stacked column.
- **Cross‑platform compatibility** – works on Windows, Linux, and macOS.
- **Easy Maven/Gradle integration** – see the *aspose slides maven* snippet below.

## Prerequisites
- **Java Development Kit (JDK):** 8 or higher.
- **IDE:** IntelliJ IDEA, Eclipse, or any Java‑compatible editor.
- **Build tool (optional):** Maven or Gradle for dependency management.
- **Basic Java knowledge** – you should be comfortable with classes, methods, and collections.

## Setting Up Aspose.Slides for Java
To get started, you need to include the Aspose.Slides library in your project.

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download:**  
Alternatively, download the latest JAR from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### License Acquisition
You can start with a free trial to explore Aspose.Slides features. To remove evaluation limitations, consider obtaining a temporary or purchased license.

- **Free Trial:** Access limited features without immediate costs.  
- **Temporary License:** Request via [Aspose’s site](https://purchase.aspose.com/temporary-license/).  
- **Purchase:** Visit the purchase page for full access.

### Basic Initialization
Here's how you initialize Aspose.Slides in your Java application:
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

## How to Create Chart: Step-by-Step Guide

### Creating a Presentation and Adding a Slide
**Overview:** Start by creating a simple presentation with an initial slide. This is your foundation for further enhancements.

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
```java
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Adding Percentage Stacked Column Chart to a Slide
**Overview:** Enhance your slide by adding a **percentage stacked column** chart, allowing for easy data comparison.

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
**Overview:** Customize the number format of your chart's vertical axis for enhanced readability.

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
**Overview:** Populate your chart with **add series data** so it becomes informative and visually appealing.

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
**Overview:** Enhance your chart's aesthetics by formatting the fill color of each series.

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
**Overview:** Make your data labels more readable by **format chart data labels** to show custom text.

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

## Common Use Cases
- **Quarterly sales dashboards** – visualize product‑line contributions as a percentage of total revenue.  
- **Project resource allocation** – show how team members split across tasks in a single column.  
- **Survey results** – compare answer distributions across multiple questions.

## Frequently Asked Questions

**Q: Do I need a paid license to generate stacked column charts?**  
A: A free trial lets you create charts, but a permanent license removes evaluation watermarks and unlocks full functionality.

**Q: Can I change the chart type after it’s created?**  
A: Yes, you can replace the chart by removing the existing shape and adding a new one with a different `ChartType`.

**Q: How do I export the presentation to PDF?**  
A: Use `presentation.save("output.pdf", SaveFormat.Pdf);` after you’ve finished editing the slides.

**Q: Is the API compatible with Java 11 and newer?**  
A: Absolutely. The library works with JDK 8 through JDK 21; just choose the appropriate classifier (e.g., `jdk16`).

**Q: What if I need to add more than three series?**  
A: Simply repeat the series‑adding block, adjusting the worksheet cell references for each new series.

## Conclusion
By following this guide you now know **how to create chart** visualizations with Aspose.Slides for Java, from setting up the Maven/Gradle dependency to customizing a percentage stacked column chart’s axes, series colors, and data labels. Experiment with different data sets, apply your own branding colors, and integrate these slides into automated reporting pipelines.

---

**Last Updated:** 2026-01-24  
**Tested With:** Aspose.Slides 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}