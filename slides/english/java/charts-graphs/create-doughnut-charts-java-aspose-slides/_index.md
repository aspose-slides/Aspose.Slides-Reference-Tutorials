---
date: '2026-08-16'
description: Learn how to add doughnut charts in Java using Aspose.Slides. This step‑by‑step
  guide covers Maven dependency setup, chart configuration, colors, labels and saving
  the PPTX.
images:
- /java/charts-graphs/create-doughnut-charts-java-aspose-slides/og-image.png
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: How to add doughnut charts in Java using Aspose.Slides. Follow this
  guide to set up Maven, customize colors, labels and generate PPTX files.
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: How to add doughnut chart in Java with Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: How to add doughnut chart in Java with Aspose.Slides
url: /java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# How to add doughnut chart in Java with Aspose.Slides

## Introduction

Creating a **doughnut chart** programmatically can turn raw numbers into an eye‑catching visual that instantly tells a story. In Java, **Aspose.Slides** makes this process straightforward, letting you generate presentation‑ready charts without ever opening PowerPoint. In this tutorial you’ll learn **how to add doughnut** charts to a PPTX file step by step— from setting up the Maven Aspose Slides dependency to customizing series, categories, colors, and labels, and finally saving the presentation.

By the end of this guide you’ll be able to embed dynamic doughnut charts into any PPTX file, perfect for reports, dashboards, or automated slide decks.

### Quick Answers
- **What library is used?** Aspose.Slides for Java  
- **Primary task?** Add a doughnut chart in a PPTX file  
- **How to add the library?** Use the Maven Aspose Slides dependency (or Gradle)  
- **Minimum Java version?** JDK 16 or higher  
- **Can I customize colors and labels?** Yes, the API provides full formatting control  

## What is a doughnut chart and why use it?

A doughnut chart is a variation of a pie chart with a blank centre, allowing multiple data series to be displayed as concentric rings. **It visualizes parts‑of‑a‑whole across several categories while preserving space for additional information in the centre.** This makes it ideal for comparing sales by region over multiple quarters, budget allocations across departments, or any scenario where you need to show hierarchical proportion data.

## Why use Aspose.Slides for Java?

You can add a doughnut chart without installing Microsoft Office, and the library processes **over 50 + input and output formats** while handling presentations that exceed 500 slides. Aspose.Slides delivers **up to 3× faster rendering** compared with native Office automation on the same hardware, and it works on Windows, Linux and macOS. These quantified benefits mean you can generate large slide decks on headless servers with predictable performance.

## Prerequisites

- **Required libraries**  
  - Aspose.Slides for Java 25.4 or later (the library that enables you to add doughnut charts).  

- **Environment**  
  - JDK 16 or higher installed on your machine.  
  - An IDE such as IntelliJ IDEA, Eclipse or NetBeans.  

- **Knowledge**  
  - Basic Java syntax and object‑oriented concepts.  
  - Familiarity with Maven or Gradle for dependency management.  

## Maven Aspose Slides dependency

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
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

You can also download the JAR directly from the official release page:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Acquiring a license

To remove the evaluation watermark and unlock the full feature set:

- **Free trial** – start with a temporary license.  
- **Temporary license** – request one from the [Aspose website](https://purchase.aspose.com/temporary-license/).  
- **Commercial license** – purchase for production use.

Apply the license in your code:

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## Implementation guide

### Initializing a presentation and adding a doughnut chart

Presentation is the Aspose.Slides class that represents a PowerPoint presentation.  
Load an existing PPTX or create a new `Presentation` object, then add a doughnut chart to the first slide.

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### Configuring the chart data workbook and clearing existing data

The workbook is an internal spreadsheet that stores the chart’s data.  
Obtain the workbook that backs the chart, then clear any default series or categories so you can start with a clean slate.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Adding series to the chart

A series represents a collection of data points plotted on the chart.  
You can add up to 15 series. Each series can be customized—here we set the explosion, doughnut‑hole size, and first‑slice angle.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### Adding categories and data points

Categories are the labels for each data point along the chart’s axis.  
Create 15 categories and populate each series with a data point. The last series receives special label formatting.

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### Customizing colors and data labels

`FillType.Solid` specifies a solid fill color for chart elements.  
Set a solid fill color for each series and enable data labels. For the final series we also change the label font color.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### Saving the presentation

`save` writes the presentation to a file in the chosen format.  
Write the updated presentation to disk in PPTX format, or export to PDF if required.

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## Common issues and solutions

- **License not found** – Verify the path to `license.lic` is correct and the file is readable.  
- **Chart appears blank** – Ensure you cleared existing series/categories before adding new ones.  
- **Incorrect colors** – Confirm that `FillType.Solid` is set for both fill and line formats.  
- **Performance with many series** – Limit the number of series/categories or reuse workbook cells to keep memory usage under control.  

## Frequently asked questions

**Q: Can I generate a doughnut chart without a pre‑existing PPTX file?**  
A: Yes, instantiate `new Presentation()` to start from a blank slide deck, then add a chart as shown above.

**Q: Does Aspose.Slides support exporting to PDF?**  
A: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);` to get a PDF version of the slide.

**Q: How do I change the doughnut hole size?**  
A: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` where `value` ranges from 0 to 100.

**Q: Is it possible to add data labels to all series, not just the last one?**  
A: Yes, move the label‑formatting block outside the `if (i == ...)` condition and apply it to each `dataPoint`.

**Q: What versions of Java are supported?**  
A: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the appropriate classifier in the Maven dependency.

---

**Last Updated:** 2026-08-16  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

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

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Related Tutorials

- [How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [How to Customize Pie Chart Colors in Java with Aspose.Slides – A Complete Guide](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Animate PowerPoint Chart Categories with Aspose.Slides for Java | Step-by-Step Guide](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}