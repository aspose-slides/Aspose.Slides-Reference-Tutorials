---
title: Creating Simple Ellipse Shape in Presentation Slides with Aspose.Slides
linktitle: Creating Simple Ellipse Shape in Presentation Slides with Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to create a simple ellipse shape in presentation slides using Aspose.Slides for .NET. This step-by-step guide provides source code and instructions for adding, customizing, and saving ellipse shapes.
type: docs
weight: 11
url: /net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---

## Introduction to Creating Simple Ellipse Shape in Presentation Slides

If you're looking to enhance your presentation slides by adding visually appealing shapes, Aspose.Slides for .NET provides a powerful solution to accomplish this. In this step-by-step guide, we will walk you through the process of creating a simple ellipse shape in your presentation slides using Aspose.Slides for .NET.

## Prerequisites

Before we begin, make sure you have the following prerequisites in place:

- Visual Studio or any other .NET development environment installed.
- Aspose.Slides for .NET library. You can download it from [here](https://releases.aspose.com/slides/net/).

## Setting Up Your Project

1. Create a new Visual Studio project or open an existing one.
2. Add a reference to the Aspose.Slides for .NET library in your project.

## Creating a Presentation

To get started, let's create a new presentation where we'll add our ellipse shape.

```csharp
using Aspose.Slides;

// Create a new presentation
Presentation presentation = new Presentation();
```

## Adding an Ellipse Shape

Now that we have our presentation ready, let's add an ellipse shape to a slide.

```csharp
// Access the first slide of the presentation
ISlide slide = presentation.Slides[0];

// Define ellipse dimensions and position
float x = 100;   // X-coordinate
float y = 100;   // Y-coordinate
float width = 200;  // Width
float height = 100; // Height

// Add the ellipse shape to the slide
IAutoShape ellipseShape = slide.Shapes.AddAutoShape(ShapeType.Ellipse, x, y, width, height);
```

## Customizing the Ellipse

You can customize the appearance of the ellipse shape using various properties.

```csharp
// Set the fill color of the ellipse
ellipseShape.FillFormat.SolidFillColor.Color = Color.Blue;

// Set the outline color and width
ellipseShape.LineFormat.FillFormat.SolidFillColor.Color = Color.Red;
ellipseShape.LineFormat.Width = 2;

// Add a text frame to the ellipse
ITextFrame textFrame = ellipseShape.TextFrame;
textFrame.Text = "Hello, Aspose.Slides!";
```

## Saving the Presentation

After adding and customizing the ellipse shape, it's time to save the presentation.

```csharp
// Save the presentation
presentation.Save("EllipsePresentation.pptx", SaveFormat.Pptx);
```

## Conclusion

Congratulations! You've successfully created a simple ellipse shape in your presentation slides using Aspose.Slides for .NET. This guide covered the process of setting up your project, creating a presentation, adding an ellipse shape, customizing its appearance, and saving the final presentation.

## FAQ's

### How can I change the position of the ellipse shape?

You can modify the `x` and `y` coordinates when adding the ellipse shape to adjust its position on the slide.

### Can I change the color of the ellipse's outline?

Yes, you can set the outline color using the `LineFormat.FillFormat.SolidFillColor.Color` property.

### Is it possible to add text inside the ellipse?

Absolutely! You can add text to the ellipse shape using the `TextFrame.Text` property.

### What other shapes can I create using Aspose.Slides for .NET?

Aspose.Slides for .NET supports various shapes, including rectangles, lines, arrows, and more.

### Where can I find more information about Aspose.Slides for .NET?

For detailed documentation and examples, refer to the [Aspose.Slides for .NET documentation](https://reference.aspose.com/slides/net/).
