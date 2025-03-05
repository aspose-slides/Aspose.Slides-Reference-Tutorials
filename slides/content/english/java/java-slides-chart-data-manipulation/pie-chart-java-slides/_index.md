---
title: Pie Chart in Java Slides
linktitle: Pie Chart in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to create stunning Pie Charts in PowerPoint presentations using Aspose.Slides for Java. Step-by-step guide with source code for Java developers.
type: docs
weight: 23
url: /java/chart-data-manipulation/pie-chart-java-slides/
---

## Introduction to Creating a Pie Chart in Java Slides using Aspose.Slides

In this tutorial, we'll demonstrate how to create a Pie Chart in a PowerPoint presentation using Aspose.Slides for Java. We'll provide you with step-by-step instructions and Java source code to help you get started. This guide assumes you have already set up your development environment with Aspose.Slides for Java.

## Prerequisites

Before you begin, make sure you have the Aspose.Slides for Java library installed and configured in your project. You can download it from [here](https://releases.aspose.com/slides/java/).

## Step 1: Import Required Libraries

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Make sure to import the necessary classes from the Aspose.Slides library.

## Step 2: Initialize the Presentation

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

// Instantiate Presentation class that represents PPTX file
Presentation presentation = new Presentation();
```

Create a new Presentation object to represent your PowerPoint file. Replace `"Your Document Directory"` with the actual path where you want to save the presentation.

## Step 3: Add a Slide

```java
// Access the first slide
ISlide slide = presentation.getSlides().get_Item(0);
```

Get the first slide of the presentation where you want to add the Pie Chart.

## Step 4: Add a Pie Chart

```java
// Add a pie chart with default data
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

Add a Pie Chart to the slide at the specified position and size.

## Step 5: Set Chart Title

```java
// Set chart title
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

Set a title for the Pie Chart. You can customize the title as needed.

## Step 6: Customize Chart Data

```java
// Set the first series to show values
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Setting the index of the chart data sheet
int defaultWorksheetIndex = 0;

// Getting the chart data worksheet
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Delete default generated series and categories
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Adding new categories
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// Adding new series
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Populating series data
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Customize the chart data by adding categories and series, and setting their values. In this example, we have three categories and one series with corresponding data points.

## Step 7: Customize Pie Chart Sectors

```java
// Set sector colors
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Customize the appearance of each sector
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Customize sector border
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Customize other sectors in a similar way
```

Customize the appearance of each sector in the Pie Chart. You can change the colors, border styles, and other visual properties.

## Step 8: Customize Data Labels

```java
// Customize data labels
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Customize data labels for other data points in a similar way
```

Customize data labels for each data point in the Pie Chart. You can control which values are displayed on the chart.

## Step 9: Show Leader Lines

```java
// Show leader lines for the chart
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Enable leader lines to connect data labels to their corresponding sectors.

## Step 10: Set Pie Chart Rotation Angle

```java
// Set the rotation angle for Pie Chart sectors
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Set the rotation angle for the Pie Chart sectors. In this example, we set it to 180 degrees.

## Step 11: Save the Presentation

```java
// Save the presentation with the Pie Chart
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Save the presentation with the Pie Chart to the specified directory.

## Complete Source Code For Pie Chart in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Instantiate Presentation class that represents PPTX file
Presentation presentation = new Presentation();
// Access first slide
ISlide slides = presentation.getSlides().get_Item(0);
// Add chart with default data
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// Setting chart Title
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Set first series to Show Values
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Setting the index of chart data sheet
int defaultWorksheetIndex = 0;
// Getting the chart data worksheet
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Delete default generated series and categories
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Adding new categories
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// Adding new series
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Now populating series data
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Not working in new version
// Adding new points and setting sector color
// series.IsColorVaried = true;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Setting Sector border
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// Setting Sector border
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// Setting Sector border
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// Create custom labels for each of categories for new series
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(true);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// Showing Leader Lines for Chart
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// Setting Rotation Angle for Pie Chart Sectors
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Save presentation with chart
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Conclusion

You have successfully created a Pie Chart in a PowerPoint presentation using Aspose.Slides for Java. You can customize the chart's appearance and data labels according to your specific requirements. This tutorial provides a basic example, and you can further enhance and customize your charts as needed.

## FAQ's

### How can I change the colors of individual sectors in the Pie Chart?

To change the colors of individual sectors in the Pie Chart, you can customize the fill color for each data point. In the provided code example, we demonstrated how to set the fill color for each sector using the `getSolidFillColor().setColor()` method. You can modify the color values to achieve the desired appearance.

### Can I add more categories and data series to the Pie Chart?

Yes, you can add additional categories and data series to the Pie Chart. To do this, you can use the `getChartData().getCategories().add()` and `getChartData().getSeries().add()` methods, as shown in the example. Simply provide the appropriate data and labels for the new categories and series to expand your chart.

### How do I customize the appearance of data labels?

You can customize the appearance of data labels using the `getDataLabelFormat()` method on each data point's label. In the example, we demonstrated how to show the value on data labels using `getDataLabelFormat().setShowValue(true)`. You can further customize data labels by controlling which values are displayed, showing legend keys, and adjusting other formatting options.

### Can I change the title of the Pie Chart?

Yes, you can change the title of the Pie Chart. In the provided code, we set the chart title using `chart.getChartTitle().addTextFrameForOverriding("Sample Title")`. You can replace `"Sample Title"` with your desired title text.

### How do I save the generated presentation with the Pie Chart?

To save the presentation with the Pie Chart, use the `presentation.save()` method. Provide the desired file path and name along with the format in which you want to save the presentation. For example:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Make sure to specify the correct file path and format.

### Can I create other types of charts using Aspose.Slides for Java?

Yes, Aspose.Slides for Java supports various chart types, including Bar Charts, Line Charts, and more. You can create different types of charts by changing the `ChartType` when adding a chart. Refer to the Aspose.Slides documentation for more details on creating different types of charts.

### How can I find more information and examples for working with Aspose.Slides for Java?

For more information, detailed documentation, and additional examples, you can visit the [Aspose.Slides for Java documentation](https://reference.aspose.com/slides/java/). It provides comprehensive resources to help you use the library effectively.
