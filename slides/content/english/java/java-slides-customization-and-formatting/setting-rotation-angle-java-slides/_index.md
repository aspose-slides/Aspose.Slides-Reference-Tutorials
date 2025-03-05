---
title: Setting Rotation Angle in Java Slides
linktitle: Setting Rotation Angle in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Optimize your Java slides with Aspose.Slides for Java. Learn to setting rotation angles for text elements. Step-by-step guide with source code.
type: docs
weight: 17
url: /java/customization-and-formatting/setting-rotation-angle-java-slides/
---

## Introduction to Setting Rotation Angle in Java Slides

In this tutorial, we will explore how to set the rotation angle for text in a chart axis title using the Aspose.Slides for Java library. By adjusting the rotation angle, you can customize the appearance of your chart's axis titles to better suit your presentation needs.

## Prerequisites

Before we begin, make sure you have the Aspose.Slides for Java library installed and set up in your Java project. You can download the library from the Aspose website and follow the installation instructions provided in their documentation.

## Step 1: Create a Presentation

First, you need to create a new presentation or load an existing one. In this example, we'll create a new presentation:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Step 2: Add a Chart to the Slide

Next, we'll add a chart to the slide. In this example, we're adding a clustered column chart:

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

## Step 3: Set Rotation Angle for Axis Title

To set the rotation angle for the axis title, you'll need to access the chart's vertical axis title and adjust its rotation angle. Here's how you can do it:

```java
    chart.getAxes().getVerticalAxis().setTitle(true);
    chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
```

In this code snippet, we're setting the rotation angle to 90 degrees, which will rotate the text vertically. You can adjust the angle to your desired value.

## Step 4: Save the Presentation

Finally, save the presentation to a PowerPoint file:

```java
    pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Complete Source Code For Setting Rotation Angle in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
	pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

In this tutorial, you've learned how to set the rotation angle for text in a chart axis title using Aspose.Slides for Java. This feature allows you to customize the appearance of your charts to create visually appealing presentations. Experiment with different rotation angles to achieve the desired look for your charts.

## FAQ's

### How can I change the rotation angle for other text elements in a slide?

You can change the rotation angle for other text elements, such as shapes or text boxes, using a similar approach. Access the text format of the element and set the rotation angle as needed.

### Can I rotate text in the horizontal axis title as well?

Yes, you can rotate text in the horizontal axis title by adjusting the rotation angle. Simply set the rotation angle to your desired value, such as 90 degrees for vertical text or 0 degrees for horizontal text.

### What other formatting options are available for chart titles?

Aspose.Slides for Java provides various formatting options for chart titles, including font styles, colors, and alignment. You can explore the documentation for more details on customizing chart titles.

### Is it possible to animate the rotation of text in a chart axis title?

Yes, you can add animation effects to text elements, including chart axis titles, using Aspose.Slides for Java. Refer to the documentation for information on adding animations to your presentations.
