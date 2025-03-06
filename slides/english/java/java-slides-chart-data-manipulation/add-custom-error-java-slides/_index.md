---
title: Add Custom Error in Java Slides
linktitle: Add Custom Error in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to add custom error bars to PowerPoint charts in Java Slides using Aspose.Slides. Step-by-step guide with source code for precise data visualization.
weight: 11
url: /java/chart-data-manipulation/add-custom-error-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Custom Error in Java Slides


## Introduction to Adding Custom Error Bars in Java Slides using Aspose.Slides

In this tutorial, you will learn how to add custom error bars to a chart in a PowerPoint presentation using Aspose.Slides for Java. Error bars are useful for displaying variability or uncertainty in data points on a chart.

## Prerequisites

Before you begin, make sure you have the following:

- Aspose.Slides for Java library installed and configured in your project.
- A Java development environment set up.

## Step 1: Create an Empty Presentation

First, create an empty PowerPoint presentation.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Creating empty presentation
Presentation presentation = new Presentation();
```

## Step 2: Add a Bubble Chart

Next, we'll add a bubble chart to the presentation.

```java
// Creating a bubble chart
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Step 3: Add Custom Error Bars

Now, let's add custom error bars to the chart series.

```java
// Adding custom Error bars and setting their format
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Step 4: Set Error Bars Data

In this step, we'll access the chart series data points and set the custom error bars values for each point.

```java
// Accessing chart series data points and setting error bars values for individual points
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Setting error bars for chart series points
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## Step 5: Save the Presentation

Finally, save the presentation with the custom error bars.

```java
// Saving presentation
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

That's it! You have successfully added custom error bars to a chart in a PowerPoint presentation using Aspose.Slides for Java.

## Complete Source Code For Add Custom Error in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Creating empty presentation
Presentation presentation = new Presentation();
try
{
	// Creating a bubble chart
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Adding custom Error bars and setting its format
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Accessing chart series data point and setting error bars values for individual point
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Setting error bars for chart series points
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// Saving presentation
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

In this comprehensive tutorial, you've learned how to enhance your PowerPoint presentations by adding custom error bars to charts using Aspose.Slides for Java. Error bars provide valuable insights into data variability and uncertainty, making your charts more informative and visually appealing.

## FAQ's

### How do I customize the appearance of error bars?

You can customize the appearance of error bars by modifying the properties of the `IErrorBarsFormat` object, such as line style, line color, and error bar width.

### Can I add error bars to other chart types?

Yes, you can add error bars to various chart types supported by Aspose.Slides for Java, including bar charts, line charts, and scatter charts.

### How do I set different error bar values for each data point?

You can loop through the data points and set custom error bar values for each point, as shown in the code above.

### Is it possible to hide error bars for specific data points?

Yes, you can control the visibility of error bars for individual data points by setting the `setVisible` property of the `IErrorBarsFormat` object.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
