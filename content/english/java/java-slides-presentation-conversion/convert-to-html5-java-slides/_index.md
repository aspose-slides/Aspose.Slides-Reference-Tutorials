---
title: Convert to HTML5 in Java Slides
linktitle: Convert to HTML5 in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 23
url: /java/java-slides-presentation-conversion/convert-to-html5-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory
        String dataDir = "Your Document Directory";
        // The path to output file
        String outFilePath = RunExamples.getOutPath() + "Demo.html";
        Presentation pres = new Presentation(dataDir + "Demo.pptx");
        try {
            // Export a presentation containing slides transitions, animations, and shapes animations to HTML5
            Html5Options options = new Html5Options();
            options.setAnimateShapes(true);
            options.setAnimateTransitions(true);
            // Save presentation
            pres.save(outFilePath, SaveFormat.Html5, options);
        } finally {
            if (pres != null) pres.dispose();
        }
```
