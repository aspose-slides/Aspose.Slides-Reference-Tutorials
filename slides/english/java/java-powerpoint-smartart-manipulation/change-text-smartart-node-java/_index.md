---
title: Change Text on SmartArt Node using Java
linktitle: Change Text on SmartArt Node using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Discover how to update SmartArt node text in PowerPoint using Java with Aspose.Slides, enhancing presentation customization.
weight: 22
url: /java/java-powerpoint-smartart-manipulation/change-text-smartart-node-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
SmartArt in PowerPoint is a powerful feature for creating visually appealing diagrams. Aspose.Slides for Java provides comprehensive support to manipulate SmartArt elements programmatically. In this tutorial, we'll guide you through the process of changing text on a SmartArt node using Java.
## Prerequisites
Before you begin, ensure you have the following:
- Java Development Kit (JDK) installed on your system.
- Aspose.Slides for Java library downloaded and referenced in your Java project.
- Basic understanding of Java programming.

## Import Packages
First, import the necessary packages to access Aspose.Slides functionality within your Java code.
```java
import com.aspose.slides.*;
```
Let's break down the example into multiple steps:
## Step 1: Initialize Presentation Object
```java
Presentation presentation = new Presentation();
```
Create a new instance of the `Presentation` class to work with a PowerPoint presentation.
## Step 2: Add SmartArt to Slide
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
Add SmartArt to the first slide. In this example, we're using the `BasicCycle` layout.
## Step 3: Access SmartArt Node
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
Get a reference to the second root node of the SmartArt.
## Step 4: Set Text on Node
```java
node.getTextFrame().setText("Second root node");
```
Set the text for the selected SmartArt node.
## Step 5: Save Presentation
```java
presentation.save(dataDir + "ChangeText_On_SmartArt_Node_out.pptx", SaveFormat.Pptx);
```
Save the modified presentation to a specified location.

## Conclusion
In this tutorial, we've demonstrated how to change text on a SmartArt node using Java and Aspose.Slides. With this knowledge, you can dynamically manipulate SmartArt elements in your PowerPoint presentations, enhancing their visual appeal and clarity.
## FAQ's
### Can I change the layout of the SmartArt after adding it to the slide?
Yes, you can change the layout by accessing the `SmartArt.setAllNodes(LayoutType)` method.
### Is Aspose.Slides compatible with Java 11?
Yes, Aspose.Slides for Java is compatible with Java 11 and newer versions.
### Can I customize the appearance of SmartArt nodes programmatically?
Certainly, you can modify various properties like color, size, and shape using Aspose.Slides API.
### Does Aspose.Slides support other types of SmartArt layouts?
Yes, Aspose.Slides supports a wide range of SmartArt layouts, allowing you to choose the one that best suits your presentation needs.
### Where can I find more resources and support for Aspose.Slides?
You can visit the [Aspose.Slides documentation](https://reference.aspose.com/slides/java/) for detailed API references and tutorials. Additionally, you can seek help from the [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) or consider purchasing a [temporary license](https://purchase.aspose.com/temporary-license/) for professional support.

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
