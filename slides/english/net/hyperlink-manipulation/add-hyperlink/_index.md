---
title: Adding Hyperlinks to Slides in .NET using Aspose.Slides
linktitle: Add Hyperlink to Slide
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to add hyperlinks to PowerPoint slides with Aspose.Slides for .NET. Enhance your presentations with interactive elements.
weight: 12
url: /net/hyperlink-manipulation/add-hyperlink/
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Adding Hyperlinks to Slides in .NET using Aspose.Slides


In the world of digital presentations, interactivity is key. Adding hyperlinks to your slides can make your presentation more engaging and informative. Aspose.Slides for .NET is a powerful library that allows you to create, modify, and manipulate PowerPoint presentations programmatically. In this tutorial, we'll show you how to add hyperlinks to your slides using Aspose.Slides for .NET. 

## Prerequisites

Before we dive into adding hyperlinks to slides, make sure you have the following prerequisites in place:

1. Visual Studio: You should have Visual Studio installed on your computer to write and execute the .NET code.

2. Aspose.Slides for .NET: You need to have the Aspose.Slides for .NET library installed. You can download it from [here](https://releases.aspose.com/slides/net/).

3. Basic C# Knowledge: Familiarity with C# programming will be beneficial.

## Import Namespaces

To get started, you need to import the necessary namespaces in your C# project. In this case, you'll require the following namespaces from the Aspose.Slides library:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

Now, let's break down the process of adding hyperlinks to slides into multiple steps.

## Step 1: Initialize Presentation

First, create a new presentation using Aspose.Slides. Here's how you can do it:

```csharp
using (Presentation presentation = new Presentation())
{
    // Your code goes here
}
```

This code initializes a new PowerPoint presentation.

## Step 2: Add Text Frame

Now, let's add a text frame to your slide. This text frame will serve as the clickable element in your slide. 

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

The code above creates a rectangular auto shape and adds a text frame with the text "Aspose: File Format APIs."

## Step 3: Add Hyperlink

Next, let's add a hyperlink to the text frame you've created. This will make the text clickable.

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

In this step, we set the hyperlink URL to "https://www.aspose.com/" and provide a tooltip for additional information. You can also format the hyperlink's appearance, as shown above.

## Step 4: Save Presentation

Finally, save your presentation with the added hyperlink.

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

This code saves the presentation as "presentation-out.pptx."

Now, you have successfully added a hyperlink to a slide using Aspose.Slides for .NET.

## Conclusion

In this tutorial, we've explored how to add hyperlinks to slides in PowerPoint presentations using Aspose.Slides for .NET. By following these steps, you can make your presentations more interactive and engaging, providing valuable links to additional resources or information.

For more detailed information and documentation, visit the [Aspose.Slides for .NET documentation](https://reference.aspose.com/slides/net/).

## FAQs

### 1. Can I add hyperlinks to other shapes besides text frames?

Yes, you can add hyperlinks to various shapes like rectangles, images, and more using Aspose.Slides for .NET.

### 2. How can I remove a hyperlink from a shape in a PowerPoint slide?

You can remove a hyperlink from a shape by setting the `HyperlinkClick` property to `null`.

### 3. Can I change the hyperlink URL dynamically in my code?

Absolutely! You can update the URL of a hyperlink at any point in your code by modifying the `Hyperlink` property.

### 4. What other interactive elements can I add to PowerPoint slides using Aspose.Slides?

Aspose.Slides offers a wide range of interactive features, including action buttons, multimedia elements, and animations.

### 5. Is Aspose.Slides available for other programming languages?

Yes, Aspose.Slides is available for various programming languages, including Java and Python.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
