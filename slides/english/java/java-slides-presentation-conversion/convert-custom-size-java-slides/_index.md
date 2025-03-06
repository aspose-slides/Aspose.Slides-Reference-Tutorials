---
title: Convert with Custom Size in Java Slides
linktitle: Convert with Custom Size in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to convert PowerPoint presentations to TIFF images with custom size using Aspose.Slides for Java. Step-by-step guide with code examples for developers.
weight: 31
url: /java/presentation-conversion/convert-custom-size-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convert with Custom Size in Java Slides


## Introduction to Convert with Custom Size in Java Slides

In this article, we will explore how to convert PowerPoint presentations to TIFF images with custom size using the Aspose.Slides for Java API. Aspose.Slides for Java is a powerful library that allows developers to work with PowerPoint files programmatically. We will go step by step and provide you with the necessary Java code to accomplish this task.

## Prerequisites

Before we begin, make sure you have the following prerequisites in place:

- Java Development Kit (JDK) installed
- Aspose.Slides for Java library

You can download the Aspose.Slides for Java library from the website: [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/)

## Step 1: Import Aspose.Slides Library

To get started, you need to import the Aspose.Slides library into your Java project. Here's how you can do it:

```java
// Add the necessary import statement
import com.aspose.slides.*;
```

## Step 2: Load the PowerPoint Presentation

Next, you'll need to load the PowerPoint presentation that you want to convert to a TIFF image. Replace `"Your Document Directory"` with the actual path to your presentation file.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

// Instantiate a Presentation object that represents a Presentation file
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## Step 3: Set TIFF Conversion Options

Now, let's set the options for the TIFF conversion. We'll specify the compression type, DPI (dots per inch), image size, and notes position. You can customize these options as per your requirements.

```java
// Instantiate the TiffOptions class
TiffOptions opts = new TiffOptions();

// Setting compression type
opts.setCompressionType(TiffCompressionTypes.Default);

// Setting image DPI
opts.setDpiX(200);
opts.setDpiY(100);

// Set Image Size
opts.setImageSize(new Dimension(1728, 1078));

// Set notes position
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## Step 4: Save as TIFF

With all the options configured, you can now save the presentation as a TIFF image with the specified settings.

```java
// Save the presentation to TIFF with specified image size
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## Complete Source Code For Convert with Custom Size in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Instantiate a Presentation object that represents a Presentation file
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// Instantiate the TiffOptions class
	TiffOptions opts = new TiffOptions();
	// Setting compression type
	opts.setCompressionType(TiffCompressionTypes.Default);
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// Compression Types
	// Default - Specifies the default compression scheme (LZW).
	// None - Specifies no compression.
	// CCITT3
	// CCITT4
	// LZW
	// RLE
	// Depth depends on the compression type and cannot be set manually.
	// Resolution unit  is always equal to “2” (dots per inch)
	// Setting image DPI
	opts.setDpiX(200);
	opts.setDpiY(100);
	// Set Image Size
	opts.setImageSize(new Dimension(1728, 1078));
	// Save the presentation to TIFF with specified image size
	pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Congratulations! You've successfully converted a PowerPoint presentation to a TIFF image with custom size using Aspose.Slides for Java. This can be a valuable feature when you need to generate high-quality images from your presentations for various purposes.

## FAQ's

### How can I change the compression type for the TIFF image?

You can change the compression type by modifying the `setCompressionType` method in the `TiffOptions` class. There are different compression types available, such as Default, None, CCITT3, CCITT4, LZW, and RLE.

### Can I adjust the DPI (dots per inch) of the TIFF image?

Yes, you can adjust the DPI by using the `setDpiX` and `setDpiY` methods in the `TiffOptions` class. Simply set the desired values to control the image resolution.

### What are the available options for notes position in the TIFF image?

The notes position in the TIFF image can be configured using the `setNotesPosition` method with options like BottomFull, BottomTruncated, and SlideOnly. Choose the one that best suits your needs.

### Is it possible to specify a custom image size for the TIFF conversion?

Absolutely! You can set a custom image size by using the `setImageSize` method in the `TiffOptions` class. Provide the dimensions (width and height) you want for the output image.

### Where can I find more information about Aspose.Slides for Java?

For detailed documentation and additional information about Aspose.Slides for Java, please visit the documentation: [Aspose.Slides for Java API Reference](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
