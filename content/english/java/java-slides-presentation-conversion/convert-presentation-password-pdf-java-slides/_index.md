---
title: Convert Presentation to Password-Protected PDF in Java Slides
linktitle: Convert Presentation to Password-Protected PDF in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 17
url: /java/java-slides-presentation-conversion/convert-presentation-password-pdf-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Instantiate a Presentation object that represents a presentation file
        Presentation presentation = new Presentation(dataDir + "DemoFile.pptx");
        try
        {
            // Instantiate the PdfOptions class
            PdfOptions pdfOptions = new PdfOptions();
            // Setting PDF password
            pdfOptions.setPassword("password");
            // Save the presentation to password protected PDF
            presentation.save(dataDir + "PasswordProtectedPDF_out.pdf", SaveFormat.Pdf, pdfOptions);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
