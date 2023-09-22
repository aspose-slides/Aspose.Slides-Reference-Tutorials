---
title: Save Properties in Java Slides
linktitle: Save Properties in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-slides-saving-options/save-properties-in-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Instantiate a Presentation object that represents a PPT file
        Presentation presentation = new Presentation();
        try
        {
            //....do some work here.....
            // Setting access to document properties in password protected mode
            presentation.getProtectionManager().setEncryptDocumentProperties(false);
            // Setting Password
            presentation.getProtectionManager().encrypt("pass");
            // Save your presentation to a file
            presentation.save(dataDir + "Password Protected Presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
