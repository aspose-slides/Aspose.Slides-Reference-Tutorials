---
title: Extract Video from Slide
linktitle: Extract Video from Slide
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Master video extraction from PowerPoint slides using Aspose.Slides for .NET. Follow our guide with code examples.
type: docs
weight: 14
url: /net/audio-and-video-extraction/extract-video/
---

## Introduction

In today's digital world, multimedia presentations have become an essential part of communication. PowerPoint presentations often include a mix of text, images, and videos to convey information effectively. However, there might be times when you need to extract a video from a slide for various purposes, such as archiving, sharing, or further editing. This is where Aspose.Slides for .NET comes into play.

## Prerequisites

Before we dive into the step-by-step guide, make sure you have the following prerequisites in place:

- Basic knowledge of C# and .NET framework
- Visual Studio installed
- Aspose.Slides for .NET library (download from [here](https://releases.aspose.com/slides/net)

## Step-by-Step Guide

Let's walk through the process of extracting a video from a slide using Aspose.Slides for .NET:

### Step 1: Installation

1. Open Visual Studio and create a new C# project.
2. Right-click on your project in the Solution Explorer, and select "Manage NuGet Packages."
3. Search for "Aspose.Slides" and install the latest version.

### Step 2: Load Presentation

```csharp
using Aspose.Slides;

// Load the presentation
using var presentation = new Presentation("your-presentation.pptx");
```

Replace `"your-presentation.pptx"` with the actual path to your PowerPoint presentation file.

### Step 3: Extract Video

```csharp
// Get the first slide
var slide = presentation.Slides[0];

// Iterate through slide shapes
foreach (var shape in slide.Shapes)
{
    if (shape is IVideoFrame videoFrame)
    {
        // Extract the video from the video frame
        var video = videoFrame.EmbeddedVideo;
        // Further processing can be done with the video object
    }
}
```

### Step 4: Save Video

```csharp
// Save the extracted video
video.WriteToFile("extracted-video.mp4");
```

Replace `"extracted-video.mp4"` with the desired name and path for the extracted video file.

## Conclusion

Aspose.Slides for .NET simplifies the task of extracting videos from PowerPoint presentations. With just a few lines of code, you can retrieve videos embedded within slides and save them as separate video files. Whether you're looking to repurpose content or create compilations, this library provides a seamless solution.

## FAQ's

### How can I access Aspose.Slides documentation?

You can refer to the official documentation for Aspose.Slides for .NET at [here](https://reference.aspose.com/slides/net/).

### Is Aspose.Slides available for other programming languages?

Yes, Aspose.Slides is available for multiple programming languages, including Java. You can find the appropriate libraries on the official Aspose website.

### Can I extract audio using the same approach?

No, the provided example is specifically for extracting videos. To extract audio, you would need to modify the code to work with audio frames.

### Are there any licensing fees for using Aspose.Slides?

Yes, Aspose.Slides is a commercial product. You can find detailed information about licensing and pricing on the official Aspose website.

### How do I access the extracted video's properties?

The `EmbeddedVideo` object obtained from the `IVideoFrame` provides access to various properties of the video, such as duration, resolution, and more.
