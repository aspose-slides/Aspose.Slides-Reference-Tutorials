---
title: Save as Read-Only in Java Slides
linktitle: Save as Read-Only in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 11
url: /java/java-slides-saving-options/save-as-read-only-in-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Create directory if it is not already present.
        boolean IsExists = new File(dataDir).exists();
        if (!IsExists)
            new File(dataDir).mkdirs();
        // Instantiate a Presentation object that represents a PPT file
        Presentation presentation = new Presentation();
        try
        {
            //....do some work here.....
            // Setting Write protection Password
            presentation.getProtectionManager().setWriteProtection("test");
            // Save your presentation to a file
            presentation.save(dataDir + "WriteProtected_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
