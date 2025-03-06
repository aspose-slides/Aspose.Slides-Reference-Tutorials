---
title: Default Markers in Chart in Java Slides
linktitle: Default Markers in Chart in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to create Java Slides with default markers in charts using Aspose.Slides for Java. Step-by-step guide with source code.
weight: 16
url: /java/chart-data-manipulation/default-markers-in-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduction to Default Markers in Chart in Java Slides

In this tutorial, we'll explore how to create a chart with default markers using Aspose.Slides for Java. Default markers are symbols or shapes added to data points in a chart to highlight them. We'll create a line chart with markers to visualize data.

## Prerequisites

Before you begin, make sure you have the Aspose.Slides for Java library installed and set up in your Java project.

## Step 1: Create a Presentation

First, let's create a presentation and add a slide to it. We'll then add a chart to the slide.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Step 2: Add a Line Chart with Markers

Now, let's add a line chart with markers to the slide. We'll also clear any default data from the chart.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Step 3: Populate Chart Data

We'll populate the chart with sample data. In this example, we'll create two series with data points and categories.

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Series 1
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

// Series 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Populating series data
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## Step 4: Customize the Chart

You can customize the chart further, such as adding a legend and adjusting its appearance.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## Step 5: Save the Presentation

Finally, save the presentation with the chart to your desired location.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

That's it! You've created a line chart with default markers using Aspose.Slides for Java.

## Complete Source Code For Default Markers in Chart in Java Slides

```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //Take second chart series
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //Now populating series data
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Conclusion

In this comprehensive tutorial, you've learned how to create Java Slides with default markers in charts using Aspose.Slides for Java. We covered the entire process, from setting up a presentation to customizing the chart's appearance and saving the result.

## FAQ's

### How can I change the marker symbols?

You can customize the marker symbols by setting the marker style for each data point. Use `IDataPoint.setMarkerStyle()` to change the marker symbol.

### How do I adjust the chart's colors?

To modify the chart's colors, you can use the `IChartSeriesFormat` and `IShapeFillFormat` interfaces to set fill and line properties.

### Can I add labels to the data points?

Yes, you can add labels to data points using the `IDataPoint.getLabel()` method and customize them as needed.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
