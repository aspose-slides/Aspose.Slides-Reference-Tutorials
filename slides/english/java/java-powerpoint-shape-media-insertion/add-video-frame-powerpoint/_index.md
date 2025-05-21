---
title: Add Video Frame in PowerPoint
linktitle: Add Video Frame in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to seamlessly integrate video content into PowerPoint presentations using Aspose.Slides for Java. Your slides with multimedia elements to engage your audience.
weight: 17
url: /java/java-powerpoint-shape-media-insertion/add-video-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Add Video Frame in PowerPoint

## Introduction
In this tutorial, we will guide you through the process of adding a video frame to a PowerPoint presentation using Aspose.Slides for Java. By following these step-by-step instructions, you'll be able to seamlessly integrate video content into your presentations with ease.
## Prerequisites
Before you begin, ensure you have the following prerequisites in place:
- Java Development Kit (JDK) installed on your system
- Aspose.Slides for Java library downloaded and set up in your Java project
## Import Packages
First, you need to import the necessary packages to utilize Aspose.Slides functionalities in your Java code. 
```java
import com.aspose.slides.*;

import java.io.File;
```
## Step 1: Set Up Document Directory
Ensure you have a directory set up to store your PowerPoint files.
```java
String dataDir = "Your Document Directory";
```
## Step 2: Create Presentation Object
Instantiate the `Presentation` class to represent the PowerPoint file.
```java
Presentation pres = new Presentation();
```
## Step 3: Add Video Frame to Slide
Get the first slide and add a video frame to it.
```java
ISlide sld = pres.getSlides().get_Item(0);
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 150, dataDir + "video1.avi");
```
## Step 4: Set Play Mode and Volume
Set the play mode and volume of the video frame.
```java
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## Step 5: Save Presentation
Save the modified PowerPoint file to disk.
```java
pres.save(dataDir + "VideoFrame_out.pptx", SaveFormat.Pptx);
```
## Conclusion
Congratulations! You have successfully learned how to add a video frame to a PowerPoint presentation using Aspose.Slides for Java. Enhance your presentations by incorporating multimedia elements to engage your audience effectively.
## FAQ's
### Can I add videos of any format to the PowerPoint presentation?
Aspose.Slides supports various video formats such as AVI, WMV, MP4, and more. Ensure the format is compatible with PowerPoint.
### Is Aspose.Slides compatible with different versions of Java?
Yes, Aspose.Slides for Java is compatible with JDK versions 6 and above.
### How can I adjust the size and position of the video frame?
You can customize the dimensions and coordinates of the video frame by modifying the parameters in the `addVideoFrame` method.
### Can I control the playback settings of the video?
Yes, you can set the play mode and volume of the video frame according to your preferences.
### Where can I find more support and resources for Aspose.Slides?
Visit the [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) for assistance, documentation, and community support.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
