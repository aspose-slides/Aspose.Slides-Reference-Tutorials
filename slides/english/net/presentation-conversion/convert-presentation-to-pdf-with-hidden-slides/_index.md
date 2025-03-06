---
title: Convert Presentation to PDF with Hidden Slides
linktitle: Convert Presentation to PDF with Hidden Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to use Aspose.Slides for .NET to convert presentations to PDF with hidden slides seamlessly.
weight: 26
url: /net/presentation-conversion/convert-presentation-to-pdf-with-hidden-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convert Presentation to PDF with Hidden Slides


## Introduction to Aspose.Slides for .NET

Aspose.Slides for .NET is a powerful library that provides comprehensive features for working with presentations in .NET applications. It allows developers to create, edit, manipulate, and convert presentations to various formats, including PDF.

## Understanding Hidden Slides in Presentations

Hidden slides are slides within a presentation that are not visible during a normal slideshow. They can contain supplementary information, backup content, or content that is intended for specific audiences. When converting presentations to PDF, it's essential to ensure that these hidden slides are also included to maintain the integrity of the presentation.

## Setting Up the Development Environment

Before we begin, make sure you have the following in place:

- Visual Studio or any .NET development environment installed.
- Aspose.Slides for .NET library. You can download it from [here](https://releases.aspose.com/slides/net).

## Loading a Presentation File

To get started, let's load a presentation file using Aspose.Slides for .NET:

```csharp
using Aspose.Slides;

// Load the presentation
using var presentation = new Presentation("sample.pptx");
```

## Converting Presentation to PDF with Hidden Slides

Now that we can identify hidden slides, let's proceed to convert the presentation to PDF while ensuring that hidden slides are included:

```csharp
var pdfOptions = new PdfOptions();
pdfOptions.ShowHiddenSlides = true; // Include hidden slides in PDF

presentation.Save("output.pdf", SaveFormat.Pdf, pdfOptions);
```

## Additional Options and Customizations

Aspose.Slides for .NET offers various options and customizations for the conversion process. You can set PDF-specific options, such as page size, orientation, and quality, to optimize the output PDF.

## Code Example: Convert Presentation to PDF with Hidden Slides

Here's a complete example of converting a presentation to PDF with hidden slides using Aspose.Slides for .NET:

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        using var presentation = new Presentation("sample.pptx");

        var pdfOptions = new PdfOptions();
        pdfOptions.ShowHiddenSlides = true;

        presentation.Save("output.pdf", SaveFormat.Pdf, pdfOptions);
    }
}
```

## Conclusion

Converting presentations to PDF is a common task, but when dealing with hidden slides, it's important to use a reliable library like Aspose.Slides for .NET. By following the steps outlined in this guide, you can seamlessly convert presentations to PDF while ensuring that hidden slides are included, maintaining the overall quality and context of the presentation.

## FAQ's

### How do I include hidden slides in the PDF using Aspose.Slides for .NET?

To include hidden slides in the PDF conversion, you can set the `ShowHiddenSlides` property to `true` in the PDF options before saving the presentation as a PDF.

### Can I customize the PDF output settings using Aspose.Slides?

Yes, Aspose.Slides for .NET provides various options to customize the PDF output settings, such as page size, orientation, and image quality.

### Is Aspose.Slides for .NET suitable for both simple and complex presentations?

Absolutely, Aspose.Slides for .NET is designed to handle presentations of varying complexities. It's suitable for both simple and complex presentation conversion tasks.

### Where can I download the Aspose.Slides for .NET library?

You can download the Aspose.Slides for .NET library from [here](https://releases.aspose.com/slides/net).

### Is there any documentation for Aspose.Slides for .NET?

Yes, you can find the documentation and usage examples for Aspose.Slides for .NET at [here](https://reference.aspose.com/slides/net).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
