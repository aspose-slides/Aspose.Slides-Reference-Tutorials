---
title: Create Stunning Sketched Shapes with Aspose.Slides
linktitle: Creating Sketched Shapes in Presentation Slides with Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to add creative sketched shapes to your presentation slides using Aspose.Slides for .NET. Enhance visual appeal effortlessly!
weight: 13
url: /net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create Stunning Sketched Shapes with Aspose.Slides

## Introduction
Welcome to our step-by-step guide on creating sketched shapes in presentation slides using Aspose.Slides for .NET. If you want to add a touch of creativity to your presentations, sketched shapes provide a unique and hand-drawn aesthetic. In this tutorial, we will walk you through the process, breaking it down into simple steps to ensure a smooth experience.
## Prerequisites
Before we dive into the tutorial, make sure you have the following prerequisites in place:
- Aspose.Slides for .NET: Ensure you have the Aspose.Slides library for .NET installed. You can download it [here](https://releases.aspose.com/slides/net/).
- Development Environment: Set up a .NET development environment with your preferred IDE.
## Import Namespaces
Start by importing the necessary namespaces in your .NET project. This step ensures that you have access to the classes and functionalities required for working with Aspose.Slides.
```csharp
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## Step 1: Set Up the Project
Begin by creating a new .NET project or opening an existing one. Make sure to include Aspose.Slides in your project references.
## Step 2: Initialize Aspose.Slides
Initialize Aspose.Slides by adding the following code snippet. This sets up the presentation and specifies the output paths for the presentation file and the thumbnail image.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // Continue to the next steps...
}
```
## Step 3: Add Sketched Shape
Now, let's add a sketched shape to the slide. In this example, we'll add a rectangle with a freehand sketch effect.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Transform shape to sketch of a freehand style
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## Step 4: Generate Thumbnail
Generate a thumbnail of the slide to visualize the sketched shape. Save the thumbnail as a PNG file.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Step 5: Save Presentation
Save the presentation file with the sketched shape.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
That's it! You've successfully created a presentation with sketched shapes using Aspose.Slides for .NET.
## Conclusion
Adding sketched shapes to your presentation slides can enhance the visual appeal and engage your audience. With Aspose.Slides for .NET, the process becomes straightforward, allowing you to unleash your creativity effortlessly.
## FAQs
### 1. Can I customize the sketched effect?
Yes, Aspose.Slides for .NET provides various customization options for sketched effects. Refer to the [documentation](https://reference.aspose.com/slides/net/) for detailed information.
### 2. Is there a free trial available?
Certainly! You can explore a free trial of Aspose.Slides for .NET [here](https://releases.aspose.com/).
### 3. Where can I get support?
For any assistance or queries, visit the [Aspose.Slides forum](https://forum.aspose.com/c/slides/11).
### 4. How can I purchase Aspose.Slides for .NET?
To purchase Aspose.Slides for .NET, visit the [purchase page](https://purchase.aspose.com/buy).
### 5. Do you offer temporary licenses?
Yes, temporary licenses are available [here](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
