---
title: Convert Presentation to Responsive HTML in Java Slides
linktitle: Convert Presentation to Responsive HTML in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 18
url: /java/java-slides-presentation-conversion/convert-presentation-responsive-html-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Instantiate a Presentation object that represents a presentation file
        Presentation presentation = new Presentation(dataDir + "Convert_HTML.pptx");
        try
        {
            ResponsiveHtmlController controller = new ResponsiveHtmlController();
            HtmlOptions htmlOptions = new HtmlOptions();
            htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(controller));
            // Saving the presentation to HTML
            presentation.save(dataDir + "ConvertPresentationToResponsiveHTML_out.html", SaveFormat.Html, htmlOptions);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
