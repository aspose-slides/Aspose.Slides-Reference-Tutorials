---
title: Automatic Chart Series Color in Java Slides
linktitle: Automatic Chart Series Color in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to create dynamic charts with automatic series color in PowerPoint presentations using Aspose.Slides for Java. Enhance your data visualizations effortlessly.
weight: 14
url: /java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduction to Automatic Chart Series Color in Aspose.Slides for Java

In this tutorial, we will explore how to create a PowerPoint presentation with a chart using Aspose.Slides for Java and set automatic fill colors for chart series. Automatic fill colors can make your charts more visually appealing and save you time by letting the library choose colors for you.

## Prerequisites

Before you begin, make sure you have the Aspose.Slides for Java library installed in your project. You can download it from [here](https://releases.aspose.com/slides/java/).

## Step 1: Create a New Presentation

First, we'll create a new PowerPoint presentation and add a slide to it.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an instance of Presentation class
Presentation presentation = new Presentation();
```

## Step 2: Add a Chart to the Slide

Next, we'll add a clustered column chart to the slide. We'll also set the first series to show values.

```java
// Access first slide
ISlide slide = presentation.getSlides().get_Item(0);
// Add chart with default data
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Set first series to Show Values
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Step 3: Populate Chart Data

Now, we'll populate the chart with data. We'll start by deleting the default generated series and categories and then add new series and categories.

```java
// Setting the index of chart data sheet
int defaultWorksheetIndex = 0;
// Getting the chart data worksheet
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Delete default generated series and categories
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Adding new series
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Adding new categories
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Step 4: Populate Series Data

We will populate the series data for both Series 1 and Series 2.

```java
// Take first chart series
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Now populating series data
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Take second chart series
series = chart.getChartData().getSeries().get_Item(1);
// Now populating series data
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Step 5: Set Automatic Fill Color for Series

Now, let's set automatic fill colors for the chart series. This will make the library choose colors for us.

```java
// Setting automatic fill color for series
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Step 6: Save the Presentation

Finally, we'll save the presentation with the chart to a PowerPoint file.

```java
// Save presentation with chart
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Complete Source Code For Automatic Chart Series Color in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an instance of Presentation class
Presentation presentation = new Presentation();
try
{
	// Access first slide
	ISlide slide = presentation.getSlides().get_Item(0);
	// Add chart with default data
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	// Set first series to Show Values
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Setting the index of chart data sheet
	int defaultWorksheetIndex = 0;
	// Getting the chart data worksheet
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Delete default generated series and categories
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// Adding new series
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// Adding new categories
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// Take first chart series
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	// Now populating series data
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// Setting automatic fill color for series
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Take second chart series
	series = chart.getChartData().getSeries().get_Item(1);
	// Now populating series data
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// Setting fill color for series
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// Save presentation with chart
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

In this tutorial, we've learned how to create a PowerPoint presentation with a chart using Aspose.Slides for Java and set automatic fill colors for chart series. Automatic colors can enhance the visual appeal of your charts and make your presentations more engaging. You can further customize the chart as needed for your specific requirements.

## FAQ's

### How do I set automatic fill colors for chart series in Aspose.Slides for Java?

To set automatic fill colors for chart series in Aspose.Slides for Java, use the following code:

```java
// Setting automatic fill color for series
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

This code will let the library choose colors automatically for the chart series.

### Can I customize the chart colors if needed?

Yes, you can customize the chart colors as needed. In the example provided, we used automatic fill colors, but you can set specific colors by modifying the `FillType` and `SolidFillColor` properties of the series' format.

### How can I add additional series or categories to the chart?

To add additional series or categories to the chart, use the `getSeries()` and `getCategories()` methods of the chart's `ChartData` object. You can add new series and categories by specifying their data and labels.

### Is it possible to further format the chart and labels?

Yes, you can further format the chart, series, and labels as needed. Aspose.Slides for Java provides extensive formatting options for charts, including fonts, colors, styles, and more. You can explore the documentation for more details on formatting options.

### Where can I find more information on working with Aspose.Slides for Java?

For more information and detailed documentation on Aspose.Slides for Java, you can visit the reference documentation [here](https://reference.aspose.com/slides/java/).

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
