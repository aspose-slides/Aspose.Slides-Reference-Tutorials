---
title: Aspose.Slides - Adding Embedded Videos in .NET Presentations
linktitle: Aspose.Slides - Adding Embedded Videos in .NET Presentations
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Enhance your presentations with embedded videos using Aspose.Slides for .NET. Follow our step-by-step guide for seamless integration.
weight: 19
url: /net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
In the dynamic world of presentations, integrating multimedia elements can significantly enhance engagement. Aspose.Slides for .NET provides a powerful solution for incorporating embedded video frames into your presentation slides. This tutorial will guide you through the process, breaking down each step to ensure a seamless experience.
## Prerequisites
Before we dive into the tutorial, make sure you have the following:
- Aspose.Slides for .NET Library: Download and install the library from the [release page](https://releases.aspose.com/slides/net/).
- Media Content: Have a video file (e.g., "Wildlife.mp4") that you want to embed in your presentation.
## Import Namespaces
Begin by importing the necessary namespaces in your .NET project:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Step 1: Set Up Directories
Ensure your project has the required directories for document and media files:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Create directory if it is not already present.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Step 2: Instantiate Presentation Class
Create an instance of the Presentation class to represent the PPTX file:
```csharp
using (Presentation pres = new Presentation())
{
    // Get the first slide
    ISlide sld = pres.Slides[0];
```
## Step 3: Embed Video Inside Presentation
Use the following code to embed a video inside the presentation:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Step 4: Add Video Frame
Now, add a video frame to the slide:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Step 5: Set Video Properties
Set the video to the video frame and configure play mode and volume:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## Step 6: Save the Presentation
Finally, save the PPTX file to disk:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Repeat these steps for each video you want to embed in your presentation.
## Conclusion
Congratulations! You've successfully added an embedded video frame to your presentation using Aspose.Slides for .NET. This dynamic feature can elevate your presentations to new heights, captivating your audience with multimedia elements seamlessly integrated into your slides.
## FAQs
### Can I embed videos in any slide of the presentation?
Yes, you can choose any slide by modifying the index in `pres.Slides[index]`.
### Which video formats are supported?
Aspose.Slides supports a variety of video formats, including MP4, AVI, and WMV.
### Can I customize the size and position of the video frame?
Absolutely! Adjust the parameters in `AddVideoFrame(x, y, width, height, video)` as needed.
### Is there a limit to the number of videos I can embed?
The number of embedded videos is typically limited by the capacity of your presentation software.
### How can I seek further assistance or share my experience?
Visit the [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) for community support and discussions.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
