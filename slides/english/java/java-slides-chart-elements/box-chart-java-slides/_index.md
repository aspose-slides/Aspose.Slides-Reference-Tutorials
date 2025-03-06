---
title: Box Chart in Java Slides
linktitle: Box Chart in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to create Box Charts in Java presentations with Aspose.Slides. Step-by-step guide and source code included for effective data visualization.
type: docs
weight: 10
url: /java/chart-elements/box-chart-java-slides/
---

## Introduction to Box Chart in Aspose.Slides for Java

In this tutorial, we will walk you through the process of creating a Box Chart using Aspose.Slides for Java. Box charts are useful for visualizing statistical data with various quartiles and outliers. We will provide step-by-step instructions along with source code to help you get started.

## Prerequisites

Before you begin, make sure you have the following:

- Aspose.Slides for Java library installed and configured.
- A Java development environment set up.

## Step 1: Initialize the Presentation

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

In this step, we initialize a presentation object using the path to an existing PowerPoint file ("test.pptx" in this example).

## Step 2: Create the Box Chart

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

In this step, we create a Box Chart shape on the first slide of the presentation. We also clear any existing categories and series from the chart.

## Step 3: Define Categories

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

In this step, we define the categories for the Box Chart. We use the `IChartDataWorkbook` to add categories and label them accordingly.

## Step 4: Create the Series

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Here, we create a BoxAndWhisker series for the chart and configure various options like quartile method, mean line, mean markers, inner points, and outlier points.

## Step 5: Add Data Points

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

In this step, we add data points to the BoxAndWhisker series. These data points represent the statistical data for the chart.

## Step 6: Save the Presentation

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Finally, we save the presentation with the Box Chart to a new PowerPoint file named "BoxAndWhisker.pptx."

Congratulations! You have successfully created a Box Chart using Aspose.Slides for Java. You can customize the chart further by adjusting various properties and adding more data points as needed.

## Complete Source Code For Box Chart in Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

In this tutorial, we have learned how to create a Box Chart using Aspose.Slides for Java. Box Charts are valuable tools for visualizing statistical data, including quartiles and outliers. We provided a step-by-step guide along with source code to help you get started with creating Box Charts in your Java applications.

## FAQ's

### How can I change the appearance of the Box Chart?

You can customize the appearance of the Box Chart by modifying properties such as line styles, colors, and fonts. Refer to the Aspose.Slides for Java documentation for details on chart customization.

### Can I add additional data series to the Box Chart?

Yes, you can add multiple data series to the Box Chart by creating additional `IChartSeries` objects and adding data points to them.

### What does the QuartileMethodType.Exclusive mean?

The `QuartileMethodType.Exclusive` setting specifies that the quartile calculations should be done using the exclusive method. You can choose different quartile calculation methods depending on your data and requirements.
