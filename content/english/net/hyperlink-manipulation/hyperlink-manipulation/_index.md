---
title: Hyperlink Manipulation in Aspose.Slides
linktitle: Hyperlink Manipulation in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to enhance PowerPoint presentations with hyperlinks using Aspose.Slides for .NET. Create, modify, and manage interactive content seamlessly.
type: docs
weight: 10
url: /net/hyperlink-manipulation/hyperlink-manipulation/
---

## Introduction to Hyperlink Manipulation

Hyperlinks enrich presentations by connecting slides, documents, web pages, and more. They provide an interactive experience, enhancing the audience's engagement. Aspose.Slides for .NET offers comprehensive functionality to manage hyperlinks programmatically, giving you full control over your presentation's navigation.

## Setting Hyperlinks in Slides

To create hyperlinks, you can use Aspose.Slides for .NET's `HyperlinkManager` class. This class allows you to add various types of hyperlinks to specific shapes or text in your slides.

```csharp
// Code example to add a hyperlink to a shape
HyperlinkManager.AddHyperlinkToShape(shape, "https://www.example.com", "Visit our website");
```

## Modifying Hyperlinks

You can easily modify existing hyperlinks using Aspose.Slides for .NET. This is useful when you need to update the target URL or change the hyperlink's text.

```csharp
// Code example to modify a hyperlink's URL
HyperlinkManager.ModifyHyperlinkUrl(shape, "https://newurl.com");
```

## Removing Hyperlinks

If you wish to remove a hyperlink from a shape, Aspose.Slides for .NET provides a straightforward method to do so.

```csharp
// Code example to remove a hyperlink from a shape
HyperlinkManager.RemoveHyperlink(shape);
```

## Working with Anchor Points

Anchor points are crucial when dealing with hyperlinks within slides. They determine the position where the hyperlink points to within the target slide.

```csharp
// Code example to set an anchor point for a hyperlink
HyperlinkManager.SetHyperlinkAnchor(shape, targetSlide, anchorX, anchorY);
```

## Handling Different Hyperlink Types

Aspose.Slides for .NET supports various hyperlink types, including URL links, internal document links, links to email addresses, and more.

```csharp
// Code example to add an email hyperlink
HyperlinkManager.AddEmailHyperlink(shape, "support@example.com", "Contact Support");
```

## Adding Tooltips to Hyperlinks

Tooltips provide additional information when users hover over hyperlinks. Aspose.Slides for .NET enables you to set tooltips for your hyperlinks.

```csharp
// Code example to add a tooltip to a hyperlink
HyperlinkManager.AddHyperlinkWithTooltip(shape, "https://www.example.com", "Visit our website", "Click to explore");
```

## Managing External Hyperlinks

You can also manage external hyperlinks using Aspose.Slides for .NET, ensuring that your presentations remain connected to relevant online resources.

```csharp
// Code example to open a hyperlink in a web browser
HyperlinkManager.OpenHyperlinkInBrowser(shape);
```

## Hyperlinks in Master Slides

Master slides often contain recurring elements. Aspose.Slides for .NET allows you to apply hyperlinks to master slides, ensuring consistency across your presentation.

```csharp
// Code example to set a hyperlink in a master slide
HyperlinkManager.SetHyperlinkInMasterSlide(masterSlide, "https://www.example.com", "Visit our website");
```

## Extracting Hyperlink Information

You can extract information from existing hyperlinks using Aspose.Slides for .NET, which can be helpful for analysis or reporting purposes.

```csharp
// Code example to extract hyperlink information
HyperlinkManager.ExtractHyperlinkInfo(shape, out string linkUrl, out string linkText);
```

## Adding Hyperlinks to Images and Shapes

Hyperlinks can be added not only to text but also to images and shapes within your slides.

```csharp
// Code example to add a hyperlink to an image
HyperlinkManager.AddHyperlinkToImage(imageShape, "https://www.example.com", "Click the image to learn more");
```

## Linking to Email Addresses and Phone Numbers

Aspose.Slides for .NET enables you to create hyperlinks that trigger email composition or initiate phone calls when clicked.

```csharp
// Code example to create an email hyperlink
HyperlinkManager.AddEmailHyperlink(shape, "support@example.com", "Contact Support");

// Code example to create a phone number hyperlink
HyperlinkManager.AddPhoneHyperlink(shape, "+1234567890", "Call our support");
```

## Hyperlink Formatting

You can apply formatting to hyperlinks to make them visually distinct from regular text or shapes.

```csharp
// Code example to format a hyperlink's appearance
HyperlinkManager.FormatHyperlink(shape, HyperlinkFormat.Highlighted);
```

## Adding Hyperlinks through API

Aspose.Slides for .NET provides a robust API for hyperlink manipulation. You can integrate these features seamlessly into your applications.

```csharp
// Code example to add a hyperlink through the API
HyperlinkManager.AddHyperlink(shape, HyperlinkType.Url, "https://www.example.com");
```

## Conclusion

Hyperlink manipulation using Aspose.Slides for .NET offers a comprehensive toolkit for enhancing the interactivity and engagement of your PowerPoint presentations. With the ability to create, modify, and manage hyperlinks, you can create dynamic and informative slideshows that captivate your audience.

## FAQ's

### How do I remove a hyperlink from a shape?

To remove a hyperlink from a shape, you can use the following code:

```csharp
HyperlinkManager.RemoveHyperlink(shape);
```

### Can I apply hyperlinks to images in my slides?

Yes, you can add hyperlinks to images and shapes within your slides using Aspose.Slides for .NET. For example:

```csharp
HyperlinkManager.AddHyperlinkToImage(imageShape, "https://www.example.com", "Click the image to learn more");
```

### Is it possible to format the appearance of a hyperlink?

Certainly! You can format the appearance of a hyperlink using Aspose.Slides for .NET. Here's an example:

```csharp
HyperlinkManager.FormatHyperlink(shape, HyperlinkFormat.Highlighted);
```

### How can I extract information from an existing hyperlink?

You can extract information from an existing hyperlink using the following approach:

```csharp
HyperlinkManager.ExtractHyperlinkInfo(shape, out string linkUrl, out string linkText);
```

### Where can I access more detailed documentation about Aspose.Slides for .NET?

For more detailed information and code examples, you can refer to the [documentation](https://reference.aspose.com/slides/net/) for Aspose.Slides for .NET.
