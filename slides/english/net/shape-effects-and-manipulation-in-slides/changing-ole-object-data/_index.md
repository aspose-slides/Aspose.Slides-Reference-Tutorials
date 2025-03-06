---
title: Changing OLE Object Data in Presentation with Aspose.Slides
linktitle: Changing OLE Object Data in Presentation with Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Explore the power of Aspose.Slides for .NET in changing OLE object data effortlessly. Enhance your presentations with dynamic content. 
weight: 25
url: /net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Changing OLE Object Data in Presentation with Aspose.Slides

## Introduction
Creating dynamic and interactive PowerPoint presentations is a common requirement in today's digital world. One powerful tool for achieving this is Aspose.Slides for .NET, a robust library that allows developers to manipulate and enhance PowerPoint presentations programmatically. In this tutorial, we'll delve into the process of changing OLE (Object Linking and Embedding) object data within presentation slides using Aspose.Slides.
## Prerequisites
Before you start working with Aspose.Slides for .NET, ensure that you have the following prerequisites in place:
1. Development Environment: Set up a development environment with .NET installed.
2. Aspose.Slides Library: Download and install the Aspose.Slides for .NET library. You can find the library [here](https://releases.aspose.com/slides/net/).
3. Basic Understanding: Familiarize yourself with basic concepts of C# programming and PowerPoint presentations.
## Import Namespaces
In your C# project, import the necessary namespaces to use Aspose.Slides functionalities:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## Step 1: Set up Your Project
Begin by creating a new C# project and importing the Aspose.Slides library. Make sure your project is configured correctly, and you have the required dependencies in place.
## Step 2: Access Presentation and Slide
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## Step 3: Locate OLE Object
Traverse through all shapes in the slide to find the OLE object frame:
```csharp
OleObjectFrame ole = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is OleObjectFrame)
    {
        ole = (OleObjectFrame)shape;
    }
}
```
## Step 4: Read and Modify Workbook Data
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // Reading object data in Workbook
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // Modifying the workbook data
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // Changing Ole frame object data
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## Step 5: Save the Presentation
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## Conclusion
By following these steps, you can seamlessly change OLE object data within presentation slides using Aspose.Slides for .NET. This opens up a world of possibilities for creating dynamic and customized presentations tailored to your specific needs.
## Frequently Asked Questions
### What is Aspose.Slides for .NET?
Aspose.Slides for .NET is a powerful library that enables developers to work with PowerPoint presentations programmatically, allowing for easy manipulation and enhancement.
### Where can I find the Aspose.Slides documentation?
The documentation for Aspose.Slides for .NET can be found [here](https://reference.aspose.com/slides/net/).
### How do I download Aspose.Slides for .NET?
You can download the library from the release page [here](https://releases.aspose.com/slides/net/).
### Is there a free trial available for Aspose.Slides?
Yes, you can access the free trial [here](https://releases.aspose.com/).
### Where can I get support for Aspose.Slides for .NET?
For support and discussions, visit the [Aspose.Slides forum](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
