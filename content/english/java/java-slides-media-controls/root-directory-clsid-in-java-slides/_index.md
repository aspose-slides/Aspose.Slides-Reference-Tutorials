---
title: Root Directory ClsId in Java Slides
linktitle: Root Directory ClsId in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 10
url: /java/java-slides-media-controls/root-directory-clsid-in-java-slides/
---

## Complete Source Code
```java
        // Output file name
        String resultPath = RunExamples.getOutPath() + "pres.ppt";
        Presentation pres = new Presentation();
        try {
            PptOptions pptOptions = new PptOptions();
            // set CLSID to 'Microsoft Powerpoint.Show.8'
            pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
            // Save presentation
            pres.save(resultPath, SaveFormat.Ppt, pptOptions);
        } finally {
            if (pres != null) pres.dispose();
        }
```
