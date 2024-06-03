---
title: Update Presentation Properties with New Template
linktitle: Update Presentation Properties with New Template
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 13
url: /java/java-powerpoint-properties-management/update-presentation-properties-new-template/
---

## Complete Source Code
```java
package com.aspose.slides.examples.presentations;

import com.aspose.slides.DocumentProperties;
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.IPresentationInfo;
import com.aspose.slides.PresentationFactory;
import com.aspose.slides.examples.RunExamples;


public class UpdatePresentationPropertiesUsingNewTemplate
{
    //ExStart:UpdatePresentationPropertiesUsingNewTemplate
    public static void main(String[] args)
    {
        // The path to the documents directory.
        String dataDir = RunExamples.getDataDir_PresentationProperties();

        DocumentProperties template = new DocumentProperties();
        template.setAuthor("Template Author");
        template.setTitle("Template Title");
        template.setCategory("Template Category");
        template.setKeywords("Keyword1, Keyword2, Keyword3");
        template.setCompany("Our Company");
        template.setComments("Created from template");
        template.setContentType("Template Content");
        template.setSubject("Template Subject");

        updateByTemplate(dataDir + "doc1.pptx", template);
        updateByTemplate(dataDir + "doc2.odp", template);
        updateByTemplate(dataDir + "doc3.ppt", template);
    }

    private static void updateByTemplate(String path, IDocumentProperties template)
    {
        IPresentationInfo toUpdate = PresentationFactory.getInstance().getPresentationInfo(path);
        toUpdate.updateDocumentProperties(template);
        toUpdate.writeBindedPresentation(path);
    }
    //ExEnd:UpdatePresentationPropertiesUsingNewTemplate
}

```
