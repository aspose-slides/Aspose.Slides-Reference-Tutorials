---
title: Hide Shapes in PowerPoint with Aspose.Slides .NET Tutorial
linktitle: Hiding Shapes in Presentation Slides with Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to hide shapes in PowerPoint slides using Aspose.Slides for .NET. Customize presentations programmatically with this step-by-step guide.
weight: 21
url: /net/shape-geometry-and-positioning-in-slides/hiding-shapes/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
In the dynamic world of presentations, customization is key. Aspose.Slides for .NET provides a powerful solution for manipulating PowerPoint presentations programmatically. One common requirement is the ability to hide specific shapes within a slide. This tutorial will guide you through the process of hiding shapes in presentation slides using Aspose.Slides for .NET.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites in place:
- Aspose.Slides for .NET: Make sure you have the Aspose.Slides library installed. You can download it [here](https://releases.aspose.com/slides/net/).
- Development Environment: Set up your preferred development environment for .NET.
- Basic Knowledge of C#: Familiarize yourself with C# as the code examples provided are in this language.
## Import Namespaces
To start working with Aspose.Slides, import the necessary namespaces in your C# project. This ensures that you have access to the required classes and methods.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Now, let's break down the example code into multiple steps for a clear and concise understanding.
## Step 1: Set Up Your Project
Create a new C# project and make sure to include the Aspose.Slides library.
## Step 2: Create a Presentation
Instantiate the `Presentation` class, representing the PowerPoint file. Add a slide and get a reference to it.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## Step 3: Add Shapes to the Slide
Add autoshapes to the slide, such as rectangles and moons, with specific dimensions.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Step 4: Hide Shapes Based on Alternative Text
Specify an alternative text and hide shapes that match this text.
```csharp
String alttext = "User Defined";
int iCount = sld.Shapes.Count;
for (int i = 0; i < iCount; i++)
{
    AutoShape ashp = (AutoShape)sld.Shapes[i];
    if (String.Compare(ashp.AlternativeText, alttext, StringComparison.Ordinal) == 0)
    {
        ashp.Hidden = true;
    }
}
```
## Step 5: Save the Presentation
Save the modified presentation to disk in PPTX format.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Conclusion
Congratulations! You've successfully hidden shapes in your presentation using Aspose.Slides for .NET. This opens up a world of possibilities for creating dynamic and customized slides programmatically.
---
## FAQs
### Is Aspose.Slides compatible with .NET Core?
Yes, Aspose.Slides supports .NET Core, providing flexibility in your development environment.
### Can I hide shapes based on conditions other than alternative text?
Absolutely! You can customize the hiding logic based on various attributes like shape type, color, or position.
### Where can I find additional Aspose.Slides documentation?
Explore the documentation [here](https://reference.aspose.com/slides/net/) for in-depth information and examples.
### Are temporary licenses available for Aspose.Slides?
Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/) for testing purposes.
### How can I get community support for Aspose.Slides?
Join the Aspose.Slides community on the [forum](https://forum.aspose.com/c/slides/11) for discussions and assistance.

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
