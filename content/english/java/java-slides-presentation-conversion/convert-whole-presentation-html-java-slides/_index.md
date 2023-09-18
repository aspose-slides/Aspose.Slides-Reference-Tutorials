---
title: Convert Whole Presentation to HTML in Java Slides
linktitle: Convert Whole Presentation to HTML in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 29
url: /java/java-slides-presentation-conversion/convert-whole-presentation-html-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Instantiate a Presentation object that represents a presentation file
        Presentation presentation = new Presentation(dataDir + "Convert_HTML.pptx");
        try
        {
            HtmlOptions htmlOpt = new HtmlOptions();
            htmlOpt.setHtmlFormatter(HtmlFormatter.createDocumentFormatter("", false));
            INotesCommentsLayoutingOptions notesOptions = htmlOpt.getNotesCommentsLayouting();
            notesOptions.setNotesPosition(NotesPositions.BottomFull);
            // Saving the presentation to HTML
            presentation.save(dataDir + "ConvertWholePresentationToHTML_out.html", SaveFormat.Html, htmlOpt);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
