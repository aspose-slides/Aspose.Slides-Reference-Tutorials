---
title: Font Properties for Chart in Java Slides
linktitle: Font Properties for Chart in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Enhance Chart Font Properties in Java Slides with Aspose.Slides for Java. Customize font size, style, and color for impactful presentations.
weight: 11
url: /java/customization-and-formatting/font-properties-for-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduction to Font Properties for Chart in Java Slides

This guide will walk you through setting font properties for a chart in Java Slides using Aspose.Slides. You can customize the font size and appearance of the chart text to enhance the visual appeal of your presentations.

## Prerequisites

Before you begin, make sure you have Aspose.Slides for Java API integrated into your project. If you haven't already, you can download it from the [Aspose.Slides for Java documentation](https://reference.aspose.com/slides/java/).

## Step 1: Create a Presentation

First, create a new presentation using the following code:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Step 2: Add a Chart

Now, let's add a clustered column chart to your presentation:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Here, we are adding a clustered column chart to the first slide at coordinates (100, 100) with a width of 500 units and a height of 400 units.

## Step 3: Customize Font Properties

Next, we'll customize the font properties of the chart. In this example, we are setting the font size to 20 for all chart text:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

This code sets the font size to 20 points for all text within the chart.

## Step 4: Show Data Labels

You can also show data labels on the chart using the following code:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

This line of code enables data labels for the first series in the chart, displaying the values on the chart columns.

## Step 5: Save the Presentation

Finally, save the presentation with your customized chart font properties:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

This code will save the presentation to the specified directory with the filename "FontPropertiesForChart.pptx."

## Complete Source Code For Font Properties for Chart in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

In this tutorial, you've learned how to customize font properties for a chart in Java Slides using Aspose.Slides for Java. You can apply these techniques to enhance the appearance of your charts and presentations. Explore more options in the [Aspose.Slides for Java documentation](https://reference.aspose.com/slides/java/).

## FAQ's

### How can I change the font color?

To change the font color for chart text, use `chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);`, replacing `Color.RED` with the desired color.

### Can I change the font style (bold, italic, etc.)?

Yes, you can change the font style. Use `chart.getTextFormat().getPortionFormat().setFontBold(true);` to make the font bold. Similarly, you can use `setFontItalic(true)` to make it italic.

### How do I customize font properties for specific chart elements?

To customize font properties for specific chart elements, such as axis labels or legend text, you can access those elements and set their font properties using similar methods as shown above.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
