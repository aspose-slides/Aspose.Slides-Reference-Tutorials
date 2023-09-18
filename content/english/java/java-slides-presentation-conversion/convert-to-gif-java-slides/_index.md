---
title: Convert to GIF in Java Slides
linktitle: Convert to GIF in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 22
url: /java/java-slides-presentation-conversion/convert-to-gif-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory
        String dataDir = "Your Document Directory";
        // The path to output file
        String outPath = RunExamples.getOutPath() + "ConvertToGif.gif";
        // Instantiate a Presentation object that represents a presentation file
        Presentation presentation = new Presentation(dataDir + "ConvertToGif.pptx");
        try {
            GifOptions gifOptions = new GifOptions();
            gifOptions.setFrameSize(new Dimension(540, 480)); // the size of the resulted GIF
            gifOptions.setDefaultDelay(1500); // how long each slide will be showed until it will be changed to the next one
            gifOptions.setTransitionFps(60); // increase FPS to better transition animation quality
            // Save the presentation to Gif
            presentation.save(outPath, SaveFormat.Gif, gifOptions);
        } finally {
            if (presentation != null) presentation.dispose();
        }
```
