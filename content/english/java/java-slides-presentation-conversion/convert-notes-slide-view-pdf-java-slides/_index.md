---
title: Convert Notes Slide View to PDF in Java Slides
linktitle: Convert Notes Slide View to PDF in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 16
url: /java/java-slides-presentation-conversion/convert-notes-slide-view-pdf-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Instantiate a Presentation object that represents a presentation file
        Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
        try
        {
            PdfOptions pdfOptions = new PdfOptions();
            INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
            options.setNotesPosition(NotesPositions.BottomFull);
            // Saving the presentation to PDF notes
            presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
