---
title: Adding Stretch Offset for Image Fill in PowerPoint Presentations
linktitle: Adding Stretch Offset for Image Fill in Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to enhance PowerPoint presentations with Aspose.Slides for .NET. Follow a step-by-step guide to add a stretch offset for image fill.
type: docs
weight: 18
url: /net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---
## Introduction
In the dynamic world of presentations, visuals play a pivotal role in capturing the audience's attention. Aspose.Slides for .NET empowers developers to enhance their PowerPoint presentations by providing a robust set of features. One such feature is the ability to add a stretch offset for image fill, allowing for creative and visually appealing slides.
## Prerequisites
Before diving into the tutorial, make sure you have the following prerequisites in place:
1. Aspose.Slides for .NET Library: Download and install the library from the [Aspose.Slides for .NET documentation](https://reference.aspose.com/slides/net/).
2. Development Environment: Ensure that you have a working .NET development environment set up.
Now, let's get started with the step-by-step guide.
## Import Namespaces
Firstly, import the necessary namespaces to leverage Aspose.Slides functionality within your .NET application.
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Step 1: Set Up Your Project
Create a new .NET project in your preferred development environment. Ensure that Aspose.Slides for .NET is properly referenced.
## Step 2: Initialize Presentation Class
Instantiate the `Presentation` class to represent the PowerPoint file.
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Your code goes here
}
```
## Step 3: Get the First Slide
Retrieve the first slide from the presentation to work with.
```csharp
ISlide sld = pres.Slides[0];
```
## Step 4: Instantiate ImageEx Class
Create an instance of the `ImageEx` class to handle the image you want to add to the slide.
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## Step 5: Add Picture Frame
Utilize the `AddPictureFrame` method to add a picture frame to the slide. Specify the dimensions and position of the frame.
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## Step 6: Save the Presentation
Save the modified presentation to disk.
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
That's it! You have successfully added a stretch offset for image fill in slides using Aspose.Slides for .NET.
## Conclusion
Enhancing your PowerPoint presentations is now easier than ever with Aspose.Slides for .NET. By following this tutorial, you've learned how to incorporate stretch offset for image fill, bringing a new level of creativity to your slides.
## FAQs
### Can I use Aspose.Slides for .NET in my web applications?
Yes, Aspose.Slides for .NET is suitable for both desktop and web applications.
### Is there a free trial available for Aspose.Slides for .NET?
Yes, you can download a free trial from [here](https://releases.aspose.com/).
### How can I get support for Aspose.Slides for .NET?
Visit the [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) for community support.
### Where can I find the complete documentation for Aspose.Slides for .NET?
Refer to the [documentation](https://reference.aspose.com/slides/net/) for detailed information.
### Can I purchase Aspose.Slides for .NET?
Yes, you can buy the product [here](https://purchase.aspose.com/buy).
