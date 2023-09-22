---
title: Remove Write Protection in Java Slides
linktitle: Remove Write Protection in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 10
url: /java/java-slides-document-protection/remove-write-protection-in-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Opening the presentation file
        Presentation presentation = new Presentation(dataDir + "RemoveWriteProtection.pptx");
        try
        {
            // Checking if presentation is write protected
            if (presentation.getProtectionManager().isWriteProtected())
                // Removing Write protection
                presentation.getProtectionManager().removeWriteProtection();
            // Saving presentation
            presentation.save(dataDir + "File_Without_WriteProtection_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
