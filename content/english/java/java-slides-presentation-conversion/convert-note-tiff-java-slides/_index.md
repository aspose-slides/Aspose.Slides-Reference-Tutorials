---
title: Convert with Note to TIFF in Java Slides
linktitle: Convert with Note to TIFF in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 32
url: /java/java-slides-presentation-conversion/convert-note-tiff-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Instantiate a Presentation object that represents a presentation file
        Presentation pres = new Presentation(dataDir + "ConvertWithNoteToTiff.pptx");
        try
        {
            TiffOptions opts = new TiffOptions();
            INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
            notesOptions.setNotesPosition(NotesPositions.BottomFull);
            // Saving the presentation to TIFF notes
            pres.save(dataDir + "TestNotes_out.tiff", SaveFormat.Tiff, opts);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
