---
title: Adding Stretch Offset to Left for Picture Frame in Aspose.Slides
linktitle: Adding Stretch Offset to Left for Picture Frame in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to add stretch offset to the left for a picture frame in PowerPoint using Aspose.Slides for .NET. Step-by-step guide with complete source code example.
type: docs
weight: 14
url: /net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/
---

## Introduction to Aspose.Slides for .NET

Aspose.Slides for .NET is a comprehensive library that empowers .NET developers to work with PowerPoint presentations without the need for Microsoft Office. It provides a wide range of features, including creating, editing, and manipulating slides, shapes, text, images, and more.

## Prerequisites

Before we begin, make sure you have the following prerequisites in place:

1. Visual Studio installed on your machine.
2. Basic understanding of C# and .NET framework.
3. Aspose.Slides for .NET library. You can download it from [here](https://releases.aspose.com/slides/net/).

## Setting up the Project

Let's start by setting up a new C# project in Visual Studio:

1. Open Visual Studio.
2. Click on "Create a new project."
3. Select "Console App (.NET Framework/Core)."
4. Choose a suitable name and location for your project.
5. Click "Create."

Next, add a reference to the Aspose.Slides for .NET library in your project. Right-click on the "References" in the Solution Explorer, choose "Manage NuGet Packages," search for "Aspose.Slides," and install the package.

## Adding Stretch Offset to Left for Picture Frame

To add a stretch offset to the left for a picture frame using Aspose.Slides for .NET, follow these steps:

1. Load the presentation file using `Presentation` class.
2. Locate the slide containing the picture frame you want to modify.
3. Access the picture frame shape by iterating through the shapes on the slide.
4. Apply the stretch offset to the left using the `PictureFrame` class.

## Example Code

```csharp
using Aspose.Slides;
using Aspose.Slides.ShapeManagers;

namespace PictureFrameStretchOffsetExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Load the presentation
            using (Presentation presentation = new Presentation("sample.pptx"))
            {
                // Get the first slide
                ISlide slide = presentation.Slides[0];

                // Iterate through the shapes on the slide
                foreach (IShape shape in slide.Shapes)
                {
                    if (shape is IPictureFrame)
                    {
                        IPictureFrame pictureFrame = (IPictureFrame)shape;

                        // Apply stretch offset to the left
                        pictureFrame.PictureFormat.StretchOffsetX = -10;
                    }
                }

                // Save the modified presentation
                presentation.Save("output.pptx", SaveFormat.Pptx);
            }
        }
    }
}
```

In this example, we load a presentation, iterate through the shapes on the first slide, and if we find a picture frame shape, we apply a stretch offset of -10 to the left.

## Testing the Application

To test the application, follow these steps:

1. Ensure you have a sample PowerPoint presentation (`sample.pptx`) with at least one picture frame.
2. Run the application.
3. The modified presentation with the added stretch offset will be saved as `output.pptx`.

## Conclusion

In this tutorial, you've learned how to add a stretch offset to the left for a picture frame in Aspose.Slides using .NET. Aspose.Slides for .NET provides a powerful set of tools for programmatically manipulating PowerPoint presentations, enabling developers to create dynamic and customized slideshows seamlessly.

## FAQ's

### How can I install Aspose.Slides for .NET?

You can download Aspose.Slides for .NET from the official website [here](https://releases.aspose.com/slides/net/).

### Can I use Aspose.Slides for other PowerPoint manipulation tasks?

Absolutely! Aspose.Slides for .NET offers a wide range of features, including creating, editing, and converting PowerPoint presentations. You can explore its documentation for more details and examples.

### Is Aspose.Slides compatible with different PowerPoint formats?

Yes, Aspose.Slides supports various PowerPoint formats, including PPTX, PPT, POTX, and more. It also supports conversion between different formats.

### How can I customize other properties of shapes in a presentation?

You can access and modify various properties of shapes, including text, position, size, formatting, and more, using the Aspose.Slides library. Check out the documentation for comprehensive information and examples.

### Can I use Aspose.Slides with other programming languages?

Yes, Aspose.Slides provides libraries for various programming languages, including Java, Python, and more. You can choose the one that suits your development environment.
