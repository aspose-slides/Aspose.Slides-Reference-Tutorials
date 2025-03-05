---
title: Adding Stretch Offset to Left in PowerPoint with Aspose.Slide
linktitle: Adding Stretch Offset to Left for Picture Frame in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to enhance PowerPoint presentations using Aspose.Slides for .NET. Follow our step-by-step guide to add stretch offset to left for picture frames.
type: docs
weight: 14
url: /net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/
---
## Introduction
Aspose.Slides for .NET is a powerful library that empowers developers to manipulate PowerPoint presentations with ease. In this tutorial, we'll explore the process of adding a stretch offset to the left for a picture frame using Aspose.Slides for .NET. Follow this step-by-step guide to enhance your skills in working with images and shapes within PowerPoint presentations.
## Prerequisites
Before diving into the tutorial, make sure you have the following prerequisites in place:
- Aspose.Slides for .NET: Ensure you have the library installed. If not, download it from the [Aspose.Slides for .NET documentation](https://reference.aspose.com/slides/net/).
- Development Environment: Have a working development environment with .NET capabilities.
## Import Namespaces
Begin by importing the necessary namespaces in your .NET project:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Step 1: Set Up Your Project
Create a new project or open an existing one. Ensure that you have the Aspose.Slides library referenced in your project.
## Step 2: Create Presentation Object
Instantiate the `Presentation` class, representing the PPTX file:
```csharp
using (Presentation pres = new Presentation())
{
    // Your code for subsequent steps will go here.
}
```
## Step 3: Get the First Slide
Retrieve the first slide from the presentation:
```csharp
ISlide slide = pres.Slides[0];
```
## Step 4: Instantiate the Image
Load the image you want to use:
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## Step 5: Add Rectangle AutoShape
Create an AutoShape of Rectangle type:
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Step 6: Set Fill Type and Picture Fill Mode
Configure the shape's fill type and picture fill mode:
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## Step 7: Set Image to Fill the Shape
Specify the image to fill the shape:
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## Step 8: Specify Stretch Offsets
Define the image offsets from the corresponding edges of the shape's bounding box:
```csharp
aShape.FillFormat.PictureFillFormat.StretchOffsetLeft = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetRight = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetTop = -20;
aShape.FillFormat.PictureFillFormat.StretchOffsetBottom = -10;
```
## Step 9: Save the Presentation
Write the PPTX file to disk:
```csharp
pres.Save(dataDir + "StretchOffsetLeftForPictureFrame_out.pptx", SaveFormat.Pptx);
```
Congratulations! You've successfully added a stretch offset to the left for a picture frame using Aspose.Slides for .NET.
## Conclusion
In this tutorial, we explored the process of manipulating picture frames in PowerPoint presentations using Aspose.Slides for .NET. By following the step-by-step guide, you've gained insights into working with images, shapes, and offsets.
## Frequently Asked Questions
### Q: Can I apply stretch offsets to other shapes besides rectangles?
A: While this tutorial focuses on rectangles, stretch offsets can be applied to various shapes supported by Aspose.Slides.
### Q: How can I adjust the stretch offsets for different effects?
A: Experiment with different offset values to achieve the desired visual impact. Fine-tune the values to suit your specific requirements.
### Q: Is Aspose.Slides compatible with the latest .NET framework?
A: Aspose.Slides is regularly updated to ensure compatibility with the latest .NET framework versions.
### Q: Where can I find additional examples and resources for Aspose.Slides?
A: Explore the [Aspose.Slides documentation](https://reference.aspose.com/slides/net/) for comprehensive examples and guidance.
### Q: Can I apply multiple stretch offsets to a single shape?
A: Yes, you can combine multiple stretch offsets to achieve complex and customized visual effects.
