---
title: Scattered Chart in Java Slides
linktitle: Scattered Chart in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to create Scatter Charts in Java using Aspose.Slides. Step-by-step guide with Java source code for data visualization in presentations.
type: docs
weight: 11
url: /java/java-slides-chart-creation/scattered-chart-java-slides/
---

## Introduction to Scattered Chart in Aspose.Slides for Java

In this tutorial, we will guide you through the process of creating a Scatter Chart using Aspose.Slides for Java. Scatter charts are useful for visualizing data points on a two-dimensional plane. We'll provide step-by-step instructions and include Java source code for your convenience.

## Prerequisites

Before you begin, make sure you have the following prerequisites in place:

1. [Aspose.Slides for Java](https://products.aspose.com/slides/java) installed.
2. A Java development environment set up.

## Step 1: Initialize the Presentation

First, import the necessary libraries and create a new presentation.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

// Create directory if it is not already present.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Create a new presentation
Presentation pres = new Presentation();
```

## Step 2: Add a Slide and Create the Scatter Chart

Next, add a slide and create the scatter chart on it. We'll use the `ScatterWithSmoothLines` chart type in this example.

```java
// Get the first slide
ISlide slide = pres.getSlides().get_Item(0);

// Creating the scatter chart
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Step 3: Prepare Chart Data

Now, let's prepare the data for our scatter chart. We'll add two series, each with multiple data points.

```java
// Getting the default chart data worksheet index
int defaultWorksheetIndex = 0;

// Getting the chart data worksheet
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Delete demo series
chart.getChartData().getSeries().clear();

// Add the first series
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Take the first chart series
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Add data points to the first series
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Edit the type of series
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Change marker size
series.getMarker().setSymbol(MarkerStyleType.Star); // Change marker symbol

// Take the second chart series
series = chart.getChartData().getSeries().get_Item(1);

// Add data points to the second series
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// Change the marker style for the second series
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## Step 4: Save the Presentation

Finally, save the presentation with the scatter chart to a PPTX file.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

That's it! You've successfully created a Scatter Chart using Aspose.Slides for Java. You can now customize this example further to suit your specific data and design requirements.

## Complete Source Code For Scattered Chart in Java Slides
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create directory if it is not already present.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// Creating the default chart
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Getting the default chart data worksheet index
int defaultWorksheetIndex = 0;
// Getting the chart data worksheet
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Delete demo series
chart.getChartData().getSeries().clear();
// Add new series
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Take first chart series
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Add new point (1:3) there.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Add new point (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Edit the type of series
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Changing the chart series marker
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Take second chart series
series = chart.getChartData().getSeries().get_Item(1);
// Add new point (5:2) there.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Add new point (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Add new point (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Add new point (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Changing the chart series marker
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Conclusion

In this tutorial, we've walked you through the process of creating a Scatter Chart using Aspose.Slides for Java. Scatter charts are powerful tools for visualizing data points in a two-dimensional space, making it easier to analyze and understand complex data relationships.

## FAQ's

### How can I change the chart type?

To change the chart type, use the `setType` method on the chart series and provide the desired chart type. For example, `series.setType(ChartType.Line)` would change the series to a line chart.

### How do I customize the marker size and style?

You can change the marker size and style using the `getMarker` method on the series and then set the size and symbol properties. For example:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Feel free to explore more customization options in the Aspose.Slides for Java documentation.

Remember to replace `"Your Document Directory"` with the actual path where you want to save the presentation.
