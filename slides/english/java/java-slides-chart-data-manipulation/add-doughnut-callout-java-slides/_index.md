---
title: Add Doughnut Callout in Java Slides
linktitle: Add Doughnut Callout in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn to Add Doughnut Callouts in Java Slides using Aspose.Slides for Java. Step-by-step guide with source code for enhanced presentations.
weight: 12
url: /java/chart-data-manipulation/add-doughnut-callout-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Doughnut Callout in Java Slides


## Introduction to Add a Doughnut Callout in Java Slides using Aspose.Slides for Java

In this tutorial, we will walk you through the process of adding a Doughnut Callout to a slide in Java using Aspose.Slides for Java. A Doughnut Callout is a chart element that can be used to highlight specific data points in a Doughnut chart. We will provide you with step-by-step instructions and complete source code for your convenience.

## Prerequisites

Before you begin, make sure you have the following prerequisites in place:

1. Java Development Environment
2. Aspose.Slides for Java library
3. Integrated Development Environment (IDE) like Eclipse or IntelliJ IDEA
4. A PowerPoint presentation where you want to add the Doughnut Callout

## Step 1: Set up your Java Project

1. Create a new Java project in your chosen IDE.
2. Add the Aspose.Slides for Java library to your project as a dependency.

## Step 2: Initialize the Presentation

To get started, you'll need to initialize a PowerPoint presentation and create a slide where you want to add the Doughnut Callout. Here's the code to achieve this:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

Make sure to replace `"Your Document Directory"` with the actual path to your PowerPoint presentation file.

## Step 3: Create a Doughnut Chart

Next, you'll create a Doughnut chart on the slide. You can customize the chart's position and size as per your requirements. Here's the code to add a Doughnut chart:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Step 4: Customize the Doughnut Chart

Now, it's time to customize the Doughnut chart. We'll set various properties like removing the legend, configuring the hole size, and adjusting the first slice angle. Here's the code:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

This code snippet sets the properties for the Doughnut chart. You can adjust the values to meet your specific needs.

## Step 5: Add Data to the Doughnut Chart

Now, let's add data to the Doughnut chart. We'll also customize the appearance of the data points. Here's the code to accomplish this:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Customize data point appearance here
        i++;
    }
    categoryIndex++;
}
```

In this code, we're adding categories and data points to the Doughnut chart. You can further customize the appearance of data points as needed.

## Step 6: Save the Presentation

Finally, don't forget to save your presentation after adding the Doughnut Callout. Here's the code to save the presentation:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

Make sure to replace `"chart.pptx"` with your desired file name.

Congratulations! You have successfully added a Doughnut Callout to a Java slide using Aspose.Slides for Java. You can now run your Java application to generate the PowerPoint presentation with the Doughnut chart and Callout.

## Complete Source Code For Add Doughnut Callout in Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
			IDataLabel lbl = dataPoint.getLabel();
			lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
			lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
			lbl.getDataLabelFormat().setShowValue(false);
			lbl.getDataLabelFormat().setShowCategoryName(true);
			lbl.getDataLabelFormat().setShowSeriesName(false);
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## Conclusion

In this tutorial, we have covered the process of adding a Doughnut Callout to a Java slide using Aspose.Slides for Java. You've learned how to create a Doughnut chart, customize its appearance, and add data points. Feel free to further enhance your presentations with this powerful library and explore more charting options.

## FAQ's

### How can I change the appearance of the Doughnut Callout?

You can customize the appearance of the Doughnut Callout by modifying the properties of data points in the chart. In the code provided, you can see how to set the fill color, line color, font style, and other attributes of data points.

### Can I add more data points to the Doughnut chart?

Yes, you can add as many data points as needed to the Doughnut chart. Simply extend the loops in the code where categories and data points are added, and provide the appropriate data and formatting.

### How can I adjust the position and size of the Doughnut chart on the slide?

You can change the position and size of the Doughnut chart by modifying the parameters in the `addChart` method. The four numbers in that method correspond to the X and Y coordinates of the chart's top-left corner and its width and height, respectively.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
