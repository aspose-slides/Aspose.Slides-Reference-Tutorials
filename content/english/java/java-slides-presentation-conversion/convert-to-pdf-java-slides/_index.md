---
title: Convert to PDF in Java Slides
linktitle: Convert to PDF in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 25
url: /java/java-slides-presentation-conversion/convert-to-pdf-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Instantiate a Presentation object that represents a presentation file
        Presentation presentation = new Presentation(dataDir + "ConvertToPDF.pptx");
        try
        {
            // Save the presentation to PDF with default options
            presentation.save(dataDir + "output_out.pdf", SaveFormat.Pdf);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
