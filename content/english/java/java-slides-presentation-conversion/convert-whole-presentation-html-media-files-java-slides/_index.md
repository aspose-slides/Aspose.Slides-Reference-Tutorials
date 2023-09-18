---
title: Convert Whole Presentation to HTML with Media Files in Java Slides
linktitle: Convert Whole Presentation to HTML with Media Files in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 30
url: /java/java-slides-presentation-conversion/convert-whole-presentation-html-media-files-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        String htmlDocumentFileName = "presentationWithVideo.html";
        Presentation pres = new Presentation("presentationWith.pptx");
        try
        {
            VideoPlayerHtmlController controller = new VideoPlayerHtmlController(
                    "", htmlDocumentFileName, "http://www.example.com/");
            HtmlOptions htmlOptions = new HtmlOptions(controller);
            SVGOptions svgOptions = new SVGOptions(controller);
            htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(controller));
            htmlOptions.setSlideImageFormat(SlideImageFormat.svg(svgOptions));
            pres.save(htmlDocumentFileName, SaveFormat.Html, htmlOptions);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
