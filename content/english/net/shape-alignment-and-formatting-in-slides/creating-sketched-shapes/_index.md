---
title: Creating Sketched Shapes in Presentation Slides with Aspose.Slides
linktitle: Creating Sketched Shapes in Presentation Slides with Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to create captivating presentation slides with sketched shapes using Aspose.Slides for .NET. Follow this step-by-step guide with complete source code to add personalized and creative elements to your slides.
type: docs
weight: 13
url: /net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---

## Introduction to Creating Sketched Shapes in Presentation Slides

Presentation slides are a powerful tool for conveying information visually. Sometimes, you might want to add a personal touch to your slides by incorporating sketched shapes, which can make your presentations more engaging and creative. In this step-by-step guide, we'll explore how to achieve this using the Aspose.Slides for .NET library. By the end of this tutorial, you'll be able to create presentation slides with sketched shapes that stand out. Let's dive in!

## Setting Up the Project

Before we begin, make sure you have the .NET development environment set up on your machine. You can download the latest version of Aspose.Slides from the website [here](https://releases.aspose.com/slides/net/). Once downloaded, install the library into your project.

## Creating a New Presentation

Let's start by creating a new presentation using Aspose.Slides. Here's how you can do it:

```csharp
using Aspose.Slides;

// Create a new presentation
Presentation presentation = new Presentation();
```

## Adding Sketched Shapes

To add sketched shapes to your slides, you can use freeform shapes available in Aspose.Slides. These shapes can be customized to resemble hand-drawn sketches. Here's an example of how to add a sketched rectangle to a slide:

```csharp
// Access the first slide
ISlide slide = presentation.Slides[0];

// Define the points for the sketched rectangle
PointF[] points = new PointF[]
{
    new PointF(100, 100),
    new PointF(200, 100),
    new PointF(200, 200),
    new PointF(100, 200)
};

// Add a freeform shape to the slide
IFreeformShape freeformShape = slide.Shapes.AddFreeform(ShapeType.Rectangle, points);

// Customize the appearance of the sketched shape
freeformShape.LineFormat.Style = LineStyle.Single;
freeformShape.LineFormat.Width = 2;
freeformShape.FillFormat.FillType = FillType.Solid;
freeformShape.FillFormat.SolidFillColor.Color = Color.LightGray;
```

## Customizing Sketched Shapes

You can further customize the sketched shapes by adjusting their colors, line styles, and other properties. Experiment with different settings to achieve the desired hand-drawn effect.

## Saving and Exporting the Presentation

Once you've added sketched shapes to your presentation, you can save it and export it to various formats, such as PPTX or PDF. Here's how you can do it:

```csharp
// Save the presentation to a file
presentation.Save("SketchedShapesPresentation.pptx", SaveFormat.Pptx);
```

## Conclusion

In this tutorial, we explored how to create presentation slides with sketched shapes using Aspose.Slides for .NET. By adding sketched shapes to your slides, you can add a creative and personalized touch to your presentations, making them more engaging for your audience. Feel free to experiment with different shapes and customization options to create visually appealing slides that leave a lasting impact.

## FAQ's

### How can I download Aspose.Slides for .NET?

You can download the latest version of Aspose.Slides for .NET from their releases page [here](https://releases.aspose.com/slides/net/).

### Can I customize the appearance of sketched shapes?

Yes, you can customize the appearance of sketched shapes by adjusting their colors, line styles, and other properties using Aspose.Slides.

### Is Aspose.Slides suitable for both beginners and experienced developers?

Yes, Aspose.Slides provides a user-friendly API that is suitable for both beginners and experienced developers. It offers comprehensive documentation to help you get started.

### Can I export my presentation with sketched shapes to PDF?

Absolutely! You can export your presentation with sketched shapes to various formats, including PDF, using the exporting options provided by Aspose.Slides.

### How can I add other types of sketched shapes, such as circles or lines?

You can add other types of sketched shapes, such as circles or lines, by modifying the points and shape type in the `AddFreeform` method. Experiment with different point configurations to create the shapes you want.
