---
title: Access Modifying Properties in Java Slides
linktitle: Access Modifying Properties in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 11
url: /java/java-slides-presentation-properties/access-modifying-properties-in-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Instanciate the Presentation class that represents the PPTX
        Presentation presentation = new Presentation(dataDir + "AccessModifyingProperties.pptx");
        // Create a reference to DocumentProperties object associated with Prsentation
        IDocumentProperties documentProperties = presentation.getDocumentProperties();
        // Access and modify custom properties
        for (int i = 0; i < documentProperties.getCountOfCustomProperties(); i++)
        {
            // Display names and values of custom properties
            System.out.println("Custom Property Name : " + documentProperties.getCustomPropertyName(i));
            System.out.println("Custom Property Value : " + documentProperties.get_Item(documentProperties.getCustomPropertyName(i)));
            // Modify values of custom properties
            documentProperties.set_Item(documentProperties.getCustomPropertyName(i), "New Value " + (i + 1));
        }
        // Save your presentation to a file
        presentation.save(dataDir + "CustomDemoModified_out.pptx", SaveFormat.Pptx);
```
