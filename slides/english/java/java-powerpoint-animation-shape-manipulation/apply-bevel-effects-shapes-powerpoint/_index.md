---
title: Apply Bevel Effects on Shapes in PowerPoint
linktitle: Apply Bevel Effects on Shapes in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to apply bevel effects to shapes in PowerPoint using Aspose.Slides for Java with our step-by-step guide. Enhance your presentations.
type: docs
weight: 13
url: /java/java-powerpoint-animation-shape-manipulation/apply-bevel-effects-shapes-powerpoint/
---
## Introduction
Creating visually appealing presentations is crucial for capturing and maintaining your audience's attention. Adding bevel effects to shapes can enhance the overall aesthetics of your slides, making your presentation stand out. In this tutorial, we’ll walk you through the process of applying bevel effects to shapes in PowerPoint using Aspose.Slides for Java. Whether you're a developer looking to automate presentation creation or just someone who loves tinkering with design, this guide has got you covered.
## Prerequisites
Before diving into the tutorial, make sure you have the following prerequisites in place:
- Java Development Kit (JDK): Ensure you have JDK installed. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Slides for Java Library: Download the library from [Aspose.Slides for Java](https://releases.aspose.com/slides/java/).
- IDE (Integrated Development Environment): Use any IDE of your choice, such as IntelliJ IDEA, Eclipse, or NetBeans.
- Aspose License: To use Aspose.Slides without limitations, obtain a license from [Aspose Purchase](https://purchase.aspose.com/buy) or get a [temporary license](https://purchase.aspose.com/temporary-license/) for evaluation.
## Import Packages
First, you need to import the necessary packages for working with Aspose.Slides in your Java project. Here’s how you can do it:
```java
import com.aspose.slides.*;

import java.awt.*;
```
## Step 1: Set Up Your Project
Before you can start coding, ensure your project is set up correctly. Include the Aspose.Slides library in your project’s build path. If you’re using Maven, add the following dependency to your `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>23.6</version>
</dependency>
```
## Step 2: Create a Presentation
To start working with Aspose.Slides, you need to create an instance of the `Presentation` class. This class represents a PowerPoint file.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an instance of Presentation class
Presentation pres = new Presentation();
```
## Step 3: Access the First Slide
After creating a presentation, access the first slide where you will add and manipulate shapes.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Step 4: Add a Shape to the Slide
Now, add a shape to the slide. In this example, we’ll add an ellipse.
```java
// Add a shape on the slide
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Ellipse, 30, 30, 100, 100);
shape.getFillFormat().setFillType(FillType.Solid);
shape.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
ILineFillFormat format = shape.getLineFormat().getFillFormat();
format.setFillType(FillType.Solid);
format.getSolidFillColor().setColor(Color.ORANGE);
shape.getLineFormat().setWidth(2.0);
```
## Step 5: Apply Bevel Effects to the Shape
Next, apply bevel effects to the shape to give it a three-dimensional appearance.
```java
// Set ThreeDFormat properties of the shape
shape.getThreeDFormat().setDepth((short) 4);
shape.getThreeDFormat().getBevelTop().setBevelType(BevelPresetType.Circle);
shape.getThreeDFormat().getBevelTop().setHeight(6);
shape.getThreeDFormat().getBevelTop().setWidth(6);
shape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.OrthographicFront);
shape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.ThreePt);
shape.getThreeDFormat().getLightRig().setDirection(LightingDirection.Top);
```
## Step 6: Save the Presentation
Finally, save the presentation as a PPTX file to your specified directory.
```java
// Write the presentation as a PPTX file
pres.save(dataDir + "Bevel_out.pptx", SaveFormat.Pptx);
```
## Step 7: Dispose of the Presentation Object
To free up resources, always ensure that the `Presentation` object is disposed of properly.
```java
if (pres != null) pres.dispose();
```
## Conclusion
Applying bevel effects to shapes in PowerPoint presentations using Aspose.Slides for Java is a straightforward process that can significantly enhance your slides' visual appeal. By following the steps outlined in this guide, you can easily create professional and engaging presentations. Remember to explore the [Aspose.Slides documentation](https://reference.aspose.com/slides/java/) for more detailed information and advanced features.
## FAQ's
### What is Aspose.Slides for Java?
Aspose.Slides for Java is a powerful API that allows developers to create, modify, and manage PowerPoint presentations programmatically.
### Can I use Aspose.Slides for Java for free?
Aspose.Slides offers a free trial which you can download from [here](https://releases.aspose.com/). For full features, you need to purchase a license.
### What types of shapes can I add to my slides?
You can add various shapes such as rectangles, ellipses, lines, and custom shapes using Aspose.Slides for Java.
### Is it possible to apply other 3D effects besides bevel?
Yes, Aspose.Slides for Java allows you to apply various 3D effects, including depth, lighting, and camera effects.
### Where can I get support for Aspose.Slides for Java?
You can get support from the Aspose community and support team on their [support forum](https://forum.aspose.com/c/slides/11).
