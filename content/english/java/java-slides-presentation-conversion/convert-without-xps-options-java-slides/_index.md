---
title: Convert Without XPS Options in Java Slides
linktitle: Convert Without XPS Options in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 33
url: /java/java-slides-presentation-conversion/convert-without-xps-options-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Instantiate a Presentation object that represents a presentation file
        Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
        try
        {
            // Saving the presentation to XPS document
            pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
