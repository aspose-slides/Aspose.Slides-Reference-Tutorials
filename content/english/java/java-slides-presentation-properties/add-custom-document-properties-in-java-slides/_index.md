---
title: Add Custom Document Properties in Java Slides
linktitle: Add Custom Document Properties in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 13
url: /java/java-slides-presentation-properties/add-custom-document-properties-in-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Instantiate the Presentation class
        Presentation presentation = new Presentation();
        // Getting Document Properties
        IDocumentProperties documentProperties = presentation.getDocumentProperties();
        // Adding Custom properties
        documentProperties.set_Item("New Custom", 12);
        documentProperties.set_Item("My Name", "Mudassir");
        documentProperties.set_Item("Custom", 124);
        // Getting property name at particular index
        String getPropertyName = documentProperties.getCustomPropertyName(2);
        // Removing selected property
        documentProperties.removeCustomProperty(getPropertyName);
        // Saving presentation
        presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```
