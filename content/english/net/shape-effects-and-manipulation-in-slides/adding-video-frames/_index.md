---
title: Adding Video Frames to Presentation Slides using Aspose.Slides
linktitle: Adding Video Frames to Presentation Slides using Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to enhance your presentations by adding video frames using Aspose.Slides for .NET. Create engaging and interactive content seamlessly. 
type: docs
weight: 19
url: /net/shape-effects-and-manipulation-in-slides/adding-video-frames/
---

## Introduction to Aspose.Slides and Video Integration

Aspose.Slides is a comprehensive library that empowers developers to create, manipulate, and convert PowerPoint presentations programmatically. By integrating video frames into your slides, you can elevate your presentations and make them more dynamic and engaging.

## Prerequisites for Incorporating Videos

Before you start, ensure you have the following:

- Visual Studio or any preferred .NET development environment
- Aspose.Slides for .NET library installed
- A PowerPoint presentation (PPTX) where you want to add video frames

## Setting up Your Development Environment

1. Open Visual Studio and create a new .NET project.
2. Install the Aspose.Slides NuGet package: `Install-Package Aspose.Slides`.

## Loading a Presentation and Accessing Slides

To get started, load your PowerPoint presentation using Aspose.Slides:

```csharp
using Aspose.Slides;

// Load the presentation
using Presentation presentation = new Presentation("your-presentation.pptx");

// Access slides
ISlideCollection slides = presentation.Slides;
```

## Adding Video Files to the Presentation

1. Place your video files in a folder within your project.
2. Add references to these files in your code:

```csharp
// Add video files
string videoPath = "path-to-your-videos-folder";
string[] videoFiles = Directory.GetFiles(videoPath, "*.mp4");
```

## Placing Video Frames on Slides

Iterate through the slides and add video frames:

```csharp
foreach (ISlide slide in slides)
{
    foreach (string videoFile in videoFiles)
    {
        IVideoFrame videoFrame = slide.Shapes.AddVideoFrame(100, 100, 320, 240, videoFile);
    }
}
```

## Customizing Video Frame Properties

You can customize video frame properties like position, size, and style:

```csharp
foreach (IVideoFrame videoFrame in slide.Shapes.OfType<IVideoFrame>())
{
    videoFrame.X = 200;
    videoFrame.Y = 150;
    videoFrame.Width = 480;
    videoFrame.Height = 360;
}
```

## Handling Playback Options

Control video playback using the `VideoPlayModePreset` enumeration:

```csharp
foreach (IVideoFrame videoFrame in slide.Shapes.OfType<IVideoFrame>())
{
    videoFrame.PlayMode = VideoPlayModePreset.Auto;
}
```

## Saving and Exporting the Modified Presentation

Save your presentation after adding video frames:

```csharp
presentation.Save("modified-presentation.pptx", SaveFormat.Pptx);
```

## Conclusion

Incorporating video frames into your presentation slides using Aspose.Slides enhances the visual impact of your content. You've learned how to seamlessly integrate videos, customize video frame properties, and control playback options. Start creating dynamic and engaging presentations that captivate your audience.

## FAQs

### How do I add multiple videos to a single slide?

Iterate through your video files and add video frames to the desired slide using the provided code.

### Can I control video playback settings?

Yes, you can use the `VideoPlayModePreset` enumeration to set playback options such as automatic playback.

### What video formats are supported?

Aspose.Slides supports various video formats, including MP4, AVI, WMV, and more.

### Is it possible to add videos programmatically in C#?

Absolutely, Aspose.Slides for .NET provides a user-friendly API to add videos to slides programmatically using C#.

### Can I modify the appearance of the video frame?

Yes, you can customize the video frame's position, size, and other visual properties according to your requirements.