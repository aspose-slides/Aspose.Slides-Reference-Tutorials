---
title: Add Relative Scale Height Picture Frame in PowerPoint
linktitle: Add Relative Scale Height Picture Frame in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to add relative scale height picture frames in PowerPoint presentations using Aspose.Slides for Java, enhancing your visual content.
weight: 15
url: /java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
In this tutorial, you'll learn how to add a picture frame with relative scale height in PowerPoint presentations using Aspose.Slides for Java.
## Prerequisites
Before you begin, make sure you have the following:
1. Java Development Kit (JDK) installed on your system.
2. Aspose.Slides for Java library downloaded and added to your Java project.

## Import Packages
To begin, import the necessary packages in your Java project:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Step 1: Set up Your Project
First, ensure you have a directory set up for your project, and your Java environment is properly configured.
## Step 2: Instantiate Presentation Object
Create a new presentation object using Aspose.Slides:
```java
Presentation presentation = new Presentation();
```
## Step 3: Load Image to be Added
Load the image you want to add to the presentation:
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## Step 4: Add Picture Frame to Slide
Add a picture frame to a slide in the presentation:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## Step 5: Set Relative Scale Width and Height
Set the relative scale width and height for the picture frame:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## Step 6: Save Presentation
Save the presentation with the added picture frame:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## Conclusion
By following these steps, you can easily add a picture frame with relative scale height in PowerPoint presentations using Aspose.Slides for Java. Experiment with different scale values to achieve the desired appearance for your images.

## FAQ's
### Can I add multiple picture frames to a single slide using this method?
Yes, you can add multiple picture frames to a slide by repeating the process for each image.
### Is Aspose.Slides for Java compatible with all versions of PowerPoint?
Aspose.Slides for Java is compatible with various versions of PowerPoint, ensuring flexibility in creating presentations.
### Can I customize the position and size of the picture frame?
Absolutely, you can adjust the position and size parameters in the `addPictureFrame` method to suit your requirements.
### Does Aspose.Slides for Java support other image formats besides JPEG?
Yes, Aspose.Slides for Java supports various image formats, including PNG, GIF, BMP, and more.
### Is there a community forum or support channel available for Aspose.Slides users?
Yes, you can visit the Aspose.Slides forum for any questions, discussions, or assistance regarding the library.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
