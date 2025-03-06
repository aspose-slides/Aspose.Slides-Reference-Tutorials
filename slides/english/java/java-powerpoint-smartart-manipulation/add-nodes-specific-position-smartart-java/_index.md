---
title: Add Nodes at Specific Position in SmartArt using Java
linktitle: Add Nodes at Specific Position in SmartArt using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Discover how to add nodes at specific positions in SmartArt using Java with Aspose.Slides. Create dynamic presentations effortlessly.
weight: 16
url: /java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Nodes at Specific Position in SmartArt using Java

## Introduction
In this tutorial, we'll guide you through the process of adding nodes at specific positions in SmartArt using Java with Aspose.Slides. SmartArt is a feature in PowerPoint that allows you to create visually appealing diagrams and charts.
## Prerequisites
Before you begin, ensure you have the following:
1. Java Development Kit (JDK) installed on your system.
2. Aspose.Slides for Java library downloaded. You can download it from [here](https://releases.aspose.com/slides/java/).
3. Basic knowledge of Java programming language.

## Import Packages
First, let's import the necessary packages in our Java code:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Step 1: Create a Presentation Instance
Start by creating an instance of the Presentation class:
```java
Presentation pres = new Presentation();
```
## Step 2: Access the Presentation Slide
Access the slide where you want to add the SmartArt:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Step 3: Add SmartArt Shape
Add a SmartArt shape to the slide:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Step 4: Access SmartArt Node
Access the SmartArt node at the desired index:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Step 5: Add Child Node at Specific Position
Add a new child node at a specific position in the parent node:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Step 6: Add Text to the Node
Set the text for the newly added node:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Step 7: Save the Presentation
Save the modified presentation:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Conclusion
In this tutorial, you learned how to add nodes at specific positions in SmartArt using Java with Aspose.Slides. By following these steps, you can manipulate SmartArt shapes programmatically to create dynamic presentations.
## FAQ's
### Can I add multiple nodes at once?
Yes, you can add multiple nodes programmatically by iterating over the desired positions.
### Is Aspose.Slides compatible with all versions of PowerPoint?
Aspose.Slides supports various PowerPoint formats, ensuring compatibility with most versions.
### Can I customize the appearance of SmartArt nodes?
Yes, you can customize the appearance of nodes, including their size, color, and style.
### Does Aspose.Slides offer support for other programming languages?
Yes, Aspose.Slides provides libraries for multiple programming languages, including .NET and Python.
### Is there a trial version available for Aspose.Slides?
Yes, you can download a free trial version from [here](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
