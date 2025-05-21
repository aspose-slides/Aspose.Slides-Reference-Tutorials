---
title: Convert to PDF with Hidden Slides in Java Slides
linktitle: Convert to PDF with Hidden Slides in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to convert PowerPoint presentations to PDF with hidden slides using Aspose.Slides for Java. Follow our step-by-step guide with source code for seamless PDF generation.
weight: 27
url: /java/presentation-conversion/convert-pdf-hidden-slides-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Convert to PDF with Hidden Slides in Java Slides


## Introduction to Convert PowerPoint Presentation to PDF with Hidden Slides using Aspose.Slides for Java

In this step-by-step guide, you'll learn how to convert a PowerPoint presentation to PDF while preserving hidden slides using Aspose.Slides for Java. Hidden slides are those that are not displayed during a regular presentation but can be included in the PDF output. We'll provide you with the source code and detailed instructions for achieving this task.

## Prerequisites

Before you begin, make sure you have the following prerequisites in place:

1. Aspose.Slides for Java Library: Ensure you have the Aspose.Slides for Java library set up in your Java project. You can download it from the [Aspose.Slides for Java documentation](https://reference.aspose.com/slides/java/).

2. Java Development Environment: You should have a Java development environment installed on your system.

## Step 1: Import Aspose.Slides for Java

First, you need to import the Aspose.Slides library into your Java project. Make sure you have added the library to your project's build path.

```java
import com.aspose.slides.*;
```

## Step 2: Load the PowerPoint Presentation

You'll start by loading the PowerPoint presentation that you want to convert to PDF. Replace `"Your Document Directory"` and `"HiddingSlides.pptx"` with the appropriate file path.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## Step 3: Configure PDF Options

Configure the PDF options to include hidden slides in the PDF output. You can do this by setting the `setShowHiddenSlides` property of the `PdfOptions` class to `true`.

```java
// Instantiate the PdfOptions class
PdfOptions pdfOptions = new PdfOptions();
// Specify that the generated document should include hidden slides
pdfOptions.setShowHiddenSlides(true);
```

## Step 4: Save the Presentation as PDF

Now, save the presentation to a PDF file with the specified options. Replace `"PDFWithHiddenSlides_out.pdf"` with your desired output file name.

```java
// Save the presentation to PDF with specified options
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Step 5: Cleanup Resources

Make sure to release the resources used by the presentation when you are done with it.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Complete Source Code For Convert to PDF with Hidden Slides in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// Instantiate the PdfOptions class
	PdfOptions pdfOptions = new PdfOptions();
	// Specify that the generated document should include hidden slides
	pdfOptions.setShowHiddenSlides(true);
	// Save the presentation to PDF with specified options
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

In this comprehensive guide, you've learned how to convert a PowerPoint presentation to PDF while preserving hidden slides using Aspose.Slides for Java. We've provided you with a step-by-step tutorial along with the necessary source code to achieve this task seamlessly.

## FAQ's

### How can I hide slides in a PowerPoint presentation?

To hide a slide in a PowerPoint presentation, follow these steps:
1. Select the slide you want to hide in the Slide Sorter view.
2. Right-click on the selected slide.
3. Choose "Hide Slide" from the context menu.

### Can I programmatically unhide hidden slides in Aspose.Slides for Java?

Yes, you can programmatically unhide hidden slides in Aspose.Slides for Java by setting the `Hidden` property of the `Slide` class to `false`. Here's an example:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // Replace slideIndex with the index of the hidden slide
slide.setHidden(false);
```

### How do I download Aspose.Slides for Java?

You can download Aspose.Slides for Java from the Aspose website. Visit the [Aspose.Slides for Java download page](https://releases.aspose.com/slides/java/) to get the latest version.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
