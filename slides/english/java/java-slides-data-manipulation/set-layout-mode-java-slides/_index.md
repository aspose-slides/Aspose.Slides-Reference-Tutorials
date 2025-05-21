---
title: Set Layout Mode in Java Slides
linktitle: Set Layout Mode in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to set layout modes for Java slides using Aspose.Slides. Customize chart positioning and sizing in this step-by-step guide with source code.
weight: 23
url: /java/data-manipulation/set-layout-mode-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Set Layout Mode in Java Slides


## Introduction to Set Layout Mode in Java Slides

In this tutorial, we will learn how to set the layout mode for a chart in Java slides using Aspose.Slides for Java. The layout mode determines the positioning and sizing of the chart within the slide.

## Prerequisites

Before we begin, make sure you have the Aspose.Slides for Java library installed and set up in your Java project. You can download the library from [here](https://releases.aspose.com/slides/java/).

## Step 1: Create a Presentation

First, we need to create a new presentation.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Step 2: Add a Slide and Chart

Next, we will add a slide and a chart to it. In this example, we'll create a clustered column chart.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Step 3: Set Chart Layout

Now, let's set the layout for the chart. We will adjust the position and size of the chart within the slide using the `setX`, `setY`, `setWidth`, `setHeight` methods. Additionally, we will set the `LayoutTargetType` to determine the layout mode.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

In this example, we have set the chart to have its layout target type as "Inner," which means it will be positioned and sized relative to the inner area of the slide.

## Step 4: Save the Presentation

Finally, let's save the presentation with the chart layout settings.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Complete Source Code For Set Layout Mode in Java Slides

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

In this tutorial, we have learned how to set the layout mode for a chart in Java slides using Aspose.Slides for Java. You can customize the chart's position and size according to your specific requirements by adjusting the values in the `setX`, `setY`, `setWidth`, `setHeight`, and `setLayoutTargetType` methods. This gives you control over the placement of charts within your slides.

## FAQ's

### How do I change the layout mode for a chart in Aspose.Slides for Java?

To change the layout mode for a chart in Aspose.Slides for Java, you can use the `setLayoutTargetType` method on the chart's plot area. You can set it to either `LayoutTargetType.Inner` or `LayoutTargetType.Outer` depending on your desired layout.

### Can I customize the position and size of the chart within the slide?

Yes, you can customize the position and size of the chart within the slide by using the `setX`, `setY`, `setWidth`, and `setHeight` methods on the chart's plot area. Adjust these values to position and size the chart according to your requirements.

### Where can I find more information about Aspose.Slides for Java?

You can find more information about Aspose.Slides for Java in the [documentation](https://reference.aspose.com/slides/java/). It includes detailed API references and examples to help you work with slides and charts effectively in Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
