---
title: Access Layout Formats in Java Slides
linktitle: Access Layout Formats in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 10
url: /java/java-slides-presentation-properties/access-layout-formats-in-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "pres.pptx");
        try
        {
            for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
            {
                IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
                int i = 0;
                for (IShape shape : layoutSlide.getShapes())
                {
                    fillFormats[i] = shape.getFillFormat();
                    i++;
                }
                ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
                int j = 0;
                for (IShape shape : layoutSlide.getShapes())
                {
                    lineFormats[j] = shape.getLineFormat();
                    j++;
                }
            }
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
