---
title: Create Stunning Gradients in PowerPoint with Aspose.Slides
linktitle: Filling Shapes with Gradient in Presentation Slides using Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Enhance your presentations with Aspose.Slides for .NET! Learn the step-by-step process of filling shapes with gradients. Download your free trial now!
weight: 21
url: /net/image-and-video-manipulation-in-slides/filling-shapes-gradient/
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Create Stunning Gradients in PowerPoint with Aspose.Slides

## Introduction
Crafting visually captivating presentation slides is essential to capture and maintain your audience's attention. In this tutorial, we'll walk you through the process of enhancing your slides by filling an ellipse shape with a gradient using Aspose.Slides for .NET.
## Prerequisites
Before we begin, ensure you have the following:
- Basic knowledge of the C# programming language.
- Visual Studio installed on your machine.
- Aspose.Slides for .NET library. Download it [here](https://releases.aspose.com/slides/net/).
- A project directory to organize your files.
## Import Namespaces
In your C# project, include the required namespaces for Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Step 1: Create a Presentation
Begin by creating a new presentation using the Aspose.Slides library:
```csharp
string dataDir = "Your Documents Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Your code goes here...
}
```
## Step 2: Add an Ellipse Shape
Insert an ellipse shape into the first slide of your presentation:
```csharp
ISlide sld = pres.Slides[0];
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 75, 150);
```
## Step 3: Apply Gradient Formatting
Specify that the shape should be filled with a gradient and define the gradient characteristics:
```csharp
shp.FillFormat.FillType = FillType.Gradient;
shp.FillFormat.GradientFormat.GradientShape = GradientShape.Linear;
shp.FillFormat.GradientFormat.GradientDirection = GradientDirection.FromCorner2;
```
## Step 4: Add Gradient Stops
Define the colors and positions of the gradient stops:
```csharp
shp.FillFormat.GradientFormat.GradientStops.Add((float)1.0, PresetColor.Purple);
shp.FillFormat.GradientFormat.GradientStops.Add((float)0, PresetColor.Red);
```
## Step 5: Save the Presentation
Save your presentation with the newly added gradient-filled shape:
```csharp
pres.Save(dataDir + "EllipseShpGrad_out.pptx", SaveFormat.Pptx);
```
Repeat these steps in your C# code, ensuring proper sequence and parameter values. This will result in a presentation file with a visually appealing ellipse shape filled with a gradient.
## Conclusion
With Aspose.Slides for .NET, you can effortlessly elevate the visual aesthetics of your presentations. By following this guide, you've learned how to fill shapes with gradients, giving your slides a professional and engaging look.
---
## FAQs
### Q: Can I apply gradients to shapes other than ellipses?
A: Certainly! Aspose.Slides for .NET supports gradient filling for various shapes such as rectangles, polygons, and more.
### Q: Where can I find additional examples and detailed documentation?
A: Explore the [Aspose.Slides for .NET documentation](https://reference.aspose.com/slides/net/) for comprehensive guides and examples.
### Q: Is there a free trial available for Aspose.Slides for .NET?
A: Yes, you can access a free trial [here](https://releases.aspose.com/).
### Q: How can I get support for Aspose.Slides for .NET?
A: Seek assistance and engage with the community on the [Aspose.Slides forum](https://forum.aspose.com/c/slides/11).
### Q: Can I purchase a temporary license for Aspose.Slides for .NET?
A: Certainly, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
