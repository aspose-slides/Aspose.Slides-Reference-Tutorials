---
title: "Create Scatter Chart Java with Aspose.Slides – Customize and Save"
description: "Step‑by‑step guide to create scatter chart java using Aspose.Slides, add data points scatter and work with multiple series scatter chart."
date: "2026-01-24"
weight: 1
url: "/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/"
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Create Scatter Chart Java with Aspose.Slides

In this tutorial you’ll **create scatter chart java** projects from scratch, add data points scatter, and learn how to work with multiple series scatter chart—all using Aspose.Slides for Java. We’ll walk through directory setup, presentation initialization, chart creation, data management, marker customization, and finally saving the presentation.

**What You'll Learn**
- Setting up a directory for storing presentation files  
- Initializing and manipulating presentations using Aspose.Slides  
- Creating a scatter chart on a slide  
- Adding and managing data points for each series  
- Customizing series types, markers, and handling multiple series scatter chart  
- Saving the finished presentation  

Let's get started with the prerequisites.

## Quick Answers
- **What is the primary library?** Aspose.Slides for Java  
- **Which Java version is required?** JDK 8 or higher (JDK 16 recommended)  
- **Can I add more than two series?** Yes – you can add any number of series to a scatter chart  
- **How do I change marker colors?** Use `series.getMarker().getFillFormat().setFillColor(Color)`  
- **Is a license needed for production?** Yes, a commercial license removes evaluation limits  

## Prerequisites

To follow this tutorial, ensure you have:
- **Aspose.Slides for Java** – version 25.4 or later.  
- **Java Development Kit (JDK)** – JDK 8 or newer.  
- Basic Java knowledge and familiarity with Maven or Gradle.  

## Setting Up Aspose.Slides for Java

Integrate Aspose.Slides into your project with one of the following methods.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Or download the latest package from [Aspose Releases](https://releases.aspose.com/slides/java/).

#### License Acquisition
- **Free Trial** – 30‑day evaluation.  
- **Temporary License** – Extended testing.  
- **Commercial License** – Full production use.

Now let’s dive into the code.

## Implementation Guide

### Step 1: Directory Setup
First, make sure the output folder exists so the presentation can be saved without errors.

```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```

### Step 2: Presentation Initialization
Create a new presentation and grab the first slide.

```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Step 3: Add a Scatter Chart
Insert a scatter chart with smooth lines onto the slide.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### Step 4: Manage Chart Data (Clear & Add Series)
Clear any default series and add our own series for the **multiple series scatter chart**.

```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### Step 5: Add Data Points Scatter
Populate each series with X‑Y values using **add data points scatter**.

```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### Step 6: Customize Series Types & Markers
Adjust the visual style—switch to straight lines with markers and set distinct marker symbols.

```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### Step 7: Save the Presentation
Persist the file to disk.

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Practical Applications
- **Financial Analysis** – Plot stock price movements with multiple series scatter chart.  
- **Scientific Research** – Visualize experimental measurements using add data points scatter for precise data representation.  
- **Project Management** – Show resource allocation trends across several projects on a single scatter chart.

## Performance Considerations
- Dispose of the `Presentation` object after saving to free memory.  
- For large datasets, populate the workbook in batches rather than one‑by‑one.  
- Avoid excessive styling inside tight loops; apply styles after data insertion.

## Common Issues & Solutions
| Issue | Solution |
|-------|----------|
| **Chart appears empty** | Verify that data points are added to the correct series and that the workbook indices match. |
| **Markers not visible** | Ensure `series.getMarker().setSize()` is set to a value greater than 0 and that the marker symbol is defined. |
| **OutOfMemoryError on large charts** | Use `pres.dispose()` after saving and consider increasing JVM heap size (`-Xmx`). |

## Frequently Asked Questions

### How do I change the color of the markers?
Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color` is an instance of `java.awt.Color`.

### Can I add more than two series to a scatter chart?
Absolutely. Repeat the series‑creation block (Step 4) for each additional series you need.

### Is it possible to export the chart as an image?
Yes. Call `chart.exportChartImage("chart.png", ImageFormat.Png)` after adding all data.

### Does Aspose.Slides support interactive tooltips on scatter points?
While PowerPoint itself doesn’t provide runtime tooltips, you can embed data labels using `series.getDataPoints().get_Item(i).getLabel().setText("Your text")`.

### How can I animate the scatter series?
Use `chart.getChartData().getSeries().get_Item(i).getFormat().getEffectFormat().setPresetEffect(PresetEffectType.Appear)` to add a simple appear animation.

---

**Last Updated:** 2026-01-24  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}