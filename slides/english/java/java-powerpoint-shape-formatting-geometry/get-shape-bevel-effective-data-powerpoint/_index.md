---
title: Get Shape Bevel Effective Data in PowerPoint
linktitle: Get Shape Bevel Effective Data in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to retrieve shape bevel effective data in PowerPoint using Aspose.Slides for Java. Enhance your presentations with stunning visual effects.
type: docs
weight: 26
url: /java/java-powerpoint-shape-formatting-geometry/get-shape-bevel-effective-data-powerpoint/
---
## Introduction
In modern business presentations, visual appeal plays a crucial role in conveying information effectively. One of the elements that can enhance the visual impact of shapes in PowerPoint presentations is the bevel effect. Aspose.Slides for Java provides powerful tools to access and manipulate various properties of shapes, including their bevel effects. In this tutorial, we'll guide you through the process of retrieving shape bevel effective data using Aspose.Slides for Java.
## Prerequisites
Before we begin, ensure you have the following prerequisites:
1. Basic understanding of Java programming language.
2. Installed Java Development Kit (JDK) on your system.
3. Downloaded and installed Aspose.Slides for Java. You can download it from [here](https://releases.aspose.com/slides/java/).
## Import Packages
Start by importing the necessary packages in your Java project:
```java
import com.aspose.slides.IThreeDFormatEffectiveData;
import com.aspose.slides.Presentation;

```
## Step 1: Set up Document Directory
Define the path to your document directory where the PowerPoint presentation is located:
```java
String dataDir = "Your Document Directory";
```
## Step 2: Load Presentation
Load the PowerPoint presentation using Aspose.Slides library:
```java
Presentation pres = new Presentation(dataDir + "Presentation1.pptx");
```
## Step 3: Retrieve Bevel Effective Data
Access the effective bevel data of the shape:
```java
IThreeDFormatEffectiveData threeDEffectiveData = pres.getSlides().get_Item(0).getShapes().get_Item(0).getThreeDFormat().getEffective();
```
## Step 4: Print Bevel Properties
Print out the effective shape's top face relief properties:
```java
System.out.println("= Effective shape's top face relief properties =");
System.out.println("Type: " + threeDEffectiveData.getBevelTop().getBevelType());
System.out.println("Width: " + threeDEffectiveData.getBevelTop().getWidth());
System.out.println("Height: " + threeDEffectiveData.getBevelTop().getHeight());
```

## Conclusion
In this tutorial, we've demonstrated how to retrieve shape bevel effective data in PowerPoint using Aspose.Slides for Java. By following these steps, you can easily access and manipulate various properties of shapes to enhance the visual appeal of your presentations.
## FAQ's
### Can I apply bevel effects to multiple shapes simultaneously?
Yes, you can iterate through shapes in a slide and apply bevel effects as needed.
### Does Aspose.Slides support other 3D effects apart from bevel?
Yes, Aspose.Slides provides a wide range of 3D effects that you can apply to shapes in PowerPoint presentations.
### Is Aspose.Slides compatible with different versions of PowerPoint?
Aspose.Slides ensures compatibility with various versions of PowerPoint, allowing you to work seamlessly across different environments.
### Can I customize the bevel effect properties further?
Absolutely, you have full control over the bevel effect properties and can customize them according to your requirements.
### Where can I find more resources and support for Aspose.Slides?
You can visit the [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) for any questions, support, or additional resources.
