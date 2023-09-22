---
title: Access Open Doc in Java Slides
linktitle: Access Open Doc in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-slides-presentation-properties/access-open-doc-in-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Open the ODP file
        Presentation pres = new Presentation(dataDir + "AccessOpenDoc.odp");
        // Saving the ODP presentation to PPTX format
        pres.save(dataDir + "AccessOpenDoc_out.pptx", SaveFormat.Pptx);
```
