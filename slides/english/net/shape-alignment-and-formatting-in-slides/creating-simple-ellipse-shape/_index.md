---
title: Create Ellipse Shape Easily with Aspose.Slides .NET
linktitle: Creating Simple Ellipse Shape in Presentation Slides with Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to create stunning ellipse shapes in presentation slides using Aspose.Slides for .NET. Easy steps for dynamic design!
weight: 11
url: /net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create Ellipse Shape Easily with Aspose.Slides .NET

## Introduction
In the dynamic world of presentation design, incorporating shapes like ellipses can add a touch of creativity and professionalism. Aspose.Slides for .NET offers a powerful solution for manipulating presentation files programmatically. This tutorial will guide you through the process of creating a simple ellipse shape in presentation slides using Aspose.Slides for .NET.
## Prerequisites
Before diving into the tutorial, make sure you have the following prerequisites in place:
- Aspose.Slides for .NET: Ensure that you have installed the Aspose.Slides library for .NET. You can download it from the [releases page](https://releases.aspose.com/slides/net/).
- Development Environment: Set up a .NET development environment on your machine.
## Import Namespaces
In your .NET project, start by importing the necessary namespaces:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
These namespaces provide the essential classes and methods required for working with presentation slides and shapes.
## Step 1: Set Up the Presentation
Begin by creating a new presentation and accessing the first slide. Add the following code to achieve this:
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create directory if it is not already present.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// Instantiate Presentation class
using (Presentation pres = new Presentation())
{
    // Get the first slide
    ISlide sld = pres.Slides[0];
```
This code initializes a new presentation and selects the first slide for further manipulation.
## Step 2: Add Ellipse Shape
Now, let's add an ellipse shape to the slide using the `AddAutoShape` method:
```csharp
// Add autoshape of ellipse type
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
This line of code creates an ellipse shape at coordinates (50, 150) with a width of 150 units and a height of 50 units.
## Step 3: Save the Presentation
Finally, save the modified presentation to disk with a specified file name using the following code:
```csharp
// Write the PPTX file to disk
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
This step ensures that your changes are persisted, and you can view the resulting presentation with the newly added ellipse shape.
## Conclusion
Congratulations! You've successfully created a simple ellipse shape in a presentation slide using Aspose.Slides for .NET. This tutorial provides a foundational understanding of working with shapes, setting up presentations, and saving the modified files.
---
## FAQs
### Can I customize the ellipse shape further?
Yes, you can modify various properties of the ellipse shape, such as color, size, and position, to meet your specific design requirements.
### Is Aspose.Slides compatible with the latest .NET frameworks?
Yes, Aspose.Slides is regularly updated to ensure compatibility with the latest .NET frameworks.
### Where can I find more tutorials and examples for Aspose.Slides?
Visit the [documentation](https://reference.aspose.com/slides/net/) for comprehensive guides and examples.
### How can I obtain a temporary license for Aspose.Slides?
Follow the [temporary license link](https://purchase.aspose.com/temporary-license/) to request a temporary license for testing purposes.
### Need assistance or have specific questions?
Visit the [Aspose.Slides support forum](https://forum.aspose.com/c/slides/11) to get help from the community and experts.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
