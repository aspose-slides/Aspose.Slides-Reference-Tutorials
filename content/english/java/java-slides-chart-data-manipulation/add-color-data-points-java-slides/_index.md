---
title: Add Color to Data Points in Java Slides
linktitle: Add Color to Data Points in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to add color to data points in Java slides using Aspose.Slides for Java.
type: docs
weight: 10
url: /java/chart-data-manipulation/add-color-data-points-java-slides/
---

## Introduction to Add Color to Data Points in Java Slides

In this tutorial, we will demonstrate how to add color to data points in Java slides using Aspose.Slides for Java. This step-by-step guide includes source code examples to help you achieve this task.

## Prerequisites

Before you begin, make sure you have the following prerequisites in place:

- Java Development Environment
- Aspose.Slides for Java library

## Step 1: Create a New Presentation

First, we'll create a new presentation using Aspose.Slides for Java. This presentation will serve as the container for our chart.

```java
Presentation pres = new Presentation();
```

## Step 2: Add a Sunburst Chart

Now, let's add a Sunburst chart to the presentation. We specify the chart type, position, and size.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## Step 3: Access Data Points

To modify data points in the chart, we need to access the `IChartDataPointCollection` object.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## Step 4: Customize Data Points

In this step, we'll customize specific data points. Here, we are changing the color of data points and configuring label settings.

```java
// Customize data point 0
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// Customize data point 9
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## Step 5: Save the Presentation

Finally, save the presentation with the customized chart.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

That's it! You have successfully added color to specific data points in a Java slide using Aspose.Slides for Java.

## Complete Source Code For Add Color to Data Points in Java Slides

```java
Presentation pres = new Presentation();
try
{
	// The path to the documents directory.
	String dataDir = "Your Document Directory";
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
	IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
	dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
	IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
	branch1Label.getDataLabelFormat().setShowCategoryName(false);
	branch1Label.getDataLabelFormat().setShowSeriesName(true);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
	IFormat steam4Format = dataPoints.get_Item(9).getFormat();
	steam4Format.getFill().setFillType(FillType.Solid);
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//TODO
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

In this tutorial, you learned how to add color to data points in Java slides using Aspose.Slides for Java. You can further customize your charts and presentations based on your specific requirements.

## FAQ's

### How can I change the color of other data points?

To change the color of other data points, you can follow a similar approach as shown in Step 4. Access the data point you want to customize and modify its color and label settings.

### Can I customize other aspects of the chart?

Yes, you can customize various aspects of the chart, including fonts, labels, titles, and more. Refer to the [Aspose.Slides for Java documentation](https://reference.aspose.com/slides/java/) for detailed customization options.

### Where can I find more examples and documentation?

You can find more examples and detailed documentation on using Aspose.Slides for Java on the [Aspose.Slides documentation](https://reference.aspose.com/slides/java/) website.
