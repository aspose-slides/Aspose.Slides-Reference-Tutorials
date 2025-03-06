---
title: Histogram Chart in Java Slides
linktitle: Histogram Chart in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to create Histogram Charts in PowerPoint presentations using Aspose.Slides for Java. Step-by-step guide with source code for data visualization.
weight: 19
url: /java/chart-data-manipulation/histogram-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Histogram Chart in Java Slides


## Introduction to Histogram Chart in Java Slides using Aspose.Slides

In this tutorial, we will guide you through the process of creating a Histogram Chart in a PowerPoint presentation using the Aspose.Slides for Java API. A Histogram Chart is used to represent the distribution of data over a continuous interval.

## Prerequisites

Before you begin, make sure you have the Aspose.Slides for Java library installed. You can download it from the [Aspose website](https://releases.aspose.com/slides/java/).

## Step 1: Initialize Your Project

Create a Java project and include the Aspose.Slides library in your project's dependencies.

## Step 2: Import Necessary Libraries

```java
import com.aspose.slides.*;
```

## Step 3: Load an Existing Presentation

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Make sure to replace `"Your Document Directory"` with the actual path to your PowerPoint document.

## Step 4: Create a Histogram Chart

Now, let's create a Histogram Chart on a slide in the presentation.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Add data points to the series
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // Set horizontal axis aggregation type to Automatic
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // Save the presentation
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

In this code, we first clear any existing categories and series from the chart. Then, we add data points to the series using the `getDataPoints().addDataPointForHistogramSeries` method. Finally, we set the horizontal axis aggregation type to Automatic and save the presentation.

## Complete Source Code For Histogram Chart in Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
	chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
	pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

In this tutorial, we've explored how to create a Histogram Chart in a PowerPoint presentation using the Aspose.Slides for Java API. Histogram Charts are valuable tools for visualizing the distribution of data over a continuous interval, and they can be a powerful addition to your presentations, especially when dealing with statistical or analytical content.

## FAQ's

### How do I install Aspose.Slides for Java?

You can download the Aspose.Slides for Java library from [here](https://releases.aspose.com/slides/java/). Follow the installation instructions provided on their website.

### What is a Histogram Chart used for?

A Histogram Chart is used to visualize the distribution of data over a continuous interval. It's commonly used in statistics to represent frequency distributions.

### Can I customize the appearance of the Histogram Chart?

Yes, you can customize the appearance of the chart, including its colors, labels, and axes, using the Aspose.Slides API.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
