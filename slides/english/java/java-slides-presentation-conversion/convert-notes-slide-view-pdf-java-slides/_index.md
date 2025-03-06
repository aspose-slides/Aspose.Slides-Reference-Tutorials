---
title: Convert Notes Slide View to PDF in Java Slides
linktitle: Convert Notes Slide View to PDF in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to convert PowerPoint presentations with notes into PDFs using Aspose.Slides for Java. Follow our step-by-step guide with source code.
weight: 16
url: /java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduction to Convert Notes Slide View to PDF in Java Slides

In this tutorial, we'll guide you through the process of converting a PowerPoint presentation with notes slide view into a PDF using the Aspose.Slides for Java library. This library provides powerful features for working with PowerPoint presentations in Java.

## Prerequisites
1. Java Development Kit (JDK) installed.
2. Aspose.Slides for Java library added to your project.

## Step 1: Import Necessary Classes
To get started, you'll need to import the necessary classes from the Aspose.Slides library. Here's the code to do that:

```java
import com.aspose.slides.*;
```

## Step 2: Load the PowerPoint Presentation
You should have your PowerPoint presentation file ready. Replace `"Your Document Directory"` with the path to the directory where your presentation file is located. Here's the code to load the presentation:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## Step 3: Configure PDF Options
Now, let's configure the PDF export options. Specifically, we'll set the notes position to "BottomFull" to include notes below the slides in the PDF. Here's the code:

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

You can customize other PDF options according to your requirements.

## Step 4: Save the Presentation as PDF with Notes
Finally, let's save the presentation as a PDF file, including the notes. You can specify the output file name (e.g., `"Pdf_Notes_out.pdf"`) and choose the format (`SaveFormat.Pdf`). Here's the code to do that:

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Step 5: Clean Up Resources
Don't forget to release the resources once you're done with the presentation:

```java
if (presentation != null) presentation.dispose();
```

## Complete Source Code For Convert Notes Slide View to PDF in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Instantiate a Presentation object that represents a presentation file
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
try
{
	PdfOptions pdfOptions = new PdfOptions();
	INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
	options.setNotesPosition(NotesPositions.BottomFull);
	// Saving the presentation to PDF notes
	presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

In this tutorial, we have explored how to convert PowerPoint presentations with notes slide views into PDFs using the Aspose.Slides for Java library. We followed a step-by-step guide with source code to achieve this conversion. Here are the key takeaways:

## FAQ's

### How do I change the notes position in the PDF?

You can change the notes position in the PDF by modifying the `setNotesPosition` method argument. For example, you can set it to `NotesPositions.RightFull` to position notes on the right side of the slides.

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### Can I customize the PDF export further?

Yes, you can customize the PDF export by adjusting various options in the `PdfOptions` object. For example, you can set the quality, compression, and other parameters according to your needs.

### How can I obtain Aspose.Slides for Java?

You can download Aspose.Slides for Java from the website at [here](https://releases.aspose.com/slides/java/).

### Are there any licensing requirements for using Aspose.Slides?

Yes, Aspose.Slides requires a valid license for commercial use. You can obtain a license from the Aspose website.

### Where can I find more documentation and examples?

You can find comprehensive documentation and examples for Aspose.Slides for Java at [here](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
