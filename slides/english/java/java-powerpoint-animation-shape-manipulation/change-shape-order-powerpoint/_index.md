---
title: Change Shape Order in PowerPoint
linktitle: Change Shape Order in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to change the shape order in PowerPoint using Aspose.Slides for Java with this step-by-step tutorial. Enhance your presentation skills effortlessly.
weight: 15
url: /java/java-powerpoint-animation-shape-manipulation/change-shape-order-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
Creating visually appealing and well-structured presentations can be a daunting task. However, with the right tools and techniques, you can make it significantly easier. Aspose.Slides for Java is a powerful library that helps you manipulate and manage PowerPoint presentations programmatically. In this tutorial, we’ll walk you through the steps to change the shape order in a PowerPoint slide using Aspose.Slides for Java.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites in place:
1. Java Development Kit (JDK): Make sure you have JDK installed on your machine. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides for Java Library: Download the latest version from [Aspose.Slides for Java download page](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Use an IDE like IntelliJ IDEA or Eclipse for coding.
4. Presentation File: Have a PowerPoint file ready that you want to manipulate.
## Import Packages
To get started, you need to import the necessary packages from the Aspose.Slides library. These imports will allow you to work with presentations, slides, and shapes.
```java
import com.aspose.slides.*;

```
In this guide, we will break down the process of changing the shape order into several steps for better understanding and ease of implementation.
## Step 1: Load the Presentation
First, you need to load the PowerPoint presentation file you want to work with. This step involves initializing the `Presentation` class with the path to your PowerPoint file.
```java
String dataDir = "Your Document Directory";
Presentation presentation1 = new Presentation(dataDir + "HelloWorld.pptx");
```
## Step 2: Access the Desired Slide
Once the presentation is loaded, access the slide where you want to reorder shapes. Slides are indexed starting from 0, so to access the first slide, use index 0.
```java
ISlide slide = presentation1.getSlides().get_Item(0);
```
## Step 3: Add Shapes to the Slide
Next, add the shapes to the slide. For demonstration, we will add a rectangle and a triangle shape to the slide.
```java
IAutoShape shp3 = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.getFillFormat().setFillType(FillType.NoFill);
shp3.addTextFrame(" ");
ITextFrame txtFrame = shp3.getTextFrame();
IParagraph para = txtFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Watermark Text Watermark Text Watermark Text");
shp3 = slide.getShapes().addAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## Step 4: Reorder the Shapes
Now, reorder the shapes on the slide. The `reorder` method allows you to specify the new position for the shape within the shapes collection of the slide.
```java
slide.getShapes().reorder(2, shp3);
```
## Step 5: Save the Modified Presentation
After reordering the shapes, save the modified presentation to a new file. This ensures your original file remains unchanged.
```java
presentation1.save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
## Step 6: Clean Up Resources
Finally, dispose of the presentation object to free up resources.
```java
if (presentation1 != null) presentation1.dispose();
```
## Conclusion
By following these steps, you can easily change the order of shapes in a PowerPoint slide using Aspose.Slides for Java. This powerful library simplifies many tasks associated with PowerPoint presentations, enabling you to create and manipulate slides programmatically. Whether you are automating the creation of presentations or just need to make bulk changes, Aspose.Slides for Java is an invaluable tool.
## FAQ's
### What is Aspose.Slides for Java?
Aspose.Slides for Java is a Java API for creating and manipulating PowerPoint presentations without using Microsoft PowerPoint.
### Can I use Aspose.Slides for Java with other Java IDEs?
Yes, you can use it with any Java IDE such as IntelliJ IDEA, Eclipse, or NetBeans.
### Is Aspose.Slides for Java compatible with all PowerPoint formats?
Yes, Aspose.Slides for Java supports PPT, PPTX, and other PowerPoint formats.
### How do I get a free trial of Aspose.Slides for Java?
You can download a free trial from the [Aspose.Slides for Java download page](https://releases.aspose.com/).
### Where can I find more documentation on Aspose.Slides for Java?
You can find detailed documentation on the [Aspose.Slides for Java documentation page](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
