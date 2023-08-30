---
title: Setting Slide Numbers for Presentations using Aspose.Slides
linktitle: Setting Slide Numbers for Presentations using Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to add and customize slide numbers in PowerPoint presentations using Aspose.Slides for .NET. This step-by-step guide provides source code examples for setting up the project, loading a presentation, adding slide numbers, customizing their format, and adjusting their placement.
type: docs
weight: 16
url: /net/printing-and-rendering-in-slides/setting-slide-numbers/
---

## Introduction to Aspose.Slides for .NET

Aspose.Slides for .NET is a versatile library that enables .NET developers to create, modify, and manipulate PowerPoint presentations programmatically. It provides a wide range of features to interact with various elements of presentations, including slides, shapes, text, images, and more. In this guide, we'll focus on adding and customizing slide numbers using Aspose.Slides for .NET.

## Prerequisites

Before we begin, make sure you have the following prerequisites in place:

- Visual Studio (or any other .NET development environment)
- Aspose.Slides for .NET library (Download from [here](https://releases.aspose.com/slides/net/)

## Setting up the Project

1. Create a new Visual Studio project (Console Application, for example).
2. Add a reference to the Aspose.Slides for .NET library.

## Loading a Presentation

To get started, let's load an existing PowerPoint presentation:

```csharp
using Aspose.Slides;

// Load the presentation
using Presentation presentation = new Presentation("your-presentation.pptx");
```

## Adding Slide Numbers

Next, let's add slide numbers to each slide in the presentation:

```csharp
// Enable slide numbers
foreach (ISlide slide in presentation.Slides)
{
    // Add slide number shape
    IAutoShape slideNumberShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 10, 10, 50, 20);
    slideNumberShape.TextFrame.Text = (slide.SlideNumber).ToString();
}
```

## Customizing Slide Number Format

You can customize the appearance of the slide numbers by adjusting font, color, size, and more:

```csharp
foreach (IAutoShape shape in presentation.Slides[0].Shapes.OfType<IAutoShape>())
{
    // Customize font and color
    ITextFrame textFrame = shape.TextFrame;
    IParagraph paragraph = textFrame.Paragraphs[0];
    IPortion portion = paragraph.Portions[0];
    
    portion.PortionFormat.FontHeight = 12;
    portion.PortionFormat.FillFormat.SolidFillColor.Color = Color.Black;
}
```

## Updating Slide Number Placement

You can also adjust the position of the slide numbers on each slide:

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IAutoShape shape in slide.Shapes.OfType<IAutoShape>())
    {
        shape.Left = slide.SlideSize.Size.Width - shape.Width - 10;
        shape.Top = slide.SlideSize.Size.Height - shape.Height - 10;
    }
}
```

## Saving the Modified Presentation

Once you've added and customized the slide numbers, save the modified presentation:

```csharp
presentation.Save("output-presentation.pptx", SaveFormat.Pptx);
```

## Conclusion

In this guide, we explored how to enhance your presentations by adding and customizing slide numbers using Aspose.Slides for .NET. By following the provided steps and code examples, you can automate the process of adding slide numbers and create professional-looking presentations.

## FAQ's

### How do I install Aspose.Slides for .NET?

You can download the Aspose.Slides for .NET library from [here](https://releases.aspose.com/slides/net/). After downloading, add a reference to the library in your .NET project.

### Can I customize the appearance of slide numbers?

Yes, you can customize the font, color, size, and other attributes of the slide numbers using the provided code examples.

### How can I adjust the position of slide numbers on each slide?

You can adjust the position of slide numbers by modifying the coordinates of the slide number shapes, as shown in the code examples.

### Is Aspose.Slides for .NET only for adding slide numbers?

No, Aspose.Slides for .NET offers a wide range of features beyond adding slide numbers. It allows you to create, modify, and manipulate various elements of PowerPoint presentations programmatically.

### Are the modifications reversible if I want to remove slide numbers later?

Yes, you can easily remove the slide numbers by removing the corresponding shapes from the slides using the Aspose.Slides library.
