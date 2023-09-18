---
title: Convert with Custom Size in Java Slides
linktitle: Convert with Custom Size in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 31
url: /java/java-slides-presentation-conversion/convert-custom-size-java-slides/
---

## Complete Source Code
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
