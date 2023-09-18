---
title: Convert to SWF in Java Slides
linktitle: Convert to SWF in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 35
url: /java/java-slides-presentation-conversion/convert-to-swf-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Instantiate a Presentation object that represents a presentation file
        Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
        try
        {
            SwfOptions swfOptions = new SwfOptions();
            swfOptions.setViewerIncluded(false);
            INotesCommentsLayoutingOptions notesOptions = swfOptions.getNotesCommentsLayouting();
            notesOptions.setNotesPosition(NotesPositions.BottomFull);
            // Saving presentation and notes pages
            presentation.save(dataDir + "SaveAsSwf_out.swf", SaveFormat.Swf, swfOptions);
            swfOptions.setViewerIncluded(true);
            presentation.save(dataDir + "SaveNotes_out.swf", SaveFormat.Swf, swfOptions);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
