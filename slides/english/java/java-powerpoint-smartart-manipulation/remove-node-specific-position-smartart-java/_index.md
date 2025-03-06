---
title: Remove Node at Specific Position in SmartArt
linktitle: Remove Node at Specific Position in SmartArt
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to remove a node at a specific position within SmartArt using Aspose.Slides for Java. Enhance presentation customization effortlessly.
weight: 15
url: /java/java-powerpoint-smartart-manipulation/remove-node-specific-position-smartart-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
In the realm of Java development, Aspose.Slides emerges as a powerful tool for manipulating presentations programmatically. Whether it's creating, modifying, or managing slides, Aspose.Slides for Java provides a robust set of features to streamline these tasks efficiently. One such common operation is removing a node at a specific position within a SmartArt object. This tutorial delves into the step-by-step process of accomplishing this using Aspose.Slides for Java.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites set up:
1. Java Development Kit (JDK): Make sure you have JDK installed on your system. You can download it from [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides for Java: Obtain the Aspose.Slides library for Java. You can download it from [this link](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Have an IDE like IntelliJ IDEA or Eclipse installed to write and execute Java code seamlessly.

## Import Packages
In your Java project, include the necessary packages to utilize Aspose.Slides functionalities:
```java
import com.aspose.slides.*;
```
## Step 1: Load the Presentation
Begin by loading the presentation file where the SmartArt object exists:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "RemoveNodeSpecificPosition.pptx");
```
## Step 2: Traverse SmartArt Shapes
Traverse through each shape in the presentation to identify SmartArt objects:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes()) {
    if (shape instanceof ISmartArt) {
        ISmartArt smart = (ISmartArt) shape;
```
## Step 3: Access SmartArt Node
Access the SmartArt node at the desired position:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Step 4: Remove Child Node
Remove the child node at the specified position:
```java
((ISmartArtNodeCollection) node.getChildNodes()).removeNode(1);
```
## Step 5: Save Presentation
Finally, save the modified presentation:
```java
pres.save(dataDir + "RemoveSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Conclusion
With Aspose.Slides for Java, manipulating SmartArt objects within presentations becomes a straightforward task. By following the outlined steps, you can seamlessly remove nodes at specific positions, enhancing your presentation customization capabilities.
## FAQ's
### Is Aspose.Slides for Java free to use?
Aspose.Slides for Java is a commercial library, but you can explore its functionalities with a free trial. Visit [this link](https://releases.aspose.com/) to get started.
### Where can I find support for Aspose.Slides-related queries?
For any assistance or queries, you can visit the Aspose.Slides forum [here](https://forum.aspose.com/c/slides/11).
### Can I obtain a temporary license for Aspose.Slides?
Yes, you can obtain a temporary license from [here](https://purchase.aspose.com/temporary-license/) for evaluation purposes.
### How can I purchase Aspose.Slides for Java?
To purchase Aspose.Slides for Java, visit the purchase page [here](https://purchase.aspose.com/buy).
### Where can I find detailed documentation for Aspose.Slides for Java?
You can access the comprehensive documentation [here](https://reference.aspose.com/slides/java/).

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
