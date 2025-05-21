---
title: Reshaping Presentation Slides with Aspose.Slides for .NET
linktitle: Changing Order of Shapes in Presentation Slides using Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to reshape presentation slides using Aspose.Slides for .NET. Follow this step-by-step guide to reorder shapes and enhance visual appeal.
weight: 26
url: /net/shape-effects-and-manipulation-in-slides/changing-order-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Reshaping Presentation Slides with Aspose.Slides for .NET

## Introduction
Creating visually appealing presentation slides is a crucial aspect of effective communication. Aspose.Slides for .NET empowers developers to manipulate slides programmatically, offering a wide range of functionalities. In this tutorial, we'll delve into the process of changing the order of shapes in presentation slides using Aspose.Slides for .NET.
## Prerequisites
Before we embark on this journey, make sure you have the following prerequisites in place:
- Aspose.Slides for .NET: Ensure that you have the Aspose.Slides library integrated into your .NET project. If not, you can download it from the [releases page](https://releases.aspose.com/slides/net/).
- Development Environment: Set up a working development environment with Visual Studio or any other .NET development tool.
- Basic Understanding of C#: Familiarize yourself with the basics of C# programming language.
## Import Namespaces
In your C# project, include the necessary namespaces to access the Aspose.Slides functionality:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Step 1: Set Up Your Project
Create a new project in Visual Studio or your preferred .NET development environment. Ensure that Aspose.Slides for .NET is referenced in your project.
## Step 2: Load the Presentation
```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## Step 3: Access the Slide and Shapes
```csharp
ISlide slide = presentation.Slides[0];
```
## Step 4: Add a New Shape
```csharp
IAutoShape shp3 = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.FillFormat.FillType = FillType.NoFill;
shp3.AddTextFrame(" ");
```
## Step 5: Modify the Text in the Shape
```csharp
ITextFrame txtFrame = shp3.TextFrame;
IParagraph para = txtFrame.Paragraphs[0];
IPortion portion = para.Portions[0];
portion.Text = "Watermark Text Watermark Text Watermark Text";
```
## Step 6: Add Another Shape
```csharp
shp3 = slide.Shapes.AddAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## Step 7: Change the Order of Shapes
```csharp
slide.Shapes.Reorder(2, shp3);
```
## Step 8: Save the Modified Presentation
```csharp
presentation.Save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
This completes the step-by-step guide for changing the order of shapes in presentation slides using Aspose.Slides for .NET.
## Conclusion
Aspose.Slides for .NET simplifies the task of manipulating presentation slides programmatically. By following this tutorial, you've learned how to reorder shapes, allowing you to enhance the visual appeal of your presentations.
## FAQs
### Q: Can I use Aspose.Slides for .NET in both Windows and Linux environments?
A: Yes, Aspose.Slides for .NET is compatible with both Windows and Linux environments.
### Q: Are there any licensing considerations for using Aspose.Slides in a commercial project?
A: Yes, you can find licensing details and purchase options on the [Aspose.Slides purchase page](https://purchase.aspose.com/buy).
### Q: Is there a free trial available for Aspose.Slides for .NET?
A: Yes, you can explore the features with the [free trial](https://releases.aspose.com/) available on the Aspose.Slides website.
### Q: Where can I find support or ask questions related to Aspose.Slides for .NET?
A: Visit the [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) to get support and engage with the community.
### Q: How can I obtain a temporary license for Aspose.Slides for .NET?
A: You can acquire a [temporary license](https://purchase.aspose.com/temporary-license/) for evaluation purposes.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
