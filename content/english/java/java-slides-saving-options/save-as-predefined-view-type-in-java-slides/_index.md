---
title: Save as Predefined View Type in Java Slides
linktitle: Save as Predefined View Type in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 10
url: /java/java-slides-saving-options/save-as-predefined-view-type-in-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Opening the presentation file
        Presentation presentation = new Presentation();
        try
        {
            // Setting view type
            presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
            // Saving presentation
            presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
