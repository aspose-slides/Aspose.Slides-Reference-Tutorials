---
title: Converting Presentation to HTML with Preserving Original Fonts in Java Slides
linktitle: Converting Presentation to HTML with Preserving Original Fonts in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Convert PowerPoint presentations to HTML while preserving original fonts using Aspose.Slides for Java.
weight: 14
url: /java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduction to Converting Presentation to HTML with Preserving Original Fonts in Java Slides

In this tutorial, we will explore how to convert a PowerPoint presentation (PPTX) to HTML while preserving the original fonts using Aspose.Slides for Java. This will ensure that the resulting HTML closely resembles the appearance of the original presentation.

## Step 1: Setting up the Project
Before we dive into the code, let's ensure that you have the necessary setup in place:

1. Download Aspose.Slides for Java: If you haven't already, download and include the Aspose.Slides for Java library in your project.

2. Create a Java Project: Set up a Java project in your favorite IDE, and make sure you have a "lib" folder where you can place the Aspose.Slides JAR file.

3. Import Required Classes: Import the necessary classes at the beginning of your Java file:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Step 2: Converting Presentation to HTML with Original Fonts

Now, let's convert a PowerPoint presentation to HTML while preserving the original fonts:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

// Load the presentation
Presentation pres = new Presentation("input.pptx");

try {
    // Exclude default presentation fonts like Calibri and Arial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Create HTML options and set the custom HTML formatter
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Save the presentation as HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Dispose of the presentation object
    if (pres != null) pres.dispose();
}
```

In this code snippet:

- We load the input PowerPoint presentation using `Presentation`.

- We define a list of fonts (`fontNameExcludeList`) that we want to exclude from embedding in the HTML. This is useful for excluding common fonts like Calibri and Arial to reduce the file size.

- We create an instance of `EmbedAllFontsHtmlController` and pass the font exclusion list to it.

- We create `HtmlOptions` and set a custom HTML formatter using `HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Finally, we save the presentation as HTML with the specified options.

## Complete Source Code For Converting Presentation to HTML with Preserving Original Fonts in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// exclude default presentation fonts
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

In this tutorial, you've learned how to convert a PowerPoint presentation to HTML while preserving the original fonts using Aspose.Slides for Java. This is useful when you want to maintain the visual fidelity of your presentations when sharing them on the web.

## FAQ's

### How do I download Aspose.Slides for Java?

You can download Aspose.Slides for Java from the Aspose website. Visit [here](https://downloads.aspose.com/slides/java/) to get the latest version.

### Can I customize the list of excluded fonts?

Yes, you can customize the `fontNameExcludeList` array to include or exclude specific fonts as per your requirements.

### Does this method work for older PowerPoint formats like PPT?

This code example is designed for PPTX files. If you need to convert older PPT files, you may need to make adjustments to the code.

### How can I further customize the HTML output?

You can explore the `HtmlOptions` class to customize various aspects of the HTML output, such as slide size, image quality, and more.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
