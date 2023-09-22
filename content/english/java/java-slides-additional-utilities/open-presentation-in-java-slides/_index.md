---
title: Open Presentation in Java Slides
linktitle: Open Presentation in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 16
url: /java/java-slides-additional-utilities/open-presentation-in-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Opening the presentation file by passing the file path to the constructor of Presentation class
        Presentation pres = new Presentation(dataDir + "OpenPresentation.pptx");
        try
        {
            // Printing the total number of slides present in the presentation
            System.out.println(pres.getSlides().size());
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
