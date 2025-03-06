---
title: Set Bullet Fill Format in SmartArt using Java
linktitle: Set Bullet Fill Format in SmartArt using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to set bullet fill format in SmartArt using Java with Aspose.Slides. Step-by-step guide for efficient presentation manipulation.
weight: 18
url: /java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Set Bullet Fill Format in SmartArt using Java

## Introduction
In the realm of Java programming, the efficient manipulation of presentations is a common requirement, especially when dealing with SmartArt elements. Aspose.Slides for Java emerges as a powerful tool for such tasks, offering an array of functionalities to handle presentations programmatically. In this tutorial, we'll delve into the process of setting bullet fill format in SmartArt using Java with Aspose.Slides, step by step.
## Prerequisites
Before we embark on this tutorial, ensure you have the following prerequisites in place:
### Java Development Kit (JDK)
You need to have JDK installed on your system. You can download it from the [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) and follow the installation instructions.
### Aspose.Slides for Java
Download and install Aspose.Slides for Java from the [download link](https://releases.aspose.com/slides/java/). Follow the installation instructions provided in the documentation for your specific operating system.

## Import Packages
To begin, import the necessary packages into your Java project:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Let's break down the example provided into multiple steps for a clear understanding of how to set bullet fill format in SmartArt using Java with Aspose.Slides.
## Step 1: Create Presentation Object
```java
Presentation presentation = new Presentation();
```
Firstly, create a new instance of the Presentation class, which represents a PowerPoint presentation.
## Step 2: Add SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Next, add a SmartArt shape to the slide. This line of code initializes a new SmartArt shape with specified dimensions and layout.
## Step 3: Access SmartArt Node
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Now, access the first node (or any desired node) within the SmartArt shape to modify its properties.
## Step 4: Set Bullet Fill Format
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Here, we check if the bullet fill format is supported. If it is, we load an image file and set it as the bullet fill for the SmartArt node.
## Step 5: Save Presentation
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Finally, save the modified presentation to a specified location.

## Conclusion
Congratulations! You've successfully learned how to set bullet fill format in SmartArt using Java with Aspose.Slides. This capability opens up a world of possibilities for dynamic and visually appealing presentations in Java applications.
## FAQ's
### Can I use Aspose.Slides for Java to create presentations from scratch?
Absolutely! Aspose.Slides provides comprehensive APIs for creating, modifying, and manipulating presentations entirely through code.
### Is Aspose.Slides compatible with different versions of PowerPoint?
Yes, Aspose.Slides ensures compatibility with various versions of Microsoft PowerPoint, enabling seamless integration into your workflow.
### Can I customize SmartArt elements beyond bullet fill format?
Indeed, Aspose.Slides empowers you to customize every aspect of SmartArt shapes, including layout, style, content, and more.
### Is there a trial version available for Aspose.Slides for Java?
Yes, you can explore the features of Aspose.Slides with a free trial. Simply download it from the [website](https://releases.aspose.com/slides/java/) and start exploring.
### Where can I find support for Aspose.Slides for Java?
For any queries or assistance, you can visit the Aspose.Slides forum at [this link](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
