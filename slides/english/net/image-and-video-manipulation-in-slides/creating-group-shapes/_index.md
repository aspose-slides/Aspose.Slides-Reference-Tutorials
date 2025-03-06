---
title: Aspose.Slides - Creating Group Shapes in .NET
linktitle: Creating Group Shapes in Presentation Slides with Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to create group shapes in PowerPoint with Aspose.Slides for .NET. Follow our step-by-step guide for visually appealing presentations.
weight: 11
url: /net/image-and-video-manipulation-in-slides/creating-group-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
If you're looking to enhance the visual appeal of your presentation slides and organize content more efficiently, incorporating group shapes is a powerful solution. Aspose.Slides for .NET provides a seamless way to create and manipulate group shapes in your PowerPoint presentations. In this tutorial, we'll walk through the process of creating group shapes using Aspose.Slides, breaking it down into easy-to-follow steps.
## Prerequisites
Before we dive into the tutorial, make sure you have the following:
- Aspose.Slides for .NET: Ensure that you have the Aspose.Slides library installed. You can download it from the [website](https://releases.aspose.com/slides/net/).
- Development Environment: Set up a working environment with a .NET-compatible IDE, such as Visual Studio.
- Basic Knowledge of C#: Familiarize yourself with the basics of C# programming language.
## Import Namespaces
In your C# project, begin by importing the necessary namespaces:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Step 1: Instantiate Presentation Class

Create an instance of the `Presentation` class and specify the directory where your documents are stored:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // Continue with the following steps within this using block
}
```

## Step 2: Access the First Slide

Retrieve the first slide from the presentation:

```csharp
ISlide sld = pres.Slides[0];
```

## Step 3: Accessing the Shape Collection

Access the collection of shapes on the slide:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## Step 4: Adding a Group Shape

Add a group shape to the slide:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## Step 5: Adding Shapes Inside the Group Shape

Populate the group shape with individual shapes:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## Step 6: Adding Group Shape Frame

Define the frame for the entire group shape:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## Step 7: Save the Presentation

Save the modified presentation to your specified directory:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Repeat these steps in your C# application to successfully create group shapes in your presentation slides using Aspose.Slides.

## Conclusion
In this tutorial, we explored the process of creating group shapes with Aspose.Slides for .NET. By following these steps, you can enhance the visual appeal and organization of your PowerPoint presentations.
## Frequently Asked Questions
### Is Aspose.Slides compatible with the latest version of .NET?
Yes, Aspose.Slides is regularly updated to support the latest .NET versions. Check the [documentation](https://reference.aspose.com/slides/net/) for compatibility details.
### Can I try Aspose.Slides before purchasing?
Absolutely! You can download a free trial version [here](https://releases.aspose.com/).
### Where can I find support for Aspose.Slides-related queries?
Visit the Aspose.Slides [forum](https://forum.aspose.com/c/slides/11) for community support and discussions.
### How do I obtain a temporary license for Aspose.Slides?
You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
### Where can I purchase a full license for Aspose.Slides?
You can buy a license from the [purchase page](https://purchase.aspose.com/buy).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
