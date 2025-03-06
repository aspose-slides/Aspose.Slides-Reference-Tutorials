---
title: Sunburst Chart in Java Slides
linktitle: Sunburst Chart in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Create Stunning Sunburst Charts in Java Slides with Aspose.Slides. Learn Step-by-Step Chart Creation and Data Manipulation.
weight: 16
url: /java/chart-elements/sunburst-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sunburst Chart in Java Slides


## Introduction to Sunburst Chart in Java Slides with Aspose.Slides

In this tutorial, you will learn how to create a Sunburst chart in a PowerPoint presentation using the Aspose.Slides for Java API. A Sunburst chart is a radial chart used to represent hierarchical data. We'll provide step-by-step instructions along with source code.

## Prerequisites

Before you begin, make sure you have the Aspose.Slides for Java library installed and configured in your Java project. You can download the library from [here](https://releases.aspose.com/slides/java/).

## Step 1: Import Required Libraries

First, import the necessary libraries to work with Aspose.Slides and create a Sunburst chart in your Java application.

```java
import com.aspose.slides.*;
```

## Step 2: Initialize the Presentation

Initialize a PowerPoint presentation and specify the directory where your presentation file will be saved.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Step 3: Create the Sunburst Chart

Create a Sunburst chart on a slide. We specify the position (X, Y) and dimensions (width, height) of the chart.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## Step 4: Prepare Chart Data

Clear any existing categories and series data from the chart, and create a data workbook for the chart.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## Step 5: Define Chart Hierarchy

Define the hierarchical structure of the Sunburst chart. You can add branches, stems, and leaves as categories.

```java
// Branch 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// Branch 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## Step 6: Add Data to the Chart

Add data points to the Sunburst chart series.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## Step 7: Save the Presentation

Finally, save the presentation with the Sunburst chart.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Complete Source Code For Sunburst Chart in Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//branch 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//branch 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

In this tutorial, you've learned how to create a Sunburst chart in a PowerPoint presentation using the Aspose.Slides for Java API. You've seen how to initialize the presentation, create the chart, define chart hierarchy, add data points, and save the presentation. You can now use this knowledge to create interactive and informative Sunburst charts in your Java applications.

## FAQ's

### How do I customize the appearance of the Sunburst chart?

You can customize the appearance of the Sunburst chart by modifying properties such as colors, labels, and styles. Refer to the Aspose.Slides documentation for detailed customization options.

### Can I add more data points to the chart?

Yes, you can add more data points to the chart by using the `series.getDataPoints().addDataPointForSunburstSeries()` method for each data point you want to include.

### How can I add tooltips to the Sunburst chart?

To add tooltips to the Sunburst chart, you can set the data label format to display additional information, such as values or descriptions, when hovering over chart segments.

### Is it possible to create interactive Sunburst charts with hyperlinks?

Yes, you can create interactive Sunburst charts with hyperlinks by adding hyperlinks to specific chart elements or segments. Refer to the Aspose.Slides documentation for details on adding hyperlinks.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
