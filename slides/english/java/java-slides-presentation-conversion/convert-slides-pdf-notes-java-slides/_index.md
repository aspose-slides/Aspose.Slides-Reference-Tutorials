---
title: Convert Slides to PDF with Notes in Java Slides
linktitle: Convert Slides to PDF with Notes in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to convert PowerPoint slides to PDF with notes in Java using Aspose.Slides for Java. Step-by-step guide for Java developers. Enhance your presentation sharing.
weight: 19
url: /java/presentation-conversion/convert-slides-pdf-notes-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Convert Slides to PDF with Notes in Java Slides


## Introduction to Convert Slides to PDF with Notes in Java

In the world of digital presentations, the ability to convert slides to PDF with accompanying notes is a valuable feature. Java developers can achieve this using the Aspose.Slides for Java library, which provides a robust set of tools for working with PowerPoint presentations programmatically. In this step-by-step guide, we will explore how to convert slides to PDF with notes using Java and Aspose.Slides for Java.

## Prerequisites

Before we dive into the code, make sure you have the following prerequisites in place:

- Java Development Kit (JDK) installed on your system.
- Aspose.Slides for Java library. You can download it from [here](https://releases.aspose.com/slides/java/).

Now that we have our outline, let's dive into the implementation step by step.
## Step 1: Setting Up the Project

First, create a Java project and add the Aspose.Slides for Java library to your project's dependencies.

## Step 2: Loading the Presentation

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## Step 3: Creating a New Presentation

```java
Presentation auxPresentation = new Presentation();
```

## Step 4: Copying Slides

```java
ISlide slide = presentation.getSlides().get_Item(0);
auxPresentation.getSlides().insertClone(0, slide);
```

## Step 5: Adjusting Slide Size

```java
auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## Step 6: Configuring PDF Options

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

## Step 7: Saving as PDF

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Complete Source Code For Convert Slides to PDF with Notes in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Instantiate a Presentation object that represents a presentation file 
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// Setting Slide Type and Size
		//auxPresentation.getSlideSize().setSize(presentation.getSlideSize().getSize().getWidth(), presentation.getSlideSize().getSize().getHeight(),SlideSizeScaleType.EnsureFit);
		auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
		PdfOptions pdfOptions = new PdfOptions();
		INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
		options.setNotesPosition(NotesPositions.BottomFull);
		auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
	}
	finally
	{
		if (auxPresentation != null) auxPresentation.dispose();
	}
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

In this tutorial, we learned how to convert slides to PDF with notes in Java using Aspose.Slides for Java. We covered setting up the project, loading the presentation, creating a new presentation, copying slides, adjusting slide size, configuring PDF options, and finally, saving the presentation as a PDF with notes.

## FAQ's

### How do I install Aspose.Slides for Java?

To install Aspose.Slides for Java, follow these steps:
1. Download the library from [here](https://releases.aspose.com/slides/java/).
2. Add the JAR file to your Java project's classpath.

### Can I customize the notes position in the generated PDF?

Yes, you can customize the notes position by modifying the `NotesPositions` enum in the PDF options. In this tutorial, we set it to `BottomFull`, but you can explore other options as well.

### Are there any licensing requirements for using Aspose.Slides for Java?

Yes, Aspose.Slides for Java is a commercial library, and you may need to acquire a license to use it in production. Visit the Aspose website for licensing details.

### Can I convert multiple slides at once?

Certainly! You can loop through the slides in your presentation and clone them into the new presentation, allowing you to convert multiple slides to PDF with notes in one go.

### Where can I find more documentation for Aspose.Slides for Java?

You can find detailed documentation for Aspose.Slides for Java on the site: [Aspose.Slides for Java API Reference](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
