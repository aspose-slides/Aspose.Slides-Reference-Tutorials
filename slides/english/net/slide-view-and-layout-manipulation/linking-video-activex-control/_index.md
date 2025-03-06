---
title: Linking Video via ActiveX Control in PowerPoint
linktitle: Linking Video via ActiveX Control
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to link videos to PowerPoint slides using Aspose.Slides for .NET. This step-by-step guide includes source code and tips for creating interactive and engaging presentations with linked videos.
weight: 12
url: /net/slide-view-and-layout-manipulation/linking-video-activex-control/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

Linking a Video via ActiveX Control in a Presentation using Aspose.Slides for .NET

In Aspose.Slides for .NET, you can programmatically link a video to a presentation slide using the ActiveX control. This allows you to create interactive presentations where the video content can be played directly within the slide. In this step-by-step guide, we will walk you through the process of linking a video to a presentation slide using Aspose.Slides for .NET.

## Prerequisites:
- Visual Studio (or any other .NET development environment)
- Aspose.Slides for .NET library. You can download it from [here](https://releases.aspose.com/slides/net/).

## Step 1: Create a New Project
Create a new project in your preferred .NET development environment (e.g., Visual Studio) and add references to the Aspose.Slides for .NET library.

## Step 2: Import Necessary Namespaces
In your project, import the necessary namespaces for working with Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## Step 3: Load Presentation
Load the PowerPoint presentation where you want to add the linked video:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Your code to add the linked video will go here
}
```

## Step 4: Add ActiveX Control
Create an instance of the `IOleObjectFrame` interface to add the ActiveX control to the slide:

```csharp
ISlide slide = presentation.Slides[0]; // Choose the slide where you want to add the video
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

In the code above, we are adding an ActiveX control frame of dimensions 640x480 to the slide. We are specifying the ProgID for the ShockwaveFlash ActiveX control, which is commonly used for embedding videos.

## Step 5: Set Properties of ActiveX Control
Set the properties of the ActiveX control to specify the linked video source:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Replace with the actual video file path
oleObjectFrame.AlternativeText = "Linked Video";
```

Replace `"YourVideoPathHere"` with the actual path to your video file. The `AlternativeText` property provides a description for the linked video.

## Step 6: Save Presentation
Save the modified presentation:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## FAQs:

### How can I specify the size and position of the linked video on the slide?
You can adjust the dimensions and position of the ActiveX control frame using the parameters of the `AddOleObjectFrame` method. The four numerical arguments represent the X and Y coordinates of the top-left corner and the width and height of the frame, respectively.

### Can I link videos of different formats using this approach?
Yes, you can link videos of various formats as long as the appropriate ActiveX control is available for that format. For example, the ShockwaveFlash ActiveX control used in this guide is suitable for Flash videos (SWF). For other formats, you might need to use different ProgIDs.

### Is there a limit to the size of the linked video?
The size of the linked video might affect the overall size and performance of your presentation. It's recommended to optimize your videos for web playback before linking them to the presentation.

### Conclusion:
By following the steps outlined in this guide, you can easily link a video via ActiveX control in a presentation using Aspose.Slides for .NET. This feature enables you to create engaging and interactive presentations that incorporate multimedia content seamlessly.

For more details and advanced options, you can refer to the [Aspose.Slides for .NET documentation](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
