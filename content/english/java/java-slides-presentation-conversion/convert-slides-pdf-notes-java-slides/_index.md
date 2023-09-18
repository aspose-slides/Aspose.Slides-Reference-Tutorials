---
title: Convert Slides to PDF with Notes in Java Slides
linktitle: Convert Slides to PDF with Notes in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 19
url: /java/java-slides-presentation-conversion/convert-slides-pdf-notes-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Instantiate a Presentation object that represents a presentation file 
        Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
        try
        {
            Presentation auxPresentation = new Presentation();
            try
            {
                ISlide slide = presentation.getSlides().get_Item(0);
                auxPresentation.getSlides().insertClone(0, slide);
                // Setting Slide Type and Size
                //auxPresentation.getSlideSize().setSize(presentation.getSlideSize().getSize().getWidth(), presentation.getSlideSize().getSize().getHeight(),SlideSizeScaleType.EnsureFit);
                auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
                PdfOptions pdfOptions = new PdfOptions();
                INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
                options.setNotesPosition(NotesPositions.BottomFull);
                auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
            }
            finally
            {
                if (auxPresentation != null) auxPresentation.dispose();
            }
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
