---
title: Setting Automatic Pie Chart Slice Colors in Java Slides
linktitle: Setting Automatic Pie Chart Slice Colors in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to create dynamic pie charts with automatic slice colors in Java PowerPoint presentations using Aspose.Slides for Java. Step-by-step guide with source code.
type: docs
weight: 24
url: /java/java-slides-data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/
---

## Introduction to Setting Automatic Pie Chart Slice Colors in Java Slides

In this tutorial, we will explore how to create a pie chart in a PowerPoint presentation using Aspose.Slides for Java and set automatic slice colors for the chart. We will provide step-by-step guidance along with source code.

## Prerequisites

Before you begin, make sure you have the Aspose.Slides for Java library installed and set up in your Java project. You can download the library from the Aspose website: [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

## Step 1: Import Required Packages

First, you need to import the necessary packages from Aspose.Slides for Java:

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## Step 2: Create a PowerPoint Presentation

Instantiate the `Presentation` class to create a new PowerPoint presentation:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Step 3: Add a Slide

Access the first slide of the presentation and add a chart to it with default data:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## Step 4: Set Chart Title

Set a title for the chart:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Step 5: Configure Chart Data

Set the chart to show values for the first series and configure the chart data:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Step 6: Add Categories and Series

Add new categories and series to the chart:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## Step 7: Populate Series Data

Populate the series data for the pie chart:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## Step 8: Enable Varied Slice Colors

Enable varied slice colors for the pie chart:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Step 9: Save the Presentation

Finally, save the presentation to a PowerPoint file:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Complete Source Code For Setting Automatic Pie Chart Slice Colors in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Instantiate Presentation class that represents PPTX file
Presentation presentation = new Presentation();
try
{
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
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

You have successfully created a pie chart in a PowerPoint presentation using Aspose.Slides for Java and configured it to have automatic slice colors. This step-by-step guide provides you with the necessary source code to achieve this. You can further customize the chart and presentation as needed.

## FAQ's

### How can I customize the colors of individual slices in the pie chart?

To customize the colors of individual slices in the pie chart, you can use the `getAutomaticSeriesColors` method to retrieve the default color scheme and then modify the colors as needed. Here's an example:

```java
// Get the default color scheme
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Modify the colors as needed
colors.get_Item(0).setColor(Color.RED); // Set the color of the first slice to red
colors.get_Item(1).setColor(Color.BLUE); // Set the color of the second slice to blue
// Add more color modifications as required
```

### How can I add a legend to the pie chart?

To add a legend to the pie chart, you can use the `getLegend` method and configure it as follows:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Set the legend position
legend.setOverlay(true); // Display the legend over the chart
```

### Can I change the title font and style?

Yes, you can change the title font and style. Use the following code to set the title font and style:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Set font size
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Make the title bold
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // Make the title italic
```

You can adjust the font size, boldness, and italic style as needed.
