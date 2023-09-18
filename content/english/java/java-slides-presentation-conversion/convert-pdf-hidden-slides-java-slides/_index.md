---
title: Convert to PDF with Hidden Slides in Java Slides
linktitle: Convert to PDF with Hidden Slides in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 27
url: /java/java-slides-presentation-conversion/convert-pdf-hidden-slides-java-slides/
---

## Complete Source Code
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
