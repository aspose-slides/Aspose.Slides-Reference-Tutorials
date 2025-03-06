---
title: Fill Shapes with Picture in PowerPoint
linktitle: Fill Shapes with Picture in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to fill shapes with pictures in PowerPoint presentations using Aspose.Slides for Java. Enhance visual appeal effortlessly.
weight: 12
url: /java/java-powerpoint-shape-formatting-geometry/fill-shapes-picture-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
PowerPoint presentations often require visual elements like shapes filled with images to enhance their appeal and convey information effectively. Aspose.Slides for Java provides a powerful set of tools to accomplish this task seamlessly. In this tutorial, we'll learn how to fill shapes with pictures using Aspose.Slides for Java step by step.
## Prerequisites
Before we begin, ensure you have the following:
1. Java Development Kit (JDK) installed on your system.
2. Aspose.Slides for Java library downloaded. You can get it from [here](https://releases.aspose.com/slides/java/).
3. Basic knowledge of Java programming.
## Import Packages
In your Java project, import the necessary packages:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Step 1: Set up the Project Directory
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
Ensure to replace `"Your Document Directory"` with the path to your project directory.
## Step 2: Create a Presentation
```java
Presentation pres = new Presentation();
```
Instantiate the `Presentation` class to create a new PowerPoint presentation.
## Step 3: Add a Slide and Shape
```java
ISlide sld = pres.getSlides().get_Item(0);
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
Add a slide to the presentation and create a rectangle shape on it.
## Step 4: Set Fill Type to Picture
```java
shp.getFillFormat().setFillType(FillType.Picture);
```
Set the fill type of the shape to picture.
## Step 5: Set Picture Fill Mode
```java
shp.getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Tile);
```
Set the picture fill mode of the shape.
## Step 6: Set Picture
```java
BufferedImage img = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
shp.getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
Load the image and set it as the fill for the shape.
## Step 7: Save Presentation
```java
pres.save(dataDir + "RectShpPic_out.pptx", SaveFormat.Pptx);
```
Save the modified presentation to a file.

## Conclusion
With Aspose.Slides for Java, filling shapes with pictures in PowerPoint presentations becomes a straightforward process. By following the steps outlined in this tutorial, you can easily enhance your presentations with visually appealing elements.

## FAQ's
### Can I fill different shapes with pictures using Aspose.Slides for Java?
Yes, Aspose.Slides for Java supports filling various shapes with pictures, providing flexibility in design.
### Is Aspose.Slides for Java compatible with all versions of PowerPoint?
Aspose.Slides for Java generates presentations compatible with PowerPoint 97 and above, ensuring broad compatibility.
### How can I resize the image within the shape?
You can resize the image within the shape by adjusting the dimensions of the shape or scaling the image accordingly before setting it as the fill.
### Are there any limitations on the image formats supported for filling shapes?
Aspose.Slides for Java supports a wide range of image formats, including JPEG, PNG, GIF, BMP, and TIFF, among others.
### Can I apply effects to the filled shapes?
Yes, Aspose.Slides for Java provides comprehensive APIs to apply various effects, such as shadows, reflections, and 3D rotations, to filled shapes.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
