---
title: "How to Set Language in PowerPoint Shapes Using Aspose.Slides for .NET"
description: "Learn how to set language attributes for text within shapes using Aspose.Slides for .NET. This guide covers adding auto shapes, setting language IDs, and saving presentations."
date: "2025-04-16"
weight: 1
url: "/net/shapes-text-frames/set-language-in-shapes-with-aspose-slides/"
keywords:
- Aspose.Aspose.Slides
- Net
- Document Processing

---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}
# How to Set Language in PowerPoint Shapes Using Aspose.Slides for .NET

In the world of digital presentations, ensuring your content is accessible and correctly formatted across different languages can be a challenge. With Aspose.Slides for .NET, you can effortlessly set language attributes for text within shapes in PowerPoint slides. This feature is especially beneficial when preparing multilingual documents or ensuring consistency in global communications.

**What You'll Learn:**
- Adding auto shapes and inserting text into them.
- Setting the language ID for text portions using Aspose.Slides.
- Saving presentations with custom configurations.

Let's dive into how you can implement this feature seamlessly.

## Prerequisites

Before we begin, ensure you have the following:

- **Libraries and Dependencies**: You need to have Aspose.Slides for .NET installed. This library is essential for manipulating PowerPoint presentations in C#.
  
- **Environment Setup**: A development environment with .NET Core or .NET Framework is required.

- **Knowledge Prerequisites**: Familiarity with basic C# programming concepts and understanding of object-oriented programming principles will be helpful.

## Setting Up Aspose.Slides for .NET

To get started, you need to install the Aspose.Slides library. You can do this using one of the following methods:

**.NET CLI**
```shell
dotnet add package Aspose.Slides
```

**Package Manager**
```powershell
Install-Package Aspose.Slides
```

**NuGet Package Manager UI**
Search for "Aspose.Slides" and install the latest version.

### License Acquisition

You can start with a free trial by downloading a temporary license from [here](https://purchase.aspose.com/temporary-license/). For ongoing use, consider purchasing a license through [this link](https://purchase.aspose.com/buy).

Once you have your setup ready, initialize Aspose.Slides in your project:

```csharp
using Aspose.Slides;
```

## Implementation Guide

Now that we're set up, let's implement the feature to set language for shape text.

### Feature Overview: Setting Shape Text Language

This feature allows you to specify the language of text within a PowerPoint shape. By setting the language ID, you ensure that spell checking and other language-specific features are applied correctly.

#### Step 1: Initialize Presentation

Start by creating an instance of the `Presentation` class.

```csharp
using (Presentation pres = new Presentation())
{
    // Your code here
}
```

This initializes a new PowerPoint presentation object which we'll manipulate.

#### Step 2: Add Auto Shape and Text Frame

Add a rectangle shape to your slide and insert text into it:

```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
shape.AddTextFrame("Text to apply spellcheck language");
```

Here, `AddAutoShape` adds a rectangle to the first slide. The parameters define its position and size.

#### Step 3: Set Language ID

Set the language for the text portion within the shape:

```csharp
shape.TextFrame.Paragraphs[0].Portions[0].PortionFormat.LanguageId = "en-EN";
```

This assigns English (UK) as the language for spell-checking.

#### Step 4: Save the Presentation

Finally, save your presentation to a specified path:

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY\	est1.pptx\
{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}