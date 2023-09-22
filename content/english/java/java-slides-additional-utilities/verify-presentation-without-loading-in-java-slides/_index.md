---
title: Verify Presentation Without Loading in Java Slides
linktitle: Verify Presentation Without Loading in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 18
url: /java/java-slides-additional-utilities/verify-presentation-without-loading-in-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        int format = PresentationFactory.getInstance().getPresentationInfo(dataDir + "HelloWorld.pptx").getLoadFormat();
        // It will return "LoadFormat.Unknown" if the file is other than presentation formats
```
