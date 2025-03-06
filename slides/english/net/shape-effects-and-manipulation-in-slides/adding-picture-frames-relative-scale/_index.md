---
title: Adding Picture Frames Tutorial with Aspose.Slides .NET
linktitle: Adding Picture Frames with Relative Scale Height in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn to add picture frames with relative scale height in Aspose.Slides for .NET. Follow this step-by-step guide for seamless presentations.
weight: 17
url: /net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
Aspose.Slides for .NET is a powerful library that allows developers to create, manipulate, and convert PowerPoint presentations in their .NET applications effortlessly. In this tutorial, we'll dive into the process of adding picture frames with relative scale height using Aspose.Slides for .NET. Follow along with this step-by-step guide to enhance your presentation-building skills.
## Prerequisites
Before we start, ensure you have the following:
- Basic knowledge of C# programming language.
- Visual Studio or any other preferred C# development environment installed.
- Aspose.Slides for .NET library added to your project.
## Import Namespaces
Begin by importing the necessary namespaces into your C# code. This step ensures that you have access to the classes and functionalities provided by the Aspose.Slides library.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Step 1: Set Up Your Project
Start by creating a new C# project in your preferred development environment. Make sure to add the Aspose.Slides for .NET library to your project by referencing it.
## Step 2: Load Presentation and Image
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    // Load Image to be added in the presentation image collection
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
In this step, we create a new presentation object and load the image that we want to add to the presentation.
## Step 3: Add Picture Frame to Slide
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
Now, add a picture frame to the first slide of the presentation. Adjust the parameters such as shape type, position, and dimensions according to your requirements.
## Step 4: Set Relative Scale Width and Height
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
Set the relative scale height and width for the picture frame to achieve the desired scaling effect.
## Step 5: Save Presentation
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Finally, save the presentation with the added picture frame in the specified output format.
## Conclusion
Congratulations! You've successfully learned how to add picture frames with relative scale height using Aspose.Slides for .NET. Experiment with different images, positions, and scales to create visually appealing presentations tailored to your needs.
## Frequently Asked Questions
### Can I use Aspose.Slides for .NET with other programming languages?
Aspose.Slides primarily supports .NET languages, but you can explore other Aspose products for compatibility with different platforms.
### Where can I find detailed documentation for Aspose.Slides for .NET?
Refer to the [documentation](https://reference.aspose.com/slides/net/) for comprehensive information and examples.
### Is there a free trial available for Aspose.Slides for .NET?
Yes, you can get a [free trial](https://releases.aspose.com/) to evaluate the library's capabilities.
### How can I get support for Aspose.Slides for .NET?
Visit the [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) to seek assistance from the community and Aspose experts.
### Where can I purchase Aspose.Slides for .NET?
You can buy Aspose.Slides for .NET from the [purchase page](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
