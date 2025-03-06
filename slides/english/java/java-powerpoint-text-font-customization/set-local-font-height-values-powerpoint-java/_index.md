---
title: Set Local Font Height Values in PowerPoint using Java
linktitle: Set Local Font Height Values in PowerPoint using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to adjust font heights in PowerPoint presentations using Java with Aspose.Slides. Enhance text formatting in your slides effortlessly.
weight: 17
url: /java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
In this tutorial, you will learn how to manipulate font heights at various levels within PowerPoint presentations using Aspose.Slides for Java. Controlling font sizes is crucial for creating visually appealing and structured presentations. We will walk through step-by-step examples to illustrate how to set font heights for different text elements.
## Prerequisites
Before you begin, ensure you have the following:
- Java Development Kit (JDK) installed on your system
- Aspose.Slides for Java library. You can download it [here](https://releases.aspose.com/slides/java/).
- A basic understanding of Java programming and PowerPoint presentations
## Import Packages
Make sure to include the necessary Aspose.Slides packages in your Java file:
```java
import com.aspose.slides.*;
```
## Step 1: Initialize a Presentation Object
First, create a new PowerPoint presentation object:
```java
Presentation pres = new Presentation();
```
## Step 2: Add a Shape and Text Frame
Add an auto shape with a text frame to the first slide:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Step 3: Create Text Portions
Define text portions with different font heights:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Step 4: Set Font Heights
Set font heights at different levels:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## Step 5: Save the Presentation
Save the modified presentation to a file:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## Conclusion
This tutorial demonstrated how to adjust font heights within PowerPoint slides programmatically using Aspose.Slides for Java. By manipulating font sizes at different levels (presentation-wide, paragraph, and portion), you can achieve precise control over text formatting in your presentations.
## FAQ's
### What is Aspose.Slides for Java?
Aspose.Slides for Java is a powerful API for manipulating PowerPoint presentations programmatically.
### Where can I find documentation for Aspose.Slides for Java?
You can find the documentation [here](https://reference.aspose.com/slides/java/).
### Can I try Aspose.Slides for Java before purchasing?
Yes, you can get a free trial [here](https://releases.aspose.com/).
### How can I get support for Aspose.Slides for Java?
For support, visit the [Aspose.Slides forum](https://forum.aspose.com/c/slides/11).
### Where can I purchase a license for Aspose.Slides for Java?
You can purchase a license [here](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
