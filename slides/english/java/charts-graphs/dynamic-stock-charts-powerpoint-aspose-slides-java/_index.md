---
date: '2026-09-12'
description: Learn how to use Maven Aspose Slides to add and customize dynamic stock
  charts in PowerPoint with Java. Includes setup, adding data series, formatting lines,
  and saving.
images:
- /java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/og-image.png
keywords:
- maven aspose slides
- add data series chart
- format chart lines
- customize chart java
lastmod: '2026-09-12'
og_description: Maven Aspose Slides tutorial shows how to create and customize dynamic
  stock charts in PowerPoint using Java, covering data series, line formatting, and
  saving.
og_image_alt: Illustration of a Java-generated stock chart in PowerPoint using Aspose.Slides
og_title: 'Maven Aspose Slides guide: create dynamic stock charts in PowerPoint'
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
title: 'Maven Aspose Slides: create dynamic stock charts in PowerPoint with Java'
url: /java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose Slides: create dynamic stock charts in PowerPoint with Java

## Introduction

**Maven Aspose Slides** lets you programmatically generate sophisticated PowerPoint presentations from Java. In this tutorial you’ll learn how to create dynamic stock charts, add and format data series, customize chart lines, and finally save the file. Whether you’re a financial analyst preparing quarterly reports or a developer building automated slide decks, the steps below give you a complete, production‑ready solution.

**What you’ll learn**
- How to set up Maven with Aspose.Slides for Java  
- How to add a stock chart and clear default data  
- How to **add data series chart** and **format chart lines**  
- How to **customize chart java**‑specific visual elements  
- How to save the updated presentation

Ready to turn raw numbers into eye‑catching stock visuals? Let’s get started!

## Quick answers
- **Which Maven artifact do I need?** `aspose-slides` version 25.4 (or newer).  
- **Can I run this on any OS?** Yes – the library is pure Java and works on Windows, macOS, and Linux.  
- **Do I need a license for development?** A free temporary license works for testing; a full license is required for production.  
- **What chart types are supported?** Over 70 built‑in chart types, including Stock, Line, and Bar charts.  
- **How large a presentation can I process?** Aspose.Slides can handle files with 500+ slides without loading the whole file into memory.

## What is Maven Aspose Slides?

`Aspose.Slides for Java` is a Java API that enables creation, manipulation, and conversion of PowerPoint files without Microsoft Office. Maven integration simplifies dependency management, letting you pull the library directly from Maven Central.

## Why use Maven Aspose Slides for stock charts?

Aspose.Slides supports **70+ chart types** and can render multi‑hundred‑page presentations in under a second on typical server hardware. Its **high‑low line** and **up/down bar** features give you precise control over financial visualizations, far beyond what PowerPoint’s UI offers.

## Prerequisites

- **Java Development Kit (JDK)** – version 11 or higher.  
- **IDE** – IntelliJ IDEA, Eclipse, or any editor you prefer.  
- **Aspose.Slides for Java** – version 25.4 (the latest at the time of writing).  

### Setting up Aspose.Slides for Java

#### Maven
To integrate Aspose.Slides into your project using Maven, add the following dependency to your `pom.xml`:

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
For Gradle users, include this in your `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Direct download
Alternatively, download the latest JAR from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**License acquisition** – start with a free trial or request a temporary license. For commercial use, purchase a full license.

For detailed API reference, see the [Aspose.Slides documentation](https://docs.aspose.com/slides/java/).

## How to create a dynamic stock chart step by step

Load your presentation, add a stock chart, clear default data, and then inject your own series and categories. The direct answer to the core question is:

> Load an existing PPTX with `new Presentation("template.pptx")`, add a `Chart` of type `ChartType.Stock`, clear its default series and categories, then populate it with your own data points and formatting options. Finally, call `presentation.save("output.pptx", SaveFormat.Pptx)`.

### Initialize presentation
#### Overview
Start by loading an existing PowerPoint file so you can modify it in place.

#### Step‑by‑step
1. **Import the library** – the `Presentation` class is the entry point for all slide operations.  

   ```java
   import com.aspose.slides.Presentation;
   ```

2. **Load the presentation file** – provide the path to your template PPTX.  

   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Ready to perform operations on 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Add stock chart to slide
#### Overview
Insert a Stock chart onto the first slide of the presentation.

The `Chart` class represents a chart shape that can be added to a slide.

#### Direct answer
You add a stock chart by calling `slide.getShapes().addChart(ChartType.Stock, x, y, width, height)`. This creates a chart object that you can immediately manipulate.

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

### Clear existing data series and categories in chart
#### Overview
Remove any pre‑populated series or categories so you can start with a clean data set.

The `ChartData` object holds the series and categories for a chart.

#### Direct answer
Invoke `chart.getChartData().getSeries().clear()` and `chart.getChartData().getCategories().clear()` to wipe the default content before adding your own.

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

### Add categories to chart data
#### Overview
Define the X‑axis categories (e.g., dates) that group your stock values.

A `ChartCategory` represents an X‑axis label for a chart.

#### Direct answer
Create a new `ChartCategory` for each label using `chart.getChartData().getCategories().add(dataWorkbook.getCell(0, row, 0), "Jan")`, repeating for each month or period.

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

### Add data series to chart
#### Overview
Add the four essential series: Open, High, Low, and Close.

A `ChartSeries` holds a collection of data points for a specific series in the chart.

#### Direct answer
For each series, call `chart.getChartData().getSeries().add(dataWorkbook.getCell(0, 0, colIndex), chart.getType())`. This registers the series with the chart’s data workbook.

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

### Add data points to series
#### Overview
Populate each series with numeric values representing stock prices.

A `DataPoint` represents a single value in a series.

#### Direct answer
Loop through your data collection and use `series.getDataPoints().addDataPointForBarSeries(dataWorkbook.getCell(0, row, col), value)` (or the appropriate method for the series type) to insert each point.

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

### Format high‑low lines and up/down bars
#### Overview
Adjust the visual style of the high‑low connectors and the up/down bar fills.

A `Marker` defines the visual symbol for a data point.

#### Direct answer
Set `chart.getChartData().getSeries().get(0).getMarker().setSize(10)` and configure `chart.getChartData().getSeries().get(0).getFormat().getLine().setWidth(2)` to control line thickness and color.

   ```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Format high-low lines for 'Close' series
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

#### Display up/down bars
Use the chart’s `setShowUpDownBars(true)` method to make the up/down bars visible.

   ```java
   // Display up/down bars for the stock chart series group
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### Customize data labels on high‑low lines
#### Overview
Show numeric values directly on the high‑low lines for quick reference.

A `DataLabel` controls the appearance of labels attached to data points.

#### Direct answer
Enable data labels with `chart.getChartData().getSeries().get(0).getDataPoints().get(i).getLabel().setShowValue(true)` and style them as needed.

   ```java
    // Show values on up/down bars for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### Set up/down bars fill color
#### Overview
Give the up bars a green fill and the down bars a red fill to convey market movement intuitively.

The `UpDownBars` object provides access to the up and down bar formatting.

#### Direct answer
Apply `chart.getUpDownBars().getUpBar().getFillFormat().setFillType(FillType.Solid)` and set the solid color to `Color.GREEN`; repeat for the down bar with `Color.RED`.

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

### Save the PowerPoint file
#### Overview
Persist your changes to a new PPTX file.

The `save` method writes the presentation to disk in the specified format.

#### Direct answer
Call `presentation.save("DynamicStockChart.pptx", SaveFormat.Pptx)` – this writes the modified presentation to disk in the standard PowerPoint format.

   ```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## Common issues and troubleshooting

- **Chart not appearing** – ensure the chart’s X/Y coordinates and dimensions are within the slide bounds.  
- **Data points missing** – verify that the data workbook cell indices match the series/row you intend to populate.  
- **License exception** – a temporary trial license expires after 30 days; replace it with a permanent license for production builds.  
- **Performance slowdown on large files** – use `Presentation.setCacheSize(0)` to disable caching if you process thousands of slides in a batch.

## Frequently asked questions

**Q: Can I use this code in a web application?**  
A: Yes. The library is pure Java, so you can run it in any servlet container or Spring Boot service.

**Q: Does Aspose.Slides support other chart types besides Stock?**  
A: Absolutely. It supports over 70 chart types, including Line, Bar, Pie, and Radar charts.

**Q: How do I add a chart title programmatically?**  
A: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")` and then format the title as needed.

**Q: Is there a limit to the number of data points per series?**  
A: Practically, you can add tens of thousands of points; memory usage scales linearly, and the library streams data to keep the footprint low.

**Q: Which Maven coordinates should I use for the latest version?**  
A: The latest version is always available under `com.aspose:aspose-slides:25.4` (or newer) on Maven Central.

---

**Last Updated:** 2026-09-12  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

## Related Tutorials

- [aspose slides maven dependency: Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Create PowerPoint Chart Java – Save Presentations with Charts Using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [Create Format Powerpoint Charts Aspose Slides Java](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}