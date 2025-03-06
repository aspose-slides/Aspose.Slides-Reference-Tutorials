---
title: Set Text Font Properties in PowerPoint with Java
linktitle: Set Text Font Properties in PowerPoint with Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to set text font properties in PowerPoint using Aspose.Slides for Java. Easy, step-by-step guide for Java developers.#Learn how to manipulate PowerPoint text font properties using Aspose.Slides for Java with this step-by-step tutorial for Java developers.
weight: 18
url: /java/java-powerpoint-text-font-customization/set-text-font-properties-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
In this tutorial, you'll learn how to use Aspose.Slides for Java to set various text font properties in a PowerPoint presentation programmatically. We'll cover setting font type, style (bold, italic), underline, size, and color for text in slides.
## Prerequisites
Before you begin, make sure you have the following:
- JDK installed on your system.
- Aspose.Slides for Java library. You can download it from [here](https://releases.aspose.com/slides/java/).
- Basic knowledge of Java programming.
- Integrated Development Environment (IDE) such as IntelliJ IDEA or Eclipse set up.
## Import Packages
First, ensure you have imported the necessary Aspose.Slides classes:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## Step 1: Set up your Java Project
Create a new Java project in your IDE and add Aspose.Slides library to your project's build path.
## Step 2: Initialize Presentation Object
Instantiate a `Presentation` object to work with PowerPoint files:
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Step 3: Access Slide and Add AutoShape
Get the first slide and add an AutoShape (Rectangle) to it:
```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
## Step 4: Set Text to AutoShape
Set text content to the AutoShape:
```java
ITextFrame textFrame = shape.getTextFrame();
textFrame.setText("Aspose TextBox");
```
## Step 5: Set Font Properties
Access the portion of text and set various font properties:
```java
IPortion portion = textFrame.getParagraphs().get_Item(0).getPortions().get_Item(0);
// Set Font Family
portion.getPortionFormat().setLatinFont(new FontData("Times New Roman"));
// Set Bold
portion.getPortionFormat().setFontBold(NullableBool.True);
// Set Italic
portion.getPortionFormat().setFontItalic(NullableBool.True);
// Set Underline
portion.getPortionFormat().setFontUnderline(TextUnderlineType.Single);
// Set Font Size
portion.getPortionFormat().setFontHeight(25);
// Set Font Color
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```
## Step 6: Save Presentation
Save the modified presentation to a file:
```java
presentation.save(dataDir + "SetTextFontProperties_out.pptx", SaveFormat.Pptx);
```
## Step 7: Cleanup Resources
Dispose of the Presentation object to release resources:
```java
if (presentation != null) {
    presentation.dispose();
}
```

## Conclusion
In this tutorial, you've learned how to use Aspose.Slides for Java to customize text font properties in PowerPoint slides dynamically. By following these steps, you can efficiently format text to meet specific design requirements programmatically.
## FAQ's
### Can I apply these font changes to existing text in a PowerPoint slide?
Yes, you can modify existing text by accessing its `Portion` and applying the desired font properties.
### How can I change the font color to a gradient or pattern fill?
Instead of `SolidFillColor`, use `GradientFillColor` or `PatternedFillColor` accordingly.
### Is Aspose.Slides compatible with PowerPoint templates (.potx)?
Yes, you can use Aspose.Slides to work with PowerPoint templates.
### Does Aspose.Slides support exporting to PDF format?
Yes, Aspose.Slides allows exporting presentations to various formats including PDF.
### Where can I find more help and support for Aspose.Slides?
Visit [Aspose.Slides Forum](https://forum.aspose.com/c/slides/11) for community support and guidance.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
