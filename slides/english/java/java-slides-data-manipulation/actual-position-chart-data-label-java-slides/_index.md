---
title: Get Actual Position of Chart Data Label in Java Slides
linktitle: Get Actual Position of Chart Data Label in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to get the actual position of chart data labels in Java Slides using Aspose.Slides for Java. Step-by-step guide with source code.
weight: 18
url: /java/data-manipulation/actual-position-chart-data-label-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Get Actual Position of Chart Data Label in Java Slides


## Introduction to Get Actual Position of Chart Data Label in Java Slides

In this tutorial, you will learn how to retrieve the actual position of chart data labels using Aspose.Slides for Java. We will create a Java program that generates a PowerPoint presentation with a chart, customizes the data labels, and then adds shapes representing the positions of these data labels.

## Prerequisites

Before you begin, make sure you have the Aspose.Slides for Java library set up in your Java project.

## Step 1: Create a PowerPoint Presentation

First, let's create a new PowerPoint presentation and add a chart to it. We will customize the chart's data labels later in the tutorial.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## Step 2: Customize Data Labels
Now, let's customize the data labels for the chart series. We will set their position and show the values.

```java
try {
    // ... (previous code)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (remaining code)
} finally {
    if (pres != null) pres.dispose();
}
```

## Step 3: Get Actual Position of Data Labels
In this step, we will iterate through the data points of the chart series and retrieve the actual position of data labels that have a value greater than 4. We will then add ellipses to represent these positions.

```java
try {
    // ... (previous code)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ... (remaining code)
} finally {
    if (pres != null) pres.dispose();
}
```

## Step 4: Save the Presentation
Finally, save the generated presentation to a file.

```java
try {
    // ... (previous code)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Complete Source Code for Get Actual Position of Chart Data Label in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//TODO
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

In this tutorial, you have learned how to retrieve the actual position of chart data labels in Java Slides using Aspose.Slides for Java. You can now use this knowledge to enhance your PowerPoint presentations with customized data labels and visual representations of their positions.

## FAQ's

### How can I customize data labels in a chart?

To customize data labels in a chart, you can use the `setDefaultDataLabelFormat` method on the chart series and set properties like position and visibility. For example:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### How can I add shapes to represent data label positions?

You can iterate through the data points of a chart series and use the `getActualX`, `getActualY`, `getActualWidth`, and `getActualHeight` methods of the data label to get its position. Then, you can add shapes using the `addAutoShape` method. Here's an example:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### How can I save the generated presentation?

You can save the generated presentation using the `save` method. Provide the desired file path and the `SaveFormat` as parameters. For example:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
