---
title: Second Plot Options for Charts in Java Slides
linktitle: Second Plot Options for Charts in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to customize charts in Java Slides using Aspose.Slides for Java. Explore second plot options and enhance your presentations.
weight: 12
url: /java/chart-creation/second-plot-options-charts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Second Plot Options for Charts in Java Slides


## Introduction to Second Plot Options for Charts in Java Slides

In this tutorial, we will explore how to add second plot options to charts using Aspose.Slides for Java. Second plot options allow you to customize the appearance and behavior of charts, particularly in scenarios like Pie of Pie charts. We will provide step-by-step instructions and source code examples to achieve this. 

## Prerequisites
Before we begin, make sure you have Aspose.Slides for Java installed and set up in your Java project.

## Step 1: Create a Presentation
Let's start by creating a new presentation:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an instance of Presentation class
Presentation presentation = new Presentation();
```

## Step 2: Add a Chart to a Slide
Next, we will add a chart to a slide. In this example, we'll create a Pie of Pie chart:

```java
// Add chart on slide
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Step 3: Customize Chart Properties
Now, let's set different properties for the chart, including second plot options:

```java
// Show data labels for the first series
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Set the size of the second pie (in percentage)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Split the pie by percentage
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Set the position of the split
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Step 4: Save the Presentation
Finally, save the presentation with the chart and second plot options:

```java
// Write presentation to disk
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Complete Source Code For Second Plot Options

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an instance of Presentation class
Presentation presentation = new Presentation();
// Add chart on slide
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Set different properties
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Write presentation to disk
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Conclusion

In this tutorial, we've learned how to add second plot options to charts in Java Slides using Aspose.Slides for Java. You can customize various properties to enhance the appearance and functionality of your charts, making your presentations more informative and visually appealing.

## FAQ's

### How can I change the size of the second pie in a Pie of Pie chart?

To change the size of the second pie in a Pie of Pie chart, use the `setSecondPieSize` method as shown in the code example above. Adjust the value to specify the size in percentage.

### What does `PieSplitBy` control in a Pie of Pie chart?

The `PieSplitBy` property controls how the pie chart is split. You can set it to either `PieSplitType.ByPercentage` or `PieSplitType.ByValue` to split the chart by percentage or by a specific value, respectively.

### How do I set the position of the split in a Pie of Pie chart?

You can set the position of the split in a Pie of Pie chart using the `setPieSplitPosition` method. Adjust the value to specify the desired position.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
