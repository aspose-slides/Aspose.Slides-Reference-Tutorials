---
title: Mastering 3D Rotation in Presentations with Aspose.Slides for .NET
linktitle: Applying 3D Rotation Effect on Shapes in Presentation Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Enhance your presentations with Aspose.Slides for .NET! Learn to apply 3D rotation effects to shapes in this tutorial. Create dynamic and visually stunning presentation.
type: docs
weight: 23
url: /net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/
---
## Introduction
Creating engaging and dynamic presentation slides is a key aspect of effective communication. Aspose.Slides for .NET provides a powerful set of tools to enhance your presentations, including the ability to apply 3D rotation effects to shapes. In this tutorial, we will walk through the process of applying a 3D rotation effect to shapes in presentation slides using Aspose.Slides for .NET.
## Prerequisites
Before we dive into the tutorial, make sure you have the following prerequisites in place:
- Aspose.Slides for .NET: Ensure that you have the Aspose.Slides library for .NET installed. You can download it from the [website](https://releases.aspose.com/slides/net/).
- Development Environment: Set up a .NET development environment, such as Visual Studio, to write and run your code.
## Import Namespaces
In your .NET project, import the necessary namespaces to leverage the functionality of Aspose.Slides. Include the following namespaces at the beginning of your code:
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Step 1: Set up Your Project
Create a new project in your preferred .NET development environment. Ensure that you have added the Aspose.Slides reference to your project.
## Step 2: Initialize Presentation
Instantiate a Presentation class to begin working with slides:
```csharp
Presentation pres = new Presentation();
```
## Step 3: Add AutoShape
Add an AutoShape to the slide, specifying its type, position, and dimensions:
```csharp
IShape autoShape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
## Step 4: Set 3D Rotation Effect
Configure the 3D rotation effect for the AutoShape:
```csharp
autoShape.ThreeDFormat.Depth = 6;
autoShape.ThreeDFormat.Camera.SetRotation(40, 35, 20);
autoShape.ThreeDFormat.Camera.CameraType = CameraPresetType.IsometricLeftUp;
autoShape.ThreeDFormat.LightRig.LightType = LightRigPresetType.Balanced;
```
## Step 5: Save the Presentation
Save the modified presentation with the applied 3D rotation effect:
```csharp
pres.Save("Your Document Directory" + "Rotation_out.pptx", SaveFormat.Pptx);
```
## Step 6: Repeat for Other Shapes
If you have additional shapes, repeat Steps 3 to 5 for each shape.
## Conclusion
Adding 3D rotation effects to shapes in your presentation slides can significantly enhance their visual appeal. With Aspose.Slides for .NET, this process becomes straightforward, allowing you to create captivating presentations.
## FAQs
### Can I apply 3D rotation to text boxes in Aspose.Slides for .NET?
Yes, you can apply 3D rotation effects to various shapes, including text boxes, using Aspose.Slides.
### Is there a trial version of Aspose.Slides for .NET available?
Yes, you can access the trial version [here](https://releases.aspose.com/).
### How can I get support for Aspose.Slides for .NET?
Visit the [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) for community support and discussions.
### Can I purchase a temporary license for Aspose.Slides for .NET?
Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
### Where can I find detailed documentation for Aspose.Slides for .NET?
The documentation is available [here](https://reference.aspose.com/slides/net/).
