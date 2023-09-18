---
title: Convert Specific Slide to PDF in Java Slides
linktitle: Convert Specific Slide to PDF in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 20
url: /java/java-slides-presentation-conversion/convert-specific-slide-pdf-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Instantiate a Presentation object that represents a presentation file
        Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
        try
        {
            // Setting array of slides positions
            int[] slides = {1, 3};
            // Save the presentation to PDF
            presentation.save(dataDir + "RequiredSelectedSlides_out.pdf", slides, SaveFormat.Pdf);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
