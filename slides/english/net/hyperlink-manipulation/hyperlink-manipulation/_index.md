---
title: Hyperlink Manipulation in Aspose.Slides
linktitle: Hyperlink Manipulation in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to add and remove hyperlinks in Aspose.Slides for .NET. Enhance your presentations with interactive links easily.
weight: 10
url: /net/hyperlink-manipulation/hyperlink-manipulation/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Hyperlinks are essential elements in presentations, as they provide a convenient way to navigate between slides or access external resources. Aspose.Slides for .NET offers powerful features for adding and removing hyperlinks in your presentation slides. In this tutorial, we will guide you through the process of hyperlink manipulation using Aspose.Slides for .NET. We will cover adding hyperlinks to a slide and removing hyperlinks from a slide. So, let's dive in!

## Prerequisites

Before you begin, ensure you have the following prerequisites in place:

1. Aspose.Slides for .NET: You must have the Aspose.Slides for .NET library installed and set up. You can find the documentation [here](https://reference.aspose.com/slides/net/) and download it from [this link](https://releases.aspose.com/slides/net/).

2. Your Document Directory: You need a directory where you will store your presentation files. Make sure to specify the path to this directory in your code.

3. Basic Knowledge of C#: This tutorial assumes you have a basic understanding of C# programming.

Now that you have your prerequisites in place, let's move on to the step-by-step guide for hyperlink manipulation using Aspose.Slides for .NET.

## Adding Hyperlinks to a Slide

### Step 1: Initialize Presentation

To get started, you need to initialize a presentation using Aspose.Slides. You can do this with the following code:

```csharp
using (Presentation presentation = new Presentation())
{
    // Your code here
}
```

### Step 2: Add Text Frame

Now, let's add a text frame to a slide. This code creates a rectangular shape with text:

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

### Step 3: Add Hyperlink

Next, you'll add a hyperlink to the text in the shape you created. Here's how you can do it:

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

### Step 4: Save Presentation

Finally, save your presentation with the added hyperlink:

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Congratulations! You've successfully added a hyperlink to a slide using Aspose.Slides for .NET.

## Removing Hyperlinks from a Slide

### Step 1: Initialize Presentation

To remove hyperlinks from a slide, you need to open an existing presentation:

```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Hyperlink.pptx");
```

### Step 2: Remove Hyperlinks

Now, remove all hyperlinks from the presentation using the following code:

```csharp
presentation.HyperlinkQueries.RemoveAllHyperlinks();
```

### Step 3: Save Presentation

After removing the hyperlinks, save the presentation:

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

And that's it! You've successfully removed hyperlinks from a slide using Aspose.Slides for .NET.

In conclusion, Aspose.Slides for .NET provides an efficient way to manipulate hyperlinks in your presentations, allowing you to create interactive and engaging slides. Whether you want to add hyperlinks to external resources or remove them, Aspose.Slides simplifies the process and enhances your presentation-building capabilities.

Thank you for joining us in this tutorial on hyperlink manipulation in Aspose.Slides for .NET. If you have any questions or need further assistance, feel free to explore the [Aspose.Slides documentation](https://reference.aspose.com/slides/net/) or reach out to the Aspose community on the [support forum](https://forum.aspose.com/).

---

## Conclusion

In this tutorial, we've learned how to manipulate hyperlinks in presentations using Aspose.Slides for .NET. We covered both the addition and removal of hyperlinks, enabling you to create dynamic and interactive presentations. Aspose.Slides simplifies the process, making it easy to enhance your slides with hyperlinks to external resources.

Do you have any more questions about working with Aspose.Slides or other aspects of presentation design? Check out the FAQs below for more insights.

## FAQs (Frequently Asked Questions)

### What are the key advantages of using Aspose.Slides for .NET?
Aspose.Slides for .NET offers a wide range of features for creating, manipulating, and converting presentations. It provides a comprehensive set of tools for adding content, animations, and interactions to your slides.

### Can I add hyperlinks to objects other than text in Aspose.Slides?
Yes, Aspose.Slides allows you to add hyperlinks to various objects, including shapes, images, and text, giving you flexibility in creating interactive presentations.

### Is Aspose.Slides compatible with different PowerPoint file formats?
Absolutely. Aspose.Slides supports various PowerPoint formats, including PPT, PPTX, PPS, and more. It ensures compatibility with different versions of Microsoft PowerPoint.

### Where can I find additional resources and support for Aspose.Slides?
For in-depth documentation and community support, visit the [Aspose.Slides documentation](https://reference.aspose.com/slides/net/) and the [Aspose support forum](https://forum.aspose.com/).

### How can I obtain a temporary license for Aspose.Slides?
If you need a temporary license for Aspose.Slides, you can get one [here](https://purchase.aspose.com/temporary-license/).

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
