---
title: Conversion to TIFF with Notes in Java Slides
linktitle: Conversion to TIFF with Notes in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 10
url: /java/java-slides-presentation-conversion/conversion-tiff-notes-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Instantiate a Presentation object that represents a presentation file
        Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
        try
        {
            // Saving the presentation to TIFF notes
            presentation.save(dataDir + "Notes_In_Tiff_out.tiff", SaveFormat.Tiff);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
