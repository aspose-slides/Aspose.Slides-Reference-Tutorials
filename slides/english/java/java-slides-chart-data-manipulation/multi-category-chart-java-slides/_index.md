---
title: Multi-Category Chart in Java Slides
linktitle: Multi-Category Chart in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Create Multi-Category Charts in Java Slides using Aspose.Slides for Java. Step-by-step guide with source code for impressive data visualization in presentations.
weight: 20
url: /java/chart-data-manipulation/multi-category-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduction to Multi-Category Chart in Java Slides with Aspose.Slides

In this tutorial, we will learn how to create a multi-category chart in Java slides using the Aspose.Slides for Java API. This guide will provide step-by-step instructions along with source code to help you create a clustered column chart with multiple categories and series.

## Prerequisites
Before we begin, make sure you have the Aspose.Slides for Java library installed and set up in your Java development environment.

## Step 1: Setting up the Environment
First, import the necessary classes and create a new Presentation object to work with slides.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Step 2: Adding a Slide and Chart
Next, create a slide and add a clustered column chart to it.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## Step 3: Clearing Existing Data
Clear any existing data from the chart.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## Step 4: Setting Up Data Categories
Now, let's set up data categories for the chart. We will create multiple categories and group them.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// Add categories and group them
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## Step 5: Adding Series
Now, let's add a series to the chart along with data points.

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## Step 6: Saving the Presentation
Finally, save the presentation with the chart.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

That's it! You've successfully created a multi-category chart in a Java slide using Aspose.Slides. You can customize this chart further to suit your specific requirements.

## Complete Source Code For Multi-Category Chart in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
//            Adding Series
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
// Save presentation with chart
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Conclusion

In this tutorial, we have learned how to create a multi-category chart in Java slides using the Aspose.Slides for Java API. We went through a step-by-step guide with source code to create a clustered column chart with multiple categories and series.

## FAQ's

### How can I customize the chart appearance?

You can customize the chart appearance by modifying properties such as colors, fonts, and styles. Refer to the Aspose.Slides documentation for detailed customization options.

### Can I add more series to the chart?

Yes, you can add additional series to the chart by following a similar process as shown in Step 5.

### How do I change the chart type?

To change the chart type, replace `ChartType.ClusteredColumn` with the desired chart type when adding the chart in Step 2.

### How can I add a title to the chart?

You can add a title to the chart by using the `ch.getChartTitle().getTextFrame().setText("Chart Title");` method.

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
