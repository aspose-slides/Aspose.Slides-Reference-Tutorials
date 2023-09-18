---
title: Convert Notes Slide View in Java Slides
linktitle: Convert Notes Slide View in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 15
url: /java/java-slides-presentation-conversion/convert-notes-slide-view-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Instantiate a Presentation object that represents a presentation file
        Presentation pres = new Presentation(dataDir + "Convert_Tiff_Default.pptx");
        try
        {
            // Saving the presentation to TIFF document
            pres.save(dataDir + "Tiff_out.tiff", SaveFormat.Tiff);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
