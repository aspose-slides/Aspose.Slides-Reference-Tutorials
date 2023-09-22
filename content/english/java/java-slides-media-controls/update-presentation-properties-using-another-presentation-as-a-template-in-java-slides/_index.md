---
title: Update Presentation Properties Using Another Presentation as a Template in Java Slides
linktitle: Update Presentation Properties Using Another Presentation as a Template in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 14
url: /java/java-slides-media-controls/update-presentation-properties-using-another-presentation-as-a-template-in-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        DocumentProperties template;
        IPresentationInfo info = PresentationFactory.getInstance().getPresentationInfo(dataDir + "template.pptx");
        template = (DocumentProperties) info.readDocumentProperties();
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
```
