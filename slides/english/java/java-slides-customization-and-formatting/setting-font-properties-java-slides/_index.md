---
title: Setting Font Properties in Java Slides
linktitle: Setting Font Properties in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to setting font properties in Java slides using Aspose.Slides for Java. This step-by-step guide includes code examples and FAQs.
weight: 15
url: /java/customization-and-formatting/setting-font-properties-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduction to Setting Font Properties in Java Slides

In this tutorial, we will explore how to set font properties for text in Java slides using Aspose.Slides for Java. Font properties such as boldness and font size can be customized to enhance the appearance of your slides.

## Prerequisites

Before you begin, make sure you have the Aspose.Slides for Java library added to your project. You can download it from [here](https://releases.aspose.com/slides/java/).

## Step 1: Initialize Presentation

First, you need to initialize a presentation object by loading an existing PowerPoint file. Replace `"Your Document Directory"` with the actual path to your document directory.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Step 2: Add a Chart

In this example, we will work with a chart on the first slide. You can change the slide index according to your needs. We will add a clustered column chart and enable the data table.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.setDataTable(true);
```

## Step 3: Customize Font Properties

Now, let's customize the font properties of the chart data table. We will set the font to be bold and adjust the font height (size).

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontHeight(20);
```

- `setFontBold(NullableBool.True)`: This line sets the font to be bold.
- `setFontHeight(20)`: This line sets the font height to 20 points. You can adjust this value as needed.

## Step 4: Save the Presentation

Finally, save the modified presentation to a new file. You can specify the output format; in this case, we are saving it as a PPTX file.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

## Complete Source Code For Setting Font Properties in Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.setDataTable(true);
	chart.getChartDataTable().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
	chart.getChartDataTable().getTextFormat().getPortionFormat().setFontHeight(20);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

In this tutorial, you learned how to set font properties for text in Java slides using Aspose.Slides for Java. You can apply these techniques to enhance the appearance of text in your PowerPoint presentations.

## FAQ's

### How do I change font color?

To change the font color, use the `setFontColor` method and specify the desired color. For example:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontColor(Color.RED);
```

### Can I change the font for other text in slides?

Yes, you can change the font for other text elements in slides, such as titles and labels. Use the appropriate objects and methods to access and customize the font properties for specific text elements.

### How do I set italic font style?

To set the font style to italic, use the `setFontItalic` method:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontItalic(NullableBool.True);
```

Adjust the `NullableBool.True` parameter as needed to enable or disable italic style.

### How can I change the font for data labels in a chart?

To change the font for data labels in a chart, you need to access the data label text format using the appropriate methods. For example:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0); // Change the index as needed
series.getLabels().getDefaultDataLabelFormat().getPortionFormat().setFontBold(NullableBool.True);
```

This code sets the font of data labels in the first series to bold.

### How do I change the font for a specific portion of text?

If you want to change the font for a specific portion of text within a text element, you can use the `PortionFormat` class. Access the portion you want to modify and then set the desired font properties.

```java
IAutoShape textShape = (IAutoShape)slide.getShapes().get_Item(0); // Change the index as needed
ITextFrame textFrame = textShape.getTextFrame();
IParagraph paragraph = textFrame.getParagraphs().get_Item(0); // Change the index as needed
IPortion portion = paragraph.getPortions().get_Item(0); // Change the index as needed

portion.getPortionFormat().setFontBold(NullableBool.True);
portion.getPortionFormat().setFontHeight(24);
```

This code sets the font of the first portion of text within a shape to bold and adjusts the font height.

### How can I apply font changes to all slides in a presentation?

To apply font changes to all slides in a presentation, you can iterate through the slides and adjust the font properties as needed. Use a loop to access each slide and the text elements within them, then customize the font properties.

```java
for (ISlide slide : pres.getSlides()) {
    // Access and customize text elements' font properties here
}
```

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
