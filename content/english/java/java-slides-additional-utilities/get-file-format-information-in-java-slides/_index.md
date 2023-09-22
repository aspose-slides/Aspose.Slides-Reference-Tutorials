---
title: Get File Format Information in Java Slides
linktitle: Get File Format Information in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 11
url: /java/java-slides-additional-utilities/get-file-format-information-in-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        IPresentationInfo info = PresentationFactory.getInstance().getPresentationInfo(dataDir + "HelloWorld.pptx");
        switch (info.getLoadFormat())
        {
            case LoadFormat.Pptx:
            {
                break;
            }
            case LoadFormat.Unknown:
            {
                break;
            }
        }
```
