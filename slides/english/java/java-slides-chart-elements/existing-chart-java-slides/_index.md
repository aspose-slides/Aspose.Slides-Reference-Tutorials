---
title: Existing Chart in Java Slides
linktitle: Existing Chart in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Enhance your PowerPoint presentations with Aspose.Slides for Java. Learn to modify existing charts programmatically. Step-by-step guide with source code for chart customization.
weight: 12
url: /java/chart-elements/existing-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Existing Chart in Java Slides


## Introduction to Existing Chart in Java Slides using Aspose.Slides for Java

In this tutorial, we'll demonstrate how to modify an existing chart in a PowerPoint presentation using Aspose.Slides for Java. We'll go through the steps to change chart data, category names, series names, and add a new series to the chart. Make sure you have Aspose.Slides for Java set up in your project.

## Prerequisites

Before we begin, ensure you have the following prerequisites in place:

1. Aspose.Slides for Java library included in your project.
2. An existing PowerPoint presentation with a chart that you want to modify.
3. Java development environment set up.

## Step 1: Load the Presentation

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

// Instantiate Presentation class that represents PPTX file
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Step 2: Access the Slide and Chart

```java
// Access the first slide
ISlide sld = pres.getSlides().get_Item(0);

// Access the chart on the slide
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Step 3: Change Chart Data and Category Names

```java
// Setting the index of the chart data sheet
int defaultWorksheetIndex = 0;

// Getting the chart data worksheet
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Change chart category names
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Step 4: Update First Chart Series

```java
// Take the first chart series
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Update series name
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Update series data
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Step 5: Update Second Chart Series

```java
// Take the second chart series
series = chart.getChartData().getSeries().get_Item(1);

// Update series name
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Update series data
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Step 6: Add a New Series to the Chart

```java
// Adding a new series
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Take the third chart series
series = chart.getChartData().getSeries().get_Item(2);

// Populate series data
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Step 7: Change Chart Type

```java
// Change the chart type to Clustered Cylinder
chart.setType(ChartType.ClusteredCylinder);
```

## Step 8: Save the Modified Presentation

```java
// Save the presentation with the modified chart
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Congratulations! You have successfully modified an existing chart in a PowerPoint presentation using Aspose.Slides for Java. You can now use this code to customize charts in your PowerPoint presentations programmatically.

## Complete Source Code For Existing Chart in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Instantiate Presentation class that represents PPTX file// Instantiate Presentation class that represents PPTX file
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Access first slideMarker
ISlide sld = pres.getSlides().get_Item(0);
// Add chart with default data
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Setting the index of chart data sheet
int defaultWorksheetIndex = 0;
// Getting the chart data worksheet
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Changing chart Category Name
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Take first chart series
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Now updating series data
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Modifying series name
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Take Second chart series
series = chart.getChartData().getSeries().get_Item(1);
// Now updating series data
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Modifying series name
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Now, Adding a new series
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Take 3rd chart series
series = chart.getChartData().getSeries().get_Item(2);
// Now populating series data
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Save presentation with chart
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Conclusion

In this comprehensive tutorial, we've learned how to modify an existing chart in a PowerPoint presentation using Aspose.Slides for Java. By following the step-by-step guide and utilizing source code examples, you can easily customize and update charts to meet your specific requirements. Here's a recap of what we covered:

## FAQ's

### How can I change the chart type?

You can change the chart type by using the `chart.setType(ChartType.ChartTypeHere)` method. Replace `ChartTypeHere` with the desired chart type, such as `ChartType.ClusteredCylinder` in our example.

### Can I add more data points to a series?

Yes, you can add more data points to a series using the `series.getDataPoints().addDataPointForBarSeries(cell)` method. Make sure to provide the appropriate cell data.

### How do I update the category names?

You can update category names by using `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` to set the new category names.

### How do I modify series names?

To modify series names, use `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` to set the new series names.

### Is there a way to remove a series from the chart?

Yes, you can remove a series from the chart by using the `chart.getChartData().getSeries().removeAt(index)` method, where `index` is the index of the series you want to remove.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
