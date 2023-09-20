---
title: Manage Properties Charts in Java Slides
linktitle: Manage Properties Charts in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn to create stunning charts and manage properties in Java slides with Aspose.Slides. Step-by-step guide with source code for powerful presentations.
type: docs
weight: 13
url: /java/java-slides-data-manipulation/manage-properties-charts-java-slides/
---

## Introduction to Managing Properties and Charts in Java Slides using Aspose.Slides

In this tutorial, we will explore how to manage properties and create charts in Java slides using Aspose.Slides. Aspose.Slides is a powerful Java API for working with PowerPoint presentations. We will walk through the step-by-step process, including source code examples.

## Prerequisites

Before we begin, make sure you have the Aspose.Slides library for Java installed and set up in your project. You can download it from [here](https://releases.aspose.com/slides/java/).

## Adding a Chart to a Slide

To add a chart to a slide, follow these steps:

1. Import the necessary classes and create an instance of the Presentation class.

```java
// Create an instance of Presentation class
Presentation presentation = new Presentation();
```

2. Access the slide where you want to add the chart. In this example, we access the first slide.

```java
// Access first slide
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Add a chart with default data. In this case, we're adding a StackedColumn3D chart.

```java
// Add chart with default data
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Setting Chart Data

To set the chart data, we need to create a chart data workbook and add series and categories. Follow these steps:

4. Set the index of the chart data sheet.

```java
// Setting the index of chart data sheet
int defaultWorksheetIndex = 0;
```

5. Get the chart data workbook.

```java
// Getting the chart data worksheet
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Add series to the chart. In this example, we add two series named "Series 1" and "Series 2."

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Add categories to the chart. Here, we add three categories.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Setting 3D Rotation Properties

Now, let's set 3D rotation properties for the chart:

8. Set the right angle axes.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. Set the rotation angles for X and Y axes. In this example, we rotate X by 40 degrees and Y by 270 degrees.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Set the depth percentage to 150.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Populating Series Data

11. Take the second chart series and populate it with data points.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Populate series data
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Adjusting Overlap

12. Set the overlap value for series. For example, you can set it to 100 for no overlap.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## Saving the Presentation

Finally, save the presentation to disk.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

That's it! You've successfully created a 3D stacked column chart with custom properties using Aspose.Slides in Java.

## Complete Source Code For Manage Properties Charts in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an instance of Presentation class
Presentation presentation = new Presentation();
// Access first slide
ISlide slide = presentation.getSlides().get_Item(0);
// Add chart with default data
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// Setting the index of chart data sheet
int defaultWorksheetIndex = 0;
// Getting the chart data worksheet
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Add series
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Add Catrgories
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Set Rotation3D properties
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Take second chart series
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Now populating series data
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Set OverLap value
series.getParentSeriesGroup().setOverlap((byte) 100);
// Write presentation to disk
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Conclusion

In this tutorial, we delved into the world of managing properties and creating charts in Java slides using Aspose.Slides. Aspose.Slides is a robust Java API that empowers developers to work with PowerPoint presentations efficiently. We covered the essential steps and provided source code examples to guide you through the process.

## FAQ's

### How can I change the chart type?

You can change the chart type by modifying the `ChartType` parameter when adding the chart. Refer to Aspose.Slides documentation for available chart types.

### Can I customize the chart colors?

Yes, you can customize the chart colors by setting the fill properties of series data points or categories.

### How do I add more data points to a series?

You can add more data points to a series by using the `series.getDataPoints().addDataPointForBarSeries()` method and specifying the cell containing the data value.

### How can I set a different rotation angle?

To set a different rotation angle for the X and Y axes, use `chart.getRotation3D().setRotationX()` and `chart.getRotation3D().setRotationY()` with the desired angle values.

### What other 3D properties can I customize?

You can explore other 3D properties of the chart, such as depth, perspective, and lighting, by referring to the Aspose.Slides documentation.
