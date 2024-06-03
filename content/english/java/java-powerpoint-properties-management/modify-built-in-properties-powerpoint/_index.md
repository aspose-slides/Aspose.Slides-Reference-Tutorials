---
title: Modify Built-in Properties in PowerPoint
linktitle: Modify Built-in Properties in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-powerpoint-properties-management/modify-built-in-properties-powerpoint/
---

## Complete Source Code
```java
package com.aspose.slides.examples.presentations;

import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.examples.RunExamples;


public class ModifyBuiltinProperties
{
    public static void main(String[] args)
    {
        //ExStart:ModifyBuiltinProperties
        // The path to the documents directory.
        String dataDir = RunExamples.getDataDir_PresentationProperties();

        // Instantiate the Presentation class that represents the Presentation
        Presentation presentation = new Presentation(dataDir + "ModifyBuiltinProperties.pptx");
        try
        {
            // Create a reference to IDocumentProperties object associated with Presentation
            IDocumentProperties documentProperties = presentation.getDocumentProperties();

            // Set the builtin properties
            documentProperties.setAuthor("Aspose.Slides for .NET");
            documentProperties.setTitle("Modifying Presentation Properties");
            documentProperties.setSubject("Aspose Subject");
            documentProperties.setComments("Aspose Description");
            documentProperties.setManager("Aspose Manager");

            // Save your presentation to a file
            presentation.save(dataDir + "DocumentProperties_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
        //ExEnd:ModifyBuiltinProperties
    }
}

```
