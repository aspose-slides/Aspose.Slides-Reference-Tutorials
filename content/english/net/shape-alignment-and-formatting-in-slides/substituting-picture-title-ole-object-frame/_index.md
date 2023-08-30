---
title: Substituting Picture Title of OLE Object Frame in Presentation Slides
linktitle: Substituting Picture Title of OLE Object Frame in Presentation Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to substitute picture titles of OLE object frames in presentation slides using Aspose.Slides for .NET. Step-by-step guide with complete source code.
type: docs
weight: 15
url: /net/shape-alignment-and-formatting-in-slides/substituting-picture-title-ole-object-frame/
---

## Introduction to Aspose.Slides for .NET

Aspose.Slides for .NET is a powerful API that allows developers to create, modify, and manipulate PowerPoint presentations without requiring Microsoft Office or PowerPoint to be installed. It provides a wide range of features to work with different elements of presentations, including slides, shapes, text, images, and OLE object frames.

## Prerequisites

Before we begin, ensure you have the following:

- Visual Studio or any compatible .NET development environment installed.
- Aspose.Slides for .NET library. You can download it from [here](https://releases.aspose.com/slides/net/).

## Loading a Presentation

Let's start by loading an existing PowerPoint presentation using Aspose.Slides for .NET. If you don't have a presentation for testing, you can create a new one or download a sample presentation.

```csharp
using Aspose.Slides;

// Load the presentation
using var presentation = new Presentation("sample.pptx");
```

## Accessing OLE Object Frames

OLE (Object Linking and Embedding) object frames allow you to embed objects like images, documents, or other files within a PowerPoint slide. To access OLE object frames in a slide, you can iterate through the shapes and check for instances of `OleObjectFrameEx`.

```csharp
// Iterate through slides
foreach (var slide in presentation.Slides)
{
    // Iterate through shapes in the slide
    foreach (var shape in slide.Shapes)
    {
        if (shape is OleObjectFrameEx oleObject)
        {
            // Access OLE object properties
            var title = oleObject.Title;
            var data = oleObject.ObjectData;
            
            // Perform further actions
        }
    }
}
```

## Substituting Picture Title

To substitute the picture title of an OLE object frame, you can simply update the `Title` property of the `OleObjectFrameEx` instance.

```csharp
foreach (var slide in presentation.Slides)
{
    foreach (var shape in slide.Shapes)
    {
        if (shape is OleObjectFrameEx oleObject)
        {
            // Update the title
            oleObject.Title = "New Picture Title";
        }
    }
}
```

## Saving the Modified Presentation

After making the necessary changes, you need to save the modified presentation. You can save it in various formats such as PPTX, PDF, or images.

```csharp
// Save the presentation
presentation.Save("modified.pptx", SaveFormat.Pptx);
```

## Conclusion

Aspose.Slides for .NET simplifies the process of working with PowerPoint presentations programmatically. In this guide, we covered the steps to substitute the picture title of an OLE object frame in presentation slides. By following these steps, you can efficiently manipulate presentations according to your requirements.

## FAQ's

### How do I obtain the Aspose.Slides for .NET library?

You can download the Aspose.Slides for .NET library from [this link](https://releases.aspose.com/slides/net/).

### Can I use Aspose.Slides for .NET without Microsoft Office installed?

Yes, Aspose.Slides for .NET allows you to work with PowerPoint presentations without requiring Microsoft Office to be installed.

### Are there other operations I can perform on OLE object frames?

Absolutely! You can perform various actions on OLE object frames, such as replacing the object data, resizing, or repositioning them within slides.

### Is Aspose.Slides for .NET compatible with different PowerPoint formats?

Yes, Aspose.Slides for .NET supports a wide range of PowerPoint formats, including PPT, PPTX, PPS, and more.

### Can I automate the creation of PowerPoint presentations using Aspose.Slides?

Certainly! Aspose.Slides for .NET enables you to dynamically generate PowerPoint presentations from scratch, incorporating various elements like text, images, charts, and more.
