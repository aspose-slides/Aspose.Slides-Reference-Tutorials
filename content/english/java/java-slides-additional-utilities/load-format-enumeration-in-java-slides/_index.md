---
title: Load Format Enumeration in Java Slides
linktitle: Load Format Enumeration in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 14
url: /java/java-slides-additional-utilities/load-format-enumeration-in-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        boolean isOldFormat = PresentationFactory.getInstance().getPresentationInfo(dataDir + "presentation.ppt").getLoadFormat() == LoadFormat.Ppt95;
```
