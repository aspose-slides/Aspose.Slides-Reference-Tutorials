---
title: Preserving Original Fonts - Convert Presentation to HTML
linktitle: Preserving Original Fonts - Convert Presentation to HTML
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to preserve original fonts while converting presentations to HTML using Aspose.Slides for .NET. Ensure font consistency and visual impact effortlessly.
weight: 14
url: /net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


In this comprehensive guide, we will walk you through the process of preserving original fonts when converting a presentation to HTML using Aspose.Slides for .NET. We'll provide you with the necessary C# source code and explain each step in detail. By the end of this tutorial, you'll be able to ensure that the fonts in your converted HTML document remain faithful to the original presentation.

## 1. Introduction

When converting PowerPoint presentations to HTML, it's crucial to maintain the original fonts to ensure the visual consistency of your content. Aspose.Slides for .NET provides a powerful solution for achieving this. In this tutorial, we'll guide you through the steps needed to preserve the original fonts during the conversion process.

## 2. Prerequisites

Before we begin, make sure you have the following prerequisites in place:

- Visual Studio installed on your machine.
- Aspose.Slides for .NET library added to your project.

## 3. Setting Up Your Project

To get started, create a new project in Visual Studio and add the Aspose.Slides for .NET library as a reference.

## 4. Loading the Presentation

Use the following code to load your PowerPoint presentation:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Your code here
}
```

Replace `"Your Document Directory"` with the path to your presentation file.

## 5. Excluding Default Fonts

To exclude default fonts like Calibri and Arial, use the following code:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

You can customize this list as needed.

## 6. Embedding All Fonts

Next, we'll embed all the fonts in the HTML document. This ensures that the original fonts are preserved. Use the following code:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. Saving as HTML

Now, save the presentation as an HTML document with embedded fonts:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

Replace `"output.html"` with your desired output file name.

## 8. Conclusion

In this tutorial, we've demonstrated how to preserve original fonts when converting a PowerPoint presentation to HTML using Aspose.Slides for .NET. By following these steps, you can ensure that your converted HTML document maintains the visual integrity of the original presentation.

## 9. FAQs

### Q1: Can I customize the list of excluded fonts?

Yes, you can. Modify the `fontNameExcludeList` array to include or exclude specific fonts according to your requirements.

### Q2: What if I don't want to embed all fonts?

If you want to embed only specific fonts, you can modify the code accordingly. Consult the Aspose.Slides for .NET documentation for more details.

### Q3: Are there any licensing requirements for using Aspose.Slides for .NET?

Yes, you may need a valid license to use Aspose.Slides for .NET in your projects. Refer to the Aspose website for licensing information.

### Q4: Can I convert other file formats to HTML using Aspose.Slides for .NET?

Aspose.Slides for .NET primarily focuses on PowerPoint presentations. For converting other file formats to HTML, you may need to explore other Aspose products tailored for those formats.

### Q5: Where can I access additional resources and support?

You can find more documentation, tutorials, and support on the Aspose website. Visit [Aspose.Slides for .NET Documentation](https://reference.aspose.com/slides/net/) for detailed information.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
