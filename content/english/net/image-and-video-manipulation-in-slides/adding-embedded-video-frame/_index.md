---
title: Adding Embedded Video Frame in Presentation Slides using Aspose.Slides
linktitle: Adding Embedded Video Frame in Presentation Slides using Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to enhance your presentation slides by adding embedded video frames using Aspose.Slides for .NET. Follow this step-by-step guide with complete source code to seamlessly integrate videos, customize playback, and create captivating presentations.
type: docs
weight: 19
url: /net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---

## Introduction to Aspose.Slides for .NET

Aspose.Slides for .NET is a versatile and feature-rich library that enables developers to work with PowerPoint presentations programmatically. It provides a wide range of functionalities, including creating, editing, converting, and manipulating presentations. In this guide, we will focus on the process of embedding video frames within presentation slides.

## Prerequisites

Before we dive into the implementation, make sure you have the following prerequisites in place:

- Visual Studio (or any other .NET development environment)
- Basic knowledge of C# programming language
- Aspose.Slides for .NET library

## Installing Aspose.Slides for .NET

To get started, you need to install the Aspose.Slides for .NET library. You can download the library from the official website or use a package manager like NuGet. Here's how you can install it using NuGet:

```csharp
Install-Package Aspose.Slides
```

## Creating a New Presentation

Let's start by creating a new PowerPoint presentation using Aspose.Slides. Here's a basic code snippet to create a presentation:

```csharp
using Aspose.Slides;

// Create a new presentation
Presentation presentation = new Presentation();
```

## Adding a Slide

Next, we'll add a new slide to the presentation. Slides are indexed starting from zero. Here's how you can add a slide:

```csharp
// Add a new slide to the presentation
ISlide slide = presentation.Slides.AddEmptySlide(SlideLayout.Blank);
```

## Embedding a Video

Now comes the exciting part – embedding a video into the slide. You need to have the video file path or URL to proceed. Here's how you can embed a video into the slide:

```csharp
// Path to the video file
string videoPath = "path_to_your_video.mp4";

// Add the video to the slide
IVideoFrame videoFrame = slide.Shapes.AddVideoFrame(100, 100, 480, 270, videoPath);
```

## Customizing the Video Frame

You can customize various aspects of the video frame, such as its size, position, and playback options. Here's an example of how to set the playback mode to automatically start:

```csharp
// Set video playback mode to automatically start
videoFrame.PlayMode = VideoPlayMode.Auto;
```

## Saving and Exporting the Presentation

Once you've added the video frame and customized it to your liking, it's time to save the presentation. You can save it in various formats, such as PPTX or PDF. Here's how to save it as a PPTX file:

```csharp
// Save the presentation
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## Conclusion

In this guide, we've explored how to enhance your presentation slides by adding embedded video frames using Aspose.Slides for .NET. This powerful library enables you to create dynamic and engaging presentations that leave a lasting impression on your audience. By following the steps outlined in this guide, you can seamlessly integrate multimedia content into your slides and create captivating presentations.

## FAQ's

### How do I install Aspose.Slides for .NET?

You can install Aspose.Slides for .NET using the NuGet package manager. Simply run the following command in your NuGet Package Manager Console: `Install-Package Aspose.Slides`

### Can I customize the appearance of the video frame?

Yes, you can customize the size, position, and playback options of the video frame using properties provided by the Aspose.Slides library.

### What video formats are supported for embedding?

Aspose.Slides supports embedding videos in various formats, including MP4, AVI, and WMV.

### Can I control when the video starts playing?

Absolutely! You can set the playback mode of the video frame to start automatically or manually, depending on your preferences.

### Is Aspose.Slides only for adding videos?

No, Aspose.Slides offers a wide range of functionalities beyond adding videos. It allows you to create, edit, convert, and manipulate PowerPoint presentations programmatically.
