---
title: Normal Charts in Java Slides
linktitle: Normal Charts in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Create Normal Charts in Java Slides with Aspose.Slides for Java. Step-by-step guide and source code for creating, customizing, and saving charts in PowerPoint presentations.
weight: 21
url: /java/chart-data-manipulation/normal-charts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Normal Charts in Java Slides


## Introduction to Normal Charts in Java Slides

In this tutorial, we will walk through the process of creating normal charts in Java Slides using the Aspose.Slides for Java API. We will use step-by-step instructions along with source code to demonstrate how to create a clustered column chart in a PowerPoint presentation.

## Prerequisites

Before you begin, make sure you have the following prerequisites in place:

1. Aspose.Slides for Java API installed.
2. A Java development environment set up.
3. Basic knowledge of Java programming.

## Step 1: Setting Up the Project

Ensure you have a directory for your project. Let's call it "Your Document Directory" as mentioned in the code. You can replace this with the actual path to your project directory.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create directory if it is not already present.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Step 2: Creating a Presentation

Now, let's create a PowerPoint presentation and access its first slide.

```java
// Instantiate Presentation class that represents PPTX file
Presentation pres = new Presentation();
// Access first slide
ISlide sld = pres.getSlides().get_Item(0);
```

## Step 3: Adding a Chart

We will add a clustered column chart to the slide and set its title.

```java
// Add chart with default data
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Setting chart Title
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Step 4: Setting Chart Data

Next, we will set the chart data by defining series and categories.

```java
// Set first series to Show Values
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

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

## Step 5: Populating Series Data

Now, let's populate the series data points for the chart.

```java
// Take first chart series
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Populating series data
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Setting fill color for series
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Take second chart series
series = chart.getChartData().getSeries().get_Item(1);

// Populating series data
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Setting fill color for series
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Step 6: Customizing Labels

Let's customize the data labels for the chart series.

```java
// First label will show Category name
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Show value for the third label with series name and separator
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## Step 7: Saving the Presentation

Finally, save the presentation with the chart to your project directory.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

That's it! You have successfully created a clustered column chart in a PowerPoint presentation using Aspose.Slides for Java. You can customize this chart further according to your requirements.

## Complete Source Code For Normal Charts in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create directory if it is not already present.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Instantiate Presentation class that represents PPTX file
Presentation pres = new Presentation();
// Access first slide
ISlide sld = pres.getSlides().get_Item(0);
// Add chart with default data
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Setting chart Title
// Chart.getChartTitle().getTextFrameForOverriding().setText("Sample Title");
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
// Setting fill color for series
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Take second chart series
series = chart.getChartData().getSeries().get_Item(1);
// Now populating series data
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Setting fill color for series
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// First label will be show Category name
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Show value for third label
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Save presentation with chart
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Conclusion

In this tutorial, we have learned how to create normal charts in Java Slides using the Aspose.Slides for Java API. We walked through a step-by-step guide with source code to create a clustered column chart in a PowerPoint presentation.

## FAQ's

### How can I change the chart type?

To change the chart type, modify the `ChartType` parameter when adding the chart using `sld.getShapes().addChart()`. You can choose from various chart types available in Aspose.Slides.

### Can I change the colors of the chart series?

Yes, you can change the colors of the chart series by setting the fill color for each series using `series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### How do I add more categories or series to the chart?

You can add more categories or series to the chart by adding new data points and labels using the `chart.getChartData().getCategories().add()` and `chart.getChartData().getSeries().add()` methods.

### How can I customize the chart title further?

You can customize the chart title further by modifying the properties of `chart.getChartTitle()` such as text alignment, font size, and color.

### How do I save the chart to a different file format?

To save the chart to a different file format, change the `SaveFormat` parameter in the `pres.save()` method to the desired format (e.g., PDF, PNG, JPEG).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
