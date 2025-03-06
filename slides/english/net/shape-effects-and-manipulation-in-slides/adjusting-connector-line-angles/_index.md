---
title: Adjust Connector Line Angles in PowerPoint with Aspose.Slides
linktitle: Adjusting Connector Line Angles in Presentation Slides using Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to adjust connector line angles in PowerPoint slides using Aspose.Slides for .NET. Enhance your presentations with precision and ease.
weight: 28
url: /net/shape-effects-and-manipulation-in-slides/adjusting-connector-line-angles/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
Creating visually appealing presentation slides often involves precise adjustments to connector lines. In this tutorial, we'll explore how to adjust connector line angles in presentation slides using Aspose.Slides for .NET. Aspose.Slides is a powerful library that allows developers to work with PowerPoint files programmatically, providing extensive capabilities for creating, modifying, and manipulating presentations.
## Prerequisites
Before we dive into the tutorial, ensure that you have the following:
- Basic knowledge of C# programming language.
- Visual Studio or any other C# development environment installed.
- Aspose.Slides for .NET library. You can download it [here](https://releases.aspose.com/slides/net/).
- A PowerPoint presentation file with connector lines that you want to adjust.
## Import Namespaces
To get started, make sure to include the necessary namespaces in your C# code:
```csharp
using System.IO;
using Aspose.Slides;
using System;
```
## Step 1: Set Up Your Project
Create a new C# project in Visual Studio and install the Aspose.Slides NuGet package. Set up the project structure with a reference to the Aspose.Slides library.
## Step 2: Load the Presentation
```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
Load your PowerPoint presentation file into the `Presentation` object. Replace "Your Document Directory" with the actual path to your file.
## Step 3: Access the Slide and Shapes
```csharp
Slide slide = (Slide)pres.Slides[0];
Shape shape;
```
Access the first slide in the presentation and initialize a variable to represent shapes on the slide.
## Step 4: Iterate Through Shapes
```csharp
for (int i = 0; i < slide.Shapes.Count; i++)
{
    // Code for handling connector lines
}
```
Loop through each shape on the slide to identify and process connector lines.
## Step 5: Adjust Connector Line Angles
```csharp
double dir = 0.0;
shape = (Shape)slide.Shapes[i];
if (shape is AutoShape)
{
    // Code for handling AutoShapes
}
else if (shape is Connector)
{
    // Code for handling Connectors
}
Console.WriteLine(dir);
```
Identify whether the shape is an AutoShape or a Connector, and adjust the connector line angles using the provided `getDirection` method.
## Step 6: Define the `getDirection` Method
```csharp
public static double getDirection(float w, float h, bool flipH, bool flipV)
{
    // Code for calculating direction
	float endLineX = w * (flipH ? -1 : 1);
	float endLineY = h * (flipV ? -1 : 1);
	float endYAxisX = 0;
	float endYAxisY = h;
	double angle = (Math.Atan2(endYAxisY, endYAxisX) - Math.Atan2(endLineY, endLineX));
	if (angle < 0) angle += 2 * Math.PI;
    return angle * 180.0 / Math.PI;
}
```
Implement the `getDirection` method to calculate the angle of the connector line based on its dimensions and orientation.
## Conclusion
With these steps, you can programmatically adjust connector line angles in your PowerPoint presentation using Aspose.Slides for .NET. This tutorial provides a foundation for enhancing the visual appeal of your slides.
## FAQs
### Is Aspose.Slides suitable for both Windows and web applications?
Yes, Aspose.Slides can be used in both Windows and web applications.
### Can I download a free trial of Aspose.Slides before purchasing?
Yes, you can download a free trial [here](https://releases.aspose.com/).
### Where can I find comprehensive documentation for Aspose.Slides for .NET?
The documentation is available [here](https://reference.aspose.com/slides/net/).
### How can I obtain a temporary license for Aspose.Slides?
You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
### Is there a support forum for Aspose.Slides?
Yes, you can visit the support forum [here](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
