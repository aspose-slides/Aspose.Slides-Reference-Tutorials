---
title: How to Extract Video from Slide Using Aspose.Slides for .NET
linktitle: Extract Video from Slide
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to extract videos from PowerPoint slides using Aspose.Slides for .NET. This step-by-step guide simplifies the process for you.
weight: 14
url: /net/audio-and-video-extraction/extract-video/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Aspose.Slides for .NET is a powerful library that allows you to work with PowerPoint presentations in a .NET environment. One of the useful features it provides is the ability to extract videos from slides. In this step-by-step guide, we will show you how to extract a video from a PowerPoint slide using Aspose.Slides for .NET.

## Prerequisites

Before you begin, make sure you have the following prerequisites in place:

- Aspose.Slides for .NET: You need to have Aspose.Slides for .NET installed. You can obtain it from the [website](https://purchase.aspose.com/buy).

- A PowerPoint Presentation: Prepare a PowerPoint presentation (e.g., Video.pptx) that contains the video you want to extract.

## Import Namespaces

You need to import the necessary namespaces to work with Aspose.Slides for .NET. Here's how you can do it:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

Now, let's break down the process of extracting a video from a slide into multiple steps.

## Step 1: Set the Document Directory

```csharp
string dataDir = "Your Document Directory";
```

Replace `"Your Document Directory"` with the path to the directory where your PowerPoint presentation is located.

## Step 2: Load the Presentation

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

This code initializes a Presentation object, representing your PowerPoint presentation file.

## Step 3: Iterate Through Slides and Shapes

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

Here, we loop through each slide in the presentation and then iterate through the shapes in the first slide (modify as needed).

## Step 4: Check if the Shape is a Video Frame

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

This step checks if the shape on the slide is a video frame.

## Step 5: Extract Video Data

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

This code extracts information about the video, including its content type and binary data.

## Step 6: Save the Video

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

Finally, this step saves the video to a new file in the specified directory.

Once you've completed these steps, you will have successfully extracted a video from a PowerPoint slide using Aspose.Slides for .NET.

## Conclusion

Aspose.Slides for .NET simplifies the process of working with PowerPoint presentations, allowing you to perform tasks like extracting videos from slides with ease. By following this step-by-step guide and making use of the Aspose.Slides library, you can enhance your .NET applications with powerful PowerPoint features.

## Frequently Asked Questions (FAQs)

### What is Aspose.Slides for .NET?
Aspose.Slides for .NET is a library that enables .NET applications to work with PowerPoint presentations, including creating, editing, and extracting content.

### Where can I find the documentation for Aspose.Slides for .NET?
You can find the documentation [here](https://reference.aspose.com/slides/net/).

### Is Aspose.Slides for .NET available for a free trial?
Yes, you can get a free trial version from [here](https://releases.aspose.com/).

### How can I obtain a temporary license for Aspose.Slides for .NET?
You can request a temporary license from [this link](https://purchase.aspose.com/temporary-license/).

### Where can I get support for Aspose.Slides for .NET?
You can find support on the [Aspose.Slides forum](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
