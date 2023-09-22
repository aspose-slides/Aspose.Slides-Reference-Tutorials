---
title: Set Legend Custom Options in Java Slides
linktitle: Set Legend Custom Options in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to set custom legend options in Java Slides using Aspose.Slides for Java. Customize legend position and size in your PowerPoint charts.
type: docs
weight: 14
url: /java/customization-and-formatting/set-legend-custom-options-java-slides/
---

## Introduction to Set Legend Custom Options in Java Slides

In this tutorial, we'll demonstrate how to customize the legend properties of a chart in a PowerPoint presentation using Aspose.Slides for Java. You can modify the legend's position, size, and other attributes to suit your presentation needs.

## Prerequisites

Before you begin, make sure you have the following:

- Aspose.Slides for Java API installed.
- Java development environment set up.

## Step 1: Import necessary classes:

```java
// Import Aspose.Slides for Java classes
import com.aspose.slides.*;
```

## Step 2: Specify the path to your document directory:

```java
String dataDir = "Your Document Directory";
```

## Step 3: Create an instance of the `Presentation` class:

```java
Presentation presentation = new Presentation();
```

## Step 4: Add a slide to the presentation:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Step 5: Add a clustered column chart to the slide:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Step 6. Set Legend Properties:

- Set the X-position of the legend (relative to the chart width):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Set the Y-position of the legend (relative to the chart height):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Set the width of the legend (relative to the chart width):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Set the height of the legend (relative to the chart height):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## Step 7: Save the presentation to disk:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

That's it! You've successfully customized the legend properties of a chart in a PowerPoint presentation using Aspose.Slides for Java.

## Complete Source Code For Set Legend Custom Options in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an instance of Presentation class
Presentation presentation = new Presentation();
try
{
	// Get reference of the slide
	ISlide slide = presentation.getSlides().get_Item(0);
	// Add a clustered column chart on the slide
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Set Legend Properties
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// Write presentation to disk
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## Conclusion

In this tutorial, we learned how to customize the legend properties of a chart in a PowerPoint presentation using Aspose.Slides for Java. You can modify the legend's position, size, and other attributes to create visually appealing and informative presentations.

## FAQ's

## How can I change the legend's position?

To change the legend's position, use the `setX` and `setY` methods of the legend object. The values are specified relative to the chart's width and height.

## How can I adjust the legend's size?

You can adjust the legend's size by using the `setWidth` and `setHeight` methods of the legend object. These values are also relative to the chart's width and height.

## Can I customize other legend attributes?

Yes, you can customize various attributes of the legend, such as font style, border, background color, and more. Explore the Aspose.Slides documentation for detailed information on customizing legends further.
