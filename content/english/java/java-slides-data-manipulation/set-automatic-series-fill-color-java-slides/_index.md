---
title: Set Automatic Series Fill Color in Java Slides
linktitle: Set Automatic Series Fill Color in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to set automatic series fill color in Java Slides using Aspose.Slides for Java. Step-by-step guide with code examples for dynamic presentations.
type: docs
weight: 14
url: /java/java-slides-data-manipulation/set-automatic-series-fill-color-java-slides/
---

## Introduction to Set Automatic Series Fill Color in Java Slides

In this tutorial, we will explore how to set automatic series fill color in Java Slides using the Aspose.Slides for Java API. Aspose.Slides for Java is a powerful library that allows you to create, manipulate, and manage PowerPoint presentations programmatically. By the end of this guide, you will be able to create charts and set automatic series fill colors effortlessly.

## Prerequisites

Before we dive into the code, make sure you have the following prerequisites in place:

- Java Development Kit (JDK) installed on your system.
- Aspose.Slides for Java library added to your project. You can download it from [here](https://releases.aspose.com/slides/java/).

Now that we have our outline in place, let's start with the step-by-step guide.

## Step 1: Introduction to Aspose.Slides for Java

Aspose.Slides for Java is a Java API that allows developers to work with PowerPoint presentations. It provides a wide range of features, including creating, editing, and manipulating slides, charts, shapes, and more.

## Step 2: Setting Up Your Java Project

Before we begin coding, ensure that you have set up a Java project in your preferred Integrated Development Environment (IDE). Make sure to add the Aspose.Slides for Java library to your project.

## Step 3: Creating a PowerPoint Presentation

To get started, create a new PowerPoint presentation using the following code snippet:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

Replace `"Your Document Directory"` with the path where you want to save the presentation.

## Step 4: Adding a Chart to the Presentation

Next, let's add a clustered column chart to the presentation. We'll use the following code to accomplish this:

```java
// Creating a clustered column chart
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

This code creates a clustered column chart on the first slide of the presentation.

## Step 5: Setting Automatic Series Fill Color

Now comes the key part—setting automatic series fill color. We'll iterate through the chart's series and set their fill format to automatic:

```java
// Setting series fill format to automatic
for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
{
    chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
}
```

This code ensures that the series fill color is set to automatic.

## Step 6: Saving the Presentation

To save the presentation, use the following code:

```java
// Write the presentation file to disk
presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
```

Replace `"AutoFillSeries_out.pptx"` with the desired file name.

## Complete Source Code For Set Automatic Series Fill Color in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	// Creating a clustered column chart
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
	// Setting series fill format to automatic
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
	}
	// Write the presentation file to disk
	presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

Congratulations! You've successfully set automatic series fill color in a Java Slide using Aspose.Slides for Java. You can now use this knowledge to create dynamic and visually appealing PowerPoint presentations in your Java applications.

## FAQ's

### How can I change the chart type to a different style?

You can change the chart type by replacing `ChartType.ClusteredColumn` with the desired chart type, such as `ChartType.Line` or `ChartType.Pie`.

### Can I customize the chart appearance further?

Yes, you can customize the chart appearance by modifying various properties of the chart, such as colors, fonts, and labels.

### Is Aspose.Slides for Java suitable for commercial use?

Yes, Aspose.Slides for Java can be used for both personal and commercial projects. You can refer to their licensing terms for more details.

### Are there any other features provided by Aspose.Slides for Java?

Yes, Aspose.Slides for Java offers a wide range of features, including slide manipulation, text formatting, and animation support.

### Where can I find more resources and documentation?

You can access comprehensive documentation for Aspose.Slides for Java at [here](https://reference.aspose.com/slides/java/).
