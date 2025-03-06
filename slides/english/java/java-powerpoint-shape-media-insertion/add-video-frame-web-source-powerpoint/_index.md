---
title: Add Video Frame from Web Source in PowerPoint
linktitle: Add Video Frame from Web Source in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to enhance your PowerPoint presentations by adding video frames from web sources using Aspose.Slides for Java.
weight: 18
url: /java/java-powerpoint-shape-media-insertion/add-video-frame-web-source-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
In this tutorial, we will learn how to add a video frame from a web source, such as YouTube, to a PowerPoint presentation using Aspose.Slides for Java. By following these step-by-step instructions, you'll be able to enhance your presentations by incorporating engaging multimedia elements.
## Prerequisites
Before we begin, make sure you have the following prerequisites:
- Basic knowledge of Java programming.
- JDK (Java Development Kit) installed on your system.
- Aspose.Slides for Java library downloaded and added to your Java project. You can download it from [here](https://releases.aspose.com/slides/java/).
- An active internet connection to access the web source (e.g., YouTube).

## Import Packages
First, import the necessary packages into your Java project:
```java
import com.aspose.slides.IVideoFrame;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.VideoPlayModePreset;

import java.io.ByteArrayOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.net.URL;
import java.net.URLConnection;
```
## Step 1: Create a PowerPoint Presentation Object
Initialize a Presentation object, which represents a PowerPoint presentation:
```java
Presentation pres = new Presentation();
```
## Step 2: Add a Video Frame
Now, let's add a video frame to the presentation. This frame will contain the video from the web source. We'll use the addVideoFrame method:
```java
IVideoFrame videoFrame = pres.getSlides().get_Item(0).getShapes().addVideoFrame(10, 10, 427, 240, "https://www.youtube.com/embed/VIDEO_ID");
```
Replace "VIDEO_ID" with the ID of the YouTube video you want to embed.
## Step 3: Set Video Play Mode
Set the play mode for the video frame. In this example, we'll set it to Auto:
```java
videoFrame.setPlayMode(VideoPlayModePreset.Auto);
```
## Step 4: Load Thumbnail
To enhance the visual appeal, we'll load the thumbnail of the video. This step involves fetching the thumbnail image from the web source:
```java
String thumbnailUri = "https://www.youtube.com/watch?v=VIDEO_ID";
URL url = new URL(thumbnailUri);
URLConnection connection = url.openConnection();
connection.setConnectTimeout(5000);
connection.setReadTimeout(10000);
try (InputStream input = connection.getInputStream();
     ByteArrayOutputStream output = new ByteArrayOutputStream()) {
    byte[] buffer = new byte[8192];
    for (int count; (count = input.read(buffer)) > 0;) {
        output.write(buffer, 0, count);
    }
    output.toByteArray();
    videoFrame.getPictureFormat().getPicture().setImage(pres.getImages().addImage(output.toByteArray()));
}
```
## Step 5: Save the Presentation
Finally, save the modified presentation:
```java
pres.save("YOUR_DIRECTORY/AddVideoFrameFromWebSource_out.pptx", SaveFormat.Pptx);
```
Replace "YOUR_DIRECTORY" with the directory where you want to save the presentation.

## Conclusion
Congratulations! You've successfully learned how to add a video frame from a web source in PowerPoint using Aspose.Slides for Java. Incorporating multimedia elements like videos can significantly enhance the impact and engagement of your presentations.
## FAQ's
### Can I add videos from sources other than YouTube?
Yes, you can add videos from various web sources as long as they provide an embeddable link.
### Do I need an internet connection to play the embedded video?
Yes, an active internet connection is required to stream the video from the web source.
### Can I customize the appearance of the video frame?
Absolutely! Aspose.Slides provides extensive options for customizing the appearance and behavior of video frames.
### Is Aspose.Slides compatible with all versions of PowerPoint?
Aspose.Slides supports a wide range of PowerPoint versions, ensuring compatibility across different platforms.
### Where can I find more resources and support for Aspose.Slides?
You can visit the [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) for assistance, documentation, and community support.

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
