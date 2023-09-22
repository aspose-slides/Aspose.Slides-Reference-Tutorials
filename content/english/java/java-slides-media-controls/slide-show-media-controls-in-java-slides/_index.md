---
title: Slide Show Media Controls in Java Slides
linktitle: Slide Show Media Controls in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 11
url: /java/java-slides-media-controls/slide-show-media-controls-in-java-slides/
---

## Complete Source Code
```java
        // Path to PPTX document
        String outFilePath = RunExamples.getOutPath() + "SlideShowMediaControl.pptx";
        Presentation pres = new Presentation();
        try {
            // Еnable media control display in slideshow mode.
            pres.getSlideShowSettings().setShowMediaControls(true);
            // Save presentation in PPTX format.
            pres.save(outFilePath, SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
```
