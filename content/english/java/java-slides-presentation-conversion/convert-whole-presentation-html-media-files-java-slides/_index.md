---
title: Convert Whole Presentation to HTML with Media Files in Java Slides
linktitle: Convert Whole Presentation to HTML with Media Files in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to convert presentations to HTML with media files using Java Slides. Follow our step-by-step guide with Aspose.Slides for Java API.
type: docs
weight: 30
url: /java/java-slides-presentation-conversion/convert-whole-presentation-html-media-files-java-slides/
---

## Introduction to Convert Whole Presentation to HTML with Media Files in Java Slides

In today's digital age, the need to convert presentations into various formats, including HTML, is a common requirement. Java developers often find themselves tasked with this challenge. Fortunately, with the Aspose.Slides for Java API, this task can be accomplished efficiently. In this step-by-step guide, we will explore how to convert a whole presentation to HTML while preserving media files using Java Slides.

## Prerequisites

Before we dive into the coding aspect, let's ensure we have everything set up correctly:

- Java Development Kit (JDK): Make sure you have the JDK installed on your system.
- Aspose.Slides for Java: You will need to have Aspose.Slides for Java API installed. You can download it [here](https://releases.aspose.com/slides/java/).

## Step 1: Import Necessary Packages

To get started, you need to import the necessary packages. These packages will provide the classes and methods required for our task.

```java
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SlideImageFormat;
import com.aspose.slides.SVGOptions;
import com.aspose.slides.VideoPlayerHtmlController;
```

## Step 2: Specify the Document Directory

Define the path to your document directory where the presentation file is located. Replace `"Your Document Directory"` with the actual path.

```java
String dataDir = "Your Document Directory";
```

## Step 3: Initialize the Presentation

Load the presentation you want to convert to HTML. Make sure to replace `"presentationWith.pptx"` with your presentation's file name.

```java
Presentation pres = new Presentation("presentationWith.pptx");
```

## Step 4: Create the HTML Controller

We'll create a `VideoPlayerHtmlController` to handle the conversion process. Replace the URL with your desired web address.

```java
VideoPlayerHtmlController controller = new VideoPlayerHtmlController(
    "", htmlDocumentFileName, "http://www.example.com/");
```

## Step 5: Configure HTML and SVG Options

Set up HTML and SVG options for the conversion. This is where you can customize the formatting as needed.

```java
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);
htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(controller));
htmlOptions.setSlideImageFormat(SlideImageFormat.svg(svgOptions));
```

## Step 6: Save the Presentation as HTML

Now, it's time to save the presentation as an HTML file, including media files.

```java
pres.save(htmlDocumentFileName, SaveFormat.Html, htmlOptions);
```

## Complete Source Code For Convert Whole Presentation to HTML with Media Files in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String htmlDocumentFileName = "presentationWithVideo.html";
Presentation pres = new Presentation("presentationWith.pptx");
try
{
	VideoPlayerHtmlController controller = new VideoPlayerHtmlController(
			"", htmlDocumentFileName, "http://www.example.com/");
	HtmlOptions htmlOptions = new HtmlOptions(controller);
	SVGOptions svgOptions = new SVGOptions(controller);
	htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(controller));
	htmlOptions.setSlideImageFormat(SlideImageFormat.svg(svgOptions));
	pres.save(htmlDocumentFileName, SaveFormat.Html, htmlOptions);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

In this tutorial, we've walked through the process of converting a whole presentation to HTML with media files using Java Slides and the Aspose.Slides for Java API. By following these steps, you can efficiently transform your presentations into a web-friendly format, preserving all essential media elements.

## FAQ's

### How can I install Aspose.Slides for Java?

To install Aspose.Slides for Java, visit the download page at [here](https://releases.aspose.com/slides/java/) and follow the installation instructions provided.

### Can I customize the HTML output further?

Yes, you can customize the HTML output according to your requirements. The `HtmlOptions` class provides various settings to control the conversion process, including formatting and layout options.

### Does Aspose.Slides for Java support other output formats?

Yes, Aspose.Slides for Java supports various output formats, including PDF, PPTX, and more. You can explore these options in the documentation.

### Is Aspose.Slides for Java suitable for commercial projects?

Yes, Aspose.Slides for Java is a robust and commercially viable solution for handling presentation-related tasks in Java applications. It is widely used in enterprise-level projects.

### How can I access the converted HTML presentation?

Once you've completed the conversion, you can access the HTML presentation by locating the file specified in the `htmlDocumentFileName` variable.
