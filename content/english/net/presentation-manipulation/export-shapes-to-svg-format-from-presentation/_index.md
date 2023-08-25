---
title: Export Shapes to SVG Format from Presentation
linktitle: Export Shapes to SVG Format from Presentation
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to export shapes from a PowerPoint presentation to SVG format using Aspose.Slides for .NET. Step-by-step guide with source code included. Efficiently extract shapes for various applications. 
type: docs
weight: 16
url: /net/presentation-manipulation/export-shapes-to-svg-format-from-presentation/
---
This guide will walk you through the process of exporting shapes from a presentation to SVG format using the Aspose.Slides for .NET library. Aspose.Slides is a powerful API that allows you to work with Microsoft PowerPoint files programmatically. In this tutorial, you will learn how to extract shapes from a presentation and save them in SVG format using C#.

## Prerequisites

Before you begin, make sure you have the following prerequisites in place:

- Visual Studio installed
- Basic understanding of C# programming
- Aspose.Slides for .NET library. You can download it from [here](https://releases.aspose.com/slides/net/).

## Step-by-Step Guide

Follow these steps to export shapes to SVG format from a presentation:

### 1. Create a New Project

Open Visual Studio and create a new C# project.

### 2. Add Reference to Aspose.Slides

In your project, right-click on "References" in the Solution Explorer, then click "Add Reference." Browse and select the Aspose.Slides DLL you downloaded.

### 3. Load the Presentation

```csharp
using Aspose.Slides;

// Load the presentation
Presentation presentation = new Presentation("presentation.pptx");
```

### 4. Iterate Through Shapes

```csharp
foreach (IShape shape in presentation.Slides[0].Shapes)
{
    // Check if the shape is a group shape
    if (shape is IGroupShape groupShape)
    {
        foreach (IShape groupChildShape in groupShape.Shapes)
        {
            // Export the shape to SVG
            string svgFileName = $"shape_{groupChildShape.Id}.svg";
            groupChildShape.WriteAsSvg(svgFileName);
        }
    }
    else
    {
        // Export the shape to SVG
        string svgFileName = $"shape_{shape.Id}.svg";
        shape.WriteAsSvg(svgFileName);
    }
}
```

### 5. Save SVG Files

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx); // Save changes to the presentation
```

## FAQs

### How can I install Aspose.Slides for .NET?

You can download the Aspose.Slides for .NET library from [here](https://releases.aspose.com/slides/net/). Follow the installation instructions provided in the documentation.

### How do I load a PowerPoint presentation using Aspose.Slides?

You can load a presentation using the `Presentation` class constructor. Provide the path to the PowerPoint file as a parameter.

### How do I export a shape to SVG format?

You can use the `WriteAsSvg` method on an `IShape` object to export it to SVG format. You need to specify the file name for the SVG output.

## Conclusion

In this tutorial, you learned how to export shapes from a PowerPoint presentation to SVG format using the Aspose.Slides for .NET library. This can be useful when you need to extract individual shapes for use in other applications or platforms that support SVG graphics. Aspose.Slides provides a simple and efficient way to achieve this programmatically.

For more details and advanced features, refer to the [Aspose.Slides for .NET API Reference](https://reference.aspose.com/slides/net/).