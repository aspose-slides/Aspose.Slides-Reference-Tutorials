---
title: Presentation Slide Show Setup in Java Slides
linktitle: Presentation Slide Show Setup in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 16
url: /java/java-slides-presentation-properties/presentation-slide-show-setup-in-java-slides/
---

## Complete Source Code
```java
        String outPptxPath = RunExamples.getOutPath() + "PresentationSlideShowSetup.pptx";
        Presentation pres = new Presentation();
        try {
            // Gets SlideShow settings
            SlideShowSettings slideShow = pres.getSlideShowSettings();
            // Sets "Using Timing" parameter
            slideShow.setUseTimings(false);
            // Sets Pen Color
            IColorFormat penColor = (ColorFormat)slideShow.getPenColor();
            penColor.setColor(Color.GREEN);
            // Adds slides for
            pres.getSlides().addClone(pres.getSlides().get_Item(0));
            pres.getSlides().addClone(pres.getSlides().get_Item(0));
            pres.getSlides().addClone(pres.getSlides().get_Item(0));
            pres.getSlides().addClone(pres.getSlides().get_Item(0));
            // Sets Show Slide parameter
            SlidesRange slidesRange = new SlidesRange();
            slidesRange.setStart(2);
            slidesRange.setEnd(5);
            slideShow.setSlides(slidesRange);
            // Save presentation
            pres.save(outPptxPath, SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
```
