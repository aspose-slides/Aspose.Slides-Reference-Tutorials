---
title: Add Error Bars in Java Slides
linktitle: Add Error Bars in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to add error bars to PowerPoint charts in Java using Aspose.Slides. Step-by-step guide with source code for customizing error bars.
weight: 13
url: /java/chart-data-manipulation/add-error-bars-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Error Bars in Java Slides


## Introduction to Adding Error Bars in Java Slides using Aspose.Slides

In this tutorial, we will demonstrate how to add error bars to a chart in a PowerPoint slide using Aspose.Slides for Java. Error bars provide valuable information about the variability or uncertainty of data points in a chart. We will create a bubble chart and add error bars to it. Let's get started!

## Prerequisites

Before you begin, make sure you have the Aspose.Slides for Java library installed and set up in your Java project. You can download the library from the [Aspose website](https://downloads.aspose.com/slides/java).

## Step 1: Create an Empty Presentation

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Creating empty presentation
Presentation presentation = new Presentation();
```

In this step, we create an empty presentation where we will add our chart with error bars.

## Step 2: Create a Bubble Chart

```java
// Creating a bubble chart
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Here, we create a bubble chart and specify its position and dimensions on the slide.

## Step 3: Adding Error Bars and Setting Format

```java
// Adding Error bars and setting its format
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

In this step, we add error bars to the chart and set their format. You can customize error bars by changing values, types, and other properties.

- `errBarX` represents error bars along the X-axis.
- `errBarY` represents error bars along the Y-axis.
- We make both X and Y error bars visible.
- `setValueType` specifies the value type for error bars (e.g., Fixed or Percentage).
- `setValue` sets the value for error bars.
- `setType` defines the type of error bars (e.g., Plus or Minus).
- We set the width of the error bar lines using `getFormat().getLine().setWidth(2)`.
- `setEndCap` specifies whether to include end caps on the error bars.

## Step 4: Save the Presentation

```java
// Saving presentation
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Finally, we save the presentation with the added error bars to a specified location.

That's it! You have successfully added error bars to a chart in a PowerPoint slide using Aspose.Slides for Java.

## Complete Source Code For Add Error Bars in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Creating empty presentation
Presentation presentation = new Presentation();
try
{
	// Creating a bubble chart
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Adding Error bars and setting its format
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// Saving presentation
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

In this tutorial, we have explored how to enhance your PowerPoint presentations by adding error bars to charts using Aspose.Slides for Java. Error bars provide valuable insights into data variability and uncertainties, making your presentations more informative and visually appealing.

## FAQ's

### How can I customize the appearance of error bars further?

You can customize error bars by modifying their properties, such as line style, color, and width, as demonstrated in Step 3.

### Can I add error bars to different chart types?

Yes, you can add error bars to various chart types supported by Aspose.Slides for Java. Simply create the desired chart type and follow the same error bar customization steps.

### How can I adjust the position and size of the chart on the slide?

You can control the position and dimensions of the chart by adjusting the parameters in the `addChart` method, as shown in Step 2.

### Where can I find more information about Aspose.Slides for Java?

You can refer to the [Aspose.Slides for Java documentation](https://reference.aspose.com/slides/java/) for detailed information on using the library.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
