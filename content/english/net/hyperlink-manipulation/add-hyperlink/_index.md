---
title: Add Hyperlink to Slide
linktitle: Add Hyperlink to Slide
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to add hyperlinks to slides in PowerPoint using Aspose.Slides for .NET. Enhance presentations with interactive content.
type: docs
weight: 12
url: /net/hyperlink-manipulation/add-hyperlink/
---

## Introduction to Aspose.Slides for .NET

Aspose.Slides for .NET is a comprehensive library that enables developers to create, modify, and manipulate PowerPoint presentations without relying on Microsoft Office. It provides a wide range of features, including adding and managing hyperlinks in slides.

## Prerequisites

Before you begin, make sure you have the following prerequisites in place:

- Visual Studio installed on your system.
- Aspose.Slides for .NET library. You can download it from [here](https://downloads.aspose.com/slides/net).

## Adding a Hyperlink to a Text in a Slide

1. Create a new C# project in Visual Studio.
2. Add a reference to the Aspose.Slides DLL in your project.
3. Use the following code to add a hyperlink to a text in a slide:

```csharp
using Aspose.Slides;

// Load the presentation
Presentation presentation = new Presentation("presentation.pptx");

// Access a slide
ISlide slide = presentation.Slides[0];

// Access a text box
ITextFrame textFrame = slide.Shapes[0] as ITextFrame;

// Add a portion of text with a hyperlink
textFrame.Paragraphs[0].Portions[0].Text = "Visit our website!";
textFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new HyperlinkInfo("https://www.example.com", HyperlinkAction.MouseClick);
```

## Adding a Hyperlink to a Shape in a Slide

1. Follow the steps above to create a new C# project and add the Aspose.Slides reference.
2. Use the following code to add a hyperlink to a shape in a slide:

```csharp
using Aspose.Slides;

// Load the presentation
Presentation presentation = new Presentation("presentation.pptx");

// Access a slide
ISlide slide = presentation.Slides[0];

// Access a shape
IShape shape = slide.Shapes[1];

// Add a hyperlink to the shape
shape.HyperlinkClick = new HyperlinkInfo("https://www.example.com", HyperlinkAction.MouseClick);
```

## Adding a Hyperlink to a Slide

1. Follow the initial steps to set up your C# project and reference the Aspose.Slides library.
2. Use the following code to add a hyperlink to a slide:

```csharp
using Aspose.Slides;

// Load the presentation
Presentation presentation = new Presentation("presentation.pptx");

// Access a slide
ISlide slide = presentation.Slides[2];

// Add a hyperlink to the slide
slide.HyperlinkClick = new HyperlinkInfo("https://www.example.com", HyperlinkAction.MouseClick);
```

## Adding External Hyperlinks

Apart from internal hyperlinks, you can also add external hyperlinks to your slides. Use the same approach as above, but provide the external URL as the hyperlink target.

## Modifying and Removing Hyperlinks

To modify an existing hyperlink or remove it, you can access the hyperlink properties of the respective slide element and make the necessary changes.

## Conclusion

Adding hyperlinks to slides using Aspose.Slides for .NET is a straightforward process that can greatly enhance the interactivity of your presentations. Whether you want to link to external resources or create navigation within your slides, Aspose.Slides provides the tools you need to achieve these tasks efficiently.

## FAQ's

### How do I remove a hyperlink from a portion of text?

To remove a hyperlink from a portion of text, you can simply set the `HyperlinkClick` property to `null` for that portion.

### Can I add hyperlinks to shapes other than text boxes?

Yes, you can add hyperlinks to various shapes, including images and custom shapes, using the `HyperlinkClick` property.

### Is Aspose.Slides compatible with different PowerPoint formats?

Yes, Aspose.Slides supports various PowerPoint formats, including PPTX, PPT, and more.

### How can I test the hyperlinks in my presentation?

You can run the presentation in a PowerPoint viewer or editor to test the hyperlinks' functionality.

### Where can I download the Aspose.Slides for .NET library?

You can download the Aspose.Slides for .NET library from the  Aspose website: [Download Aspose.Slides for .NET](https://releases.aspose.com/slides/net).
