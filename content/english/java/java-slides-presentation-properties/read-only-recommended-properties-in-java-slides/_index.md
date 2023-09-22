---
title: Read-Only Recommended Properties in Java Slides
linktitle: Read-Only Recommended Properties in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 17
url: /java/java-slides-presentation-properties/read-only-recommended-properties-in-java-slides/
---

## Complete Source Code
```java
        String outPptxPath = RunExamples.getOutPath() + "ReadOnlyRecommended.pptx";
        Presentation pres = new Presentation();
        try
        {
            pres.getProtectionManager().setReadOnlyRecommended(true);
            pres.save(outPptxPath, SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
