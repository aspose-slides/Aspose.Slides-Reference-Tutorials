---
title: Convert HTML Embedding Images in Java Slides
linktitle: Convert HTML Embedding Images in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 11
url: /java/java-slides-presentation-conversion/convert-html-embedding-images-java-slides/
---

## Complete Source Code
```java
        // Path to source presentation
        String presentationName = RunExamples.getDataDir_Conversion() + "PresentationDemo.pptx";
        // Path to HTML document
        String outFilePath = RunExamples.getOutPath() + "HTMLConvertion" + File.separator;
        Presentation pres = new Presentation(presentationName);
        try {
            Html5Options options = new Html5Options();
            // Force do not save images in HTML5 document
            options.setEmbedImages(false);
            // Set path for external images
            options.setOutputPath(outFilePath);
            // Create directory for output HTML document
            File f = new File(outFilePath);
            if (!f.exists())
                f.mkdir();
            // Save presentation in HTML5 format.
            pres.save(outFilePath + "pres.html", SaveFormat.Html5, options);
        } finally {
            if (pres != null) pres.dispose();
        }
```
