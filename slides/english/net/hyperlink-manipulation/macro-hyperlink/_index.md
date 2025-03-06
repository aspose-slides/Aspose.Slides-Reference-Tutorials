---
title: How to Set Macro Hyperlink Click in Aspose.Slides for .NET
linktitle: Hyperlink Management using Macros
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to set macro hyperlinks in your presentations with Aspose.Slides for .NET. Enhance interactivity and engage your audience.
weight: 13
url: /net/hyperlink-manipulation/macro-hyperlink/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


In the world of modern software development, creating dynamic and interactive presentations is a key aspect. Aspose.Slides for .NET is a powerful library that allows you to work with presentations in a seamless manner. Whether you are building a business presentation or an educational slideshow, the ability to set macro hyperlink clicks can greatly enhance the user experience. In this step-by-step guide, we will walk you through the process of setting a macro hyperlink click using Aspose.Slides for .NET. 

## Prerequisites

Before we dive into the step-by-step tutorial, there are a few prerequisites you should have in place:

1.Visual Studio: Ensure that you have Visual Studio installed on your computer, as this will be our development environment.

2.Aspose.Slides for .NET: You will need to have Aspose.Slides for .NET library installed. You can download it from [here](https://releases.aspose.com/slides/net/).

3.Basic Knowledge of C#: Familiarity with C# programming language is essential to follow along with this tutorial.

## Import Namespaces

In the first step, let's import the necessary namespaces to work with Aspose.Slides:

### Step 1: Import Namespaces

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

We've imported the `Aspose.Slides` namespace, which is the core namespace for working with presentations, and the `Aspose.Slides.Export` namespace.

## Setting Macro Hyperlink Click

Now, let's move on to the main part of this tutorial - setting a macro hyperlink click in your presentation.

### Step 2: Initialize Presentation

First, we need to initialize a new presentation.

```csharp
using (Presentation presentation = new Presentation())
{
    // Your code will go here.
}
```

Within this using statement, you create a new presentation object and perform all your operations inside it.

### Step 3: Add an AutoShape

To set a macro hyperlink click, you'll need an object on which the user can click. In this example, we'll use an AutoShape as the clickable element.

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

Here, we create an AutoShape with the type "BlankButton" at specific coordinates (20, 20) and with dimensions of 80x30. You can customize these values to suit your presentation's layout.

### Step 4: Set Macro Hyperlink Click

Now comes the part where you set the macro hyperlink click. You'll need to provide a macro name as a parameter.

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

In this example, we've set the macro hyperlink click to the "TestMacro". When the user clicks on the AutoShape, it will trigger this macro.

### Step 5: Retrieve Information

You can also retrieve information about the hyperlink you've set.

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

These lines of code allow you to print the external URL and the action type of the hyperlink.

And that's it! You've successfully set a macro hyperlink click in your presentation using Aspose.Slides for .NET.

## Conclusion

In this tutorial, we've learned how to set a macro hyperlink click in your presentation using Aspose.Slides for .NET. This can be a valuable feature to create interactive and dynamic presentations that engage your audience. With Aspose.Slides for .NET, you have a powerful tool at your disposal to take your presentation development to the next level.

Now, it's time for you to experiment and create captivating presentations with custom macro hyperlinks. Feel free to explore the [Aspose.Slides for .NET documentation](https://reference.aspose.com/slides/net/) for more in-depth information and possibilities.

## FAQs (Frequently Asked Questions)

### Can I use Aspose.Slides for .NET with other programming languages?
Aspose.Slides is primarily designed for .NET, but Aspose offers similar libraries for other programming languages, such as Java.

### Is Aspose.Slides for .NET a free library?
Aspose.Slides for .NET is a commercial library with a free trial version available. You can download it from [here](https://releases.aspose.com/).

### Are there any limitations to using macros in presentations created with Aspose.Slides for .NET?
Aspose.Slides for .NET allows you to work with macros, but you should be aware of security and compatibility considerations when using macros in presentations.

### Can I customize the appearance of the AutoShape used for the hyperlink?
Yes, you can customize the AutoShape's appearance by adjusting its properties, such as size, color, and font.

### Where can I get help or support for Aspose.Slides for .NET?
If you encounter issues or have questions, you can seek help on the Aspose support forum [here](https://forum.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
