---
title: Font Size Legend in Java Slides
linktitle: Font Size Legend in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Enhance PowerPoint presentations with Aspose.Slides for Java. Learn how to customize legend font sizes and more in our step-by-step guide.
weight: 13
url: /java/chart-elements/font-size-legend-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Font Size Legend in Java Slides


## Introduction to Font Size Legend in Java Slides

In this tutorial, you will learn how to customize the font size of the legend in a PowerPoint slide using Aspose.Slides for Java. We will provide step-by-step instructions and source code to achieve this task.

## Prerequisites

Before you begin, make sure you have the Aspose.Slides for Java library installed and set up in your Java project. You can download the library from [here](https://releases.aspose.com/slides/java/).

## Step 1: Initialize the Presentation

First, import the necessary classes and initialize your PowerPoint presentation.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Replace `"Your Document Directory"` with the actual path to your PowerPoint file.

## Step 2: Add a Chart

Next, we will add a chart to the slide and set the font size of the legend.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

In this code, we create a clustered column chart on the first slide and set the font size of the legend text to 20 points. You can adjust the `setFontHeight` value to change the font size as needed.

## Step 3: Customize Axis Values

Now, let's customize the vertical axis values of the chart.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Here, we set the minimum and maximum values for the vertical axis. You can modify the values as per your data requirements.

## Step 4: Save the Presentation

Finally, save the modified presentation to a new file.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

This code saves the modified presentation as "output.pptx" in the specified directory.

## Complete Source Code For Font Size Legend in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

You have successfully customized the font size of the legend in a Java PowerPoint slide using Aspose.Slides for Java. You can further explore the capabilities of Aspose.Slides to create interactive and visually appealing presentations.

## FAQ's

### How do I change the font size of the legend text in a chart?

To change the font size of the legend text in a chart, you can use the following code:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

In this code, we create a chart and set the font size of the legend text to 20 points. You can adjust the `setFontHeight` value to change the font size.

### Can I customize other properties of the legend in a chart?

Yes, you can customize various properties of the legend in a chart using Aspose.Slides. Some of the common properties you can customize include text formatting, position, visibility, and more. For example, to change the legend's position, you can use:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

This code sets the legend to appear at the bottom of the chart. Explore the Aspose.Slides documentation for more customization options.

### How do I set minimum and maximum values for the vertical axis in a chart?

To set minimum and maximum values for the vertical axis in a chart, you can use the following code:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Here, we disable automatic axis scaling and specify the minimum and maximum values for the vertical axis. Adjust the values as needed for your chart data.

### Where can I find more information and documentation for Aspose.Slides?

You can find comprehensive documentation and API references for Aspose.Slides for Java on the Aspose documentation website. Visit [here](https://reference.aspose.com/slides/java/) for detailed information on using the library.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
