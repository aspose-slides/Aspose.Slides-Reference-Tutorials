---
title: "Create Doughnut Chart Java with Aspose.Slides Guide"
description: "Learn how to create doughnut chart java using Aspose.Slides. This step‑by‑step guide covers Maven Aspose Slides dependency setup, chart configuration, and saving presentations."
date: "2026-03-07"
weight: 1
url: "/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Create Doughnut Chart Java with Aspose.Slides Guide

## Introduction

Creating a **doughnut chart** programmatically can turn raw numbers into an eye‑catching visual that instantly tells a story. In Java, **Aspose.Slides** makes this process straightforward, letting you generate presentation‑ready charts without ever opening PowerPoint. In this tutorial you’ll learn how to **create doughnut chart java** step by step— from setting up the Maven Aspose Slides dependency to customizing series, categories, and finally saving the presentation.

By the end of this guide you’ll be able to embed dynamic doughnut charts into any PPTX file, perfect for reports, dashboards, or automated slide decks.

### Quick Answers
- **What library is used?** Aspose.Slides for Java  
- **Primary task?** Create doughnut chart java in a PPTX file  
- **How to add the library?** Use the Maven Aspose Slides dependency (or Gradle)  
- **Minimum Java version?** JDK 16 or higher  
- **Can I customize colors and labels?** Yes, the API provides full formatting control  

## What is a Doughnut Chart and Why Use It?

A doughnut chart is a variation of a pie chart with a blank center, allowing you to display multiple data series in concentric rings. This makes it ideal for comparing parts of a whole across several categories—think sales by region over multiple quarters or budget allocations across departments.

## Why Use Aspose.Slides for Java?

- **No Office installation required** – generate PPTX files on any server.  
- **Rich API** – full control over chart types, data points, and styling.  
- **High performance** – optimized for large presentations.  
- **Cross‑platform** – works on Windows, Linux, and macOS.

## Prerequisites

- **Required Libraries:**  
  - Aspose.Slides for Java version 25.4 or later.  

- **Environment Setup:**  
  - JDK 16 or higher.  
  - Your favorite IDE (IntelliJ IDEA, Eclipse, NetBeans, etc.).  

- **Knowledge Prerequisites:**  
  - Basic Java programming.  
  - Familiarity with Maven or Gradle for dependency management.

## Maven Aspose Slides Dependency

Add the following Maven dependency to your `pom.xml`. This is the **maven aspose slides dependency** you need to pull the library into your project.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

If you prefer Gradle, use the equivalent snippet below.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

You can also download the JAR directly from the official release page:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Acquiring a License

To remove the evaluation watermark and unlock the full feature set:

- **Free trial** – start with a temporary license.  
- **Temporary license** – request one from the [Aspose website](https://purchase.aspose.com/temporary-license/).  
- **Commercial license** – purchase for production use.

Apply the license in your code:

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Implementation Guide

### Initializing Presentation and Adding a Doughnut Chart

First, create or load a presentation and add a doughnut chart to the first slide.

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Configuring the Chart Data Workbook and Clearing Existing Data

Next, obtain the workbook that backs the chart and clear any default series or categories.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Adding Series to the Chart

Now we’ll add up to 15 series. Each series can be customized—here we set the explosion, doughnut‑hole size, and first‑slice angle.

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Adding Categories and Data Points

We’ll create 15 categories and populate each series with a data point. The last series receives special label formatting.

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Saving the Presentation

Finally, write the updated presentation to disk.

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Common Issues and Solutions

- **License not found** – Verify the path to `license.lic` is correct and the file is readable.  
- **Chart appears blank** – Ensure you cleared existing series/categories before adding new ones.  
- **Incorrect colors** – Check that `FillType.Solid` is set for both fill and line formats.  
- **Performance with many series** – Limit the number of series/categories or reuse the workbook cells.

## Frequently Asked Questions

**Q: Can I generate a doughnut chart without a pre‑existing PPTX file?**  
A: Yes, instantiate `new Presentation()` to start from a blank slide deck.

**Q: Does Aspose.Slides support exporting to PDF?**  
A: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`.

**Q: How do I change the doughnut hole size?**  
A: Use `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` where value is 0‑100.

**Q: Is it possible to add data labels to all series, not just the last one?**  
A: Yes, move the label‑formatting block outside the `if (i == ...)` condition and apply it to each `dataPoint`.

**Q: What versions of Java are supported?**  
A: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the appropriate classifier.

---

**Last Updated:** 2026-03-07  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}