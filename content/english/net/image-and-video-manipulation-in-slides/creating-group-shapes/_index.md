---
title: Creating Group Shapes in Presentation Slides with Aspose.Slides
linktitle: Creating Group Shapes in Presentation Slides with Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to create captivating presentation slides with group shapes using Aspose.Slides for .NET. Follow our step-by-step guide and source code example to easily add, group, and transform shapes, enhancing your presentations.
type: docs
weight: 11
url: /net/image-and-video-manipulation-in-slides/creating-group-shapes/
---

## Introduction to Aspose.Slides for .NET

Aspose.Slides for .NET is a comprehensive and feature-rich library that allows developers to manipulate PowerPoint presentations programmatically. Whether you want to create, modify, or convert presentation files, Aspose.Slides provides a wide range of tools and functionalities to simplify the process.

## Prerequisites

Before you start working with Aspose.Slides for .NET, make sure you have the following prerequisites in place:

- Visual Studio: Install Visual Studio on your machine.
- Aspose.Slides Library: Download and reference the Aspose.Slides library in your project. You can download it from [here](https://releases.aspose.com/slides/net/).

## Adding Aspose.Slides to Your Project

1. Download the Aspose.Slides library from the provided link.
2. Create a new project in Visual Studio or open an existing one.
3. Right-click on your project in the Solution Explorer and select "Manage NuGet Packages."
4. Choose the "Browse" tab and search for "Aspose.Slides."
5. Install the Aspose.Slides package into your project.

## Creating a New Presentation

Let's start by creating a new PowerPoint presentation using Aspose.Slides:

```csharp
using Aspose.Slides;

// Create a new presentation
Presentation presentation = new Presentation();
```

## Adding Shapes to the Slide

Next, let's add some shapes to the slide. In this example, we'll add two rectangles:

```csharp
// Access the first slide
ISlide slide = presentation.Slides[0];

// Add rectangles to the slide
IShape shape1 = slide.Shapes.AddRectangle(100, 100, 200, 100);
IShape shape2 = slide.Shapes.AddRectangle(300, 100, 150, 150);
```

## Grouping Shapes Together

Now, let's group the shapes together to manage them collectively:

```csharp
// Group shapes
IGroupShape groupShape = slide.Shapes.GroupShapes(new IShape[] { shape1, shape2 });
```

## Applying Transformations to Grouped Shapes

You can apply various transformations to the grouped shapes. For instance, let's rotate the grouped shapes by 45 degrees:

```csharp
// Rotate the group by 45 degrees
groupShape.Rotation = 45;
```

## Source Code Example

Here's the complete source code example of creating group shapes using Aspose.Slides:

```csharp
using Aspose.Slides;

namespace GroupShapesExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a new presentation
            Presentation presentation = new Presentation();

            // Access the first slide
            ISlide slide = presentation.Slides[0];

            // Add rectangles to the slide
            IShape shape1 = slide.Shapes.AddRectangle(100, 100, 200, 100);
            IShape shape2 = slide.Shapes.AddRectangle(300, 100, 150, 150);

            // Group shapes
            IGroupShape groupShape = slide.Shapes.GroupShapes(new IShape[] { shape1, shape2 });

            // Rotate the group by 45 degrees
            groupShape.Rotation = 45;

            // Save the presentation
            presentation.Save("GroupShapesExample.pptx", SaveFormat.Pptx);
        }
    }
}
```

## Conclusion

In this tutorial, you've learned how to create group shapes in presentation slides using Aspose.Slides for .NET. The library provides a straightforward way to add shapes, group them together, and apply transformations to enhance your presentations dynamically.

## FAQ's

### How do I install Aspose.Slides for .NET?

You can download the Aspose.Slides library from the provided link: [here](https://releases.aspose.com/slides/net/). Once downloaded, you can add it to your project using NuGet packages.

### Can I apply different transformations to grouped shapes?

Yes, you can apply various transformations like rotation, scaling, and positioning to the grouped shapes, allowing you to customize the visual appearance of your slides.

### Is Aspose.Slides suitable for both creating and modifying presentations?

Absolutely! Aspose.Slides for .NET is a versatile library that supports creating, modifying, and converting presentation files. It provides a wide range of features to cater to different needs.

### Can I group shapes of different types together?

Yes, you can group shapes of different types, such as rectangles, circles, and text boxes, together using the `GroupShapes` method. This enables you to manage and manipulate them collectively.

### Is Aspose.Slides suitable only for .NET applications?

Yes, Aspose.Slides is specifically designed for .NET applications. However, there are versions available for other programming languages as well, such as Java.
