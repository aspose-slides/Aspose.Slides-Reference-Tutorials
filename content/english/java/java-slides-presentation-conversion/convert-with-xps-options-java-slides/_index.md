---
title: Convert with XPS Options in Java Slides
linktitle: Convert with XPS Options in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 34
url: /java/java-slides-presentation-conversion/convert-with-xps-options-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Instantiate a Presentation object that represents a presentation file
        Presentation pres = new Presentation(dataDir + "Convert_XPS_Options.pptx");
        try
        {
            // Instantiate the TiffOptions class
            XpsOptions opts = new XpsOptions();
            // Save MetaFiles as PNG
            opts.setSaveMetafilesAsPng(true);
            // Save the presentation to XPS document
            pres.save(dataDir + "XPS_With_Options_out.xps", SaveFormat.Xps, opts);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
