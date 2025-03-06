---
title: Set Invert Fill Color Chart in Java Slides
linktitle: Set Invert Fill Color Chart in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to set invert fill colors for Java Slides charts using Aspose.Slides. Enhance your chart visualizations with this step-by-step guide and source code.
weight: 22
url: /java/data-manipulation/set-invert-fill-color-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Set Invert Fill Color Chart in Java Slides


## Introduction to Set Invert Fill Color Chart in Java Slides

In this tutorial, we will demonstrate how to set the invert fill color for a chart in Java Slides using Aspose.Slides for Java. Inverting fill color is a useful feature when you want to highlight negative values in a chart with a specific color. We will provide step-by-step instructions and source code for achieving this.

## Prerequisites

Before you begin, make sure you have the following prerequisites in place:

1. Aspose.Slides for Java library installed.
2. Java development environment set up.

## Step 1: Create a Presentation

First, we need to create a presentation to add our chart to. You can use the following code to create a presentation:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Step 2: Add a Chart

Next, we will add a clustered column chart to the presentation. Here's how you can do it:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Step 3: Set Up Chart Data

Now, let's set up the chart data, including series and categories:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Adding new series and categories
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## Step 4: Populate Series Data

Now, let's populate the series data for the chart:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Step 5: Set Invert Fill Color

To set the invert fill color for the chart series, you can use the following code:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

In the above code, we set the series to invert fill color for negative values and specify the color for the inverted fill.

## Step 6: Save the Presentation

Finally, save the presentation with the chart:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Complete Source Code For Set Invert Fill Color Chart in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Adding new series and categories
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// Take first chart series and populating series data.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## Conclusion

In this tutorial, we have shown you how to set the invert fill color for a chart in Java Slides using Aspose.Slides for Java. This feature allows you to highlight negative values in your charts with a specific color, making your data more visually informative.

## FAQ's

In this section, we will address some common questions related to setting the invert fill color for a chart in Java Slides using Aspose.Slides for Java.

### How do I install Aspose.Slides for Java?

You can install Aspose.Slides for Java by including the Aspose.Slides JAR files in your Java project. You can download the library from the [Aspose.Slides for Java download page](https://releases.aspose.com/slides/java/). Follow the installation instructions provided in the documentation for your specific development environment.

### Can I customize the color for inverted fill in the chart series?

Yes, you can customize the color for the inverted fill in the chart series. In the provided code example, the `series.getInvertedSolidFillColor().setColor(Color.RED)` line sets the color to red for the inverted fill. You can replace `Color.RED` with any other color of your choice.

### How can I modify the chart type in Aspose.Slides for Java?

You can modify the chart type by changing the `ChartType` parameter when adding a chart to the presentation. In the code example, we used `ChartType.ClusteredColumn`. You can explore other chart types such as line charts, bar charts, pie charts, etc., by specifying the appropriate `ChartType` enum value.

### How do I add multiple data series to a chart?

To add multiple data series to a chart, you can use the `chart.getChartData().getSeries().add(...)` method for each series you want to add. Make sure to provide the appropriate data points and labels for each series to populate your chart with multiple series.

### Is there a way to customize other aspects of the chart appearance?

Yes, you can customize various aspects of the chart appearance, including axis labels, titles, legends, and more using Aspose.Slides for Java. Refer to the documentation for detailed guidance on customizing chart elements and appearance.

### Can I save the chart in different formats?

Yes, you can save the chart in different formats using Aspose.Slides for Java. In the provided code example, we saved the presentation as a PPTX file. You can use different `SaveFormat` options to save it in other formats like PDF, PNG, or SVG, depending on your requirements.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
