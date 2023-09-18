---
title: Convert Individual Slide in Java Slides
linktitle: Convert Individual Slide in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-slides-presentation-conversion/convert-individual-slide-java-slides/
---

## Complete Source Code
```java
        String dataDir = "Your Document Directory";
        Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
        try
        {
            HtmlOptions htmlOptions = new HtmlOptions();
            htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
            INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
            notesOptions.setNotesPosition(NotesPositions.BottomFull);
            // Saving File              
            for (int i = 0; i < presentation.getSlides().size(); i++)
                presentation.save(dataDir + "Individual Slide" + i + 1 + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
    }
    public static class CustomFormattingController implements IHtmlFormattingController
    {
        public void writeDocumentStart(IHtmlGenerator generator, IPresentation presentation)
        {
        }
        public void writeDocumentEnd(IHtmlGenerator generator, IPresentation presentation)
        {
        }
        public void writeSlideStart(IHtmlGenerator generator, ISlide slide)
        {
            generator.addHtml(String.format(SlideHeader, generator.getSlideIndex() + 1));
        }
        public void writeSlideEnd(IHtmlGenerator generator, ISlide slide)
        {
            generator.addHtml(SlideFooter);
        }
        public void writeShapeStart(IHtmlGenerator generator, IShape shape)
        {
        }
        public void writeShapeEnd(IHtmlGenerator generator, IShape shape)
        {
        }
        private static String SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
        private static String SlideFooter = "</div>";
```
