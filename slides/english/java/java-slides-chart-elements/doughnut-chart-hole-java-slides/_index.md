---
title: Doughnut Chart Hole in Java Slides
linktitle: Doughnut Chart Hole in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Create Doughnut Charts with Custom Hole Sizes in Java Slides using Aspose.Slides for Java. Step-by-step guide with source code for chart customization.
weight: 11
url: /java/chart-elements/doughnut-chart-hole-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduction to Doughnut Chart with a Hole in Java Slides

In this tutorial, we will guide you through creating a doughnut chart with a hole using Aspose.Slides for Java. This step-by-step guide will walk you through the process with source code examples.

## Prerequisites

Before you begin, make sure you have the Aspose.Slides for Java library installed and set up in your Java project. You can download it from the [Aspose.Slides for Java documentation](https://reference.aspose.com/slides/java/).

## Step 1: Import the Required Libraries

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Step 2: Initialize the Presentation

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

// Create an instance of Presentation class
Presentation presentation = new Presentation();
```

## Step 3: Create the Doughnut Chart

```java
try {
    // Create a doughnut chart on the first slide
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Set the size of the hole in the doughnut chart (in percentage)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Save the presentation to disk
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Dispose of the presentation object
    if (presentation != null) presentation.dispose();
}
```

## Step 4: Run the Code

Run the Java code in your IDE or text editor to create a doughnut chart with a specified hole size. Make sure to replace `"Your Document Directory"` with the actual path where you want to save the presentation.

## Complete Source Code For Doughnut Chart Hole in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an instance of Presentation class
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// Write presentation to disk
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

In this tutorial, you learned how to create a doughnut chart with a hole using Aspose.Slides for Java. You can customize the size of the hole by adjusting the `setDoughnutHoleSize` method parameter.

## FAQ's

### How can I change the color of the chart segments?

To change the color of the chart segments, you can use the `setDataPointsInLegend` method on the `IChart` object and set the desired color for each data point.

### Can I add labels to the doughnut chart segments?

Yes, you can add labels to the doughnut chart segments using the `setDataPointsLabelValue` method on the `IChart` object.

### Is it possible to add a title to the chart?

Certainly! You can add a title to the chart using the `setTitle` method on the `IChart` object and providing the desired title text.

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
